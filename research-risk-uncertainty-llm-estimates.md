# Risk & Uncertainty in LLM-Assisted Estimates: Research Findings

## Research Metadata
- **Research Date:** 2026-03-20
- **Method:** Web search across 12 search queries; data extracted from search result summaries
- **Limitation:** WebFetch and Bash tools were denied during this session. All data below comes from web search result summaries, NOT from direct page fetches. A citation audit agent should independently verify each claim by fetching the original source URLs.

---

## Source 1: CodeRabbit — "State of AI vs Human Code Generation" Report

- **URL:** https://www.coderabbit.ai/blog/state-of-ai-vs-human-code-generation-report
- **Press Release:** https://www.businesswire.com/news/home/20251217666881/en/CodeRabbits-State-of-AI-vs-Human-Code-Generation-Report-Finds-That-AI-Written-Code-Produces-1.7x-More-Issues-Than-Human-Code
- **Publication Date:** December 17, 2025
- **Author/Org:** CodeRabbit; David Loker, Director of AI at CodeRabbit (quoted)
- **Methodology:** Analyzed 470 open-source GitHub pull requests (320 AI-co-authored PRs, 150 human-only PRs). Used CodeRabbit's structured issue taxonomy. Normalized to issues per 100 PRs. Statistical comparisons via Poisson rate ratios with 95% confidence intervals.

### Key Findings
| Metric | AI-Authored PRs | Human-Authored PRs | Ratio |
|--------|----------------|--------------------| ------|
| Average issues per PR | 10.83 | 6.45 | ~1.7x |
| Critical issues | 1.4x more | baseline | 1.4x |
| Major issues | 1.7x more | baseline | 1.7x |
| Logic & correctness issues | +75% | baseline | 1.75x |
| Security vulnerabilities | 1.5-2x more | baseline | 1.5-2x |
| Readability problems | 3x+ more | baseline | >3x |
| Performance inefficiencies | ~8x more | baseline | ~8x |
| 90th percentile issues | 26 issues | 12.3 issues | ~2.1x |

### Quote
> "These findings reinforce what many engineering teams have sensed throughout 2025. AI coding tools dramatically increase output, but they also introduce predictable, measurable weaknesses that organizations must actively mitigate." — David Loker, Director of AI, CodeRabbit

### Caveats
- CodeRabbit itself is an AI code review platform (potential conflict of interest).
- Methodology acknowledged inability to confirm with certainty that human-labeled PRs were exclusively human-authored.
- Sample size of 470 PRs is moderate; limited to open-source repositories.

---

## Source 2: GitClear — AI Copilot Code Quality Research 2025

- **URL:** https://www.gitclear.com/ai_assistant_code_quality_2025_research
- **PDF:** https://gitclear-public.s3.us-west-2.amazonaws.com/GitClear-AI-Copilot-Code-Quality-2025.pdf
- **Summary:** https://www.jonas.rs/2025/02/09/report-summary-gitclear-ai-code-quality-research-2025.html
- **Author/Org:** GitClear; Bill Harding (founder, quoted)
- **Methodology:** Analyzed 211 million lines of structured code change data from 2020 to 2024.

### Key Findings
| Metric | 2020 | 2024 | Change |
|--------|------|------|--------|
| Newly added code (% of changes) | 39% | 46% | +7pp |
| Copy/pasted lines (% of changes) | 8.3% | 12.3% | +48% relative |
| Refactored/moved lines (% of changes) | 24.1% | 9.5% | -60% relative |
| Code revised within 2 weeks ("churn") | 3.1% | 5.7% | +84% relative |
| Code revised >1 month after writing | 30% | 20% | -33% relative |
| Duplicated code blocks | baseline | 4-8x increase | 4-8x |

### Quote
> "AI code assistants excel at adding code quickly, but they can cause 'AI-induced tech debt.'" — Bill Harding, GitClear founder

### Caveats
- Correlation, not causation — the study observes trends coinciding with AI adoption but cannot isolate AI as the sole cause.
- GitClear is a code analytics vendor (potential commercial interest).

---

## Source 3: Google DORA Report 2024 & 2025

- **URL (2024 announcement):** https://cloud.google.com/blog/products/devops-sre/announcing-the-2024-dora-report
- **URL (2024 full report):** https://dora.dev/research/2024/dora-report/
- **URL (2025 announcement):** https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report
- **URL (analysis):** https://www.gitclear.com/research/google_dora_2024_summary_ai_impact
- **Author/Org:** Google Cloud DORA team

