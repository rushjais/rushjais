## Hi, I'm Rushil 👋

🎓 Claremont McKenna College '29 · Computer Science at Harvey Mudd
🛠️ Mostly backend and infra — real-time pipelines, sandboxed execution, offline-first sync, event-streamed services
📫 rushiljaiswal1@gmail.com · [LinkedIn](https://www.linkedin.com/in/rushil-jaiswal-7888a8235/)

---

### ⭐️ Featured

**Telos — AI candidate sourcing for an IT staffing firm** *(private, ongoing)*
- 🔎 Hybrid retrieval over a 31k-resume corpus: four lanes (vector, BM25, keyword, structured filter) feeding a reranker that blends cosine similarity with placement history — `outcome_score = (placements / submissions) × avg_tenure`, capped so candidates with no history still compete on resume quality alone.
- 🧪 The result I'm proudest of is a negative one. Six signals — skill-years, total-years, role family, employer type, blended score, cosine-to-JD — all put the recruiter's actual picks past rank 250 of 6,105. Nothing we could extract from a resume predicted recruiter choice, so the honest reframing became "2,057 qualified, 70% cold and 30% with prior contact — sort by that" rather than a top-10 we couldn't justify.
- 🐛 Found a `us_only=True` default nobody had chosen that was silently discarding **36% of all recruiter submissions** (48% on location-unspecified reqs) — and it did its worst damage on exactly the technical requisitions where retrieval already looked weakest.
- 📊 Ranker changes are scored offline against frozen candidate pools and a human-labeled set (BAD@k / recall@k, holdout split), so a change can be evaluated without re-calling the LLM. 33 migrations, multi-tenant Postgres with row-level security.

**[pipecat-firewall](https://pypi.org/project/pipecat-firewall/) — a drop-in security firewall for Pipecat voice agents** · `pip install pipecat-firewall`
- 🛡️ Reads each caller turn and blocks, flags, or redacts prompt injection, PII extraction, and policy-override pressure *before* the LLM runs — a blocked turn never reaches the model, so there's no prompt left to argue with and you don't pay for the call.
- ⚡ Detectors are deliberately small and deterministic: no API key, no extra model call, microseconds on clean turns. Refusals are canned replies that bypass the LLM entirely.
- 📦 Solo. Published to PyPI with CI, and pinned `<1.0` against the pipecat-ai frame API after testing across 0.0.98–0.0.108 — 1.x restructures frames, so the cap is deliberate rather than neglect.

**[Goodhart](https://github.com/rushjais/Goodhart) — an autoresearch loop that hardens RL verifiers against reward hacking**
- 🎯 A breach is a solution that **passes the grader and fails a held-out oracle** (`R=1 ∧ T=0`). A red swarm discovers them, a green team patches the grader, and a regression gate accepts a patch **only if the breach now fails and the gold solution still passes** — so over-tightening surfaces as friendly fire instead of a win.
- 🔒 The seed exploit list is empty (`SEED_LIST = []`) and an anti-theater check enforces it, so every breach was genuinely discovered. Grader and oracle never share a test case, and no LLM sits in the verdict path — every verdict is a sandboxed subprocess parsed from JUnit XML, never exit codes.
- 🔧 I built the serving layer with [@AdvayMonga](https://github.com/AdvayMonga) and [@rayan-arya](https://github.com/rayan-arya): the event bus, the websocket server, and the 2D/3D dashboard that animates off a 7-event stream — one seam the live engine and the recorded replay both drive, so the demo can't drift from the real run. The golden run is a genuine recording, not a script.

**Strata — real-time AI guidance for plumbing contractors in the field** · v1.0 shipped April 2026 *(private)*
- 📴 Built for a contractor in a crawl space with no signal: full diagnostic guidance from a local SQLite FTS5 cache offline, with feedback and job summaries queued in an **idempotent outbox** that reconciles on reconnect.
- 📷 Camera-first diagnosis through GPT-4o Vision walking a hypothesis-elimination flow, plus hold-to-speak voice and a "Hey Strata" wake word for hands-free use.
- 🧤 The constraints drove the UI: 56px touch targets for gloved hands, 7:1 contrast for direct sunlight, one clear CTA per screen. React Native (Expo) over a Python backend.

**[Vibecheck](https://vibecheck-delta-pink.vercel.app) — plain-English security review for AI-assisted founders, with a one-click fix PR**
- 🔍 Runs Semgrep, Gitleaks, and OSV over a repo, then translates raw findings into what's wrong, why it matters in real terms, and a copy-paste fix — for founders who shipped something they can't audit themselves.
- 🔒 The scan engine never executes the target repo: shallow read-only clone, size and file caps, scanners as bounded subprocesses, clone deleted after.
- 🚀 Next.js + FastAPI + Supabase with row-level security, GitHub OAuth for private repos, and Claude rewriting files to open the fix PR.

**[Yaad](https://github.com/rushjais/Yaad) — a grounded memory engine for dementia care** · Conversational AI Hackathon, Moss (YC F25) @ Y Combinator
- 🧠 An assistant that invents a detail about someone's family is dangerous, so this one refuses when it can't cite a row — and "did I take my pills today?" routes to today's `med_logs` rather than being answered by nearest-neighbor text.
- 🎙️ I built the voice agent end to end: LiveKit + Pipecat pipeline, VAD tuning and barge-in, Groq Whisper STT, MiniMax TTS, and a dlib face-match server for the greeting path.
- 🌏 The Hindi beat failed silently until I translated the query to English *before* the memory lookup — the memories are stored in English, so retrieving in Hindi matched nothing. Output goes back out in Devanagari through a Hindi voice.

---

### Also

[Sentry](https://github.com/rushjais/Sentry) — a voice agent that patches its own guardrails mid-call: socially-engineer it into leaking a card number, and it clusters the failure, has Nemotron write new rules, hot-swaps them from a mutable `ActiveConfig`, and refuses the same attack seconds later · [hindsight-extension](https://github.com/rushjais/hindsight-extension) — grades your past predictions against what actually happened, then corrects future advice for your blind spots (YC GStack × GBrain hackathon) · [kalshi-iv-research](https://github.com/rushjais/kalshi-iv-research) — Kalshi unemployment markets Granger-cause VIX at a 2-day lead (p=0.024, 222 days), with CPI markets kept as a null control · [tab-memory-agent](https://github.com/rushjais/tab-memory-agent) — persistent intent-level memory for your browser, mem0 + Cartesia voice · [intern-tracker](https://github.com/rushjais/intern-tracker) — parses application emails and scores company fit against your real background · [signal](https://github.com/rushjais/signal) — AI-curated daily newsletter, RSS → Claude → Resend, on a cron
