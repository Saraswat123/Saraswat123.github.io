# Portfolio agent instructions

## Purpose and scope

Help Saraswat Das earn recruiter interest for Forward Deployed Engineer (FDE), technical leadership/management, and AI product roles. Make customer problems, personal ownership, shipped outcomes, technical decisions, and leadership easy to assess in a short visit.

The initial task is Part 1: audit the portfolio and establish these instructions. Website implementation is a subsequent task. Read `PORTFOLIO_AUDIT.md` for findings and the prioritized backlog.

## Repository boundaries

- This repository (`Saraswat123/Saraswat123.github.io`) contains generated GitHub Pages output, not the Next.js application source.
- The current source checkout is `../portfolio`, with remote `Saraswat123/portfolio`. Check remotes and status before editing. Preserve existing uncommitted work.
- Implement content and layout in the source repository, then regenerate output. Do not hand-edit compiled HTML, `_next` assets, or React payload files.
- Source facts live in `lib/content.ts`; shared project rendering is `components/CaseStudy.tsx`; relevant routes are `app/page.tsx`, `app/stack/page.tsx`, `app/work/`, and `app/experience/page.tsx`. Navigation is `components/TermNav.tsx`.
- Read the source AGENTS.md, including its installed Next.js documentation requirement, before application changes.
- `../portfolio/scripts/build-pages.sh` builds a temporary static copy, removes API routes, disables the recruiter bot, and syncs output here. Its `rsync --delete` currently deletes non-generated files: preserve this AGENTS.md and PORTFOLIO_AUDIT.md before using it. Do not run the script casually during an audit. `--push` publishes.
- Do not deploy merely to complete a documentation task. Follow the user's authorized scope for commits, pushes, and publication.

## Career positioning and evidence

- Target roles are aspirations, not permission to change historical job titles. Keep actual titles and dates accurate.
- FDE evidence: customer discovery, integration constraints, hands-on implementation, deployment, adoption, support, and measurable customer outcomes.
- Management evidence: team scope, prioritization, stakeholder decisions, mentoring, delivery ownership, and operating results. Distinguish direct reports from cross-functional collaborators.
- AI product evidence: user problem, workflow, success criteria, roadmap tradeoffs, model cost/quality decisions, rollout, and user feedback.
- Saved career notes are useful leads, not proof of every public claim. Confirm against project code, dated reports, approved CV facts, or the owner.
- Never invent model versions, tools used, customer counts, savings, latency improvements, uptime, or success rates. Record unknowns in planning notes; omit unsupported public claims.
- Distinguish built, used, evaluated, learning, planned, staging, and production. Installed tools are not automatically production experience. API use is not self-hosted inference. Prompting is not fine-tuning.
- Preserve explicit limitations: Rysen HQ planned scope is not fully shipped scope; Vault Harness AWS Nitro is prepared, not deployed on AWS; R&D Agent's tested pipeline is not proof of completed live rollout; merged Moltis contributions are not ownership of Moltis or model training there.
- Resolve cross-page contradictions before repeating a claim. Give counts a scope and date.

## Recruiter experience

- Within the first screen, show role positioning, a specific value statement, two or three supported outcomes, selected work, resume, and contact links.
- Provide a visible Skills entry and a concise homepage skills summary. Reuse and improve `/stack` where appropriate; preserve existing URLs.
- Organize skills by capability, with links to projects demonstrating each capability. Avoid an undifferentiated logo wall, proficiency percentages, or claiming expertise from installation alone.
- Project summaries should expose problem, personal role, deployment status, result, and core stack before long architecture detail. Keep deeper technical evidence available in case studies.
- Keep ordinary links, readable text, keyboard navigation, mobile layouts, and reduced-motion behavior usable independently of the 3D graph.

## Skills taxonomy requested by the owner

This is a candidate inventory, NOT a verified list of professional experience. Publish items only after establishing evidence and level of use.