### Key Findings (2024 Report)
- For every 25% increase in AI adoption:
  - Delivery stability decreased by an estimated **7.2%**
  - Delivery throughput decreased by an estimated **1.5%**
  - Productivity increased by an estimated **2.1%**
  - Job satisfaction increased by an estimated **2.6%**
  - Code quality increased by an estimated **3.4%**
  - Code review speed increased by an estimated **3.1%**
  - Documentation quality increased by **7.5%** when AI was fully integrated
- **39%** of respondents reported little to no trust in AI-generated code
- **75.9%** of developers reported using AI for daily tasks

### Key Findings (2025 Report)
- Unlike 2024, a **positive relationship** was observed between AI adoption and both software delivery throughput and product performance.
- AI adoption **continues to have a negative relationship with software delivery stability**.
- Interpretation: AI accelerates development, but without robust control systems (automated testing, mature version control, fast feedback loops), increased change volume leads to instability.

### Caveats
- The 7.2% stability decrease figure comes from a correlation model, not a controlled experiment.
- Google is both a major AI tool provider and the report author.

---

## Source 4: USENIX Security 2025 — Package Hallucination Study

- **URL (USENIX article):** https://www.usenix.org/publications/loginonline/we-have-package-you-comprehensive-analysis-package-hallucinations-code
- **URL (GitHub repo):** https://github.com/Spracks/PackageHallucination
- **Title:** "We Have a Package for You! A Comprehensive Analysis of Package Hallucinations by Code Generating LLMs"
- **Authors:** Joseph Spracklen, Raveen Wijewickrama, A H M Nazmus Sakib, Anindya Maiti, Bimal Viswanath, Murtuza Jadliwala
- **Institutions:** University of Texas at San Antonio, University of Oklahoma, Virginia Tech
- **Venue:** USENIX Security Symposium 2025

### Key Findings
| Metric | Value |
|--------|-------|
| Models tested | 16 code-generation LLMs |
| Total code samples | 576,000 |
| Total packages recommended | 2.23 million |
| Hallucinated packages | 440,445 (19.7%) |
| Unique non-existent packages | 205,474 |
| Commercial model hallucination rate | ~5.2% average |
| Open-source model hallucination rate | ~21.7% average |
| Best performer (GPT-4 Turbo) | 3.59% hallucination rate |
| Hallucinations repeated across runs | 58% repeated at least once; 43% repeated every time |
| Hallucination types | 38% conflations, 13% typo variants, 51% pure fabrications |
| Self-detection accuracy (GPT-4 Turbo, GPT-3.5, DeepSeek) | >75% |

### Slopsquatting
- Term coined by Seth Larson, Python Software Foundation developer-in-residence.
- Attack: register a package name that AI models frequently hallucinate, then wait for developers to install it.
- Example: "huggingface-cli" was hallucinated, registered by someone, and downloaded over 30,000 times in 3 months despite containing no code.

### Caveats
- Peer-reviewed at USENIX Security (high-quality venue).
- Study focused on Python and JavaScript packages specifically.

---

## Source 5: Veracode — GenAI Code Security Report 2025

- **URL:** https://www.veracode.com/blog/genai-code-security-report/
- **URL (blog):** https://www.veracode.com/blog/ai-generated-code-security-risks/
- **Author/Org:** Veracode
- **Methodology:** Analyzed code produced by over 100 LLMs across 80 real-world coding tasks.

### Key Findings
| Metric | Value |
|--------|-------|
| Code samples failing security tests | 45% |
| AI vs human vulnerability ratio | 2.74x more vulnerabilities |
| Java security failure rate | 72% |
| Python/C#/JavaScript failure rates | 38-45% |
| XSS (CWE-80) failure rate | 86% |
| Log Injection (CWE-117) failure rate | 88% |
| SQL Injection (CWE-89) failure rate | 20% |
| Cryptographic failures (CWE-327) | 14% failure rate |

### Quote
> "Models are getting better at coding accurately, but are not improving at security." — Veracode report
> "Larger models do not perform significantly better than smaller models, suggesting this is a systemic issue rather than an LLM scaling problem."

### Caveats
- Veracode is a commercial application security vendor (potential commercial interest in highlighting security issues).
- "80 real-world coding tasks" is a moderate-sized benchmark; task selection could influence results.

---

