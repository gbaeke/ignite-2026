# Ignite 2026 Keynote: Technologies & Documentation Map

Every technology, product and feature named in the [Ignite 2026 opening keynote](https://www.youtube.com/watch?v=ZR4v1c4CClc), with what it is, its status, and where to read more. Microsoft Learn is listed first wherever a page exists; other sources are used only when Learn has nothing yet.

Companion file: [summary](ignite-2026-opening-keynote-summary.md)

**How to read this**
- **▶ timestamps** jump to the moment in the keynote where the item is discussed.
- **Status** comes from Microsoft Learn or the [Ignite 2026 Book of News](https://news.microsoft.com/events/ignite/2026/book-of-news/). Where only the Book of News gives a status, it's marked *(BoN)*. Statuses change quickly, so check the linked page before relying on one.
- **Docs:** 📘 = Microsoft Learn · 🌐 = other source (Microsoft blog, GitHub, press) · ⚠️ = no dedicated documentation found yet.
- Names follow the keynote. Where the docs use a different name or describe something differently, the entry says so.

Research done 2026-11-18, the day after the keynote.

---

## At a glance

| # | Technology | Status | Learn docs? |
|---|---|---|---|
| 1 | Copilot Cowork | GA (work/school) | 📘 Yes |
| 2 | Copilot Code | Frontier, GA planned December *(BoN)* | 📘 Yes |
| 3 | Autopilot | Frontier preview (US first) | 📘 Yes |
| 4 | Copilot Today | Private preview via Frontier *(BoN)* | ⚠️ No |
| 5 | Copilot Workspaces | Frontier *(BoN)* | ⚠️ No (blog only) |
| 6 | Home + Office in Copilot | Home rolling out; Office in Copilot GA *(BoN)* | 📘 Partial |
| 7 | Plugins (role, industry, Dynamics 365) | Dynamics 365 Sales & ERP GA *(BoN)* | 📘 Yes |
| 8 | Salesforce in Copilot ("Copilotforce") | Preview / pilot *(BoN)* | ⚠️ No |
| 9 | GitHub Copilot Fusion | GA (Oct 28, 2026) | 🌐 GitHub/press |
| 10 | Copilot Managed Runtime (apps from Code) | GA *(BoN)* | 📘 Yes |
| 11 | Work IQ | GA | 📘 Yes |
| 12 | Microsoft IQ (Work / Fabric / Foundry / Web IQ) | GA, no new SKU *(BoN)* | 📘 Yes |
| 13 | Business plugins (governed IQ context) | Frontier *(BoN)* | 📘 Partial |
| 14 | Microsoft Decision 1.1 | GA | 📘 Yes |
| 15 | MAI Code 2 / Code 2 Flash | GA on GitHub; Flash private preview in Foundry *(BoN)* | ⚠️ No |
| 16 | MAI Cyber 2 Flash | Preview, MDASH only *(BoN)* | ⚠️ No |
| 17 | MAI Image 2.7 | Preview | 📘 Yes |
| 18 | MAI licensed weights / models under your control | Announced | ⚠️ No |
| 19 | GPT-6.2 in Foundry | Available | 📘 Yes |
| 20 | Claude & Meta models in Foundry | Available | 📘 Yes |
| 21 | Foundry model router | Available | 📘 Yes |
| 22 | Foundry Hosted Agents | GA | 📘 Yes |
| 23 | Foundry agent optimizer | GA *(BoN)* | 📘 Yes |
| 24 | Foundry training (fine-tuning) | Preview *(BoN)* | 📘 Partial |
| 25 | Microsoft Agent 365 | GA | 📘 Yes |
| 26 | Agent 365 Business Analytics | Frontier | 📘 Yes |
| 27 | Agent 365 cost management & spending policies | Preview *(BoN)* | 📘 Yes |
| 28 | Agent 365 Action Center | Private preview in December *(BoN)* | 📘 Partial |
| 29 | Local agents discovery (OpenClaw etc.) | Preview / Frontier | 📘 Yes |
| 30 | Microsoft Perception | GA | 📘 Yes |
| 31 | Endpoint shield / vulnerability shielding | Preview *(BoN)* | 📘 Partial |
| 32 | Microsoft Transparency Initiative | Announced | ⚠️ No |
| 33 | Azure HorizonDB | GA | 📘 Yes |
| 34 | HorizonDB in Fabric | Public preview | 📘 Yes |
| 35 | Azure Agent Grid | Limited preview | 📘 Yes |
| 36 | AI sandboxes (ACI micro VMs / AKS Agent Sandbox) | Public preview | 📘 Yes |
| 37 | Maia 300 | Announced; production in 2027 | 🌐 Azure blog |
| 38 | Windows local AI / Foundry Local on Windows 365 | GA *(BoN)* | 🌐 Windows blog |

---

## 1. Human ambition: Copilot

### 1. Copilot Cowork ▶ [00:06:38](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=398s) · [00:41:02](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=2462s)
**What it is:** The agentic mode of Microsoft Copilot. You describe an outcome, and it plans and runs multi-step work across Microsoft 365: sends mail, schedules meetings, builds Word, Excel and PowerPoint files, posts in Teams, does research and runs scheduled prompts. Sensitive actions need your approval. It can be extended with skills, plugins and connectors. In the keynote, Judson's NRF prep, Chevron's basis-of-design work and BlackRock's client packages were all done in Cowork.
**Status:** GA for work/school accounts. Billed by usage in Copilot Credits.
**Docs:**
- 📘 [Copilot Cowork overview](https://learn.microsoft.com/copilot/cowork/)
- 📘 [Get started with Cowork](https://learn.microsoft.com/copilot/cowork/get-started)
- 📘 [Use Cowork (skills, files, App skill)](https://learn.microsoft.com/copilot/cowork/use-cowork)
- 📘 [Cowork application card (Responsible AI)](https://learn.microsoft.com/copilot/cowork/responsible-ai/copilot-cowork-application-card)

### 2. Copilot Code ▶ [00:06:38](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=398s) · [00:48:34](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=2914s)
**What it is:** The **Code** tab in Copilot. It turns a plain-language description into working software: apps, dashboards, static sites, scripts and data transforms. It shows a live preview and runs locally or in a cloud sandbox. It can connect to GitHub (branches, commits, draft PRs) and use Work IQ context. Judson used it for his "3-D demo". Satya called it "an infinite SaaS factory".
**Status:** Frontier preview, with GA planned for December *(BoN)*. Billed by usage.
**Docs:**
- 📘 [Copilot Code (Frontier)](https://learn.microsoft.com/copilot/code/)
- 📘 [Use Copilot Code](https://learn.microsoft.com/copilot/code/use-code)
- 📘 [Copilot Code application card](https://learn.microsoft.com/copilot/code/responsible-ai/copilot-code-application-card)

### 3. Autopilot ▶ [00:08:20](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=500s) · [00:43:00](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=2580s) · [00:57:24](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=3444s)
**What it is:** An always-on, cloud-based agent with its own Microsoft Entra identity, memory, mailbox and cloud computer. You give it a goal, sources and boundaries. It runs routines, follows up on threads and works in Teams. Examples in the keynote: Judson's "Amelia" and the BlackRock relationship manager's outreach tracking. Each user can create one Autopilot. Developers can also build Autopilot blueprints from Foundry hosted agents.
**Status:** Frontier preview. Initially for eligible US customers. It needs a spending policy, because a Copilot license doesn't cover Autopilot usage.
**Docs:**
- 📘 [Autopilot overview](https://learn.microsoft.com/copilot/autopilot/overview)
- 📘 [Autopilot requirements](https://learn.microsoft.com/copilot/autopilot/requirements)
- 📘 [Configure Autopilot for your organization (admin)](https://learn.microsoft.com/copilot/autopilot/admin-configure), which includes a useful compliance-coverage table (no eDiscovery or retention for Autopilot conversations yet)
- 📘 [Autopilot scenarios](https://learn.microsoft.com/copilot/autopilot/scenarios)
- 📘 [Foundry: what is an autopilot?](https://learn.microsoft.com/azure/foundry/agents/concepts/autopilot-overview)

### 4. Copilot Today ▶ [00:37:43](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=2263s) · [00:57:24](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=3444s)
**What it is:** A proactive command center across mail, calendar, Teams, meetings and tasks. It shows what you missed and what needs attention, and pre-drafts the next step (replies, schedule changes) for you to approve. The Book of News splits it into **Today Brief** (included with M365 Copilot) and **Today Feed** (uses Copilot Credits).
**Status:** Private preview through Frontier *(BoN)*.
**Docs:**
- ⚠️ No Learn page yet.
- 🌐 [Microsoft Ignite 2026 Copilot blog](https://aka.ms/MicrosoftIgnite26Blog)
- 🌐 [Introducing the new Copilot with Home, Code and Autopilot (Sep 25, 2026)](https://blogs.microsoft.com/blog/2026/09/25/introducing-the-new-copilot-with-home-code-and-autopilot/)

### 5. Copilot Workspaces ▶ [00:11:33](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=693s) · [00:59:12](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=3552s)
**What it is:** A multiplayer space where people and their agents (including Autopilots) work toward a shared goal with shared context. It pulls in the relevant files and people and can map to a Teams channel. Per Microsoft's October blog, it evolved from **Copilot Notebooks** and supports co-editing Word, Excel and PowerPoint inside the workspace.
**Status:** Frontier *(BoN)*.
**Docs:**
- ⚠️ No dedicated Learn page yet.
- 🌐 [What's new in Microsoft Copilot, October 2026 (Tech Community)](https://techcommunity.microsoft.com/blog/microsoft-copilot-blog/what's-new-in-microsoft-copilot--october-2026/4568528)
- 📘 Related, the predecessor: [Copilot Notebooks release notes](https://learn.microsoft.com/microsoft-365/copilot/release-notes#october-27,-2026)

### 6. Home and full Office in Copilot ▶ [00:46:55](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=2815s)
**What it is:** **Home** is a single composer where Chat and Cowork come together. **Office in Copilot** means full Word, Excel and PowerPoint editing (track changes, advanced formulas, @mentions, sensitivity labels) inside the Copilot app, included in the Copilot subscription. **Auto** picks the mode, model and effort for each request.
**Status:** Home is rolling out worldwide, and Office in Copilot is GA *(BoN)*.
**Docs:**
- 📘 [Microsoft Copilot overview (licensing and features)](https://learn.microsoft.com/copilot/plan/copilot-overview)
- 📘 [Word, Excel and PowerPoint Agents FAQ](https://learn.microsoft.com/copilot/manage/faq-wordexcelppt-agents)
- 🌐 [Ignite 2026 Copilot blog](https://aka.ms/MicrosoftIgnite26Blog)

### 7. Plugins: role-based, industry and Dynamics 365 ▶ [00:09:23](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=563s) · [00:59:12](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=3552s)
**What it is:** A plugin is an installable package of **skills + tools (connectors, MCP servers) + optional agents**. IT approves a plugin once, and it then works across Chat, Cowork, Code and Autopilot. Microsoft ships role and industry plugins (Sales, Service, Finance, Legal, Accounting, Capital Markets, Education, HR) and Dynamics 365 plugins (Sales, Customer Service, ERP). The BlackRock demo used these.
**Status:** Dynamics 365 Sales and ERP plugins are GA *(BoN)*. Some role plugins are Frontier.
**Docs:**
- 📘 [What is a Microsoft 365 Copilot plugin?](https://learn.microsoft.com/plugins/overview)
- 📘 [Available plugins for Cowork](https://learn.microsoft.com/copilot/cowork/cowork-available-plugins)
- 📘 [Build plugins for Cowork](https://learn.microsoft.com/copilot/cowork/cowork-plugin-development)
- 📘 [Manage plugins, skills and MCP servers (admin)](https://learn.microsoft.com/microsoft-agent-365/admin/manage-plugins-skills-mcp-servers)
- 📘 [Dynamics 365 Sales skills in Cowork](https://learn.microsoft.com/dynamics365/sales/use-copilot-cowork-sales-skills)

### 8. Salesforce in Copilot ("Copilotforce") ▶ [01:07:01](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=4021s) · [01:08:02](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=4082s) · [01:10:32](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=4232s)
**What it is:** Announced with Salesforce, which Rohan Kumar presented: Salesforce context and actions in Microsoft 365 Copilot and Teams, with Salesforce permissions respected. There are three parts:
1. A **Salesforce sales plugin for Copilot** (sales skills plus MCP access)
2. **Salesforce Sales Cloud in Teams**
3. **Salesforce Data 360 ↔ Fabric** zero-copy data federation

Accenture is the design partner.
**Status:** The Copilot plugin is in preview, Sales Cloud in Teams is a pilot, and Data 360 ↔ Fabric federation is GA *(BoN)*.
**Docs:**
- ⚠️ No Learn page yet. The name "Copilotforce" doesn't appear in the Book of News. The only "CopilotForce" in AppSource is an unrelated third-party app.
- 🌐 [Book of News: Salesforce item](https://aka.ms/AA1457n5)

### 9. GitHub Copilot Fusion and goal-driven projects ▶ [00:09:58](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=598s)
**What it is:** **Copilot Fusion** routes each coding task to one model, or orchestrates several (Single, Cascade and Critique patterns) across Anthropic and OpenAI models, to get frontier quality at lower cost. It grew out of the September research preview **Project HydraFusion**. Satya also mentioned a new GitHub feature where you set a goal, connect one or more repos, and Copilot coordinates the work. I couldn't find an official name or docs for that feature.
**Status:** Fusion went GA on October 28, 2026 (per Artificial Analysis). On Terminal-Bench 4.0 it scored 71, the top score, at about half the cost per task of Claude Code with Opus 5.5 max.
**Docs:**
- 🌐 [GitHub blog: Project HydraFusion, multi-model orchestration](https://github.blog/ai-and-ml/github-copilot/project-hydrafusion-frontier-quality-via-multi-model-orchestration/)
- 🌐 [Artificial Analysis: Copilot Fusion benchmarks and cost](https://artificialanalysis.ai/articles/github-copilot-fusion-orchestrates-anthropic-and-openai-models-to-balance-performance-and-cost)
- ⚠️ Goal-driven multi-repo feature: not found.

### 10. Copilot Managed Runtime (hosting for Code apps) ▶ [00:48:34](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=2914s)
**What it is:** The tenant-hosted runtime where apps built in Code, Cowork's App skill or Copilot Studio are published, shared ("as easy as sharing a Word doc") and governed by admins.
**Status:** GA *(BoN)*.
**Docs:**
- 📘 [What is Copilot Managed Runtime](https://learn.microsoft.com/microsoft-365/copilot-managed-runtime/overview)
- 🌐 [Copilot Managed Runtime Ignite blog](https://aka.ms/CopilotManagedRuntime-Ignite-Blog)

---

## 2. Intelligence: Microsoft IQ, Foundry and models

### 11. Work IQ ▶ [00:08:20](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=500s) · [01:18:23](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=4703s)
**What it is:** The intelligence layer under Copilot. It combines M365 Graph data (mail, chat, files, meetings), Dataverse/Dynamics business data, connectors, memory and the semantic index, plus skills and tools. Developers can reach it through A2A, MCP (local and remote) and REST, and there's a **Work IQ CLI**.
**Status:** GA. API usage is billed in Copilot Credits.
**Docs:**
- 📘 [Work IQ overview](https://learn.microsoft.com/microsoft-365/copilot/extensibility/work-iq)
- 📘 [Work IQ API overview](https://learn.microsoft.com/microsoft-365/copilot/extensibility/work-iq/api-overview)
- 📘 [Work IQ CLI](https://learn.microsoft.com/microsoft-365/copilot/extensibility/work-iq/cli) ([GitHub](https://github.com/microsoft/work-iq-mcp))
- 📘 [Work IQ in Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/agents-experience/add-work-iq)
- 📘 [Business Applications in Work IQ (admin)](https://learn.microsoft.com/power-platform/admin/business-applications-work-iq/)

### 12. Microsoft IQ (Work IQ + Fabric IQ + Foundry IQ + Web IQ) ▶ [00:13:14](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=794s) · [01:17:50](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=4670s)
**What it is:** The "enterprise context management system" that unifies four context layers:
- **Work IQ:** how people work
- **Fabric IQ:** business entities, metrics and ontologies over OneLake/Power BI
- **Foundry IQ:** knowledge bases and agentic retrieval over documents and policies
- **Web IQ:** fresh public-web grounding via `api.microsoft.ai`

The keynote said 350+ connectors. The output is governed, shareable "business plugins". Unilever IQ was the customer example.
**Status:** GA with no new SKU *(BoN)*. Some Fabric IQ items (for example ontology) are still in preview.
**Docs:**
- 📘 [Microsoft IQ documentation hub](https://learn.microsoft.com/microsoft-iq)
- 📘 [What is Fabric IQ?](https://learn.microsoft.com/fabric/iq/overview)
- 📘 [Get started with Fabric IQ](https://learn.microsoft.com/fabric/iq/get-started-with-fabric-iq)
- 📘 [What is Foundry IQ?](https://learn.microsoft.com/azure/foundry/agents/concepts/what-is-foundry-iq)
- 📘 [Web IQ docs](https://learn.microsoft.com/web-iq/) ([FAQ](https://learn.microsoft.com/web-iq/resources/faq))
- 🌐 [Microsoft IQ Ignite launch blog](https://aka.ms/miq-ignitelaunchblog)

### 13. Business plugins (governed IQ context) ▶ [01:21:18](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=4878s)
**What it is:** In the Arun Ulag demo, context is organized as a hierarchy (company → legal → contracts → claims) with skills, sources and instructions at each level. IT certifies it as ground truth, and it's published as a durable, governed plugin that agents load selectively, which saves tokens.
**Status:** Frontier *(BoN)*.
**Docs:**
- 📘 [Business skills with Dataverse intelligence](https://learn.microsoft.com/power-apps/maker/data-platform/data-platform-business-skill-overview) (related concept)
- 🌐 [Microsoft IQ Ignite launch blog](https://aka.ms/miq-ignitelaunchblog)

### 14. Microsoft Decision 1.1 ▶ [00:15:50](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=950s) · [01:36:33](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=5793s)
**What it is:** A non-generative "decision model". It takes a `state` (text, JSON or images) plus typed questions, and returns calibrated probabilities:
- `noul`: yes/no
- `choice`: classification or routing
- `score`: ranking or grading

It's used for gates, routing, triage and as an evaluation judge, and it powers Copilot's own mode/model/effort routing. The keynote claimed ">10x faster, 200x cheaper than an LLM".
**Status:** GA in Foundry.
**Docs:**
- 📘 [Deploy and use Microsoft-Decision-1.1](https://learn.microsoft.com/azure/foundry/foundry-models/how-to/use-foundry-models-microsoft-decision)
- 📘 [Use a decision model as an evaluation judge](https://learn.microsoft.com/azure/foundry/observability/how-to/decision-model-judge)
- 🌐 [Decision model GA announcement](https://aka.ms/decision-model-ga)

### 15. MAI Code 2 / MAI Code 2 Flash ▶ [00:19:35](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1175s) · [01:34:53](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=5693s)
**What it is:** Microsoft AI's second-generation coding models, tuned for everyday enterprise coding rather than very long-horizon agentic work. **Code 2** is the flagship. **Code 2 Flash** handles fast, high-volume tasks. The keynote claimed 98% of frontier performance at 40% of the cost. They follow MAI-Code-1-Flash, released at Build in June 2026.
**Status:** GA in GitHub Copilot. Code 2 Flash is in private preview in Foundry *(BoN)*.
**Docs:**
- ⚠️ No Learn page yet.
- 🌐 [Foundry models at Ignite 2026](https://aka.ms/foundrymodelsignite2026)
- 🌐 Background on the earlier models: [IT Brief: Microsoft AI launches seven new MAI models](https://itbrief.co.uk/story/microsoft-ai-launches-seven-new-models-across-tasks)

### 16. MAI Cyber 2 Flash ▶ [00:19:35](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1175s) · [01:38:11](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=5891s) · [02:09:57](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=7797s)
**What it is:** A small security model trained on Microsoft's security data. It's the model behind Perception and MDASH. The keynote said it's "better than GPT-6 Astra at <2% cost per task". It follows MAI-Cyber-1-Flash from July 2026.
**Status:** Preview, in MDASH only *(BoN)*.
**Docs:**
- ⚠️ No Learn page yet.
- 🌐 [Foundry models at Ignite 2026](https://aka.ms/foundrymodelsignite2026)
- 🌐 Background on v1: [Help Net Security: MAI-Cyber-1-Flash](https://www.helpnetsecurity.com/2026/07/27/microsoft-mai-cyber-1-flash-ai-model/)

### 17. MAI Image 2.7 ▶ [01:38:11](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=5891s)
**What it is:** A diffusion image model for generation and precise editing. The keynote called it the "#1 image editing model at 1/5 the cost". 2.7 adds transparent backgrounds. There's also a Flash variant.
**Status:** Preview in Foundry (version `2026-11-02`).
**Docs:**
- 📘 [Deploy and use MAI image models](https://learn.microsoft.com/azure/foundry/foundry-models/how-to/use-foundry-models-mai-image)

### 18. MAI licensed weights / "models under your control" ▶ [00:19:35](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1175s) · [01:40:01](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=6001s)
**What it is:** Trusted partners get access to MAI model weights, can customize a frontier model with their own data, and control who can use it. Microsoft works with them through its Frontier company program. The AT&T custom model was the example.
**Status:** Announced.
**Docs:**
- ⚠️ No documentation found. It isn't in the readable part of the Book of News either.
- 📘 Closest related: [Foundry models sold by Azure, Microsoft/MAI section](https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-sold-directly-by-azure#microsoft-models-sold-by-azure)

### 19. GPT-6.2 in Foundry ▶ [00:17:49](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1069s)
**What it is:** OpenAI's newest reasoning models in Foundry, `gpt-6.2-astra` and `gpt-6.2-sol` (both 2026-11-17). They have a 1.05M-token context, computer use and multi-agent orchestration.
**Status:** Available, no access request needed.
**Docs:**
- 📘 [Foundry Models sold by Azure: GPT-6.2](https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-sold-directly-by-azure#gpt-62)
- 📘 [Azure OpenAI reasoning models](https://learn.microsoft.com/azure/foundry/openai/how-to/reasoning)

### 20. Claude 5.2 and Meta models in Foundry ▶ [00:17:49](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1069s)
**What it is:** Anthropic Claude (announced the week before) and Meta's latest models are in the Foundry catalog. Satya also mentioned Claude being available inside M365 Copilot.
**Status:** Available.
**Docs:**
- 📘 [Foundry Models from partners and community](https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-from-partners)
- 📘 [Configure Claude Code for Microsoft Foundry](https://learn.microsoft.com/azure/foundry/foundry-models/how-to/configure-claude-code)

### 21. Foundry model router ▶ [01:24:36](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=5076s)
**What it is:** A trained routing model, not an LLM. It sends simple prompts to small, fast models and hard prompts to frontier models, across 43+ models from OpenAI, Anthropic, xAI, DeepSeek, Meta and others. It offers Balanced, Quality and Cost modes, session affinity for prompt caching, and automatic failover. The keynote claimed up to 65% cheaper than sending everything to a frontier model.
**Status:** Available. The pool was expanded at Ignite.
**Docs:**
- 📘 [What is model router?](https://learn.microsoft.com/azure/foundry/openai/concepts/model-router)
- 📘 [How model router works](https://learn.microsoft.com/azure/foundry/openai/concepts/model-router-how-it-works)
- 📘 [Deploy and configure model router](https://learn.microsoft.com/azure/foundry/openai/how-to/model-router-configure)
- 📘 [Model router with agents and coding tools](https://learn.microsoft.com/azure/foundry/openai/how-to/model-router-agents)

### 22. Foundry Hosted Agents (managed agent harness) ▶ [00:21:12](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1272s)
**What it is:** Bring your own agent code (Agent Framework, LangGraph, the OpenAI or Anthropic Agent SDKs, or custom code) as a container or a .zip. Foundry runs it in per-session VM-isolated sandboxes. Each agent gets its own Entra identity, persistent `$HOME`, scale-to-zero, OpenTelemetry tracing and Toolbox (MCP) tools. Hosted agents can be published to Teams and M365 or turned into Autopilots.
**Status:** GA.
**Docs:**
- 📘 [What are hosted agents?](https://learn.microsoft.com/azure/foundry/agents/concepts/hosted-agents)
- 📘 [Agent Framework hosting in Foundry](https://learn.microsoft.com/agent-framework/hosting/foundry-hosted-agent)
- 📘 [Agent 365 integration with Foundry](https://learn.microsoft.com/azure/foundry/agents/concepts/agent-365-integration)

### 23. Foundry agent optimizer ▶ [01:26:11](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=5171s) · [01:31:40](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=5500s)
**What it is:** An evaluation-driven loop. You give it an agent, a dataset (which can be generated from traces) and evaluators or rubrics. It generates and scores candidate instructions, skills, tool descriptions and model choices, and shows the quality, speed and cost trade-offs so you can pick one. The Alaska Airlines ATA-code demo used it.
**Status:** GA *(BoN)*. Multi-turn evaluation is GA, and human annotation is in preview.
**Docs:**
- 📘 [What is the agent optimizer?](https://learn.microsoft.com/azure/foundry/agents/concepts/agent-optimizer-overview)
- 📘 [Quickstart: Optimize a prompt agent](https://learn.microsoft.com/azure/foundry/agents/quickstarts/quickstart-optimize-prompt-agent)
- 📘 [Make your agent optimizer-ready (hosted agents)](https://learn.microsoft.com/azure/foundry/agents/how-to/make-agent-optimizer-ready)
- 📘 [Prompt Optimizer (playground)](https://learn.microsoft.com/azure/foundry/observability/how-to/prompt-optimizer)

### 24. Foundry training / fine-tuning ("train your own model") ▶ [01:26:11](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=5171s) · [01:32:37](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=5557s)
**What it is:** The last step of the improvement loop: train the knowledge into model weights instead of long prompts. In the Alaska demo this reached about 97% accuracy at lower token cost. The Book of News lists **Managed Training** and **Programmed Training** (for open-weight models).
**Status:** Preview *(BoN)*.
**Docs:**
- 📘 [Foundry fine-tuning overview](https://learn.microsoft.com/azure/foundry/openai/concepts/fine-tuning-considerations). This is the existing fine-tuning docs. There's no Learn page yet under the new "Managed/Programmed Training" names.

---

## 3. Trust: Agent 365, security and governance

### 25. Microsoft Agent 365 ▶ [00:21:50](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1310s) · [01:47:25](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=6445s)
**What it is:** The control plane and "observability platform for AI". It provides a registry and Agent Map of all agents (Microsoft and third-party: Copilot Studio, Foundry, AWS Bedrock, GCP Vertex, OpenAI, Anthropic and others), owners, approvals, policy templates, tool/MCP governance, and Entra/Purview/Defender security. The keynote said 15M agents at the start and 50M+ managed at the end. AT&T alone runs 60,000+.
**Status:** GA (Commercial, per user). Included in Microsoft 365 E7.
**Docs:**
- 📘 [Overview of Microsoft Agent 365](https://learn.microsoft.com/microsoft-agent-365/overview)
- 📘 [Agent management in the M365 admin center](https://learn.microsoft.com/microsoft-agent-365/admin/agent-365-overview)
- 📘 [Governance and lifecycle actions](https://learn.microsoft.com/microsoft-agent-365/admin/agent-actions)
- 📘 [Agent Map](https://learn.microsoft.com/microsoft-365/admin/manage/agent-map)
- 📘 [Agent 365 service description (feature-by-license table)](https://learn.microsoft.com/office365/servicedescriptions/microsoft-agent-365/microsoft-agent-365)
- 📘 [Agent 365 SDK and CLI](https://learn.microsoft.com/microsoft-agent-365/developer/)

### 26. Agent 365 Business Analytics ▶ [00:22:49](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1369s) · [01:55:09](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=6909s)
**What it is:** "An ERP system of AI usage." It brings spend, adoption and value together across Copilot, Cowork, Autopilot, GitHub Copilot, Copilot Studio and non-Microsoft agents (for example Bedrock), with cost drivers, use-case value, forecasts, spend-cap and model-mix scenarios, and budgets per org scope. It builds on Viva Insights roles.
**Status:** Frontier public preview. Delegated spending policies and cost visibility for non-Microsoft agents arrive in December (keynote).
**Docs:**
- 📘 [Introduction to Agent 365 Business Analytics](https://learn.microsoft.com/a365-business-analytics/introduction)
- 📘 [Cost & forecast page](https://learn.microsoft.com/a365-business-analytics/cost-forecast)
- 📘 [Microsoft Copilot and Autopilot page](https://learn.microsoft.com/a365-business-analytics/services/microsoft-copilot)
- 📘 [Metrics reference](https://learn.microsoft.com/a365-business-analytics/reference/metrics)
- 🌐 [Agent 365 Business Analytics announcement](https://aka.ms/A365analytics)

### 27. Agent 365 cost management and spending policies ▶ [00:54:07](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=3247s) · [01:52:54](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=6774s)
**What it is:** IT sets spending policies with monthly and per-user limits, alerts and a billing method before Cowork or Autopilot can be used. Hard limits stop Microsoft agents at the cap, and spending groups let business owners manage their own budgets.
**Status:** Spend visibility and policies are in preview, and forecasting and recommendations are Frontier *(BoN)*.
**Docs:**
- 📘 [Set up usage-based billing for Copilot Credits](https://learn.microsoft.com/copilot/implement/usage-based-billing-copilot-credits-setup)
- 📘 [Manage usage-based billing (policy scope)](https://learn.microsoft.com/copilot/implement/usage-based-billing-manage-copilot-credits)
- 📘 [Monitor Copilot Credit spending](https://learn.microsoft.com/copilot/implement/usage-based-billing-copilot-credits-monitor-spending)

### 28. Agent 365 Action Center ▶ [01:52:17](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=6737s)
**What it is:** A prioritized queue of everything that needs admin attention, grouped and ranked, with suggested next steps. Examples from the AT&T demo: automated cleanup of agents unused for 90 days, and cost-spike forecasts when an agent switches model.
**Status:** Private preview expected in December *(BoN)*.
**Docs:**
- 📘 Closest current feature: ["Top actions for you" in the Agent overview](https://learn.microsoft.com/microsoft-agent-365/admin/agent-365-overview#top-actions-for-you) and [agent management rules](https://learn.microsoft.com/microsoft-agent-365/admin/agent-settings)
- ⚠️ No dedicated Action Center page yet.

### 29. Local agent discovery and dynamic risk ▶ [02:01:12](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=7272s)
**What it is:** Agent 365 and Defender for Endpoint find agents running on employee devices: CLI agents, desktop apps, IDE and VS Code extensions, and Claw-style agents such as OpenClaw, including their MCP server configurations. Each one gets a risk level with risk indicators, and Intune policies can block them.
**Status:** Preview / Frontier. Risk scoring requires E7 or Agent 365.
**Docs:**
- 📘 [Local agents in the M365 admin center](https://learn.microsoft.com/microsoft-agent-365/admin/agent-local)
- 📘 [Why local agents need their own governance](https://learn.microsoft.com/microsoft-agent-365/guidance/govern-local-agents)
- 📘 [Discover local AI agents with Defender for Endpoint](https://learn.microsoft.com/defender-endpoint/discover-local-ai-agents)
- 📘 [AI agent posture risk in Defender](https://learn.microsoft.com/defender-xdr/security-for-ai/ai-agent-risk-assessment)
- 📘 [Intune OpenClaw block settings](https://learn.microsoft.com/intune/device-security/security-baselines/ref-openclaw-settings)

### 30. Microsoft Perception ▶ [00:23:17](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1397s) · [00:25:12](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1512s) · [02:07:27](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=7647s) · [02:11:10](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=7870s)
**What it is:** A multi-agent security system in the Defender portal that runs three teams of agents:
- **Red team:** Recon Agent
- **Blue team:** Triage, Threat Intelligence, Attack Investigation and Detection Authoring agents
- **Green team:** Posture Prioritization Agent

You combine them into **playbooks** that are triggered manually, on a schedule or by events, with approval gates and immutable session records. It has a FinOps view that feeds Agent 365. The docs also call it "Project Perception". Leigh-Ann Russell said BNY was in the preview.
**Status:** GA. New previews: web-app testing and repository-scale vulnerability discovery *(BoN)*.
**Docs:**
- 📘 [What is Perception?](https://learn.microsoft.com/security/agentic-security/agentic-security-overview)
- 📘 [Agent categories (red, blue, green)](https://learn.microsoft.com/security/agentic-security/agentic-security-agent-categories)
- 📘 [Key concepts](https://learn.microsoft.com/security/agentic-security/agentic-security-concepts)
- 📘 [Application card (Responsible AI)](https://learn.microsoft.com/security/agentic-security/agentic-security-application-card)
- 📘 [Red team agent considerations](https://learn.microsoft.com/security/agentic-security/agentic-security-red-agent-considerations)
- 🌐 [Perception at Ignite](https://aka.ms/perceptionignite)

### 31. Endpoint shield / vulnerability shielding ▶ [02:12:49](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=7969s)
**What it is:** In the demo, David Weston used a "new endpoint shield" to protect unpatched machines while analyzing a Patch Tuesday CVE that was being actively exploited. The Book of News doesn't use "endpoint shield". The closest item is **vulnerability shielding** in Defender. It builds on **predictive shielding**, announced at Ignite 2025.
**Status:** Vulnerability shielding is in preview *(BoN)*.
**Docs:**
- 📘 [Predictive shielding in Defender](https://learn.microsoft.com/defender-xdr/shield-predict-threats)
- 📘 [Automatic attack disruption](https://learn.microsoft.com/defender-xdr/automatic-attack-disruption) (the capability that contained the autonomous attack in Satya's example ▶ [00:23:17](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1397s))
- ⚠️ No page yet under the name "endpoint shield" or "vulnerability shielding".

### 32. Microsoft Transparency Initiative ▶ [00:26:38](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1598s)
**What it is:** Standards for making AI transparent and independently verifiable: examining what AI sees and does, verifying its actions, and controlling its permissions. It has three parts: broader collaboration on agent standards, an ecosystem effort (40 organizations so far), and applying the standards to Microsoft's own models and Copilot.
**Status:** Announced.
**Docs:**
- ⚠️ No dedicated page found. It isn't in the readable part of the Book of News.
- 🌐 Closest related: [Responsible AI in 2026: How we are adapting (Sep 1, 2026)](https://blogs.microsoft.com/on-the-issues/2026/09/01/responsible-ai-in-2026-how-we-are-adapting-for-whats-ahead/), the 2026 Responsible AI Transparency Report, which focuses on agentic systems

---

## 4. Infrastructure

### 33. Azure HorizonDB ▶ [00:33:38](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=2018s)
**What it is:** A cloud-native managed database with separate compute and storage, a database-as-a-log design, up to 15 reader nodes, built-in vector search and AI model management, and mirroring to Fabric OneLake. **Note:** Satya called it a "distributed managed SQL database", but the docs describe it as built on **PostgreSQL** and fully PostgreSQL-compatible.
**Status:** GA.
**Docs:**
- 📘 [What is Azure HorizonDB?](https://learn.microsoft.com/azure/horizondb/overview/overview)
- 📘 [Create an Azure HorizonDB cluster](https://learn.microsoft.com/azure/horizondb/configure-maintain/quickstart-create-cluster)
- 📘 [Connect and query](https://learn.microsoft.com/azure/horizondb/connectivity/how-to-connect-query-guide)
- 🌐 [HorizonDB Ignite announcement](https://aka.ms/ignite26/horizondb)

### 34. HorizonDB in Microsoft Fabric ▶ [00:33:38](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=2018s)
**What it is:** The "unification of transactional and analytical data" that Satya said he'd worked toward for 25 years. **Fabric HorizonDB** is serverless PostgreSQL as a native Fabric item, with scale-to-zero. **Federated Analytics** covers mirroring to OneLake, read-only `pg_fabric_fdw` federated queries, and Copy-job data delivery (reverse ETL). Separately, Azure HorizonDB clusters can be mirrored into Fabric.
**Status:** Public preview. In the current preview, only the database creator's identity can connect.
**Docs:**
- 📘 [What is Fabric HorizonDB?](https://learn.microsoft.com/fabric/database/horizondb/overview)
- 📘 [Federated Analytics in Fabric HorizonDB](https://learn.microsoft.com/fabric/database/horizondb/federated-analytics-overview)
- 📘 [Translytical applications](https://learn.microsoft.com/fabric/database/horizondb/use-case-translytical-applications)
- 📘 [End-to-end tutorial](https://learn.microsoft.com/fabric/database/horizondb/tutorial-introduction)
- 📘 [FAQ](https://learn.microsoft.com/fabric/database/horizondb/faq)

### 35. Azure Agent Grid ▶ [00:31:52](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1912s)
**What it is:** Network security for agents built into the Azure network. Each enrolled workload gets a SPIFFE workload identity, traffic runs over mTLS tunnels, and policies are written against identities rather than IP addresses: FQDN/URL filtering, MCP tool policies, TLS inspection and Prompt Shields. Enforcement happens outside the sandbox, so the agent can't bypass it. Internally it was named "Agent Fabric".
**Status:** Limited preview, for ACI sandboxes and AKS. Request access via [aka.ms/AG_RequestAccess](https://aka.ms/AG_RequestAccess).
**Docs:**
- 📘 [What is Azure Agent Grid?](https://learn.microsoft.com/azure/agent-grid/overview)
- 📘 [Configure Agent Grid](https://learn.microsoft.com/azure/agent-grid/configure-agent-grid)
- 🌐 [AI infrastructure at Ignite 2026](https://aka.ms/ai-infra-ignite26)

### 36. AI sandboxes (sub-second micro VMs) ▶ [00:31:52](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1912s)
**What it is:** "Micro VMs that come up within a second, with full sandbox isolation". These are Hyper-V-isolated micro VMs in Azure Container Instances, with snapshot/restore, network-less enclaves, Agent ID, resizable CPU and memory, and confidential (SEV-SNP) options. There's also an Agent Sandbox extension for AKS.
**Status:** Public preview.
**Docs:**
- 📘 [Serverless sandboxes in Azure Container Instances](https://learn.microsoft.com/azure/container-instances/container-instances-ai-sandboxes)
- 📘 [Tutorial: Control sandbox outbound traffic with Agent Grid](https://learn.microsoft.com/azure/container-instances/container-instances-ai-sandboxes-tutorial-agent-grid)

### 37. Maia 300 ▶ [00:35:37](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=2137s)
**What it is:** Microsoft's next-generation custom AI inference accelerator. It has 8× HBM4 (288 GB, 18 TB/s) at 950 W, and 96 accelerators per rack. Microsoft claims about **40% more tokens per megawatt** (keynote: "per watt") than unnamed GPU systems, and up to 7× the tokens per rack of Maia 200.
**Status:** Announced. Production deployments start in 2027.
**Docs:**
- 🌐 [Azure blog: Deep dive into Azure Maia 300 architecture](https://azure.microsoft.com/en-us/blog/deep-dive-into-azure-maia-300-architecture/)
- 🌐 [InfoQ: Azure Maia 300](https://infoq.com/news/2026/10/azure-maia-300)
- ⚠️ Azure Boost and Azure Integrated HSM were also mentioned. They have existing Learn docs ([Azure Boost](https://learn.microsoft.com/azure/azure-boost/overview)), but I found no Ignite 2026 news for either.

### 38. Windows local AI ("unmetered intelligence") ▶ [00:31:52](https://www.youtube.com/watch?v=ZR4v1c4CClc&t=1912s)
**What it is:** Running capable models locally on Windows devices ("last year's frontier models on your laptop"). Judson's demo used "hybrid intelligence" on a Surface Laptop to pull in local files. The Book of News item is Windows 365 Cloud PCs with up to 32 vCPU, GPU options and **Foundry Local**.
**Status:** GA *(BoN)*.
**Docs:**
- 🌐 [Windows at Ignite 2026](https://aka.ms/WindowsAtIgnite2026)
- 📘 [Foundry Local](https://learn.microsoft.com/azure/foundry-local/what-is-foundry-local)
- 📘 [Windows 365 for Agents](https://learn.microsoft.com/windows-365/agents/introduction-windows-365-for-agents) (Cloud PCs for computer-using agents)

---

## Gaps and discrepancies

- **No documentation yet:** Today, Workspaces, Copilotforce, MAI Code 2 / Cyber 2 Flash, MAI licensed weights, the Transparency Initiative, and GitHub's goal-driven multi-repo feature. For these, rely on the keynote and the [Book of News](https://news.microsoft.com/events/ignite/2026/book-of-news/).
- **Names that differ between the keynote and the docs:**
  - Keynote "Copilotforce" ↔ Book of News "Salesforce in Copilot / Sales Cloud in Teams"
  - Keynote "endpoint shield" ↔ Book of News "vulnerability shielding"
  - Keynote "Microsoft Perception" ↔ docs "Project Perception"
  - Agent Grid ↔ former internal name "Agent Fabric"
- **Facts that differ:**
  - HorizonDB: the keynote says "SQL", the docs say PostgreSQL.
  - Microsoft IQ connectors: the keynote says "350+", the Book of News gives no number.
  - Maia 300: the keynote says "per watt", Microsoft's blog says "per megawatt", and both compare against unnamed systems.
- **Book of News caveat:** the subagent could only read the middle of that page as a summary, so statuses marked *(BoN)* for Copilot, Agent 365 and Foundry should be checked against the linked blogs.
- According to an [Office Watch analysis](https://office-watch.com/2026/microsoft-ignite-2026-ready-today/), only 76 of the 215 features announced at Ignite 2026 are GA today.
