<div align="center">
  <a href="https://linkedin.com/in/viditarora18"><img src="assets/banner.svg" alt="Vidit Arora. Agents, harnesses, skills and agentic RAG. Built, deployed, evaluated. Open to SDE and AI/ML internships, remote all year, on-site in summer 2027." width="100%"></a>
</div>

I am a B.Tech Software Engineering student at Delhi Technological University (DTU), class of 2029, with a CGPA of 9.6/10 and Department Rank 3 after two semesters 🦦. I build LLM agent systems with LangGraph and run deep learning experiments in Python and PyTorch. I also do the engineering around the model: harness, context, prompt and loop engineering, and I write agent skills for my own AI-assisted coding. Using them is how I get better at working with AI. In my projects, system one decision models such as Jev and Laya make the ranking and routing choices that need typed answers with probabilities. My research interest is the security of LLM-based agents.

I am open to SDE and AI/ML internships. Remote work is fine at any time of year, and I can work on-site anywhere in the world for summer 2027, across time zones. I am authorized to work in India and will apply for work authorization in other countries.

[LinkedIn](https://linkedin.com/in/viditarora18) · [Email](mailto:viditarora18@gmail.com) · [Resume](resume.pdf) · [Kaggle](https://www.kaggle.com/viditarora18) · [Hugging Face](https://huggingface.co/v1d1tt) · [Medium](https://medium.com/@v1d1tt) · [LeetCode](https://leetcode.com/u/viditarora/) · New Delhi, India

## What I work on

| Area | Range |
|---|---|
| AI, ML and DL | Computer vision, CNNs, RNNs and sequence models, transformers, audio and speech, image models, knowledge graphs, NLP, LLM agents, RAG (agentic, graph, self and adaptive), decision models (Jev, Laya), generative models, classical ML and forecasting |
| Agent engineering | Harness, context, prompt and loop engineering, agent skills, evaluation harnesses |
| Software engineering | Backend and APIs, full-stack web apps, databases, deployment. Intern and fresher roles now, growing toward senior-level ownership |

The projects below cover LLM agents, RAG, speech and sequence models, on-device ML and full-stack apps.

## Projects

<details>
<summary><b>Agentic Deep Research Console</b>: multi-agent RAG over 700+ arXiv papers, with a citation verifier</summary>

<br>

A research assistant over 700+ arXiv papers (2024 to 2026) on LLM agents. A Planner splits a question into searches, a Retriever queries a ChromaDB index, a Reflector critiques the evidence and can trigger a new search, and a Synthesizer writes the answer. A Citation Verifier enforces exact `[arxiv_id]` inline citations and removes claims it cannot support.

The harness runs 30 questions with the Planner, Reflector and Verifier each switchable. The repository documents the harness but reports no ablation results. The pipeline resumes from saved state after an interruption. It uses Gemini models and a Streamlit console that shows the execution trace.

[Repository](https://github.com/v1d1tt/agentic-deep-research-console)

</details>

<details>
<summary><b>Agent injection recognition</b>: do agents notice a prompt injection in their own reasoning? (archived study)</summary>

<br>

An exploratory study from my research internship at the AIMS Lab. When an agent resists a prompt injection, a benchmark score cannot say whether it spotted the attack or never saw it. I read the agents' own reasoning on two AgentDojo suites, banking and workspace, with three local open-weight models (deepseek-r1:14b, qwen2.5:14b and qwen2.5:7b). I built a rule-based recognition classifier and a tiered compliance signal for it.

In the banking runs no model showed recognition of the injection, and most resisted runs never mentioned the attack. The classifier agrees with my own labels on 60 traces (Cohen's kappa 0.75), but that check is in-sample and I am the only human annotator. The study has one run per scenario, no frontier model, and a file-name bug that changed some banking counts. Zarif et al. (October 2026) ran the same question on 33,000 trajectories, so I archived this study and did not submit it.

[Repository](https://github.com/v1d1tt/agent-injection-recognition)

</details>

<details>
<summary><b>Pulse</b>: five LangGraph agents that plan, write and guard social media posts</summary>

<br>

A hackathon team project. I wrote about nine tenths of the code. Scout finds trends, Strategist picks the posting time with a LinUCB bandit, Copywriter drafts three variants, Guardrail rejects drafts that drift from the brand voice, and Sentinel triages comments and pauses scheduled posts when sentiment turns negative. It uses FastAPI, PostgreSQL with pgvector, Redis and Next.js.

[Repository](https://github.com/v1d1tt/social-media-manager)

</details>

<details>
<summary><b>Pluvial-AI</b>: 1st prize at the AIMS x Mireye hackathon (team of 3)</summary>

<br>

I proposed the project idea and wrote one third of the code. A teammate committed it to the original repository, so its commit history does not show my account. For a US address, an Investigator and a Skeptic argue and an Adjudicator rules. Every claim must cite a sampled map point, paid data is fetched only after the user confirms a quote, and "unresolved" is an accepted verdict. The team ingested 395,783 Houston 311 complaints. The repository's backtest covers 50 cases (78.6% precision, 30.6% recall) and its NYC negative control covers 10.

[Repository](https://github.com/v1d1tt/Pluvial-AI)

</details>

<details>
<summary><b>Mamba-Dexformer</b>: separating up to five overlapping speakers with Mamba models</summary>

<br>

A 1D convolutional encoder, four Mamba blocks and two decoders extract one speaker per pass. Training uses OR-PIT loss on a two-to-five-speaker curriculum for 115 epochs.

The reported SI-SDR is 1.63, 3.38, 4.08 and 4.21 dB for two to five speakers, which is low in absolute terms. The useful result is the diagnosis. The two-speaker score is the lowest, which the README attributes to catastrophic forgetting under sequential curriculum training, and it proposes mixed-batch training. That control has not been run. I also published the Kaggle dataset [speech-sep-mixtures](https://www.kaggle.com/datasets/viditarora18/speech-sep-mixtures) (LibriMix extended to four and five speakers).

[Repository](https://github.com/v1d1tt/speech-separator)

</details>

<details>
<summary><b>Opening Radar</b>: live job and internship finder, ranked by the Laya decision model</summary>

<br>

You set a role, a location, a level, keywords, an optional target company and an optional resume PDF. Opening Radar searches Greenhouse, Lever, Ashby, Workable and SmartRecruiters, reads up to 20 postings in parallel, and drops closed links and duplicates. A browser agent reads Internshala live, and a background agent reads a target company's careers page.

A rule-based check labels each posting a live opening, check before applying, or likely ghost job. It looks at talent-pool wording, post age, reposts, thin detail and a missing location, and ghost jobs rank lower. I used the Laya decision model ([open weights](https://huggingface.co/convaiinnovations/laya)), an open alternative to Jev, for the ranking. It scores role, location and level with probabilities, and checks your resume against each posting's requirement bullets. I serve it behind a Jev-compatible endpoint. Level and location act as gates, so a Berlin job or a VP role cannot outrank a Bangalore internship in an intern search. A separate mode opens the application form and lists its fields. It never types, uploads or submits.

I built it alone for the TinyFish x DTU workshop. The stack is Next.js, React, TypeScript, Tailwind and Vercel, with TinyFish Search, Fetch, Agent and Monitor. It has no automated tests, and the ranking weights are set by hand and not benchmarked. If Laya is unreachable, the app says so and ranks with fixed rules.

[Repository](https://github.com/v1d1tt/opening-radar) · [Live app](https://opening-radar.vercel.app)

</details>

<details>
<summary><b>Vaani-Setu</b>: offline literacy app for 2 GB Android tablets (team)</summary>

<br>

I wrote about half of the code. It teaches literacy and numeracy under the PALASH programme and runs fully offline, using INT8 ONNX models for Hindi speech recognition, translation and speech synthesis.

[Repository](https://github.com/v1d1tt/Vernacular-Pedagogy)

</details>

<details>
<summary><b>Richard Feynman Digital Twin</b>: RAG agent over Feynman's lectures, books and letters</summary>

<br>

Built with LangGraph, ChromaDB, Gemini and Streamlit. It can write and run Python to draw diagrams, and it keeps long-term memory in SQLite.

[Repository](https://github.com/v1d1tt/richard-feynman-digital-twin)

</details>

## Research, leadership and competitions

- Research Intern in agentic AI security at the AIMS Lab, Department of Information Technology, DTU, under Prof. D.K. Vishwakarma, from June 2026 to present. My first study is finished and archived: [Refusal or Incompetence? Measuring Injection Recognition in Agent Chains of Thought](https://github.com/v1d1tt/agent-injection-recognition). No publication as of now.
- Co-Head of the Junior Council at AIMS, the AI & ML Society of DTU (a student society, separate from the AIMS Lab). I teach ML to juniors, with 20+ sessions planned for 100+ juniors, I volunteered in event management at the AWS Build with Bharat offline day, and I help organise BITCAMP, an agentic AI workshop and buildathon with TinyFish.
- Team Lead at Fresources @DTU, which runs the software department's academic resources on its site and a community of 4,000+ students.
- 1st prize (team of 3), AIMS x Mireye internal hackathon, with Pluvial-AI.
- Winner (team), BITS at Invictus '26, the DTU tech fest: three stages of competitive programming, CS fundamentals and an algorithmic treasure hunt.
- Top 10 finalist (team), ISRO Bharatiya Antariksh Hackathon 2026, working on SAR and other satellite imagery.
- Rank 2 of 47 in an intra-department Kaggle forecasting competition, and Rank 2 in a campus-wide Kaggle ML competition. Both are campus competitions, not official Kaggle medals.
- Wrote: [Software 1.0, 2.0, 3.0: Who Is Still at the Table?](https://medium.com/@v1d1tt/software-1-0-2-0-3-0-who-is-still-at-the-table-f92fe3488dfc), a Medium article on Karpathy's three kinds of software, based on his 2017 essay, his 2025 talk and a 2026 conversation.

## Stack

Python (primary), C++, TypeScript, SQL. LangGraph, agent harnesses and skills, RAG with ChromaDB, Jev and Laya decision models, Gemini API, PyTorch, Mamba. FastAPI, Streamlit, Gradio, Next.js, SQLite, PostgreSQL, ONNX Runtime. Git and Linux.