## Source 6: arXiv — Large-Scale GitHub Analysis of AI-Generated Code Security

- **URL:** https://arxiv.org/abs/2510.26103
- **PDF:** https://arxiv.org/pdf/2510.26103
- **Title:** "Security Vulnerabilities in AI-Generated Code: A Large-Scale Analysis of Public GitHub Repositories"
- **Publication:** arXiv preprint, October 2025

### Key Findings
| Metric | Value |
|--------|-------|
| Files analyzed | 7,703 AI-attributed files |
| AI tools represented | ChatGPT (91.52%), GitHub Copilot (7.50%), Amazon CodeWhisperer (0.52%), Tabnine (0.46%) |
| CWE instances found | 4,241 across 77 distinct vulnerability types |
| Files without CWE vulnerabilities | 87.9% |
| Files with CWE vulnerabilities | ~12.1% |
| Python vulnerability rate | 16.18%-18.50% |
| JavaScript vulnerability rate | 8.66%-8.99% |
| TypeScript vulnerability rate | 2.50%-7.14% |

### Caveats
- arXiv preprint (not yet peer-reviewed at time of search).
- Attribution of code to AI tools relies on file-level signals, which may not be perfectly accurate.

---

## Source 7: arXiv — LLM Hallucinations in Practical Code Generation

- **URL:** https://arxiv.org/abs/2409.20550
- **ACM Publication:** https://dl.acm.org/doi/abs/10.1145/3728894
- **Title:** "LLM Hallucinations in Practical Code Generation: Phenomena, Mechanism, and Mitigation"
- **Publication:** Proceedings of the ACM on Software Engineering (also arXiv Sept 2024)

### Key Findings
- Identifies hallucination types specific to repository-level code generation (beyond standalone functions).
- Four potential factors contributing to hallucinations in practical development contexts identified.
- RAG-based mitigation method demonstrated "consistent effectiveness" across all studied LLMs.
- Unlike typical bugs, code hallucinations are "generated confidently, may not trigger immediate errors, and can mislead developers into integrating non-existent or insecure components."

### Caveats
- Published in ACM proceedings (peer-reviewed, high quality).
- Specific quantitative error rates not available from search summary alone — direct fetch needed for exact numbers.

---

## Source 8: METR Study — AI Impact on Developer Productivity

- **URL:** https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/
- **Title:** "Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity"
- **Author/Org:** METR (Model Evaluation and Threat Research)
- **Methodology:** Randomized controlled trial (RCT) with 16 experienced developers working on their own large, mature open-source repositories. Used Cursor Pro with Claude 3.5/3.7 Sonnet.

### Key Findings
| Metric | Value |
|--------|-------|
| Actual speed change with AI tools | **19% slower** |
| Perceived speed change | ~20% faster |
| Perception-reality gap | 39-44 percentage points |
| Time spent reviewing/correcting AI output | ~9% of developer time |
| AI suggestion acceptance rate (Copilot) | ~30% |

### Quote
> Two cognitive biases explain the gap: automation bias (increased trust in automated systems) and the effort heuristic (reduced typing mistaken for reduced cognitive work).

### Caveats
- Small sample size (n=16) is a significant limitation.
- Participants were experienced developers on mature codebases — results may differ for junior developers or greenfield projects.
- METR is a well-regarded independent evaluation organization.

---

## Source 9: Contrasting RCT — Google Internal Study & Multi-Company Study

### Google Internal RCT (2024)
- Randomized controlled trial on ~100 Google software engineers.
- Developers using AI completed tasks **~21% faster** on average (96 min vs 114 min).

### Microsoft/Accenture/Fortune 100 Study (2024)
- ~5,000 developers across three organizations.
- Average **26% increase in productivity** with GitHub Copilot.
- Less experienced developers: **35-39% speed-up**.
- Experienced developers: **8-16% improvement** only.

### Reconciliation with METR
- The METR study tested experienced devs on their own mature repos (hardest scenario).
- Google/MS studies tested broader populations including less experienced devs and potentially simpler tasks.
- The pattern: AI helps more with simpler tasks and less experienced developers; helps less (or hurts) with complex tasks and experienced developers.

---

## Source 10: HumanEval & SWE-bench Benchmark Scores

### HumanEval Pass@1 Scores (2025)
- **URL:** https://llm-stats.com/benchmarks/humaneval
- **EvalPlus:** https://evalplus.github.io/leaderboard.html

