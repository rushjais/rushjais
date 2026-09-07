### Hi, I'm Rushil 👋

🎓 **Claremont McKenna College** '29 · Computer Science at **Harvey Mudd College**
🛠️ Backend & infra — retrieval systems, real-time pipelines, sandboxed execution
🔎 Building AI candidate sourcing for an **IT staffing firm**

📫 rushiljaiswal1@gmail.com &nbsp;·&nbsp; [LinkedIn](https://www.linkedin.com/in/rushil-jaiswal-7888a8235/)

<br>

[<img src="https://img.shields.io/badge/%F0%9F%94%8D%20Retrieval%20%26%20Infra-1f6feb?style=for-the-badge" height="38">](#-featured)
&nbsp;
[<img src="https://img.shields.io/badge/%F0%9F%9B%A1%EF%B8%8F%20Adversarial%20AI-6e40c9?style=for-the-badge" height="38">](#-featured)
&nbsp;
[<img src="https://img.shields.io/badge/%F0%9F%93%A6%20PyPI-3775A9?style=for-the-badge&logo=pypi&logoColor=white" height="38">](https://pypi.org/project/pipecat-firewall/)

---

## ⭐️ Featured

**Telos**: AI candidate sourcing over a 31k-resume corpus
[![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)](#) [![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)](#) [![Postgres](https://img.shields.io/badge/Postgres-4169E1?style=flat&logo=postgresql&logoColor=white)](#) [![Pinecone](https://img.shields.io/badge/Pinecone-000000?style=flat)](#) [![Sole author](https://img.shields.io/badge/Sole%20author%20%C2%B7%20253%20commits-1f6feb?style=flat)](#)
🔎 Hybrid retrieval across four lanes — vector, BM25, keyword, structured filter — feeding a reranker that blends cosine similarity with placement history, capped so candidates with no track record still compete on resume quality alone.
🧪 The result I'm proudest of is a negative one. Six signals all put the recruiter's actual picks past rank 250 of 6,105, so nothing we could extract from a resume predicted recruiter choice. The honest reframing became *"2,057 qualified, 70% cold and 30% with prior contact — sort by that"* rather than a top-10 we couldn't justify.
🐛 Found a `us_only=True` default nobody had chosen that was silently discarding **36% of all recruiter submissions** — and it did its worst damage on exactly the technical requisitions where retrieval already looked weakest.
📊 Ranker changes score offline against frozen pools and a human-labeled set (BAD@k / recall@k, holdout split), so a change is evaluated without re-calling the LLM.

&nbsp;

**pipecat-firewall**: a drop-in security firewall for Pipecat voice agents
[![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)](#) [![PyPI](https://img.shields.io/badge/pip%20install%20pipecat--firewall-3775A9?style=flat&logo=pypi&logoColor=white)](https://pypi.org/project/pipecat-firewall/) [![CI](https://img.shields.io/badge/CI-2ea043?style=flat&logo=githubactions&logoColor=white)](#) [![MIT](https://img.shields.io/badge/MIT-yellow?style=flat)](#)
🛡️ Reads each caller turn and blocks, flags, or redacts prompt injection, PII extraction, and policy-override pressure *before* the LLM runs — a blocked turn never reaches the model, so there's no prompt left to argue with and you don't pay for the call.
⚡ Detectors are deliberately small and deterministic: no API key, no extra model call, microseconds on clean turns. Refusals are canned replies that bypass the LLM entirely.
📦 Pinned `<1.0` against the `pipecat-ai` frame API after testing across 0.0.98–0.0.108 — 1.x restructures frames, so the cap is deliberate rather than neglect.

&nbsp;

**Goodhart**: an autoresearch loop that hardens RL verifiers against reward hacking
[![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)](#) [![Anthropic](https://img.shields.io/badge/Anthropic-191919?style=flat&logo=anthropic&logoColor=white)](#) [![WebSocket](https://img.shields.io/badge/WebSocket-5865F2?style=flat)](#) [![34 of 127 commits](https://img.shields.io/badge/34%20%2F%20127%20commits%20%C2%B7%20serving%20layer-1f6feb?style=flat)](#) [![Repository](https://img.shields.io/badge/Repository-6e40c9?style=flat&logo=github&logoColor=white)](https://github.com/rushjais/Goodhart)
🎯 A breach is a solution that **passes the grader and fails a held-out oracle**. A red swarm discovers them, a green team patches the grader, and a regression gate accepts a patch only if the breach now fails *and* the gold solution still passes — so over-tightening surfaces as friendly fire instead of a win.
🔒 The seed exploit list is empty and an anti-theater check enforces it, so every breach was genuinely discovered. Grader and oracle never share a test case, and no LLM sits in the verdict path — every verdict is a sandboxed subprocess parsed from JUnit XML, never exit codes.
🔧 I built the serving layer: the event bus, the websocket server, and the 2D/3D dashboard that animates off a 7-event stream — one seam that both the live engine and the recorded replay drive, so the demo can't drift from the real run. The golden run is a genuine recording, not a script.

&nbsp;

**Strata**: real-time AI guidance for plumbing contractors in the field
[![React Native](https://img.shields.io/badge/React_Native-61DAFB?style=flat&logo=react&logoColor=black)](#) [![Expo](https://img.shields.io/badge/Expo-000020?style=flat&logo=expo&logoColor=white)](#) [![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)](#) [![SQLite](https://img.shields.io/badge/SQLite_FTS5-003B57?style=flat&logo=sqlite&logoColor=white)](#) [![Sole author](https://img.shields.io/badge/Sole%20author%20%C2%B7%20311%20commits-1f6feb?style=flat)](#) [![v1.0](https://img.shields.io/badge/v1.0%20shipped%20%C2%B7%20Apr%202026-2ea043?style=flat)](#)
📴 Built for a contractor in a crawl space with no signal: full diagnostic guidance from a local SQLite FTS5 cache offline, with feedback and job summaries queued in an **idempotent outbox** that reconciles on reconnect.
📷 Camera-first diagnosis through GPT-4o Vision walking a hypothesis-elimination flow, plus hold-to-speak voice and a "Hey Strata" wake word for hands-free use.
🧤 The constraints drove the interface: 56px touch targets for gloved hands, 7:1 contrast for direct sunlight, one clear action per screen.

&nbsp;

**Vibecheck**: plain-English security review for AI-assisted founders, with a one-click fix PR
[![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)](#) [![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)](#) [![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat&logo=supabase&logoColor=black)](#) [![Semgrep](https://img.shields.io/badge/Semgrep-1B2B34?style=flat)](#) [![Live](https://img.shields.io/badge/Live%20demo-2ea043?style=flat&logo=vercel&logoColor=white)](https://vibecheck-delta-pink.vercel.app)
🔍 Runs Semgrep, Gitleaks, and OSV over a repo, then translates the raw findings into what's wrong, why it matters in real terms, and a copy-paste fix — for founders who shipped something they can't audit themselves.
🔒 The scan engine never executes the target repo: shallow read-only clone, size and file caps, scanners as bounded subprocesses, clone deleted after.
🚀 GitHub OAuth unlocks private repos, Postgres row-level security isolates every scan, and Claude rewrites the files to open the fix PR.

&nbsp;

**Yaad**: a grounded memory engine for dementia care
[![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)](#) [![LiveKit](https://img.shields.io/badge/LiveKit-1F1F1F?style=flat)](#) [![Pipecat](https://img.shields.io/badge/Pipecat-5865F2?style=flat)](#) [![Voice agent lead](https://img.shields.io/badge/Voice%20agent%20lead-1f6feb?style=flat)](#) [![YC](https://img.shields.io/badge/Moss%20%28YC%20F25%29%20%40%20Y%20Combinator-D4A017?style=flat&logo=ycombinator&logoColor=white)](#) [![Repository](https://img.shields.io/badge/Repository-6e40c9?style=flat&logo=github&logoColor=white)](https://github.com/rushjais/Yaad)
🧠 An assistant that invents a detail about someone's family is dangerous, so this one refuses when it can't cite a row — and *"did I take my pills today?"* routes to today's `med_logs` rather than being answered by nearest-neighbor text.
🎙️ I built the voice agent end to end: LiveKit + Pipecat pipeline, VAD tuning and barge-in, Groq Whisper STT, MiniMax TTS, and a dlib face-match server for the greeting path.
🌏 The Hindi path failed silently until I translated the query to English *before* the memory lookup — the memories are stored in English, so retrieving in Hindi matched nothing.

<br>

---

<sub>**Also:** [Sentry](https://github.com/rushjais/Sentry) — a voice agent that patches its own guardrails mid-call: leak a card number to it and it clusters the failure, has Nemotron write new rules, hot-swaps them from a mutable `ActiveConfig`, and refuses the same attack seconds later · [hindsight-extension](https://github.com/rushjais/hindsight-extension) — grades your past predictions against what actually happened, then corrects future advice for your blind spots · [kalshi-iv-research](https://github.com/rushjais/kalshi-iv-research) — Kalshi unemployment markets Granger-cause VIX at a 2-day lead (p=0.024, 222 days), with CPI markets kept as a null control · [tab-memory-agent](https://github.com/rushjais/tab-memory-agent) — persistent intent-level memory for your browser · [intern-tracker](https://github.com/rushjais/intern-tracker) — parses application emails and scores company fit against your real background · [signal](https://github.com/rushjais/signal) — AI-curated daily newsletter on a cron</sub>
