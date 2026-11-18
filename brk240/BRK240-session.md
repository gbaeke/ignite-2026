# BRK240: Build and scale the next generation of AI agents in Microsoft Foundry

**Session:** Microsoft Ignite 2026, BRK240 · 45:20
**Speakers:** Tina Schuchman (Corporate Vice President, Microsoft Foundry), Jeff Hollan (Vice President, Foundry Agent Platform), Hiroaki Kimura (Project General Manager, Toyota Motor Corporation)

Timestamps refer to the session video (mm:ss). The slides were taken from the video, with one image per slide. Screens from the live demos aren't included as slides, but the notes describe what the demos showed. Where a matching page exists, each section ends with links to Microsoft Learn.

---

## TL;DR

- **Foundry's pitch:** an "enterprise-grade developer platform for building, deploying, and operating agent applications", which handles the plumbing (runtime, identity, tools, evals) and works with any model, harness or framework.
- **Golden path:** build in GitHub, run and optimize in Foundry, and distribute through Microsoft 365 Copilot and Teams. Every step is optional.
- **New agent types:** **Microsoft Copilot harness agents** are in public preview (configuration only, no code). **Voice agents** are GA, with a P90 of 800 ms for speech-to-speech.
- **Hosted agents:** these have been GA "for quite a few months". New at Ignite: **long-running support** (checkpoint and restore) is GA, **memory snapshots** for faster cold starts are in preview, **deployment to your own AKS** is "public preview soon", and **autonomous agents with their own Microsoft 365 accounts** are in preview.
- **Governance:** three built-in boundaries are GA (agent ID, tracing, sandboxes). New enterprise controls cover egress allow/deny lists (GA), credential injection (preview), Purview and Defender (GA), private CAs (preview), cost limits (preview) and tool governance with Azure Policy (preview).
- **Continuous improvement:** observability for external agents (GA), annotations (preview), multi-turn evaluation (GA), insights (GA), and the agent optimizer for quality (GA) and cost (preview). There's also managed training (GA), programmed training (preview) and RL environments (private preview). **Skills generation from traces** (preview) and **A/B experimentation** (private preview) round it out.
- **Customers:** Petstock (task adherence 60% → 95%), Alaska Airlines (+9.8 points accuracy with fine-tuned MAI-Code-2-Flash) and Toyota (in-car agent with an "EvalOps" loop on Foundry).

---

## 1. Opening ▶ 00:00

<table><tr><td width="50%" valign="top">

![Build and scale the next generation of AI agents in Microsoft Foundry](slides/01_00m11s.jpg)

</td><td valign="top">

- Tina Schuchman opens with Jeff Hollan, who leads the Foundry Agent Platform.
- The theme of the session: building an agent is hard, but running agents in production is harder.

</td></tr></table>

## 2. The problem: operating agents at scale ▶ 00:25

<table><tr><td width="50%" valign="top">

![Building quality agents is hard, but operating them at scale is even harder](slides/02_01m37s.jpg)

</td><td valign="top">

Four problems teams run into:
1. **Too much plumbing:** runtime, identity, tools and evals instead of business logic.
2. **Risk:** without access limits and oversight, agents stay in "safe demos" instead of doing high-value work.
3. **Lock-in:** getting stuck with one model or framework as the business changes.
4. **No proof of quality:** without traces and evals, "quality is just guesswork".

Foundry's answer is a platform that is "model, harness, framework agnostic" and full code, with governance, observability and optimization built in, so agents can self-improve.

