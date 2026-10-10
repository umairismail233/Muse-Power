# ⚡ Muse-Power

A **curated, safety-vetted library of AI agent skills** — one trusted reference repo for getting any job done with an AI agent.

Every skill in this repo was:
1. **Reviewed read-only** — cloned and inspected, never executed. No code from these repos was ever run during curation.
2. **Security-vetted** — screened for malware, obfuscation, credential harvesting, data exfiltration, crypto miners, trackers, hardcoded secrets, and prompt-injection-style instructions. Anything suspicious was **excluded**.
3. **License-checked** — skills with missing or non-standard licenses were excluded.
4. **Copied verbatim** — skill content is unchanged from the source; each skill carries an `ATTRIBUTION.md` with source, author, license, and review date.

Full methodology, verdict counts, and the list of excluded repos live in [SECURITY-REVIEW.md](SECURITY-REVIEW.md). Machine-readable verdicts for all 259 reviewed links: [review-report.json](review-report.json).

## How to use a skill

Each skill lives at `skills/<category>/<skill-name>/` and contains at least a `SKILL.md` (the skill's instructions) plus any scripts/configs it ships with.

- **Claude Code / similar agents:** copy the skill folder into your project's `.claude/skills/` (or your agent's skills directory) and reference it.
- **Manual use:** read the `SKILL.md` — it tells the agent exactly what to do.
- **Check `ATTRIBUTION.md`** in each skill folder for the original source repo, author, and license before redistributing.

> ⚠️ Skills are third-party content. They were vetted at curation time (2026-10-11), but upstream repos change — for high-stakes use, re-check the source repo. See SECURITY-REVIEW.md for the exact review criteria.

## Skill index

### browser-automation

| Skill | What it does | Source | License |
|---|---|---|---|
| `open-web-bridge` | Let an agent drive the user's real browser locally via extension + daemon (page ops, HAR, replay, ev | [repo](https://github.com/woniu9524/open-web-bridge) | MIT |

### coding

