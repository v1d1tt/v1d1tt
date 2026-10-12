# Vidit Arora 🦦

B.Tech Software Engineering student at Delhi Technological University (DTU), class of 2029, CGPA **9.6/10** and Department Rank 3 after two semesters. I build LLM agent systems and run deep learning experiments in Python and PyTorch. I am looking for SDE and AI engineering internships: remote at any time of year, and on-site anywhere in the world for summer 2027, across time zones. I am authorized to work in India and will apply for work authorization in other countries. My research interest is the security of LLM-based agents.

| Project | What it shows |
|---|---|
| [Agentic Deep Research Console](https://github.com/v1d1tt/agentic-deep-research-console) | Multi-agent RAG over **700+** arXiv papers, with a citation verifier, an ablation harness and a Streamlit UI. |
| [Mamba-Dexformer](https://github.com/v1d1tt/speech-separator) | Speech separation study with Mamba models: SI-SDR of 1.6 to 4.2 dB, a documented forgetting finding, a Gradio demo. |
| [Pulse](https://github.com/v1d1tt/social-media-manager) | Five LangGraph agents with a LinUCB bandit for posting time and a circuit breaker that pauses posts when sentiment turns negative. |
| [Pluvial-AI](https://github.com/Rudransh-1508/Pluvial-AI) (team of 3) | **1st prize**, AIMS x Mireye hackathon. Adversarial agents that cite sampled map points. I proposed the idea and wrote one third of the code. |
| [Vaani-Setu](https://github.com/v1d1tt/Vernacular-Pedagogy) (team) | Offline literacy app for the PALASH programme, on **2 GB** RAM Android tablets. |

[LinkedIn](https://linkedin.com/in/viditarora18) · [Email](mailto:viditarora18@gmail.com) · [Kaggle](https://www.kaggle.com/viditarora18) · [Hugging Face](https://huggingface.co/v1d1tt) · [LeetCode](https://leetcode.com/u/v1d1t/) · New Delhi, India

## Projects I built

### [Agentic Deep Research Console](https://github.com/v1d1tt/agentic-deep-research-console)

A research assistant over 700+ arXiv papers (2024 to 2026) on LLM agents. A Planner splits a question into searches, a Retriever queries a ChromaDB index, a Reflector critiques the evidence and can trigger a new search, and a Synthesizer writes the answer. A Citation Verifier enforces exact `[arxiv_id]` inline citations and removes claims it cannot support.

The harness runs 30 questions with the Planner, Reflector and Verifier each switchable. The repository documents the harness and does not yet report ablation results. The pipeline resumes from saved state after an interruption. It uses Gemini models and a Streamlit console that shows the execution trace.

### [Mamba-Dexformer](https://github.com/v1d1tt/speech-separator)

A study of separating up to five overlapping speakers with Mamba state-space models. A 1D convolutional encoder, four Mamba blocks and two decoders extract one speaker per pass, trained with OR-PIT loss on a two-to-five-speaker curriculum for 115 epochs.

The reported SI-SDR is 1.63, 3.38, 4.08 and 4.21 dB for two to five speakers. These figures are low in absolute terms. The useful result is the diagnosis: the two-speaker score is the lowest, which the README attributes to catastrophic forgetting under sequential curriculum training, and it proposes mixed-batch training. That control has not been run. I also published the Kaggle dataset [speech-sep-mixtures](https://www.kaggle.com/datasets/viditarora18/speech-sep-mixtures) (LibriMix extended to four and five speakers).

### [Pulse](https://github.com/v1d1tt/social-media-manager)

A hackathon team project. I wrote about nine tenths of the code. Five LangGraph agents manage social media posting: Scout finds trends, Strategist picks the posting time with a LinUCB bandit, Copywriter drafts three variants, Guardrail rejects drafts that drift from the brand voice, and Sentinel triages comments and pauses scheduled posts when sentiment turns negative. It uses FastAPI, PostgreSQL with pgvector, Redis and Next.js.

### [Richard Feynman Digital Twin](https://github.com/v1d1tt/richard-feynman-digital-twin)

A RAG agent over Feynman's lectures, books and letters (LangGraph, ChromaDB, Gemini, Streamlit) that can write and run Python to draw diagrams and keeps long-term memory in SQLite.

## Team projects

- [Pluvial-AI](https://github.com/Rudransh-1508/Pluvial-AI) is a team of 3. I proposed the project idea and wrote one third of the code. A teammate committed it to the repository, so the commit history does not show my account. For a US address, an Investigator and a Skeptic argue and an Adjudicator rules. Every claim must cite a sampled map point, paid data is fetched only after the user confirms a quote, and "unresolved" is an accepted verdict. The team ingested 395,783 Houston 311 complaints; the repository's backtest covers 50 cases (78.6% precision, 30.6% recall) and its NYC negative control covers 10.
- [Vaani-Setu](https://github.com/v1d1tt/Vernacular-Pedagogy): I wrote about half of the code. It teaches literacy and numeracy under the PALASH programme and runs fully offline, using INT8 ONNX models for Hindi speech recognition, translation and speech synthesis.

## Research, leadership and competitions

- Research Intern in agentic AI security at the AIMS Lab, Department of Information Technology, DTU, under Prof. D.K. Vishwakarma, from June 2026 to October 2026. No publication yet.
- Co-Head of the Junior Council at AIMS, the AI & ML Society of DTU (a student society, separate from the AIMS Lab). I teach ML to juniors, with 20+ sessions planned for 100+ juniors, and I co-organise two hackathons in October 2026: an AWS offline build day that expects 2,500 participants and a TinyFish agentic hackathon that expects 500.
- Technical Lead at Fresources @DTU, which runs the software department's academic resources on its site and a community of 2,000+ students.
- Winner (team), BITS at Invictus '26, the DTU tech fest: three stages of competitive programming, CS fundamentals and an algorithmic treasure hunt.
- Top 10 finalist (team), ISRO Bharatiya Antariksh Hackathon 2026, working on SAR and other satellite imagery.
- Rank 2 of 47 in an intra-department Kaggle forecasting competition, and Rank 2 in a campus-wide Kaggle ML competition. Both are campus competitions, not official Kaggle medals.

## Stack

Python (primary), C++, TypeScript, SQL. PyTorch, Mamba, LangGraph, RAG with ChromaDB, Gemini API. FastAPI, Streamlit, Gradio, Next.js, SQLite, PostgreSQL, ONNX Runtime. Git and Linux.
