<div align="center">
  <img src="assets/banner.svg" alt="Vidit Arora. Agents, RAG and full-stack. Built, deployed, evaluated. Open to SDE and AI/ML internships, remote all year, on-site in summer 2027." width="100%">
</div>

B.Tech Software Engineering student at Delhi Technological University (DTU), class of 2029, CGPA **9.6/10** and Department Rank 3 after two semesters. I build LLM agent systems with LangGraph and run deep learning experiments in Python and PyTorch. My research interest is the security of LLM-based agents.

**Open to:** SDE and AI/ML internships. Remote at any time of year. On-site anywhere in the world for summer 2027, across time zones. I am authorized to work in India and will apply for work authorization in other countries.

[LinkedIn](https://linkedin.com/in/viditarora18) · [Email](mailto:viditarora18@gmail.com) · [Kaggle](https://www.kaggle.com/viditarora18) · [Hugging Face](https://huggingface.co/v1d1tt) · [LeetCode](https://leetcode.com/u/v1d1t/) · New Delhi, India

## What I have shipped

| Project | What it shows |
|---|---|
| [Opening Radar](https://github.com/v1d1tt/opening-radar) · [live](https://opening-radar.vercel.app) | A deployed job finder. Search and Fetch across 5 job boards, browser agents, a ghost-job check, and a resume check against each posting's own requirements. Built solo. |
| [Agentic Deep Research Console](https://github.com/v1d1tt/agentic-deep-research-console) | Multi-agent RAG over **700+** arXiv papers, with a citation verifier, an ablation harness and a Streamlit UI. |
| [Pulse](https://github.com/v1d1tt/social-media-manager) | Five LangGraph agents with a LinUCB bandit for posting time and a circuit breaker that pauses posts when sentiment turns negative. |
| [Mamba-Dexformer](https://github.com/v1d1tt/speech-separator) | Speech separation study with Mamba models: SI-SDR of 1.6 to 4.2 dB, a documented forgetting finding, a Gradio demo. |
| [Pluvial-AI](https://github.com/v1d1tt/Pluvial-AI) (team of 3) | **1st prize**, AIMS x Mireye hackathon. Adversarial agents that cite sampled map points. I proposed the idea and wrote one third of the code. |
| [Vaani-Setu](https://github.com/v1d1tt/Vernacular-Pedagogy) (team) | Offline literacy app for the PALASH programme, on **2 GB** RAM Android tablets. |

## What I can build for you

The first table is finished work. This one lists what that work prepares me for. I have **not** shipped the items in the last column, and I do not claim them as experience. I list them so you can see where I can contribute from day one and where I would learn on the job.

| If you need | Proof I have shipped | What I could build next (not shipped yet) |
|---|---|---|
| **Backend or full-stack SDE** | Opening Radar (Next.js, TypeScript, Vercel). Pulse (FastAPI, PostgreSQL with pgvector, Redis). | Internal tools and APIs with tests and CI. Opening Radar has no automated tests yet. |
| **LLM agent pipelines** | Planner, Retriever, Reflector, Synthesizer and Verifier agents in the Research Console. Five LangGraph agents in Pulse. | An agent that works inside a company's own tools, with a human approval step before any action. |
| **Agent safety and testing** | A citation verifier that removes unsupported claims. A guardrail agent. Agents that never log in or submit (Opening Radar). Research interest in LLM agent security. | A prompt-injection test harness for agents. No publication or results yet. |
| **Evaluation of AI systems** | A 30-question harness with each agent switchable. | Ablation reports and dashboards. The Console harness does not report results yet. |
| **Live web data and automation** | Search, Fetch, Agent and Monitor routes in Opening Radar. | Price, listing or compliance monitors with alerts. |
| **Speech and on-device ML** | Mamba-Dexformer (PyTorch). INT8 ONNX speech models on 2 GB tablets in Vaani-Setu. | A small speech feature that runs on a phone. |
| **Leading and teaching** | Co-Head at AIMS. 20+ ML sessions planned for 100+ juniors. Team Lead at Fresources, for a community of 2,000+ students. | Onboarding material and workshops for a new team. |

## Opening Radar, my newest project

<details open>
<summary>How it works</summary>

[Opening Radar](https://github.com/v1d1tt/opening-radar) finds live job and internship openings and ranks them for one person. The live app is at [opening-radar.vercel.app](https://opening-radar.vercel.app). You set a role, a location, a level, keywords, an optional target company and an optional resume PDF.

1. **Search** finds postings on Greenhouse, Lever, Ashby, Workable and SmartRecruiters at the same time.
2. **Fetch** reads up to 20 postings in parallel. Closed jobs and dead links are dropped. Duplicates are merged.
3. **A live browser agent** reads Internshala, where Fetch only sees marketing text. **A background agent** reads your target company's own careers page.
4. **A ghost-job check** labels each posting "live opening", "check before applying" or "likely ghost job". The rules are talent-pool wording, post age, reposts, thin detail and a missing location. Ghost jobs rank lower.
5. **The Laya decision model** ([open weights](https://huggingface.co/convaiinnovations/laya)) answers typed questions with probabilities, not free text, so it cannot invent a listing. Level and location work as gates: a Berlin job or a VP role cannot outrank a Bangalore internship for an intern search.
6. **Resume fit check.** Laya checks the posting's requirement bullets one by one against your resume.
7. **Application prep.** An agent opens the application form and lists every field. It never types, uploads or submits.

Stack: Next.js, React, TypeScript, Tailwind, Vercel, TinyFish Search, Fetch, Agent and Monitor. Solo build for the TinyFish x DTU workshop, Job Portal / Careers Finder track.

Limits: no automated tests yet. The ranking weights are set by hand and are not benchmarked. If the Laya service is unreachable, the app says so and ranks with fixed rules.

</details>

## More about the other projects

<details>
<summary>Agentic Deep Research Console</summary>

A research assistant over 700+ arXiv papers (2024 to 2026) on LLM agents. A Planner splits a question into searches, a Retriever queries a ChromaDB index, a Reflector critiques the evidence and can trigger a new search, and a Synthesizer writes the answer. A Citation Verifier enforces exact `[arxiv_id]` inline citations and removes claims it cannot support.

The harness runs 30 questions with the Planner, Reflector and Verifier each switchable. The repository documents the harness and does not yet report ablation results. The pipeline resumes from saved state after an interruption. It uses Gemini models and a Streamlit console that shows the execution trace.

</details>

<details>
<summary>Mamba-Dexformer</summary>

A study of separating up to five overlapping speakers with Mamba state-space models. A 1D convolutional encoder, four Mamba blocks and two decoders extract one speaker per pass, trained with OR-PIT loss on a two-to-five-speaker curriculum for 115 epochs.

The reported SI-SDR is 1.63, 3.38, 4.08 and 4.21 dB for two to five speakers. These figures are low in absolute terms. The useful result is the diagnosis: the two-speaker score is the lowest, which the README attributes to catastrophic forgetting under sequential curriculum training, and it proposes mixed-batch training. That control has not been run. I also published the Kaggle dataset [speech-sep-mixtures](https://www.kaggle.com/datasets/viditarora18/speech-sep-mixtures) (LibriMix extended to four and five speakers).

</details>

<details>
<summary>Pulse</summary>

A hackathon team project. I wrote about nine tenths of the code. Five LangGraph agents manage social media posting: Scout finds trends, Strategist picks the posting time with a LinUCB bandit, Copywriter drafts three variants, Guardrail rejects drafts that drift from the brand voice, and Sentinel triages comments and pauses scheduled posts when sentiment turns negative. It uses FastAPI, PostgreSQL with pgvector, Redis and Next.js.

</details>

<details>
<summary>Pluvial-AI (team of 3)</summary>

I proposed the project idea and wrote one third of the code. A teammate committed it to the original repository, so its commit history does not show my account. For a US address, an Investigator and a Skeptic argue and an Adjudicator rules. Every claim must cite a sampled map point, paid data is fetched only after the user confirms a quote, and "unresolved" is an accepted verdict. The team ingested 395,783 Houston 311 complaints; the repository's backtest covers 50 cases (78.6% precision, 30.6% recall) and its NYC negative control covers 10.

</details>

<details>
<summary>Vaani-Setu (team)</summary>

I wrote about half of the code. It teaches literacy and numeracy under the PALASH programme and runs fully offline, using INT8 ONNX models for Hindi speech recognition, translation and speech synthesis.

</details>

<details>
<summary>Richard Feynman Digital Twin</summary>

A RAG agent over Feynman's lectures, books and letters (LangGraph, ChromaDB, Gemini, Streamlit) that can write and run Python to draw diagrams and keeps long-term memory in SQLite. [Repository](https://github.com/v1d1tt/richard-feynman-digital-twin).

</details>

## Research, leadership and competitions

- Research Intern in agentic AI security at the AIMS Lab, Department of Information Technology, DTU, under Prof. D.K. Vishwakarma, from June 2026 to October 2026. No publication yet.
- Co-Head of the Junior Council at AIMS, the AI & ML Society of DTU (a student society, separate from the AIMS Lab). I teach ML to juniors, with 20+ sessions planned for 100+ juniors, I volunteered in event management at the AWS Build with Bharat offline day, and I help organise BITCAMP, an agentic AI workshop and buildathon with TinyFish.
- Team Lead at Fresources @DTU, which runs the software department's academic resources on its site and a community of 2,000+ students.
- Winner (team), BITS at Invictus '26, the DTU tech fest: three stages of competitive programming, CS fundamentals and an algorithmic treasure hunt.
- Top 10 finalist (team), ISRO Bharatiya Antariksh Hackathon 2026, working on SAR and other satellite imagery.
- Rank 2 of 47 in an intra-department Kaggle forecasting competition, and Rank 2 in a campus-wide Kaggle ML competition. Both are campus competitions, not official Kaggle medals.

## Stack

Python (primary), C++, TypeScript, SQL. LangGraph, RAG with ChromaDB, Gemini API, PyTorch, Mamba. FastAPI, Streamlit, Gradio, Next.js, SQLite, PostgreSQL, ONNX Runtime. Git and Linux.