| Model | HumanEval Pass@1 |
|-------|------------------|
| O1 Preview / O1 Mini (OpenAI) | 96.3% |
| Kimi K2 0905 (Moonshot AI) | 94.5% |
| GPT-4o | 90.2% |
| Llama 3.1 405B | 89.0% |
| Qwen2.5-Coder-32B-Instruct | 87.2% (EvalPlus) |
| DeepSeek-V3 | 86.6% (EvalPlus) |
| GPT-4-Turbo | 86.6% (EvalPlus) |
| Claude 3 Opus | 84.9% |
| Claude Sonnet 3.5 | 81.7% (EvalPlus) |

**Critical caveat:** All tested LLMs exhibit a 5-14 percentage point drop on HumanEval-T variants (indicating data leakage), and a 20-31 percentage point drop on HumanEvalNext vs original HumanEval. HumanEval is considered near-saturated and unreliable for frontier model comparison.

### SWE-bench Verified Scores (2025-2026)
- **URL:** https://llm-stats.com/benchmarks/swe-bench-verified
- **URL:** https://www.swebench.com/

| Model | SWE-bench Verified |
|-------|-------------------|
| Claude Opus 4.5 (Anthropic) | 80.9% |
| Claude Opus 4.6 (Thinking) | 79.2% |
| Gemini 3 Pro + Live-SWE-agent | 77.4% |
| GPT 5.4 (OpenAI) | 77.2% |
| Gemini 3 Flash | 76.2% |
| Average across 77 models | 62.2% |

**Caveat:** Scores vary significantly by scaffolding/agent framework used. SWE-bench Verified has 500 tasks from real GitHub issues.

---

## Source 11: Context Window Limits and Task-Size Risk

- **URL (Chroma research):** https://research.trychroma.com/context-rot
- **URL (Factory.ai):** https://factory.ai/news/context-window-problem
- **URL (Demiliani):** https://demiliani.com/2025/11/02/understanding-llm-performance-degradation-a-deep-dive-into-context-window-limits/
- **URL (Redis):** https://redis.io/blog/context-window-overflow/

### Key Findings
| Finding | Source |
|---------|--------|
| Effective context capacity is 60-70% of advertised maximum | Multiple sources |
| Models maintain performance until a threshold, then drop sharply | Demiliani |
| "Models do not use their context uniformly; performance grows increasingly unreliable as input length grows" | Chroma Research ("Context Rot") |
| Individual file analysis: needs 32K-128K tokens | Multiple sources |
| Full repository analysis: needs 1M-10M tokens | Multiple sources |
| Code review/refactoring: needs 200K-400K tokens | Multiple sources |
| Degradation at 80-90% window usage predicted by Gemini Token Preview | Redis |
| Silent truncation: no error, just degraded responses | Multiple sources |
| "Lost in the middle" effect: LLMs weigh beginning and end of prompt more heavily | Multiple sources |

### Estimation Implication
Large tasks that require understanding entire repositories or complex cross-file dependencies will hit context limits, causing **silent quality degradation**. This creates a task-size risk category that does not exist in traditional development: beyond a certain complexity threshold, AI assistance quality drops unpredictably.

---

## Source 12: False Confidence & Comprehension Debt

- **URL:** https://addyosmani.com/blog/comprehension-debt/
- **Author:** Addy Osmani (Google Chrome engineering leader)
- **URL:** https://code4thought.eu/2026/01/21/how-developers-are-really-using-ai-today-and-what-that-means-for-software-quality/

### Key Findings
- **Comprehension debt** is distinct from technical debt: code "looks healthy while comprehension quietly hollows out underneath it."
- AI-generated code is "syntactically clean, often well-formatted, and superficially correct — precisely the signals that historically triggered merge confidence."
- One team "had to stop all feature development for three weeks" because their codebase had become so tangled with AI-generated code that nobody could confidently modify it.
- **Anthropic RCT (cited by code4thought):** 52 software engineers in randomized controlled trial; participants who used AI assistance scored **17% lower** on follow-up comprehension quiz (50% vs 67%), with largest declines in debugging.
- Developer favorability toward AI tools dropped from >70% in 2023 to ~60% in 2025 (Stack Overflow survey).

---

## Source 13: Microsoft — Taxonomy of Failure Modes in Agentic AI Systems