| Category | Candidate content |
| --- | --- |
| Agents and orchestration | MCP, tool calling, context engineering, LangGraph, LangChain, CrewAI, AutoGen; Hugging Face agent tooling only if an actual library/use case is established |
| Evaluations and guardrails | Golden datasets, task completion, RAG evaluation, Ragas, LLM-as-judge with human calibration, Presidio, AI governance, approval gates, output/schema checks, prompt-injection testing |
| Model optimization | DSPy, fine-tuning with Hugging Face, dataset curation and held-out evaluation; RLHF only if confirmed and actually practiced |
| Models and inference | Exact model family/version and provider per project; Kimi and Qwen where supported; Groq/OpenRouter as providers, LiteLLM as gateway, vLLM/Ollama as serving tools |
| Development tools | Codex and Claude Code, kept distinct from deployed model/serving infrastructure |
| Cloud and operations | AWS, GCP and named services, Cloudflare, Docker, Ray, Kubernetes, queues, CPU/GPU resources, memory management, distributed inference, observability—only where used |
| Retrieval and data | Ingestion, chunking, embeddings, vector store, retrieval/reranking, citations, freshness, permissions, and retrieval/output-quality evaluation |
| Leadership and AI product | Discovery, product scoping, stakeholder communication, team leadership, rollout, training, adoption, and cost/quality tradeoffs |

Normalize obvious spelling: Hugging Face, CrewAI, AutoGen, Ragas, LLM-as-judge, Presidio, DSPy, LiteLLM, vLLM, Ollama, Kubernetes. Do not silently resolve ambiguous terms: “cloudflare mod”, “agent lighting”, “fable”, “kimi -3.1”, “groq -4”, “rlmf”, or “in moltis”. Confirm intended products/versions and experience before publication. In particular, do not conflate Groq with Grok, RLHF with an evaluation tool, or Moltis contributions with fine-tuning work.

## Required project evidence

Collect the following for each applicable project; use “not applicable” internally when a project has no LLM, RAG, training, or distributed serving layer.

1. Problem, users, constraints, personal role, collaborators, timeline, and deployment status.
2. Stack mapped to function: application, agent framework, model/provider/version, tools, storage, compute, deployment, and monitoring. Explain important choices and alternatives.
3. Model routing: what model handles which step, why, context/token limits, fallback, retries/timeouts, and deterministic versus model-driven stages.
4. RAG: source access, ingestion, chunking, embeddings, indexing, retrieval, reranking, citations, freshness, and failure handling, if used.
5. Resources: CPU/GPU and memory, concurrency, batching, queues, caching, scaling limits, isolation, and any actual Ray/Kubernetes/distributed inference setup. Do not add infrastructure solely as a keyword.
6. Observability: trace IDs across agent/tool/model calls, latency by stage, token usage, errors, cost, dashboards, alerts, and examples of detected failures. Redact sensitive inputs.
7. Evaluation: dataset/sample size, rubric, model and prompt versions, human review, retrieval metrics where applicable, and known failure modes. Test pass counts are not production success probability.
8. Reliability: task completion numerator/denominator, retries, timeout/error rate, fallback rate, human escalation, and uptime or incident history if measured.
9. Performance: before/after p50/p95 end-to-end latency, workload and concurrency, measurement window, environment, and cost per completed task. Separate time-to-first-token from completion latency; never invent a reduction.
10. Business outcome: adoption, time saved, operational cost, revenue/retention where evidenced; distinguish observed, estimated, and target results and explain attribution.
11. Proof: safe code/demo/architecture link, benchmark or eval report, dated measurement, or a clearly described private artifact available on request.

## Implementation and validation

- Keep shared facts centralized in source content so homepage, experience, skills, project pages, and recruiter bot agree.
- Add reusable optional project fields for model/operations/evaluation evidence instead of duplicating inconsistent prose. Do not expose internal TODOs or empty metrics on public pages.
- For documentation-only changes, review links, factual scope, and `git diff --check`; a site build is unnecessary.
- For application changes, run source lint and build, distinguishing pre-existing failures. Validate the actual static Pages export before publication; API routes and server-only features need special handling.
- Verify affected routes, resume/contact links, responsive and keyboard behavior, contrast, and no new console errors. Preserve the intentional plain-anchor navigation unless addressing its documented stale-chunk problem.
- Report what changed, what was verified, missing evidence, and whether publication occurred.
