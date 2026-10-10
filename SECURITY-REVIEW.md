# 🔒 SECURITY-REVIEW.md

How the Muse-Power skill library was vetted, and what was kept out and why.

## Methodology

1. **Source:** all 259 unique GitHub links on https://github.com/VoltAgent/awesome-agent-skills (extracted 2026-10-11).
2. **Read-only review:** each repo was cloned (`git clone --depth 1`) and inspected — SKILL.md files, scripts (`*.sh`, `*.py`, `*.js`), hooks, `package.json`, `requirements*.txt`, licenses. **No code from any repo was ever executed**: no installs, no script runs, no network calls beyond the clone itself. Work was parallelized across 10 isolated review agents; every URL got a verdict.
3. **Red flags hunted:** obfuscated code (base64 blobs, eval/exec of remote content), network calls to unknown/third-party endpoints, credential harvesting or file/env exfiltration, crypto miners, install scripts downloading binaries, tracking pixels/analytics callbacks, hardcoded API keys/secrets, instructions to disable security or bypass safeguards, prompt-injection-style instructions inside SKILL.md, skills phoning home with user data, unclear/missing licenses.
4. **Verdicts:** `SAFE` / `REVIEW` (suspicious — lead decision) / `UNSAFE` / `UNREACHABLE` / `NOT-A-REPO`.
5. **Curation rule:** only `SAFE` repos (plus 2 `REVIEW` repos cleared by lead decision, one with a skill removed) were copied — verbatim — into `skills/`, each with an `ATTRIBUTION.md` (source, author, license, review date). Deduplication preferred official/maintained repos, clear licenses, and unique category coverage.

## Verdict counts

| Verdict | Count |
|---|---|
| Reviewed (total links) | 259 |
| SAFE | 219 |
| REVIEW (lead decision) | 26 |
| UNSAFE | **0** |
| UNREACHABLE (clone failed / too large) | 12 |
| NOT-A-REPO | 2 |
| SAFE but not curated (clone unrecoverable) | 1 |
| **Curated into `skills/`** | **155** |

No malware, miners, obfuscated payloads, or hardcoded secrets were found in any of the 259 repos.

## REVIEW verdicts — lead decisions

24 excluded, 2 included (one with a skill removed):

| Repo | Lead decision |
|---|---|
| `Bomx/distribb-skill` | **EXCLUDED** |
| `BrianRWagner/ai-marketing-claude-code-skills` | **EXCLUDED** |
| `CosmoBlk/email-marketing-bible` | INCLUDED (doc-only, strong consent/safety gates, compliance-first checks documented) |
| `Linked-API/linkedin-skills` | **EXCLUDED** |
| `NoizAI/skills` | **EXCLUDED** |
| `Orchestra-Research/AI-Research-SKILLs` | **EXCLUDED** |
| `PleasePrompto/notebooklm-skill` | **EXCLUDED** |
| `YannisKiefer/dark-psychology-skills` | **EXCLUDED** |
| `alinaqi/maggy` | INCLUDED with the `credentials` skill REMOVED (that skill regex-extracts API keys from a plaintext file — excluded as a credential-harvesting pattern) |
| `browser-act/skills` | **EXCLUDED** |
| `degausai/wonda` | **EXCLUDED** |
| `eatmoreduck/boss-zhipin-scraper` | **EXCLUDED** |
| `foryourhealth111-pixel/Vibe-Skills` | **EXCLUDED** |
| `hedralab/eskill` | **EXCLUDED** |
| `jthack/ffuf_claude_skill` | **EXCLUDED** |
| `makenotion/claude-code-notion-plugin` | **EXCLUDED** |
| `mukul975/Anthropic-Cybersecurity-Skills` | **EXCLUDED** |
| `mvanhorn/last30days-skill` | **EXCLUDED** |
| `officialzeroxyz/zero-plugins` | **EXCLUDED** |
| `reliefeai/browser-relay` | **EXCLUDED** |
| `sandbaseai/sandbase-skills` | **EXCLUDED** |
| `swaylq/humanize-chinese` | **EXCLUDED** |
| `transloadit/skills` | **EXCLUDED** |
| `unbrowse-ai/unbrowse` | **EXCLUDED** |
| `vaibhavarora14/job-application-agent` | **EXCLUDED** |
| `wendylabsinc/claude-skills` | **EXCLUDED** |

### Why each excluded REVIEW repo was kept out