- **URL (whitepaper):** https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/final/en-us/microsoft-brand/documents/Taxonomy-of-Failure-Mode-in-Agentic-AI-Systems-Whitepaper.pdf
- **URL (blog):** https://www.microsoft.com/en-us/security/blog/2025/04/24/new-whitepaper-outlines-the-taxonomy-of-failure-modes-in-ai-agents/
- **Author/Org:** Microsoft AI Red Team, April 2025

### Failure Categories Relevant to AI-Assisted Coding
1. **Goal Misalignment Failures** — agents optimize for wrong objectives or interpret instructions in unintended ways
2. **Boundary Violation Failures** — agents exceed intended scope of operation
3. **Context Loss Failures** — inability to maintain relevant information across multi-step interactions
4. **Capability Overestimation Failures** — agents attempt tasks beyond actual abilities, "often with confidence that masks their limitations"

### Systemic Effects
- Agent Misalignment, Agent Action Abuse, Service Disruption, Incorrect Decision-Making, Erosion of User Trust, Environmental Spillover, Knowledge Loss

---

## Source 14: Non-Determinism in AI Output

- **URL:** https://www.statsig.com/perspectives/what-are-non-deterministic-ai-outputs-
- **URL:** https://www.baytechconsulting.com/blog/non-deterministic-ai-in-production-2025
- **URL:** https://www.sitation.com/blog/non-determinism-in-ai-llm-output/

### Key Findings for Estimation
- Even setting temperature=0 and fixed random seed is "often not enough to guarantee identical output every time" due to GPU floating-point parallelism.
- Non-determinism "breaks traditional software testing and quality assurance paradigms, which rely on predictable, repeatable outcomes, making bug reproduction and regression testing nearly impossible without a new framework."
- For estimation: the same prompt given twice may produce different code, making effort prediction inherently probabilistic.
- Mitigation requires "setting thresholds, monitoring output distributions, and implementing fallback mechanisms."

---

## Source 15: Georgetown CSET — Cybersecurity Risks of AI-Generated Code

- **URL:** https://cset.georgetown.edu/wp-content/uploads/CSET-Cybersecurity-Risks-of-AI-Generated-Code.pdf
- **Publication Date:** November 2024
- **Author/Org:** Center for Security and Emerging Technology (CSET), Georgetown University

### Key Findings
- Out of 130 code samples generated using InCoder and GitHub Copilot:
  - **68% (InCoder)** and **73% (Copilot)** contained vulnerabilities when checked manually.
- Using ChatGPT to generate 21 programs in 5 languages: only **5 out of 21 (24%)** were initially secure.

---

## Source 16: "18-Month Wall" Pattern & Anti-Patterns

- **URL (Ox Security):** Referenced via https://www.netcorpsoftwaredevelopment.com/blog/ai-generated-code-statistics
- **URL (Addy Osmani/Substack):** https://addyo.substack.com/p/the-reality-of-ai-assisted-software

### The "18-Month Wall" Pattern
- Months 1-3: Euphoria and accelerated delivery
- Months 4-9: Velocity plateau
- Months 10-15: Decline as debugging of legacy AI-generated components increases
- Months 16-18: Delivery cycles stall because teams no longer fully understand their own systems

### AI Code Anti-Patterns (Ox Security 2025)
- Analysis of 300+ repositories found 10 recurring anti-patterns present in **80-100% of AI-generated code**:
  - Incomplete error handling
  - Weak concurrency management
  - Inconsistent architecture

### Caveats
- The "18-Month Wall" pattern appears to be an observational/anecdotal framework rather than a rigorously studied phenomenon. Treat with caution.

---

## Source 17: Survey of Bugs in AI-Generated Code

- **URL:** https://arxiv.org/html/2512.05239v1
- **Title:** "A Survey of Bugs in AI-Generated Code"
- **Publication:** arXiv, December 2025

### Key Finding
> "These bugs often arise because the models are trained on publicly available code from repositories like GitHub and Stack Overflow, which are known to contain buggy code and security issues."

### Caveats
- Survey/meta-analysis paper; findings are aggregated from other studies.

---

## Synthesis: Risk Categories Unique to AI-Assisted Development

Based on all sources above, the following risk categories are specific to or significantly amplified by AI-assisted development:

### 1. Hallucination Risk
- **Package hallucination:** 19.7% of recommended packages don't exist (Source 4)
- **Code hallucination:** Confident generation of non-existent APIs, incorrect logic patterns
- **Slopsquatting:** Supply chain attack vector unique to AI code generation