| Skill | What it does | Source | License |
|---|---|---|---|
| `aegis-workflow-governance` | Agent development workflow governance (TDD, verification-before-completion, worktrees, skill routing | [repo](https://github.com/GanyuanRan/Aegis) | MIT |
| `agentic-readiness` | Assesses codebase readiness for AI coding agents | [repo](https://github.com/exadel-inc/agentic-readiness-assessment) | Apache-2.0 |
| `agmsg` | Local cross-agent messaging via SQLite | [repo](https://github.com/fujibee/agmsg) | MIT |
| `birdview` | Makes agent coding transparent: constraint canvas + review HTML showing planned architecture changes | [repo](https://github.com/Qiuner/birdview) | MIT |
| `clarity-gate` | Claim verification and document hashing skill | [repo](https://github.com/frmoretto/clarity-gate) | CC BY 4.0 |
| `coder-eval` | Evaluation harness for benchmarking coding agents on software-engineering tasks. | [repo](https://github.com/UiPath/coder_eval) | Apache-2.0 |
| `coderabbit-skills` | Official CodeRabbit skills and plugin packaging: AI-powered code review and autofix. | [repo](https://github.com/coderabbitai/skills) | MIT |
| `codex-collab` | Bridge between Claude Code and Codex: messaging + CLI for cross-agent collaboration and code review | [repo](https://github.com/Kevin7Qi/codex-collab) | MIT |
| `context-engineering-skills` | Context-engineering skills (memory systems, multi-agent patterns, harness engineering) with research | [repo](https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering) | LICENSE present |
| `cypress-ai-toolkit` | AI agent skills for writing and understanding Cypress E2E tests | [repo](https://github.com/cypress-io/ai-toolkit) | MIT |
| `data-structure-protocol` | Spec-driven development workflow protocol with git hooks | [repo](https://github.com/k-kolomeitsev/data-structure-protocol) | Apache-2.0 |
| `dev-agent-skills` | Developer workflow skills for git/GitHub | [repo](https://github.com/fvadicamo/dev-agent-skills) | MIT |
| `finding-unknowns` | Skills that help coding agents surface unknown-unknowns, bad assumptions, and test blindspots before | [repo](https://github.com/Neeeophytee/finding-unknowns-skills) | MIT |
| `fractal` | Recursive self-organizing agent orchestration (fractal node trees). | [repo](https://github.com/plasma-ai/fractal) | Apache 2.0 |
| `gh-image` | Upload images/files to GitHub issues and PRs | [repo](https://github.com/drogers0/gh-image) | MIT |
| `go-agent-skills` | Go design patterns, API, CLI, gRPC and architecture skills | [repo](https://github.com/eduardo-sl/go-agent-skills) | MIT |
| `itqan-engineering` | Full software-engineering lifecycle skill suite (discover/define/blueprint/construct/verify/inspect/ | [repo](https://github.com/saleh-alhaddad/itqan-engineering) | MIT |
| `lintlang` | Linter that catches agent failures in specs before the agent runs | [repo](https://github.com/hermes-labs-ai/lintlang) | Apache-2.0 |
| `maggy-bootstrap-pack` | Claude Code bootstrap pack: TDD enforcement, session memory, 73 engineering skills, and a multi-mode | [repo](https://github.com/alinaqi/maggy) | MIT |
| `makepad-skills` | Skill guides for building UIs with the Makepad framework (DSL, shaders, layout, animation). | [repo](https://github.com/ZhangHanDong/makepad-skills) | MIT |
| `matt-pocock-skills` | Matt Pocock's AI coding-assistant skills (TDD, code review, planning, brainstorming, git guardrails) | [repo](https://github.com/mattpocock/skills) | LICENSE present |
| `mblode-agent-skills` | Large skill collection: UI design audits, codebase architecture, CI speedup, PR babysitting, chat-hi | [repo](https://github.com/mblode/agent-skills) | LICENSE.md present |
| `mcollina-node-skills` | Node.js/Fastify/TypeScript/OAuth skill set by Matteo Collina with rules, examples, and recipes. | [repo](https://github.com/mcollina/skills) | LICENSE present |
| `model-hierarchy` | Cost-optimize agent work by routing tasks to appropriate model tiers. | [repo](https://github.com/zscole/model-hierarchy-skill) | MIT |
| `moyu` | Reminds coding agents to avoid over-engineering (minimal edits, no unsolicited abstractions/docs). | [repo](https://github.com/uucz/moyu) | MIT |
| `odai` | General-purpose agent task governance (fact-based, bounded execution). | [repo](https://github.com/orziz/odai) | MIT |
| `perfectify` | Methodology skill for verifying and improving agent work | [repo](https://github.com/dankofly/perfectify) | MIT |
| `playwright-skill` | Playwright test-automation skill pack: page-object patterns, CI setup, migration guidance, CLI usage | [repo](https://github.com/testdino-hq/playwright-skill) | MIT |
| `poka-yoke` | Defensive guardrails and hazard auditing for AI coding agents. | [repo](https://github.com/rainmanjam/poka-yoke) | MIT |
| `pypict` | Pairwise test-case generation helper for Microsoft PICT. | [repo](https://github.com/omkamal/pypict-claude-skill) | MIT |
| `qa-skills` | QA and software testing skills | [repo](https://github.com/fishzjp/qa-skills) | MIT |
| `qikly` | Separated coding/test-agent test generation tool | [repo](https://github.com/gal-a/qikly) | Apache-2.0 |
| `rails-conventions` | Ruby on Rails conventions reference skill | [repo](https://github.com/ethos-link/rails-conventions) | MIT |
| `scarletkc-agents` | Personal agent skill pack: delegate coding tasks to Grok/Codex/Antigravity CLIs, git worktree PR wor | [repo](https://github.com/scarletkc/agents) | Apache-2.0 |
| `simple-man` | High-compression professional communication mode for agents (fewer tokens, same substance) | [repo](https://github.com/Maksim-Burtsev/simple-man) | MIT |
| `skill-improvement-loop` | Monitors sessions and captures skill-improvement observations. | [repo](https://github.com/rebelytics/one-skill-to-rule-them-all) | CC-BY-4.0 |
| `skillreaper` | Skill-scaffolding CLI (skillreaper): generate skill boilerplate, gap analysis; checksum-verified rel | [repo](https://github.com/thousandflowers/skillreaper) | MIT |
| `slop-grader` | CLI that grades markdown text for AI-generated 'slop' using LLM judges. | [repo](https://github.com/lukstei/slop-grader) | LICENSE present |
| `subagent-cli-skills` | Installer and reference docs for delegating work to 24 AI coding CLIs (Gemini, Codex, Copilot, Qwen, | [repo](https://github.com/amirkiarafiei/subagent-cli-skills) | MIT |
| `superpowers` | Jesse Vincent's Claude Code plugin: TDD, systematic debugging, brainstorming, plan-execution skills. | [repo](https://github.com/obra/superpowers) | LICENSE present |
| `swiftui-agent-skill` | SwiftUI expert skill for AI coding agents, incl. API deprecation scanning via Sosumi MCP | [repo](https://github.com/AvdLee/SwiftUI-Agent-Skill) | MIT |
| `threejs-skills` | Three.js reference skills for agents (geometry, materials, shaders, lighting, animation, postprocess | [repo](https://github.com/CloudAI-X/threejs-skills) | MIT |
| `understand-anything` | Turns codebases/docs into interactive knowledge graphs the agent can explore, search and ask about | [repo](https://github.com/Egonex-AI/Understand-Anything) | MIT |
| `vexor` | Local semantic code search CLI (vexor): index repos, BM25/vector search, Claude Code plugin integrat | [repo](https://github.com/scarletkc/vexor) | MIT |
| `vibe-coding-prompts` | Vibe-coding workflow: 4 staged prompts + 11 skills to take an idea to an MVP plan with AI assistants | [repo](https://github.com/KhazP/vibe-coding-prompt-template) | MIT |
| `vibesec-secure-coding` | Defensive secure-coding guide for web applications (auth, injection, CORS, JWT, uploads) | [repo](https://github.com/BehiSecc/VibeSec-Skill) | Apache-2.0 |

### communication

| Skill | What it does | Source | License |
|---|---|---|---|
| `agentcall` | Join video meetings (Meet/Teams/Zoom) as an AI voice bot. | [repo](https://github.com/pattern-ai-labs/agentcall) | MIT |
| `resend-skills` | Resend email API usage: sending, templates, webhooks, inbound-email pipelines. | [repo](https://github.com/resend/resend-skills) | MIT |
| `sendmux-skills` | Skills letting AI agents send/manage email through the Sendmux hosted email API. | [repo](https://github.com/Sendmux/skills) | Apache-2.0 |

### crypto

| Skill | What it does | Source | License |
|---|---|---|---|
| `helius-solana-skills` | Solana development skills (Phantom, Jupiter, DFlow, OKX) + CLI/MCP | [repo](https://github.com/helius-labs/core-ai) | MIT |

### data-analysis

| Skill | What it does | Source | License |
|---|---|---|---|
| `a-share-stocks` | A-share (Chinese stock market) skill pack: realtime quotes, technical indicators, MACD strategies, p | [repo](https://github.com/shouldnotappearcalm/a-share-skill) | MIT |
| `academic-research` | Autonomous academic-research assistant skills: literature review, paper writing/review, experiments, | [repo](https://github.com/wanshuiyin/Auto-claude-code-research-in-sleep) | MIT |
| `alpha-insights` | Business-analyst skill producing decision-grade HTML research reports via a 7-stage workflow | [repo](https://github.com/Ericyoung-183/alpha-insights) | MIT |
| `apitube-news-api` | Official skill for the APITube News API: authenticated worldwide news search for coding agents. | [repo](https://github.com/apitube/news-api-skills) | MIT |
| `charlie-cfo` | AI CFO frameworks for bootstrapped startups (runway, unit economics, burn rate, forecasting) | [repo](https://github.com/EveryInc/charlie-cfo-skill) | MIT |
| `claude-ecom` | E-commerce analytics skill: sales metrics, cohort analysis, pricing checks and review validation on  | [repo](https://github.com/takechanman1228/claude-ecom) | MIT |
| `dashmotion` | Generates dashboard/diagram HTML from semantic graph JSON with deterministic layout scripts. | [repo](https://github.com/csthink/dashmotion) | MIT |
| `materials-simulation` | Computational materials-science simulation skills for agents (numerical methods, MD, V&V, optimizati | [repo](https://github.com/HeshamFS/materials-simulation-skills) | Apache-2.0 |
| `optim-agent` | Agentic parameter optimization: coding agent proposes configs, real evaluator scores them, loop conv | [repo](https://github.com/Optim-Agent/optim-agent) | MIT |
| `recursive-decomposition` | Single skill guiding agents to recursively decompose complex documents/tasks (RLM strategies) for lo | [repo](https://github.com/massimodeluisa/recursive-decomposition-skill) | LICENSE present (MIT bad |

### database

| Skill | What it does | Source | License |
|---|---|---|---|
| `qdrant-skills` | Qdrant vector database usage, deployment, and ops guidance for agents. | [repo](https://github.com/qdrant/skills) | Apache 2.0 |
| `redis-skills` | Redis data modeling, ops, clustering, and search guidance for agents. | [repo](https://github.com/redis/agent-skills) | MIT |
| `zilliz-mfs` | MFS (memory file system) skills for agents: find/ingest plus example deep-research and open-tag agen | [repo](https://github.com/zilliztech/mfs) | Apache-2.0 |

### design

| Skill | What it does | Source | License |
|---|---|---|---|
| `ai-video-editor` | Browser-based AI video editor (timeline editing, AI voiceover, captions) controllable by agents | [repo](https://github.com/MartinDelophy/ai-video-editor) | MIT |
| `auteur` | Directs cinematic, award-level marketing websites and design systems via a Claude Code skill with ex | [repo](https://github.com/agiwhitelist/auteur) | MIT |
| `color-expert` | Color-theory expert skill: techniques, colormaps, accessibility palettes, print/typography color gui | [repo](https://github.com/meodai/skill.color-expert) | LICENSE present |
| `dembrandt-skills` | UI/UX design guidance skills | [repo](https://github.com/dembrandt/dembrandt-skills) | MIT |
| `frontend-slides` | Generate animated HTML slide decks with templates, export to PDF/PPTX, deploy to Vercel. | [repo](https://github.com/zarazhangrui/frontend-slides) | MIT |
| `hand-drawn-diagrams` | Hand-drawn/Excalidraw diagram skill: renders, animates and validates diagrams locally. | [repo](https://github.com/muthuishere/hand-drawn-diagrams) | LICENSE present |
| `hig-doctor` | Apple HIG design guidance skills and audit validator. | [repo](https://github.com/raintree-technology/hig-doctor) | MIT |
| `markstream-vue` | Streaming markdown renderer UI component library with per-framework install skills. | [repo](https://github.com/Simon-He95/markstream-vue) | MIT |
| `mckinsey-visualization` | McKinsey-style charts, slides and HTML decks from notes | [repo](https://github.com/kgraph57/mckinsey-style-visualization-skill) | MIT |
| `motion-lexicon` | Copy-ready React motion components + skill guiding agents on product animation/interaction design | [repo](https://github.com/Ryan-yang125/motion-lexicon) | MIT (code) + CC BY 4.0 ( |
| `platform-design-skills` | Platform UI design guideline skills | [repo](https://github.com/ehmo/platform-design-skills) | MIT |
| `superdesign-skill` | Official Superdesign agent skill: design UI, presentations and graphics on the Superdesign canvas vi | [repo](https://github.com/superdesigndev/superdesign-skill) | MIT |
| `taste-skill` | Design-taste skills that guide agents to produce non-generic, high-quality frontend UIs | [repo](https://github.com/Leonxlnx/taste-skill) | MIT |
| `ui-skills` | UI design and improvement skills for coding agents | [repo](https://github.com/ibelick/ui-skills) | MIT |
| `ui-ux-pro-max` | UI/UX design skill: design-system generation, styling, brand/banner/slide guidance with datasets. | [repo](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) | LICENSE present (+ LICEN |
| `vibe-video-prompts` | Rewrites rough ideas into model-ready text-to-video prompts (Sora, Veo, Kling, Seedance) | [repo](https://github.com/Alisa0808/vibe-creating-skill) | MIT |

### devops

| Skill | What it does | Source | License |
|---|---|---|---|
| `app-store-connect-skills` | App Store Connect automation skills (builds, TestFlight, metadata, submissions). | [repo](https://github.com/rorkai/app-store-connect-cli-skills) | MIT |
| `aws-skills` | AWS agentic-AI, CDK/SST IaC, cost-ops, and serverless event-driven skills with CI validation. | [repo](https://github.com/zxkane/aws-skills) | MIT |
| `claude-apple-bridges` | Swift CLI bridges exposing macOS Reminders, Notes, Mail and tmux to Claude Code. | [repo](https://github.com/more-io/claude-apple-bridges) | LICENSE present (MIT bad |
| `deja-vu` | Search past AI coding sessions/decisions across tools on the local machine (recall, context, blame,  | [repo](https://github.com/vshulcz/deja-vu) | MIT |
| `google-cloud-skills` | Official agent-skills library for Google Cloud, Ads, Analytics and developer tools | [repo](https://github.com/google/skills) | Apache-2.0 |
| `homeassistant-skill` | Manage Home Assistant via local API | [repo](https://github.com/komal-SkyNET/claude-skill-homeassistant) | MIT |
| `integration-skill-pack` | Integration skill pack: Gmail, Google Workspace, Telegram/WhatsApp, SQL databases, NotebookLM, Eleve | [repo](https://github.com/sanjay3290/ai-skills) | Apache-2.0 |
| `ios-simulator-skill` | iOS Simulator automation: builds, accessibility-driven UI navigation, and device-state control for t | [repo](https://github.com/conorluddy/ios-simulator-skill) | MIT |
| `lambdatest-agent-skills` | Test-automation skills for 70+ frameworks wired to LambdaTest cloud grids | [repo](https://github.com/LambdaTest/agent-skills) | MIT |
| `linear-claude-skill` | Manage Linear issues/projects/teams via MCP, CLI, or helper scripts. | [repo](https://github.com/wrsmith108/linear-claude-skill) | MIT |
| `mirrord-skills` | Official mirrord skills (local dev against Kubernetes clusters) by MetalBear. | [repo](https://github.com/metalbear-co/skills) | LICENSE present |
| `multi-model-dispatcher` | Multi-model dispatcher: sends tasks to other AI models (Codex, Gemini, Kimi, DeepSeek, Qwen, GLM) fo | [repo](https://github.com/GiaSip/giasip-skills) | MIT |
| `n8n-skills` | Skills for building and managing n8n automation workflows | [repo](https://github.com/czlonkowski/n8n-skills) | MIT |
| `nvidia-skills` | Official NVIDIA agent skills for accelerated computing, physical AI/robotics, and AI blueprints | [repo](https://github.com/NVIDIA/skills) | Apache-2.0 AND CC-BY-4.0 |
| `orcareplay` | Answers questions about a past agent run from its recording and replays/forks that run | [repo](https://github.com/Continuum-AI-Corp/OrcaReplay) | Apache-2.0 |
| `terraform-skill` | Terraform/OpenTofu best-practices skill for AI agents, including a security/compliance reference. | [repo](https://github.com/antonbabenko/terraform-skill) | Apache-2.0 (per README b |
| `varlock-claude-skill` | Secure environment-variable/secret handling guidance for Claude Code sessions using Varlock. | [repo](https://github.com/wrsmith108/varlock-claude-skill) | MIT |
| `vmware-aiops` | AI-operated VMware/vSphere management: VM lifecycle, snapshots, guest exec, alarms, cluster triage v | [repo](https://github.com/vmware-skills/VMware-AIops) | MIT |
| `zapier-mcp` | Onboard users to Zapier MCP: authentication, discovering apps/actions, running demo workflows. | [repo](https://github.com/zapier/zapier-mcp) | MIT |

### documents

| Skill | What it does | Source | License |
|---|---|---|---|
| `agent-knowledge` | Personal knowledge-base toolchain: scaffold, ingest, query, lint and visualize local markdown knowle | [repo](https://github.com/stjbrown/agent-knowledge) | MIT |
| `app-store-preflight` | Pre-submission App Store review checklists (metadata, subscriptions, privacy, entitlements) for iOS/ | [repo](https://github.com/truongduy2611/app-store-preflight-skills) | MIT |
| `archify` | Architecture and workflow review skill that renders JSON-IR diagrams (architecture/workflow/sequence | [repo](https://github.com/tt-a1i/archify) | MIT |
| `keep-the-why` | Preserve and recover decision rationale (the 'why') in code projects. | [repo](https://github.com/oliver-zehentleitner/keep-the-why) | MIT |
| `learn-from-materials` | Extracts structured learning content from source materials | [repo](https://github.com/dmoshehun-prog/learn-from-materials) | MIT |
| `llm-wiki-manager` | Build, maintain and query a personal LLM-managed markdown wiki (second brain / research notebook) wi | [repo](https://github.com/sametbrr/llm-wiki-manager) | MIT |
| `mental-models` | Docs-only skill: reasoning mental models for Claude Code agents. | [repo](https://github.com/cyperx84/claude-skills-mental-models) | MIT |
| `multi-role-agent-pack` | Multi-role agent skill pack: product/project management, scrum, data science, slide writing, deep re | [repo](https://github.com/tronghieu/agent-skills) | MIT |
| `nutrient-pdf-skills` | PDF superpowers for agents: document generation, conversion, OCR, redaction, signing via Nutrient DW | [repo](https://github.com/PSPDFKit-labs/nutrient-agent-skill) | MIT-0 |
| `resume-skills` | Resume writing, ATS optimization, and job-search skills for career-focused agents | [repo](https://github.com/Paramchoudhary/ResumeSkills) | MIT |
| `ru-text-quality` | Russian text-quality skill: typography correction, proofreading, editorial and UX-writing guidance | [repo](https://github.com/talkstream/ru-text) | MIT |
| `skill-optimizer` | Discover, generalize and personalize agent skills from local workflows | [repo](https://github.com/hqhq1025/skill-optimizer) | MIT |
| `skills-janitor` | Manage, audit and prune installed agent skills | [repo](https://github.com/khendzel/skills-janitor) | MIT |
| `skills-library` | Curated YAML catalog of AI agent skills with CLI tools for browsing, recommending and validating ski | [repo](https://github.com/lindblomstefan/skills-library) | LICENSE present |
| `structured-thinking` | Structured-thinking skill collection: 29 reasoning frameworks (TRIZ, pre-mortem, systems thinking, S | [repo](https://github.com/tjboudreaux/cc-thinking-skills) | MIT |
| `translate-book` | Pipeline for translating books with AI assistance | [repo](https://github.com/deusyu/translate-book) | MIT |
| `tutor-skills` | Turns knowledge sources into an Obsidian StudyVault and quizzes the user for comprehension. | [repo](https://github.com/bevibing/tutor-skills) | MIT |
| `venice-ai-api-skills` | API reference skills for Venice.ai (chat, images, audio, billing, API-key management, crypto RPC, x4 | [repo](https://github.com/veniceai/skills) | MIT |

### education

| Skill | What it does | Source | License |
|---|---|---|---|
| `exam-prep` | Bilingual exam-prep coach generating quizzes, study guides and review sheets. | [repo](https://github.com/ZeKaiNie/universal-examprep-skill) | MIT |

### hardware

| Skill | What it does | Source | License |
|---|---|---|---|
| `kicad-happy` | KiCad electronics skills: SPICE simulation, PCB fab ordering, BOM tooling, and distributor part/data | [repo](https://github.com/aklofas/kicad-happy) | MIT |

### health

| Skill | What it does | Source | License |
|---|---|---|---|
| `wellally-health` | Personal health/wellness agent skills with wearable API integrations | [repo](https://github.com/huifer/WellAlly-health) | MIT |

### marketing

| Skill | What it does | Source | License |
|---|---|---|---|
| `aaron-marketing-bundle` | Comprehensive marketing skill bundle (ads, email, SEO, influencer, social) with local guardrail hook | [repo](https://github.com/aaron-he-zhu/aaron-marketing-skills) | Apache-2.0 |
| `aso-skills` | ASO playbooks for mobile apps (UA campaigns, screenshots, review management, retention, referrals) | [repo](https://github.com/Eronred/aso-skills) | MIT |
| `courier-skills` | Guides an agent in building notifications with Courier across email, SMS, push, inbox, Slack, Teams, | [repo](https://github.com/trycourier/courier-skills) | MIT |
| `creative-director` | Creative-director skill: legendary ad-campaign reference cards and structured campaign-generation wo | [repo](https://github.com/smixs/creative-director-skill) | CC BY 4.0 |
| `email-marketing-bible` | Email marketing operating manual for AI agents (campaigns, ESPs, deliverability, compliance) | [repo](https://github.com/CosmoBlk/email-marketing-bible) | MIT |
| `gtm-cofounder` | Go-to-market playbook skill library for devtool/AI startups (strategy, positioning, launch, growth l | [repo](https://github.com/AIDevGTM/gtm-cofounder) | MIT |
| `jev-social` | Social-intelligence CLI + skill (jev-social): query social data, generate evidence-backed reports, r | [repo](https://github.com/socai-io/jev-social) | MIT |
| `mailtrap-skills` | Official Mailtrap skills: sending/testing emails, templates, contacts, sending domains. | [repo](https://github.com/mailtrap/mailtrap-skills) | LICENSE present |
| `martech-cli-wrappers` | Marketing skill library with CLI wrappers for dozens of martech APIs, using the user's own API keys. | [repo](https://github.com/coreyhaines31/marketingskills) | MIT |
| `pm-skills` | PM workflow skills for agents (PRDs, OKRs, GTM, analytics, retros). | [repo](https://github.com/phuryn/pm-skills) | MIT |
| `postiz-agent` | Schedule social media posts via Postiz API | [repo](https://github.com/gitroomhq/postiz-agent) | AGPL-3.0 |
| `scrapecreators-research` | AI-agent research workflows (comment mining, ad teardowns, influencer prospecting) powered by the Sc | [repo](https://github.com/ScrapeCreators/social-media-research-skills) | MIT |
| `suede-creator-skills` | Creator/marketing skill pack: SEO audits, AI-visibility, copy, site optimization, SMS programs | [repo](https://github.com/JasonColapietro/suede-creator-skills) | MIT |
| `taisly-video-poster` | Taisly agent: schedule and post videos via MCP, device-pairing setup, local credential storage | [repo](https://github.com/taisly/agent) | MIT |
| `x-article-publisher` | Publish Markdown articles to X (Twitter) Articles with formatting, cover images, and table/diagram c | [repo](https://github.com/wshuyi/x-article-publisher-skill) | MIT |

### music

| Skill | What it does | Source | License |
|---|---|---|---|
| `ai-music-studio` | End-to-end AI music production suite (lyrics, Suno workflows, mixing/mastering, sheet music, promo,  | [repo](https://github.com/bitwize-music-studio/claude-ai-music-skills) | CC0-1.0 |

### productivity

| Skill | What it does | Source | License |
|---|---|---|---|
| `emulo` | Mines local coding-agent session histories into a private 'you.md' agent profile with dated receipts | [repo](https://github.com/ohad6k/emulo) | LICENSE present (MIT) |
| `obsidian-knowledge-brain` | Agent memory skill that captures decisions and error fixes across sessions into a searchable knowled | [repo](https://github.com/Tubo2333/obsidian-knowledge-brain) | MIT |

### research

| Skill | What it does | Source | License |
|---|---|---|---|
| `mech-eng-research` | Mechanical-engineering research workflows: lit review, proposals, analysis | [repo](https://github.com/hanhuark/mechanical-engineering-research-skill) | MIT |

### security

| Skill | What it does | Source | License |
|---|---|---|---|
| `clawsec` | Security scanning and advisory feed for OpenClaw/agent skills. | [repo](https://github.com/prompt-security/clawsec) | AGPL-3.0 |
| `cloudflare-security-audit` | Official Cloudflare skill: turns a coding agent into a structured security auditor / vuln-hunting ha | [repo](https://github.com/cloudflare/security-audit-skill) | MIT |
| `paranoid` | Security review skill with local-only proof-of-concept pentesting | [repo](https://github.com/kulchankas/paranoid) | MIT |
| `rea-reverse-engineering` | Reverse-engineering analysis toolkit (rea = reverse-engineer-anything): binary/JS analysis CLI with  | [repo](https://github.com/morluto/rea) | LICENSE present |
| `snyk-agent-scan` | Snyk agent-skill scanner: statically inspect installed agent skills/MCP servers for malicious or ris | [repo](https://github.com/snyk/agent-scan) | Apache-2.0 |

### seo

| Skill | What it does | Source | License |
|---|---|---|---|
| `claude-seo` | Comprehensive SEO workflow skills for Claude Code (audits, schema, content, GSC/GA4, sitemaps) | [repo](https://github.com/AgriciDaniel/claude-seo) | MIT |

### shopping

| Skill | What it does | Source | License |
|---|---|---|---|
| `zinc-skills` | Discover, buy, track, and return products from US retailers via the Zinc API (agent checkout). | [repo](https://github.com/zincio/skills) | MIT |

### video

| Skill | What it does | Source | License |
|---|---|---|---|
| `capcut-cli` | CLI for editing CapCut drafts: subtitles, timing, TTS, cutting long-form to shorts. | [repo](https://github.com/renezander030/capcut-cli) | MIT |
| `cutaway` | Record polished browser workflow demo videos locally via Playwright | [repo](https://github.com/half144/cutaway) | MIT |
| `youtube-clipper` | Download YouTube videos, clip segments, translate and burn bilingual subtitles, generate summaries. | [repo](https://github.com/op7418/Youtube-clipper-skill) | MIT |

### web-scraping

| Skill | What it does | Source | License |
|---|---|---|---|
| `agent-reach` | One-command web research/scraping across 16 platforms (social, career, dev, video, finance) for agen | [repo](https://github.com/Panniantong/Agent-Reach) | MIT |
| `skill-seekers` | Build AI skills from docs sites, GitHub repos, PDFs, videos, and codebases; export to vector DBs. | [repo](https://github.com/yusufkaraaslan/Skill_Seekers) | MIT |
| `youtube-fetcher` | Turns video links (YouTube/TikTok/Instagram/X) into archival Markdown notes with transcripts and fra | [repo](https://github.com/JimmySadek/youtube-fetcher-to-markdown) | MIT |

### writing

| Skill | What it does | Source | License |
|---|---|---|---|
| `novel-writing` | Novel/fiction project skill: outlining, drafting, revision, dialogue and story-outline contract chec | [repo](https://github.com/wgwtest/novel-writing) | MIT |
| `sepia` | Repairs AI narrative-architecture tells in fiction and applies domain rules to professional prose | [repo](https://github.com/Nanako0129/sepia) | MIT |
| `unslop` | Removes AI writing tics (sycophancy, em-dash overuse, hedging) so agent output reads human | [repo](https://github.com/MohamedAbdallah-14/unslop) | MIT |

## Contributing

Found a great skill that's missing, or spotted a problem with a curated one? Open an issue. New additions go through the same read-only security review before inclusion.

## License of this curation

This repo's own files (README, SECURITY-REVIEW.md, index) are public domain (CC0) where applicable. **Each skill keeps its original author's license** — see the skill's `ATTRIBUTION.md` and the source repo.