| Repo | Reason |
|---|---|
| `Bomx/distribb-skill` | Commercial SaaS skill: agent acts through the user's Distribb API key, and the API exposes ad accounts, bank accounts, social DMs, databases and GitHub to the agent — a very high privilege surface via a third-party servi |
| `BrianRWagner/ai-marketing-claude-code-skills` | 23 marketing skills, installer is purely local file-copy. However the youtube-summarizer skill explicitly instructs bypassing YouTube's cloud IP blocking via Android client emulation (platform ToS circumvention), and doc |
| `Linked-API/linkedin-skills` | Legitimate commercial product (Linked API paid SaaS) but worth a lead decision: every LinkedIn action and the user's LinkedIn account tokens flow through the vendor's cloud browser service (linkedapi.io/app.linkedapi.io) |
| `NoizAI/skills` | TTS/STT/music/sound-fx/video skill suite backed by the Noiz cloud API (noiz.ai) plus local Kokoro. No malware found: API key comes from user env/NOIZ_API_KEY, calls go to the vendor's own endpoint. Concerns for a lead: ( |
| `Orchestra-Research/AI-Research-SKILLs` | 98 skills for end-to-end autonomous AI research (model arch, fine-tuning, evals, paper writing). Code is clean (MIT, no obfuscation) but the flagship autoresearch SKILL.md explicitly instructs the agent: 'Do not ask the  |
| `PleasePrompto/notebooklm-skill` | Archived/unmaintained (Sept 2026) browser-automation skill that queries the user's Google NotebookLM via their own logged-in session. No exfil to third parties was found, but the design persists Google session cookies (i |
| `YannisKiefer/dark-psychology-skills` | Doc-only sales playbooks, but the content is 'dark psychology' persuasion/manipulation tactics for cold outreach and deal-closing. No malware or exfil found, but inclusion in a safety-vetted library needs a lead content- |
| `browser-act/skills` | Commercial browser-automation skill set whose code is clean (MIT, no miners/obfuscation/secrets), but multiple SKILL.md files coach agents in anti-bot evasion: 'open multiple stealth browser sessions and distribute work  |
| `degausai/wonda` | Docs-only skill for a commercial social-automation CLI ($19.99/mo). Documents LinkedIn/Reddit/email account creation with antidetect Chromium and proxy guidance to evade shadowbans, plus PostHog telemetry (opt-out exists |
| `eatmoreduck/boss-zhipin-scraper` | Job-listing scraper for Boss Zhipin (Chinese job site) driven via raw Chrome DevTools Protocol to bypass normal site access; likely violates the site's ToS. No malware, exfiltration, or obfuscation found — it only output |
| `foryourhealth111-pixel/Vibe-Skills` | Large third-party skill bundle (258 SKILL.md files, 56MB) plus a vgo-cli installer — a wholesale collection of other authors' skills (Apache-2.0 + THIRD_PARTY_LICENSES.md). Spot checks found no malware, but the bundle wa |
| `hedralab/eskill` | Skill-authoring/evaluation framework (spec rules, eval loops, templates). No malware, obfuscation, or network calls found — but LICENSE is a non-standard Vietnamese custom 'Use-Only License' (Giay phep Chi-Dung), not OSI |
| `jthack/ffuf_claude_skill` | Skill integrating the ffuf web fuzzer for security testing/recon (dual-use offensive-security tooling). No malware or exfiltration, and README states testing requires authorization — but there is NO LICENSE file and the  |
| `makenotion/claude-code-notion-plugin` | Benign markdown-only skills with no bundled scripts or network calls, but no LICENSE file was found anywhere, so the usage license is unclear. |
| `mukul975/Anthropic-Cybersecurity-Skills` | Contains dual-use offensive attack playbooks (NTLM relaying for ADCS ESC8, Wi-Fi password cracking with aircrack, spearphishing simulation, ransomware RE routines). No malware binaries or exfiltration found, but offensiv |
| `mvanhorn/last30days-skill` | Ships browser cookie extraction/decryption code (Chrome/Safari) and authenticated scraping across 20+ platforms; sensitive credential handling needs a lead decision. It does include built-in exfiltration/injection guard  |
| `officialzeroxyz/zero-plugins` | Ships a PreToolUse hook that auto-approves Bash commands (scoped to read-only subcommands, but still a guardrail reduction); install docs use curl|bash from zero.xyz; and the plugin moves real crypto money via wallets —  |
| `reliefeai/browser-relay` | Remote-browser-control skill (Chrome extension + daemon + hub). Transparent PRIVACY.md and MIT license, remote relay opt-in. However, in Remote Relay mode full browsing data (page text, screenshots, network metadata, for |
| `sandbaseai/sandbase-skills` | Large catalog (~230 skills) that routes through SandBase's third-party capability marketplace (email validation, talent sourcing, sales intelligence, etc.); skills send user-supplied data (emails, company names, lead lis |
| `swaylq/humanize-chinese` | Chinese AI-text humanizer (declaude-cn/deai-rewrite): all processing is local and it explicitly avoids downloading data, but the tool's core purpose is defeating AI-text detection/watermarking, which is a dual-use evasio |
| `transloadit/skills` | Official Transloadit skill pack (media-encoding/upload skills, env-var secrets handling is clean), but two issues need a lead decision: (1) no LICENSE file and no license field in package.json — unclear licensing; (2) th |
| `unbrowse-ai/unbrowse` | Legit commercial product (MIT, SECURITY.md), but by design the cookie daemon uploads browser cookies/sessions — including a wildcard '*' all-sites mode — to unbrowse.ai cloud, and logins are saved/filled server-side. Coo |
| `vaibhavarora14/job-application-agent` | Auto-applies to jobs via browser/ATS automation (intended purpose, user-driven). Flags: PostHog usage telemetry AND name/email identity sharing are enabled BY DEFAULT (opt-out, agent must show a disclosure), plus default |
| `wendylabsinc/claude-skills` | Content is benign coding-docs skills (Swift, Postgres, Linear, GitHub Actions, eval harnesses), but the repo has NO license file and no license text anywhere — unclear license is a curation blocker per the rules. |

## SAFE but not curated (65 repos)

These passed the safety review but were left out for non-safety reasons:

### no-license (9)
No license file found — redistribution rights unclear. Excluded as a curation blocker.

- `SHADOWPR0/beautiful_prose` — Style contract skill that makes an agent write forceful, AI-tic-free English prose.
- `SHADOWPR0/security-bluebook-builder` — Skill that builds a concise normative security policy ('Blue Book') for sensitive apps.
- `Upload-Post/upload-post-skill` — Skill for posting/scheduling content across social platforms via the Upload-Post API.
- `angular/skills` — Coding-agent guidance for building Angular apps: scaffolding, components/services, and reactivity best practic
- `dannwaneri/spec-writer` — Generates structured specs/plans from feature requests
- `gokapso/agent-skills` — WhatsApp Business integration via Kapso APIs
- `op7418/NanoBanana-PPT-Skills` — Generate PPT slides with Nano Banana image gen and Kling AI transition videos.
- `ramzesenok/iOS-Accessibility-Audit-Skill` — iOS SwiftUI WCAG 2.2 accessibility audits.
- `robzolkos/skill-rails-upgrade` — Rails application upgrade assessment and selective merging guidance.

### vendor-cloud (9)
The skill's core function routes the user's private content/data through a third-party vendor's cloud (email bodies, social data, video, ad/prospect data). Excluded per the no-data-leak rule.

- `Atomic-Mail/atomic-mail-agentic` — Gives AI agents a real @atomicmail.ai email inbox via JMAP API (read/send/search mail)
- `Xquik-dev/tweetclaw` — Twitter/X search, monitoring and automation plugin powered by the Xquik API.
- `Xquik-dev/x-twitter-scraper` — X/Twitter scraping skills and Apify actors powered by the Xquik API.
- `ZeroPointRepo/youtube-skills` — Skills for YouTube transcripts, channel research and video data via the TranscriptAPI service.
- `citlyze/citlyze-skills` — Vendor skills for Citlyze: auditing brand visibility in AI search and AEO page audits.
- `explorium-ai/vibeprospecting-plugin` — B2B prospecting via Explorium data APIs
- `honeydew-ai/honeydew-ai-coding-agents-plugins` — Skills and hooks for Honeydew semantic data-model MCP tools
- `squirrelscan/skills` — Agent skills for the squirrelscan website auditor: SEO/performance/security audits and an iterative fix loop v
- `video-db/skills` — Video/audio understanding skill: ingest, index, search, transcribe, edit, and generate media with VideoDB.

### restrictive-license (3)
Restrictive non-commercial / no-derivatives licensing — incompatible with a public reference library.

- `Digidai/product-manager-skills` — Product-manager skill for Claude Code/Codex/Cursor/Windsurf (SaaS metrics, PRDs, roadmaps, discovery)
- `deanpeters/Product-Manager-Skills` — Product-management skills: PRDs, roadmaps, metrics, strategy
- `lawve-ai/awesome-legal-skills` — Curated legal-professional skills: contracts, compliance, GDPR, translation

### evasion-framed (3)
Tooling marketed primarily for defeating AI-text detection — excluded as a dual-use evasion capability.

- `Vladimir-Human/humanizer-ru` — Library that rewrites AI-generated Russian text to sound human-written.
- `blader/humanizer` — Rewrites AI-sounding prose into natural writing using Wikipedia's 'Signs of AI writing' patterns.
- `ilyautov/humanizer-ru` — Russian text humanizer: de-AI-ifies bureaucratic/marked-up Russian prose

### out-of-scope (1)
Low relevance to the library’s purpose (165 education skills for classroom teaching).

- `GarethManning/education-agent-skills` — Education agent skills (PERMA lesson design, trauma-informed practice, motivation, wellbeing)

### no-skill-content (11)
No SKILL.md content to curate (directories, MCP servers without skill files, frameworks). Nothing to copy.

- `VoltAgent/awesome-agent-skills` — Curated directory of official and community agent skills.
- `VoltAgent/awesome-codex-subagents` — Curated directory of subagent definitions for coding agents.
- `VoltAgent/official-mcp-servers` — Curated list of official, vetted MCP servers.
- `VoltAgent/voltagent` — TypeScript framework for building AI agents.
- `crawlbase/crawlbase-mcp` — MCP server for the Crawlbase web-scraping API.
- `crawlbase/langchain-crawlbase` — LangChain integration (tools, retrievers, loaders) for the Crawlbase web-scraping API.
- `crawlbase/n8n-nodes-crawlbase` — n8n node and credentials for the Crawlbase web-scraping API.
- `hanfang/claude-memory-skill` — Persistent local memory system with /mem load|save|recall commands
- `rootlyhq/rootly-mcp-server` — MCP server for the Rootly incident-management API.
- `serpapi/serpapi-cli` — Official SerpApi command-line client for structured Google/other search-engine results
- `serpapi/serpapi-search-tools-python` — Official SerpApi Python toolkit: search-query tools and agent-framework adapters for LLM apps

### near-duplicate (29)
Overlaps a curated skill in the same category; the cleaner/better-licensed alternative was kept (quality over quantity).

- `NeoLabHQ/context-engineering-kit` — Advanced context-engineering techniques and plugin patterns for Claude Code, Cursor, Antigravity
- `NotMyself/claude-win11-speckit-update-skill` — Safe, customization-preserving updater for GitHub SpecKit installations (Windows/PowerShell)
- `OneWave-AI/claude-skills` — 232 agent skills spanning sales, marketing, finance, productivity, design, and coding tasks
- `Orkas-AI/Orkas-VideoStudio` — Video composition, AI generation, and editing pipeline driven by coding agents via an editable plan IR
- `ReScienceLab/opc-skills` — AI agent skills for solopreneurs: SEO/GEO, branding assets, domain hunting, launch and demand research
- `SeanZoR/claude-speed-reader` — RSVP speed-reader (Spritz-style) for reading Claude responses at 600+ WPM.
- `SupercmoHQ/superCMO-skills` — Skills for AI-generated ad images/videos/UGC through the SuperCMO platform.
- `VoDaiLocz/kilo-kit-mcp` — Large curated skill library for coding agents with a bundled local MCP server.
- `archcore-ai/archcore` — Commercial AI coding plugin (code review, planning, project init, docs) with host-wiring helpers for Claude Co
- `baskduf/FableCodex` — Evidence-based workflow gates (goals, findings, coverage checks) for Codex coding agents.
- `d1vai/d1v-cli` — CLI and skill for the d1v agent runtime
- `efremidze/swift-patterns-skill` — Swift design patterns reference skill
- `forjd/better-writing` — Improves writing quality via agent guidance
- `gooseworks-ai/goose-skills` — 200+ GTM skills: ads, social, content, SEO, competitive intel, lead gen
- `ilyautov/small-business-ru` — AI co-pilot skills for Russian small-business owners
- `indranilbanerjee/digital-marketing-pro` — Agency marketing workflows: strategy, content, analytics, compliance
- `kensaurus/cursor-kenji` — Agent skills, commands and subagents for coding workflows
- `lackeyjb/playwright-skill` — Browser automation and testing with Playwright
- `makenotion/notion-cookbook` — Cookbook of Notion sync-worker templates (TypeScript) syncing services like Zendesk, Workday and Vercel into N
- `manavmishra/ZeroSlop` — AI-writing 'slop' detection and editing toolkit: local scoring scripts, MCP server, website, marketplace packa
- `modem-dev/skills` — Single tiny skill teaching agents to write discoverable, readable code.
- `nowork-studio/notfair-plugin` — SEO/ads/CMS Claude plugin: keyword research, SEO audits, Google/Meta ads playbooks, WordPress/Strapi/Ghost too
- `obra/superpowers-lab` — Experimental skill lab: Windows VM, tmux commands, mcp-cli, duplicate-function finder.
- `ognjengt/founder-skills` — Founder/marketing skill set: X/LinkedIn writing, viral hooks, PRD generator, GTM plans, competitor intel.
- `rameerez/claude-code-startup-skills` — Startup workflow helpers: video download/transcribe, image compression, posting to X.
- `realkimbarrett/advertising-skills` — Ad copywriting and campaign-orchestration skills for agents.
- `santifer/career-ops` — AI job-search command center: scan job portals, evaluate listings, tailor CVs/cover letters, track application
- `sergebulaev/linkedin-skills` — LinkedIn automation skill pack: post writing, scheduling/publishing via Publora, AI illustration via Pixfaro, 
- `vanshyadav1408/Omentir` — Open-source LinkedIn prospecting/outreach automation workspace (self-hostable Next.js app) plus an AI-writing 

## UNREACHABLE (12)

One repo (`JasonColapietro/suede-creator-skills`) was recovered on retry, lead-reviewed SAFE, and curated — it no longer appears below.

The remaining 12 could not be cloned for review (timeouts from parallel-worker congestion, >200MB size cap, or flaky remotes). Not curated — never reviewed.

## SAFE but not curated — clone unrecoverable (1)

- `Tencent/AI-Infra-Guard` — defensive toolkit for scanning MCP servers, agent skills and AI infra (Apache-2.0, verdict SAFE). The repo's Git hosting failed 4 consecutive clone attempts (timeouts / checkout failures), so its content could not be copied verbatim into `skills/`. Revisit in a future curation pass.

| Repo | Reason |
|---|---|
| `Charlie85270/Dorothy` | Clone timed out on every attempt (initial 120s, 60s retry, 120s retry); GitHub-side slowness with many concurrent batch clones. No content was reviewed. |
| `HUANGCHIHHUNGLeo/claude-real-video` | Clone timed out on every attempt (initial 120s, 90s and 120s retries). No content was reviewed. |
| `K-Dense-AI/scientific-agent-skills` | Clone failed on every attempt: timeout (120s) and 'fetch-pack: unexpected disconnect'. No content was reviewed. |
| `Kayforkind/reimagine-it` | git clone could not complete: first attempt failed with 'No space left on device' on /tmp, retry in workspace timed out at 120s leaving an incomplete checkout; per task rules marked UNREACHABLE. |
| `aeonfun/aeon` | git clone timed out after 120s; no directory was created, so the repo could not be reviewed. |
| `awrshift/claude-memory-kit` | git clone exceeded the 120s timeout and exited non-zero (empty stderr); a partial 24MB tree was left on disk but the clone was not verified complete, so per protocol it was not reviewed. Partial tree suggested a Claude m |
| `chrono-meta/forge-harness` | Clone fetched objects but the working-tree checkout failed ('fatal: unable to checkout working tree'); the tree was not verified complete, so per protocol it was not reviewed. Partial tree suggested a multi-plugin agent  |
| `infrasity-labs/dev-gtm-claude-skills` | git clone --depth 1 failed: timeout after 120s ('fetch-pack: unexpected disconnect while reading sideband packet'). Repo could not be analyzed. |
| `openaccountants/openaccountants` | Clone is 264MB, exceeding the 200MB review cap; clone removed without review. |
| `perso-ai/perso-dubbing-plugin` | git clone timed out at 120s twice (initial attempt plus one retry): 'fetch-pack: unexpected disconnect while reading sideband packet'. |
| `thedotmack/claude-mem` | Clone failed: initial batch clone errored with 'No space left on device' (tmpfs full); after freeing space, a fresh clone hung past the 120s timeout (twice) and retrieved only empty git metadata. Repo contents could not  |
| `xberg-io/xberg` | Repo exists (git ls-remote confirms refs/heads/main), but 4 separate 'git clone --depth 1' attempts failed or returned an empty worktree ('fetch-pack: unexpected disconnect while reading sideband packet' / timeout), so n |

## NOT-A-REPO (2)

| Link | Reason |
|---|---|
| `https://github.com/axelfreeman/marketing-mindset` | GitHub returned an auth prompt ('could not read Username') for anonymous access, i.e. the repo does not exist publicly (deleted, renamed, or private) — 404-as-n |
| `https://github.com/user-attachments/assets` | Not a GitHub repository: 'user-attachments/assets' is GitHub's asset-hosting path prefix. git clone prompts for credentials (auth failure), confirming no repo e |

## Re-review note

Upstream repos change. Verdicts reflect the state on 2026-10-11. Before high-stakes use of any skill, re-check its source repo. The machine-readable master table is [review-report.json](review-report.json).