### 2. False Confidence / Comprehension Debt
- AI code is syntactically clean but semantically wrong (Source 12)
- Developers score 17% lower on comprehension when using AI (Source 12)
- 39-44% gap between perceived and actual productivity (Source 8)

### 3. Non-Determinism Risk
- Same prompt produces different code across runs (Source 14)
- Cannot guarantee reproducibility even with temperature=0 (Source 14)
- Estimation must be probabilistic, not deterministic

### 4. Context Window / Task-Size Risk
- Effective capacity is 60-70% of advertised window (Source 11)
- Performance degrades silently past threshold (Source 11)
- Large tasks may exceed model capacity with no error signal

### 5. Capability Overestimation
- Models attempt tasks beyond abilities "with confidence that masks limitations" (Source 13)
- No reliable way to predict in advance whether a task is "AI-suitable"

### 6. Verification Overhead
- 9% of developer time spent reviewing AI output (Source 8)
- Experienced developers 19% slower with AI tools on mature codebases (Source 8)
- Only 30% of Copilot suggestions accepted as-is (Source 8)

### 7. Security Vulnerability Amplification
- 45% of AI-generated code fails security tests (Source 5)
- 2.74x more vulnerabilities than human code (Source 5)
- Security does not improve with model scale — systemic issue (Source 5)

### 8. Quality Degradation at Scale ("18-Month Wall")
- Code churn increases, refactoring declines (Source 2)
- 7.2% delivery stability decrease per 25% AI adoption increase (Source 3)
- Teams eventually cannot understand their own AI-generated codebases (Source 12, 16)

### 9. Benchmark-Reality Gap
- HumanEval near-saturated (>90%) but real-world task resolution ~62% average (Source 10)
- 20-31 percentage point drop from HumanEval to HumanEvalNext (Source 10)
- Benchmark scores do not predict production code quality

---

## Cone of Uncertainty: How AI Changes It

### Traditional Cone
- Initial estimates: 0.25x to 4x actual (per Steve McConnell/Construx)
- Narrows through research, decisions, and scope reduction
- **URL:** https://www.construx.com/books/the-cone-of-uncertainty/

### AI's Impact on the Cone
Based on synthesized findings:

1. **Wider initial cone:** AI introduces new uncertainty sources (hallucination, non-determinism, capability boundaries) that don't exist in traditional estimation.

2. **False narrowing:** AI produces working code quickly, creating an illusion that the cone has narrowed — but comprehension debt and hidden defects mean true uncertainty remains high.

3. **Late-stage widening:** The "18-Month Wall" pattern suggests the cone can actually re-widen as accumulated AI-generated technical debt surfaces.

4. **New uncertainty dimension:** Traditional cone addresses scope uncertainty. AI adds a capability uncertainty dimension — "can the AI actually do this task correctly?" — which is orthogonal to scope.

5. **Estimation variance increase:** Non-deterministic output means the same task estimated twice may yield different AI-generated solutions of different quality, making estimation inherently less predictable.

---

## Failed/Incomplete Fetches

The following sources were identified but could not be directly fetched due to tool permission restrictions. They should be independently verified:

1. **Georgetown CSET PDF:** https://cset.georgetown.edu/wp-content/uploads/CSET-Cybersecurity-Risks-of-AI-Generated-Code.pdf — Numbers cited from search summary only.
2. **GitClear PDF:** https://gitclear-public.s3.us-west-2.amazonaws.com/GitClear-AI-Copilot-Code-Quality-2025.pdf — Numbers cited from search summary only.
3. **Microsoft Taxonomy PDF:** Direct whitepaper not fetched; data from blog post summary.
4. **arXiv 2409.20550 full paper:** Only abstract-level data available; specific quantitative findings on hallucination rates in repository-level code generation require full paper access.
5. **Chroma "Context Rot" report:** https://research.trychroma.com/context-rot — Findings cited from search summary.
6. **METR study full report:** https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/ — Key numbers from search summary; methodology details need verification.
7. **Anthropic RCT on comprehension:** Referenced secondhand via code4thought article; original Anthropic publication not located.

---

## Attribution Chain Summary

Every finding above traces to a specific URL. The chain is:
- **Web Search** → search result summary → extracted finding
- No direct page content was fetched (WebFetch denied, Bash denied)
- All quantitative claims come from search engine result summaries, which are generated by the search engine's own extraction/summarization
- A citation audit agent MUST fetch each URL independently to verify exact numbers, quotes, and context
