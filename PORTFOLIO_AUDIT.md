# Portfolio recruiter audit — Part 1

Reviewed 2026-11-14. Target: FDE, technical leadership/management, and AI product opportunities.

## Review scope

Inspected the local generated homepage, stack, experience, and work pages, plus Next.js source content and shared case-study components. GitHub's remote repository tree was accessible; the local homepage blob matches the remote homepage (`efce73fdda06af5210a75fd51890446fc9482c8e`). Direct live-site access failed in this environment. This is a content/source audit, not a browser rendering, accessibility, or live performance certification.

References: [deployed repository](https://github.com/Saraswat123/Saraswat123.github.io), [homepage](https://saraswat123.github.io/), [stack](https://saraswat123.github.io/stack/), [work](https://saraswat123.github.io/work/), [experience](https://saraswat123.github.io/experience/). Source checkout: `../portfolio`.

## Main finding

Skills and stacks already exist. `/stack` is titled “Agent workspace” and emphasizes connected tools, installed skills, and agents. Project cards show stacks, while shared case studies put the Stack section after design documents. Recruiters need a faster mapping from capability to ownership, shipped work, and measured results.

The strongest existing material is specific: 23 Rysen AI tools across two roles; an approval-gated Rust MCP server; Vault Harness's 36-case eval; and concrete Moltis fixes. Build the presentation around these examples, then add measured operating evidence where it exists.

## Prioritized work

| Priority | Change | Completion criterion |
| --- | --- | --- |
| P0 | Reconcile claims | Every repeated number has consistent scope, status, date, and supporting evidence |
| P0 | Make role fit clear | First screen connects technical delivery, customer/product ownership, and leadership; actual job title stays accurate |
| P1 | Make Skills visible | Homepage summary and navigation link lead to capability groups with project evidence and level of use |
| P1 | Improve project summaries | Each shows problem, personal contribution, status, supported result, stack, and evidence link |
| P1 | Add production evidence | Model/hosting choices, eval method, latency/reliability, and operational constraints appear where verified |
| P1 | Strengthen experience | Bullets connect problem → personal decision/action → outcome, including leadership and product tradeoffs |
| P2 | Reduce recruiter friction | Visible resume/contact actions, scannable text, and useful navigation without interacting with the graph |
| P2 | Validate presentation | Check mobile, keyboard navigation, contrast, links, and static export after implementation |

## Claims to reconcile before expanding copy

- Homepage: “200+ MCP tools in production”; stack: “200+ MCP tools reachable.” Connectivity does not establish production use.
- Homepage: “300+ skills”; stack: “105 skills installed, 64 of them the gstack suite.” Establish dates and counting definitions.
- Homepage: “30+ agents built”; stack: “29 agents and workers in my own code, 16 with an LLM.” Separate agents, deterministic workers, and installed subagents.
- Homepage/experience mention approximately 60% savings and 90% work efficiency, while Rysen HQ is described as planned scope, staging verification, and handover. Confirm which system and measurement period produced each outcome.
- Coddle's “1M+ user base” describes a design target in the experience copy; do not imply a measured deployed load without evidence.
- Distinguish current results from historical networking activity, and finite eval-set results from estimated production reliability.

## Project-specific gaps and next evidence to collect

| Project | Existing evidence in portfolio/source | Missing or unclear evidence |
| --- | --- | --- |
| Rysen Learning Centre | Next.js, Prisma, Neon, Groq tool calling, Vercel; 16 admin + 7 educator tools; eight-step cap; 78 tests | Exact model/version and selection rationale; hosting limits; task success and tool errors; p50/p95 response time; token cost; actual adoption and support outcomes |
| Rysen HQ | NestJS, Postgres, Redis/BullMQ, React/Vite, Spaces, Cloudflare Pages; 32 modules planned; 85 staging checks and eight critical findings | Delivered versus planned scope; personal engineering versus verification ownership; source of savings; queue/retry behavior, monitoring, capacity and rollout. Do not force an LLM story onto ordinary software |
| R&D Agent | Python, Moltis gateway, Sheets/Drive; deterministic parser; Groq/OpenRouter language step; 20 tests; explicit rollout limitations | First successful live run; exact model and implemented fallback; gateway failure handling; labelled extraction/flag-quality evaluation; end-to-end latency. Proposed golden-set audit is not a completed benchmark |
| Vault Harness | Approval/spend controls; 219 offline tests; 36/36 eval cases; seven confirmed payments; Nitro explicitly not yet run on AWS | Exact agent model; latency and cost per attempt/completion; eval rubric and coverage; failure/recovery behavior; deployed security boundary versus planned enclave. Preserve synthetic/software-authenticator limitations |
| Networking Agent | Rust MCP, SQLite, Docker, Redis; 56 tools; 21 exercised in call log; historical outreach counts | Model by research/scoring/drafting stage; provider API limits and caching; workflow latency; human approval/rejection; valid-contact and task completion rates; logs and resource limits |
| Moltis contributions | Three merged fixes covering arm64 sandbox, loopback auth, and deployment documentation | Show issue → root cause → patch → validation → operational impact. No evidence reviewed establishes fine-tuning, distributed inference, or model observability ownership here |

## Skills expansion approach

Retain demonstrated MCP, LangGraph, CrewAI, context/tool workflows, deterministic guards, eval sets, and approval controls. Link each to a concrete project. Separate coding tools (Codex/Claude Code), model families, inference providers, serving software, and cloud services.

Treat the owner's requested Hugging Face, AutoGen, Ragas, Presidio, DSPy, LiteLLM, vLLM, Ray, Kubernetes, fine-tuning, and distributed inference as an evidence-collection list until use is confirmed. Describe GCP by actual services and API integrations; “Cloud console” alone does not establish compute operations. AWS Nitro preparation does not establish AWS production operation.

Clarify “cloudflare mod”, “agent lighting”, “fable”, “kimi -3.1”, “groq -4”, “rlmf”, and the intended link between fine-tuning and Moltis. Preserve these terms in planning, not public skills claims.

## Evidence worksheet for the next pass

For each project collect: deployment status/date; personal responsibility; exact model/provider/version per stage; deployment service and resource limits; evaluation dataset/rubric/sample count; baseline and current latency under the same workload; successful tasks/total attempts and window; failure/fallback/escalation rates; token/cloud cost; monitoring tool and trace example; user adoption/business result and measurement source. Use “not measured” or “not applicable” internally where appropriate.

For leadership/product experience collect: team composition and reporting relationships, customer/stakeholder problem, roadmap decision, delivery tradeoff, rollout/training, adoption feedback, and outcome attribution.

Example case-study sentence structure (placeholders, not publishable facts): “I owned [scope] for [users], chose [model/stack] because [constraint], deployed on [service], and improved [metric] from [baseline] to [result] across [sample/window], verified by [artifact].”

## Implementation handoff

Update `../portfolio/lib/content.ts` first, then `app/stack/page.tsx`, `components/TermNav.tsx`, `app/page.tsx`, `app/work/page.tsx`, `components/CaseStudy.tsx`, and experience content as required. Keep project status explicit. Add a resume action using a current, approved public CV, after checking it for private details.

Before generating Pages output, preserve repository documentation: the current build script uses `rsync --delete` and would remove these new Markdown files. No application or deployed content was changed in Part 1.