**Microsoft Learn:**
- [Agents in Microsoft Foundry (overview)](https://learn.microsoft.com/azure/foundry/agents/overview)
- [Agent development lifecycle](https://learn.microsoft.com/azure/foundry/agents/concepts/development-lifecycle)

</td></tr></table>

## 3. End-to-end agent platform ▶ 02:50

<table><tr><td width="50%" valign="top">

![End-to-end agent platform](slides/03_02m54s.jpg)

</td><td valign="top">

The recommended "golden path":
- **Build in GitHub:** code, prompts, skills and tools, plus eval definitions. Pick from 11,000 models in the catalog and ground the agent in Microsoft IQ.
- **Run in Foundry:** every action the agent takes becomes a trace. Evals and optimization run on those traces, and that is how the agent improves.
- **Govern:** inside Foundry, or across all Microsoft and external agents with **Agent 365**.
- **Distribute:** Microsoft 365 Copilot, Teams, or your own apps and APIs.

Everything is modular. You can build with Codex, Claude Code or by hand, publish elsewhere, and bring external agents: "Just give us the traces. We can observe and optimize for you."

**Microsoft Learn:**
- [Agents in Microsoft Foundry (agent types)](https://learn.microsoft.com/azure/foundry/agents/overview#agent-types)
- [Register external agents for observability and evaluation](https://learn.microsoft.com/azure/foundry/agents/how-to/register-external-agent)
- [Agent 365 integration with Foundry](https://learn.microsoft.com/azure/foundry/agents/concepts/agent-365-integration)
- [Publish agents to Microsoft Copilot and Teams](https://learn.microsoft.com/azure/foundry/agents/how-to/publish-copilot)
- [What is Foundry IQ?](https://learn.microsoft.com/azure/foundry/agents/concepts/what-is-foundry-iq)

</td></tr></table>

## 4. Demo scenario: Caldova Deal Desk (demo: build) ▶ 05:26

<table><tr><td width="50%" valign="top">

![Demo scenario: Caldova Deal Desk](slides/04_06m16s.jpg)

</td><td valign="top">

Jeff's scenario is a deal desk that checks whether a customer's counter-proposal is acceptable. It uses two agents:
- **Deal Desk agent:** the front door, running on the **Microsoft Copilot harness**.
- **Deal Economics agent:** a specialist hosted agent built with Microsoft Agent Framework in Python. It handles margins, policies and counter-offers.

The demo showed:
- **Developer tools:** Azure Developer CLI, the Microsoft Foundry skill for coding agents (GitHub Copilot CLI, Claude), the VS Code AI Toolkit, and a canvas in the GitHub Copilot app. A **single one-line installer** sets up the **Foundry Dev Pack** on Windows, macOS or Linux.
- **Local debugging** in VS Code, with tool calls, token use and events visible, then deployment as a **hosted agent** with isolated sandboxes and its own agent identity.
- **Two other agent types:** **voice agents**, with a voice-optimized low-latency harness, and **Copilot harness agents**. The latter is "the same coding harness that powers the GitHub Copilot app and CLI" and Copilot Cowork. You give it instructions, tools and skills, and you don't write code.

**Microsoft Learn:**
- [Prepare your development environment (Foundry DevPack)](https://learn.microsoft.com/azure/foundry/how-to/develop/install-cli-sdk#install-foundry-devpack)
- [Use the Microsoft Foundry Skill in coding agents](https://learn.microsoft.com/azure/foundry/how-to/develop/use-microsoft-foundry-skill)
- [Host Agent Framework agents as Foundry hosted agents](https://learn.microsoft.com/azure/foundry/how-to/develop/framework-hosted-agents)
- [Quickstart: Deploy your first hosted agent](https://learn.microsoft.com/azure/foundry/agents/quickstarts/quickstart-hosted-agent)
- [Use the Microsoft Copilot harness with prompt agents (preview)](https://learn.microsoft.com/azure/foundry/agents/how-to/use-tools-skills-copilot-harness)

</td></tr></table>

## 5. Foundry Agent Service and developer tools announcements ▶ 12:19

<table><tr><td width="50%" valign="top">

![Foundry Agent Service and Developer Tools announcements](slides/05_13m30s.jpg)

</td><td valign="top">

- **Microsoft Copilot harness agents** (public preview): build an agent from configuration (model, tools, skills) on the Copilot harness.
- **Long-running support for hosted agents** (GA): checkpoint and restore, for resilience and human-in-the-loop. The agent checkpoints while it waits for a user and restores when the answer comes in.
- **Foundry Dev Pack** (GA): one installer for the Foundry skills, the `azd` AI agent CLI, the VS Code extension and the GitHub Copilot app extension.
- **Foundry voice agents** (GA): build, deploy, observe and optimize in one path. They support speech-to-speech and cascade modes, models from Microsoft AI, OpenAI or Azure Speech, and interruptions. Microsoft says the P90 response time is **800 ms**.

**Microsoft Learn:**
- [Use the Microsoft Copilot harness with prompt agents (preview)](https://learn.microsoft.com/azure/foundry/agents/how-to/use-tools-skills-copilot-harness)
- [Resilience for long-running hosted agents](https://learn.microsoft.com/azure/foundry/agents/concepts/long-running-agent-resilience)
- [Add a human-in-the-loop approval step](https://learn.microsoft.com/azure/foundry/agents/how-to/add-human-in-the-loop)
- [Prepare your development environment (Foundry DevPack)](https://learn.microsoft.com/azure/foundry/how-to/develop/install-cli-sdk#install-foundry-devpack)
- [How voice-based agents work](https://learn.microsoft.com/azure/foundry/agents/overview#how-voice-based-agents-work)
- [Quickstart: Create a voice agent](https://learn.microsoft.com/azure/foundry/agents/quickstarts/prompt-voice-agent)

</td></tr></table>

## 6. Demo: Deploy ▶ 14:44

<table><tr><td width="50%" valign="top">

![Demo: Deploy](slides/06_14m46s.jpg)

</td><td valign="top">

Governance and security for the deployed hosted agent:
- Each run gets a **serverless micro VM sandbox**.
- Each agent has its own **agent identity**, with role-based access to systems.
- **Guardrails** block jailbreaks. An **egress policy** blocks web access except for an allow list, so "I'm not just relying on prompts for this agent to behave."
- In **Teams**, someone posts the Northwind request in the deal desk channel. The always-on agent calls the Deal Economics sub-agent, uses IQ data, and sends the VP of Finance a direct message asking for **human approval**.
- **Cost controls**: here, a budget of $1,000 a month for the agent. Budgets can also be set per session, task or user, and they can block the agent or just send alerts.

**Microsoft Learn:**
- [What are hosted agents?](https://learn.microsoft.com/azure/foundry/agents/concepts/hosted-agents)
- [Agent identity concepts in Foundry](https://learn.microsoft.com/azure/foundry/agents/concepts/agent-identity)
- [Add guardrails to a hosted agent (incl. network egress)](https://learn.microsoft.com/azure/foundry/agents/how-to/add-hosted-agent-guardrails)
- [Cost controls overview (preview)](https://learn.microsoft.com/azure/foundry/concepts/cost-controls)
- [Publish agents to Microsoft Copilot and Teams](https://learn.microsoft.com/azure/foundry/agents/how-to/publish-copilot)

</td></tr></table>

## 7. Governed, secure agents ▶ 19:10

<table><tr><td width="50%" valign="top">

![Enterprises need governed, secure agents](slides/07_21m08s.jpg)

</td><td valign="top">

**Built-in boundaries** (all GA):
- **Agent ID:** an Entra identity for each agent that authenticates it and limits what it can do.
- **Tracing:** full lineage of which action was taken, by whom, under which identity.
- **Isolated sandboxes** for every Foundry agent.

**Enterprise controls:**
- **Limit agent reach** (GA): an egress proxy outside the sandbox with URL allow and deny lists.
- **Protect credentials** (preview): the proxy injects credentials at runtime, so the agent never holds them and can't leak them.
- **Secure your data** (GA): traces flow into Purview and Defender through Agent 365, and suspicious activity is flagged.
- **Private CAs** (preview): private HTTPS for VNet customers.
- **Cost limits** (preview): set per agent, project, user or custom tag. You can audit, alert at a threshold (for example 80%) or block.
- **Govern tools** (preview): block tools with Azure Policy so they don't appear in the catalog or toolbox.

**Microsoft Learn:**
- [Agent identity concepts in Foundry](https://learn.microsoft.com/azure/foundry/agents/concepts/agent-identity)
- [Agent tracing overview](https://learn.microsoft.com/azure/foundry/observability/concepts/trace-agent-concept)
- [Add guardrails to a hosted agent: network egress controls](https://learn.microsoft.com/azure/foundry/agents/how-to/add-hosted-agent-guardrails#network-egress-controls)
- [Inject secret-backed headers (preview)](https://learn.microsoft.com/azure/foundry/agents/how-to/configure-hosted-agent-secret-references)
- [Use Microsoft Purview with Microsoft Foundry](https://learn.microsoft.com/purview/ai-azure-foundry)
- [Connect agents to services that use a private CA (preview)](https://learn.microsoft.com/azure/foundry/agents/how-to/private-certificate-authority)
- [Create and manage cost controls (preview)](https://learn.microsoft.com/azure/foundry/how-to/create-cost-controls)
- [Govern tools in Microsoft Foundry (preview)](https://learn.microsoft.com/azure/foundry/control-plane/govern-tools)
- [Foundry governance overview](https://learn.microsoft.com/azure/foundry/control-plane/overview)

</td></tr></table>

## 8. Hosted agents announcements (demo: operate) ▶ 23:09

<table><tr><td width="50%" valign="top">

![Hosted agents announcements](slides/08_24m13s.jpg)

</td><td valign="top">

"Foundry hosted agents have been GA for quite a few months." The new additions:
- **More concurrent sessions with shared subnet IPs** (GA): "millions of concurrent sessions".
- **Faster cold starts with memory snapshots** (preview): P90 of **1.3 s**. **Warm pooling** is coming in private preview, with a P90 of about **300 ms**.
- **Deploy hosted agents to your own AKS** (public preview soon), while keeping Foundry's control plane, observability, evaluation and optimization.
- **Publish autonomous agents with Microsoft 365 accounts** (preview): agents act as themselves, with their own identity, email address and Teams presence.

**Operate demo:**
- After the counter is approved, every step shows up in **traces**: reasoning, tool calls, permissions and guardrails. Human approvals and rejections are captured as **annotations**.
- **Optimize for quality:** against a golden dataset, the optimizer tests candidate changes to skills, model or tools in micro-batches. The score goes up from **0.794**. You review the diff, merge it, and roll it out gradually.
- **Learn from past activity:** a run of about four minutes analyzes traces and human feedback. It turns the learnings into **new or updated skills** for you to review. It can run nightly.
- **Autonomous mode:** the agent wakes up on routines and event triggers. It approves proposals that fall within its guardrails and asks a human for the rest.

**Microsoft Learn:**
- [Deep dive into Foundry Agent Service networking (shared subnet IPs)](https://learn.microsoft.com/azure/foundry/agents/concepts/agents-networking-deep-dive)
- [Enable memory snapshots for hosted agents (preview)](https://learn.microsoft.com/azure/foundry/agents/how-to/use-hosted-agent-memory-snapshots)
- [Reduce startup latency for hosted agents](https://learn.microsoft.com/azure/foundry/agents/how-to/optimize-hosted-agent-latency)
- [What is an autopilot in Foundry?](https://learn.microsoft.com/azure/foundry/agents/concepts/autopilot-overview)
- [Annotate traces for evaluation (preview)](https://learn.microsoft.com/azure/foundry/observability/how-to/human-in-the-loop-annotate)
- [What is the agent optimizer?](https://learn.microsoft.com/azure/foundry/agents/concepts/agent-optimizer-overview)
- [Optimize skills from traces (preview)](https://learn.microsoft.com/azure/foundry/agents/how-to/optimize-skills-from-traces)
- [Promote hosted agents to production (gradual rollout)](https://learn.microsoft.com/azure/foundry/agents/how-to/deploy-hosted-agent-production)

</td></tr></table>

## 9. An AI system that continuously improves ▶ 31:07

<table><tr><td width="50%" valign="top">

![Enterprises need an AI system that continuously improves](slides/09_31m24s.jpg)

</td><td valign="top">

Three stages: **evaluations**, then **tuning**, then **continuous learning**.

**Evaluations:**
- **Observability for external agents** (GA): bring the traces and Foundry observes them.
- **Annotations** (preview): thumbs up or down and comments per trace, fed into optimization.
- **Rubric evaluators:** quality is GA, safety is in preview.
- **Multi-turn evaluation** (GA): evaluates whole conversations, from recorded traces or user simulation.

**Optimization:**
- **Insights** (GA): automatically flag problems such as token spikes or hallucinations.
- **Insights connected to the agent optimizer** (preview).
- **Agent optimizer:** a reflective loop over prompts, skills, tool configuration and model configuration. Quality optimization is GA and cost optimization is in preview.

**Microsoft Learn:**
- [Evaluation in Microsoft Foundry](https://learn.microsoft.com/azure/foundry/concepts/evaluation-overview)
- [Register external agents for observability and evaluation](https://learn.microsoft.com/azure/foundry/agents/how-to/register-external-agent)
- [Human in the loop: annotate traces (preview)](https://learn.microsoft.com/azure/foundry/observability/how-to/human-in-the-loop)
- [Rubric evaluators](https://learn.microsoft.com/azure/foundry/concepts/evaluation-evaluators/rubric-evaluators)
- [Evaluate deployed conversations (multi-turn)](https://learn.microsoft.com/azure/foundry/observability/how-to/cloud-evaluation-deployed-conversations)
- [Find recurring issues with insights](https://learn.microsoft.com/azure/foundry/observability/how-to/agent-insights)
- [What is the agent optimizer?](https://learn.microsoft.com/azure/foundry/agents/concepts/agent-optimizer-overview)

</td></tr></table>

## 10. Customer spotlights ▶ 34:12

<table><tr><td width="50%" valign="top">

![Customer spotlights](slides/10_34m24s.jpg)

</td><td valign="top">

Results with the agent optimizer:
- **Petstock:** business analytics agent, task adherence **60% → 95%**.
- On the slide only: NTT DATA (0.686 → 0.833), TCS (~0.57 → 0.72), Rakuten (0.753 → 0.961 on a public ShoppingBench setup) and Mazda (0.708 → 0.943).

**Microsoft Learn:**
- [What is the agent optimizer?](https://learn.microsoft.com/azure/foundry/agents/concepts/agent-optimizer-overview)
- [Make your agent optimizer-ready (hosted agents)](https://learn.microsoft.com/azure/foundry/agents/how-to/make-agent-optimizer-ready)

</td></tr></table>

## 11. Training announcements ▶ 34:37

<table><tr><td width="50%" valign="top">

![Training announcements](slides/11_35m13s.jpg)

</td><td valign="top">

When changing configuration isn't enough, you change the model weights:
- **Managed training** (GA): portal or high-level APIs. You bring a dataset and pick supervised or reinforcement fine-tuning.
- **Programmed training** (preview): you write your own training loop, with control over forward and backward passes, on Foundry's serverless compute.
- **Integrated RL environments** (private preview): tasks, tools, task state and verifiable feedback, used for both evaluation and training.

**Microsoft Learn:**
- [Training in Microsoft Foundry (Managed vs Programmed Training)](https://learn.microsoft.com/azure/foundry/fine-tuning/overview)
- [Programmed Training overview (preview)](https://learn.microsoft.com/azure/foundry/fine-tuning/programmed-training/overview)
- [Reinforcement fine-tuning](https://learn.microsoft.com/azure/foundry/openai/how-to/reinforcement-fine-tuning)

</td></tr></table>

## 12. Alaska Airlines ▶ 35:51

<table><tr><td width="50%" valign="top">

![Alaska Airlines lifts accuracy to 91.7%](slides/12_36m01s.jpg)

</td><td valign="top">

- Alaska Airlines fine-tuned **MAI-Code-2-Flash** with programmed training for ATA code classification.
- Accuracy went from **81.9% to 91.7%**, a gain of 9.8 points. Per the slide, the existing system scored about 87% and the target was 90%+.
- The same example appeared in the keynote.

**Microsoft Learn:**
- [Programmed Training overview (preview)](https://learn.microsoft.com/azure/foundry/fine-tuning/programmed-training/overview)
- [Foundry Models sold by Azure: Microsoft/MAI models](https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-sold-directly-by-azure#microsoft-models-sold-by-azure)

</td></tr></table>

## 13. Keep learning after the agent ships ▶ 36:12

<table><tr><td width="50%" valign="top">

![Keep learning after the agent ships](slides/13_36m54s.jpg)

</td><td valign="top">

- Tuning is a lot of work, so it makes sense for big changes: a new agent, a new model or a new tool. Agents learn every day, though, so a cheaper continuous method is needed.
- **Skills generation and optimization** (preview): **collect** traces and logs (with or without human input), **separate** good outcomes from bad, **categorize** why, then **improve** by generating new skills or refining existing ones. Tina compared it to OpenAI's and Anthropic's "dreaming".
- **A/B experimentation** (private preview): measure the improvement on production traffic.

**Microsoft Learn:**
- [Optimize skills from traces (preview)](https://learn.microsoft.com/azure/foundry/agents/how-to/optimize-skills-from-traces)
- [Use skills in Foundry (preview)](https://learn.microsoft.com/azure/foundry/agents/how-to/tools/skills)

</td></tr></table>

## 14. Customer spotlight: Toyota ▶ 37:37

<table><tr><td width="50%" valign="top">

![Customer Spotlight: An agent that grows the more you use it](slides/14_38m11s.jpg)

</td><td valign="top">

- "Foundry has 120,000 customers."
- Toyota is building an **in-car AI assistant**. It knows the car's features and connects to Toyota's cloud services. It runs as a **Foundry hosted agent** and uses Foundry observability and optimization.
- Hiroaki Kimura joins on stage: "an agent that grows the more you use it."

**Microsoft Learn:**
- [What are hosted agents?](https://learn.microsoft.com/azure/foundry/agents/concepts/hosted-agents)

</td></tr></table>

## 15. One question, one wrong answer ▶ 38:46

<table><tr><td width="50%" valign="top">

![One question, one wrong answer](slides/15_39m16s.jpg)

</td><td valign="top">

- Driving to Napa Valley, the driver asks "Any EV chargers out there?" The agent finds one nearby, which is a good answer to the wrong question. The driver meant once they arrive in Napa Valley.
- In a car, people speak in short phrases. The trip context (the destination) gives the meaning.
- Repeating the question takes the driver's attention off the road, so Toyota wants to avoid it.

</td></tr></table>

## 16. Every word a driver says is a lesson ▶ 39:49

<table><tr><td width="50%" valign="top">

![Every word a driver says is a lesson](slides/16_40m15s.jpg)

</td><td valign="top">

Toyota's loop, which they call "**EvalOps**" (Microsoft calls it a hill-climbing machine), rests on three ideas:
- **Learn from every word:** a rephrase is implicit feedback, and the trace shows why.
- **People decide:** AI drafts candidates, and people choose and own the change.
- **Verify before you ship:** the fix works and nothing else broke.

The agent is still in development. The loop runs today on Toyota's own system with employees, and Toyota is moving it onto Foundry: evaluations, tracing and the agent optimizer.

**Microsoft Learn:**
- [Evaluation in Microsoft Foundry](https://learn.microsoft.com/azure/foundry/concepts/evaluation-overview)
- [What is the agent optimizer?](https://learn.microsoft.com/azure/foundry/agents/concepts/agent-optimizer-overview)

</td></tr></table>

## 17. Many parts, one answer ▶ 40:43

<table><tr><td width="50%" valign="top">

![Many parts, one answer. Which one went wrong?](slides/17_41m17s.jpg)

</td><td valign="top">

- The architecture: vehicle → Toyota AI agent, which runs on Foundry Agent Service with MCP Toolbox, Hosted Agent and Foundry Models. The orchestration logic is Toyota's own code, "because Toyota answers for what the car says."
- Place search knows where the chargers are, and the agent tells it where to look. A separate Talk API writes the words the driver hears.
- Every call is traced down to the tool and its conditions, and those traces feed EvalOps. The console is Toyota's, and Foundry runs behind it.

**Microsoft Learn:**
- [What is Toolbox in Foundry?](https://learn.microsoft.com/azure/foundry/agents/concepts/toolbox-overview)
- [Agent tracing overview](https://learn.microsoft.com/azure/foundry/observability/concepts/trace-agent-concept)

</td></tr></table>

## 18. Demo 1: The trace knows what the score doesn't ▶ 41:52

<table><tr><td width="50%" valign="top">

![Demo 1: The trace knows what the score doesn't](slides/18_42m30s.jpg)

</td><td valign="top">

- **Detect:** a rephrase is flagged and a ticket opened. Asked the same way, it fails **10 out of 10** times, and 17 out of 21 times for similar phrasings. Phrasings with "nearby" never fail.
- **Cause:** the trace shows the input had a destination, but the agent searched along the route. Only one part failed: the agent picked the wrong search area.

**Microsoft Learn:**
- [Agent tracing overview](https://learn.microsoft.com/azure/foundry/observability/concepts/trace-agent-concept)
- [Convert agent traces into evaluation datasets](https://learn.microsoft.com/azure/foundry/observability/how-to/traces-to-dataset)

</td></tr></table>

## 19. Demo 2: A perfect score that cheated ▶ 42:33

<table><tr><td width="50%" valign="top">

![Demo 2: A perfect score that cheated](slides/19_42m52s.jpg)

</td><td valign="top">

- The agent optimizer generated three candidates, and the best scored a perfect 1.0.
- When the team read it, the candidate said to pick the destination "because the test wants that". It had learned the test, not the task.
- An engineer kept the two candidates that use the trip context, dropped the rest, and wrote version 2.

**Microsoft Learn:**
- [What is the agent optimizer?](https://learn.microsoft.com/azure/foundry/agents/concepts/agent-optimizer-overview)

</td></tr></table>

## 20. Demo 3: 27 to zero, and nothing else broke ▶ 42:58

<table><tr><td width="50%" valign="top">

![Demo 3: 27 to zero, and nothing else broke](slides/20_43m20s.jpg)

</td><td valign="top">

- Quality gate: failures on the improvement check went from **27 to 0**, regression stayed at 0 failures across 21 runs, and search area accuracy went from **48% to 100%**.
- The same question now finds a charger at the destination on the first try. The result is recorded, and people decide whether to ship.

**Microsoft Learn:**
- [Continuous and scheduled evaluation](https://learn.microsoft.com/azure/foundry/observability/how-to/continuous-scheduled-evaluation)

</td></tr></table>

## 21. Move fast. Never skip verification. ▶ 43:44

<table><tr><td width="50%" valign="top">

![Move fast. Never skip verification.](slides/21_43m57s.jpg)

</td><td valign="top">

- Toyota's employees are "customer zero". The next step is the same loop on Foundry, and then customers, with every change verified before it reaches them.
- "We spend our time on the agent, not on the plumbing."

</td></tr></table>

## 22. The trip continues ▶ 44:13

<table><tr><td width="50%" valign="top">

![The trip continues](slides/22_44m19s.jpg)

</td><td valign="top">

This is the first of three Toyota sessions at Ignite:
- **BRK240** (Microsoft Foundry): is the agent's behavior right?
- **BRK306** (Microsoft Fabric IQ): what is right for this person?
- **BRK313** (Microsoft Web IQ): what is right to say at the wheel?

</td></tr></table>

## 23. Microsoft IQ ▶ 44:29

<table><tr><td width="50%" valign="top">

![Microsoft IQ](slides/23_44m41s.jpg)

</td><td valign="top">

- Foundry sits inside the larger **Microsoft IQ** platform. On top is enterprise context management: Work IQ, Fabric IQ, Foundry IQ, Web IQ and third-party systems. Below it is the foundation: app hosting, model routing, agent runtime, evaluations, training and safety controls.
- The slide's principles: open, model diverse, heterogeneous, and continuously improving.
- "That's how your agent can self-improve. And this is how your business compounds."

**Microsoft Learn:**
- [Microsoft IQ documentation hub](https://learn.microsoft.com/microsoft-iq)
- [What is Foundry IQ?](https://learn.microsoft.com/azure/foundry/agents/concepts/what-is-foundry-iq)
- [What is Fabric IQ?](https://learn.microsoft.com/fabric/iq/overview)
- [Web IQ docs](https://learn.microsoft.com/web-iq/)
- [What is model router?](https://learn.microsoft.com/azure/foundry/openai/concepts/model-router)

</td></tr></table>

## 24. Related sessions ▶ 44:55

<table><tr><td width="50%" valign="top">

![Thank you and related sessions](slides/24_44m58s.jpg)

</td><td valign="top">

Recommended Foundry sessions at Ignite (from the slide):
- **Agent service:** BRK240, BRK243 (choosing an agent architecture), BRK245 (Document Intelligence and Content Understanding), BRK244 (voice agents).
- **Models and fine-tuning:** BRK254, BRK246, BRK252.
- **Observability and optimization:** BRK242 (self-improving AI platform), BRK249 (the Foundry improvement loop), BRK251 (agents in production).
- **Governance and trust:** BRK248, BRK312, BRK250, BRK253.

Session guide: aka.ms/FoundryatIgnite2026

</td></tr></table>

## 25. Ignite Concierge voice agent ▶ 45:02

<table><tr><td width="50%" valign="top">

![Call our voice agent](slides/25_45m11s.jpg)

</td><td valign="top">

- The Ignite Concierge is a phone-based voice agent built end to end on Foundry with the newly GA voice features.
- It can switch languages mid-call, be interrupted, save a session and email a recap.

**Microsoft Learn:**
- [How voice-based agents work](https://learn.microsoft.com/azure/foundry/agents/overview#how-voice-based-agents-work)
- [Configure a voice agent](https://learn.microsoft.com/azure/foundry/agents/how-to/configure-voice-agent)

</td></tr></table>
