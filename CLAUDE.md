# Ignite 2026 notes

Notes on Microsoft Ignite 2026 sessions. Each session lives in its own folder (`brk297/`, `inv643/`, ...) with `<CODE>-session.md` (committed), `slides/` (committed), and `<CODE>-transcript.md`, `*.wav` and `work/` (git-ignored). Add every new session to the "Session notes" list in `README.md`.

## Getting a session video from an ignite.microsoft.com session URL

Session pages (`https://ignite.microsoft.com/en-US/sessions/<id>`) have no download link. The video is an HLS stream in a Medius player, and the official captions are a VTT file. Use the Claude in Chrome tools:

1. Open the session page and run JS to get the Medius video id, plus the session code (e.g. `BRK356`), title, speakers and AI summary from `get_page_text`:
   ```js
   const h = document.documentElement.innerHTML;
   [...new Set(h.match(/medius\.microsoft\.com\/Embed\/video-nc\/[0-9a-f-]{36}/gi)||[])]
   ```
2. Open `https://medius.microsoft.com/Embed/video-nc/<medius-id>`, wait ~4 s, then pull the stream and caption URLs from its HTML:
   ```js
   const strip = u => (u||'').split('?')[0];
   const all = [...new Set((document.documentElement.innerHTML.match(/https?:\/\/[^"'\s?<>\\]+/gi)||[]).map(strip))];
   JSON.stringify({m3u8: all.filter(u=>/master\.m3u8/i.test(u)), vtt: all.filter(u=>/Caption_en-US\.vtt/i.test(u))})
   ```
   You get `https://stream.event.microsoft.com/prodwe/Content/HLS/LLCU/<guid>/master.m3u8` (often two GUIDs, each in `prodwe` and `prodnc`; they have been identical copies so far, so check durations with ffprobe and take the first) and `https://mediusdl.event.microsoft.com/video-<n>/<guid>/Caption_en-US.vtt`. Both download with plain curl/ffmpeg, no cookies needed.
3. Download (the 7th video variant, `v:6`, is 1920x1080):
   ```sh
   curl -s -o <code>/work/Caption_en-US.vtt "<vtt-url>"
   ffmpeg -v error -i "<master.m3u8>" -map 0:v:6 -map 0:a:0 -c copy -y ~/Downloads/<CODE>_v1.mp4
   ```
   Videos go to `~/Downloads`, never into the repo. With the official VTT there's no need to transcribe audio with Whisper.

## When you only have an MP4 (no captions)

If the user drops a plain `~/Downloads/<CODE>_v1.mp4`, transcribe it locally on the CPU (no GPU on this machine) with faster-whisper `base`, int8:
```sh
ffmpeg -v error -i ~/Downloads/<CODE>_v1.mp4 -vn -ac 1 -ar 16000 <code>/work/audio.wav
HF_HUB_OFFLINE=1 uv run --quiet --with faster-whisper --with numpy python -I transcribe.py audio.wav transcript.json <threads>
```
`transcribe.py` (keep it in the scratchpad) loads `WhisperModel("base", device="cpu", compute_type="int8", cpu_threads=<threads>)`, transcribes with `language="en", vad_filter=True, beam_size=5` and an `initial_prompt` listing the Microsoft product names, and writes `[{start, end, text}]`. A 45-minute talk takes about 2 minutes with 12 threads. The machine has 16 cores, so run two sessions in parallel with 8 threads each. Use the segments as the cues, fix product names from the slides, and don't claim official captions in the notes' intro.

## Processing a session

1. Grab a few stills (`ffmpeg -ss <t> -frames:v 1`) into a grid to see the layout, and find the crop box of the slide area (stage recordings usually show the slide inset in a frame; e.g. `crop=1112:628:156:226` or `crop=1318:740:52:170` at 1080p).
2. Slide detection: render 1 fps grayscale thumbnails of the crop (`fps=1,crop=...,scale=96:54,format=gray -f rawvideo small.gray`), then run a numpy script that splits into stable segments (mean frame diff above a threshold = change), drops black frames and merges near-duplicates, writing `slides.json` with `t`, `first` and `times`. Typical args: change 4, dup 2.5, min length 3 s. Extract a candidate frame per segment into `work/cand/`, tile them into a contact sheet with index numbers, view it, and pick the real slides (drop demo screens, speaker shots and transitions).
3. Save the picked slides as `slides/NN_MMmSSs.jpg` (from the segment midpoint, `-q:v 2`); keep each slide's `first` second as its section start.
4. Parse the VTT into cues and group the text by slide start into `work/by_slide.txt`; read it alongside tiled views of the slides.
5. Write `<CODE>-session.md` in the BRK297 format:
   - `# <CODE>: <title>`, then `**Session:** Microsoft Ignite 2026, <CODE> · mm:ss` and `**Speaker:** name (role, Microsoft)`.
   - A note on what timestamps mean and that notes come from the official English captions, then `---`, `## TL;DR` with 4 to 6 bold-led bullets, `---`.
   - One `## N. <slide title> ▶ mm:ss` per slide: an HTML table with the slide image on the left (`width="50%"`) and bullet notes on the right; describe demos in a nested `**Demo:**` list; end with `**Microsoft Learn:**` links when a matching page exists (search with the Microsoft Learn MCP, check every link returns 200).
   - Also write `<CODE>-transcript.md` (captions grouped by slide, a `**[mm:ss]**` paragraph about every 45 s). It's git-ignored.
6. Add the session to `README.md`, check that every image path exists, and commit only the session notes and slides (no video, audio, VTT, transcript or `work/`).
