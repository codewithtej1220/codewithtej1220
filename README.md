<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=200&section=header&text=Amula%20Bhanuteja&fontSize=52&fontColor=ffffff&fontAlignY=36&desc=AI%20Systems%20%7C%20Computer%20Vision%20%7C%20Real-Time%20Full-Stack&descAlignY=58&descSize=18&animation=fadeIn" width="100%" alt="Amula Bhanuteja"/>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&duration=3200&pause=900&color=52D9CA&center=true&vCenter=true&width=760&lines=I+build+AI+that+watches+other+AI;Drones+that+see+in+thermal;Promotions+that+respect+inventory;Quantum+circuits+you+can+drag+and+drop;Sub-300ms+pipelines%2C+end+to+end" alt="Typing intro"/>

<p>
  <a href="https://www.linkedin.com/in/bhanuteja-amula-codewithtej1220"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="mailto:bhanuteja.amula@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a></p>

<p>
  <img src="https://img.shields.io/badge/TCS%20Hackathon%20Winner-Prometheus%20%40%20JNTUH-52D9CA?style=flat-square" alt="TCS Hackathon winner"/>
  <img src="https://img.shields.io/badge/Defense%20Tech-HawkEye%20AI-EAB96A?style=flat-square" alt="HawkEye AI"/>
</p>

</div>

---

## About Me

```python
class Bhanuteja:
    university = "JNTUH, B.Tech in Computer Science & Engineering"
    focus      = ["LLM and agent reliability", "Computer vision", "Real-time systems", "Applied ML for decisions"]
    building   = "Observability and intervention for LLM agents that fail silently"
    wins       = ["Prometheus, TCS Hackathon winner at JNTUH"]
    mission    = "HawkEye AI: autonomous thermal surveillance for India's defense systems"
    philosophy = "If it can't be measured, traced, or replayed, it isn't finished."
```

I like problems where **the obvious signal lies**. An agent run returns `200 OK` while it loops forever. A thermal frame looks empty while a 20-pixel person walks across it. A discount looks profitable until you count the customers who would have bought anyway. Most of my projects come from that gap: I build the instrument that shows what is really happening, then the system that acts on it.

---

## Featured Projects

### Prometheus
**AI planner for promotions that respect inventory** &nbsp;|&nbsp; *TCS Hackathon winner, JNTUH (Retail / E-commerce)*

**Overview.** A decision-support system that recommends personalized promotions that are profitable and won't run the shelves empty, and explains every recommendation. It covers the whole workflow: ranked recommendations, live what-if simulation, audience targeting, guardrails, multi-team approval and learning from past campaigns.

**What makes it different**
- **Uplift modelling, not response modelling:** a T-learner trained on 175K treated/holdout exposures targets *persuadable* customers only, which cuts discount leakage to people who would have bought anyway.
- **Stock-aware economics:** demand is forecast per city and SKU from 90-day sales × festival multipliers × search intent. Inventory is projected forward with inbound purchase orders, and stock-out probability is estimated before a promo is approved.
- **Guardrail Court:** blocked promotions come with the evidence against them and what would make them admissible.
- **Three-lens approval** (Marketing, Merchandising, Store Ops) on one shared readiness score, plus predicted-vs-actual ROI calibration across 134 past campaigns.

**Skills:** `Causal ML / uplift modelling` `Demand forecasting` `scikit-learn` `Pandas` `FastAPI` `Next.js` `Data visualization`

---

### Agent Observability System
**Real-time monitoring and intervention for LLMs and LLM agents**

**Overview.** Traditional monitoring sees a `200 OK` and normal latency. This system looks at the *behavior* of each run, step by step. It detects infinite loops, tool thrashing, hallucinated tool calls and token waste while the run is still going, then recommends an intervention.

**What makes it different**
- **Three learning paradigms fused:** rule detectors, unsupervised models (IsolationForest, k-NN, HDBSCAN) and supervised gradient boosting on run prefixes, behind an open-set gate. Each covers the others' blind spots: alone, they flag a quarter of healthy runs; fused, false positives drop to about 1%.
- **Learned interventions:** a **LinUCB contextual bandit** with guardrails chooses to reflect, retry, escalate, ask a human or stop. Human review outcomes are fed back as reward.
- **LLM gateway with prompt contracts:** OpenAI, Claude and Gemini through their official SDKs, integrated by changing one base URL. Responses that break schema, PII, refusal or LLM-judge rules can be monitored, blocked or auto-repaired with model fallback.

| Fused engine, 1,500 held-out simulated runs | Precision | Recall | False-positive rate | Caught within 2 steps of onset | Failing-run tokens flagged |
|:--|:--:|:--:|:--:|:--:|:--:|
| **v1** | **97.3%** | **98.1%** | **0.9%** | **89%** | **70%** |

**Skills:** `Anomaly detection` `Contextual bandits` `scikit-learn` `HDBSCAN` `FastAPI` `React` `Python SDK design` `Docker`

---

### HawkEye AI
**Real-time thermal drone surveillance for human and weapon detection** &nbsp;|&nbsp; *Independent project, built for India's defense systems*

```
AirSim drone -> thermal capture -> YOLOv11m + SAHI slicing -> threat scoring -> WebSocket -> live dashboard
                                                              Clear | Elevated | High | Critical
```

**Overview.** A solo project I'm building toward surveillance for India's defense systems, such as border and perimeter security, where people must be spotted at night and from altitude. An autonomous quadcopter, simulated in Unreal Engine and AirSim, detects humans and weapons in thermal imagery at altitudes of 5 to 30 m and streams scored threats to a live dashboard.

**What makes it different**
- **SAHI sliced inference** on top of YOLOv11m recovers tiny, low-resolution targets that full-frame detection misses: **+20% recall** on low-res thermal data.
- **265 ms end-to-end latency** from frame to dashboard (152 ms of it inference) over an async WebSocket pipeline.
- Live feed and on-demand analysis of uploaded photos and videos in one dashboard. A single launcher starts the backend, frontend, simulator and capture pipeline.

**Skills:** `PyTorch` `YOLOv11m` `SAHI` `OpenCV` `CUDA` `AirSim` `Unreal Engine` `FastAPI` `WebSockets` `React`

---

### CredX
**AI-powered corporate credit intelligence for Indian underwriting teams**

**Overview.** An underwriting workspace that takes a borrower from uploaded documents to a credit decision. One modular backend covers document ingestion, company research, fraud screening, explainable scoring, Credit Appraisal Memo (CAM) generation and an analyst copilot.

**What makes it different**
- **Built for Indian lending:** extraction and fraud rules for India, such as GST mismatch detection and circular-trading watch rules, rather than generic credit-scoring heuristics.
- **Explainability is part of every response:** structured extraction, decision factors, the Five Cs of credit, pricing rationale and fraud alerts are returned together, so an analyst can defend every decision.
- **Built for model upgrades:** the scoring path is transparent and deterministic today, with stable API contracts so XGBoost and SHAP models can be added later without breaking clients.
- Consolidates four earlier prototypes into one modular FastAPI service, with Docker, CI and tests.

**Skills:** `FinTech / credit risk` `Document AI` `Fraud analytics` `Explainable AI` `LLM copilot` `FastAPI` `React` `TypeScript` `Docker` `CI/CD`

---

### DialogAI
**AI presentation coach and examiner**

**Overview.** You present to your camera and DialogAI coaches you the way a strict audience would. It analyses what you say, how you say it and how you look while saying it, scores the session, and asks the follow-up questions a real examiner would.

**What makes it different**
- **Three channels analysed together:** speech transcribed with **Whisper**; prosody and filler words from the audio; body language, gaze and gestures through **MediaPipe**; and an NLP clarity score on the content.
- **Examiner mode:** an LLM coach generates context-aware follow-up questions about *your* presentation instead of generic tips.
- **Six practice scenarios** (interview simulation, presentation practice, public speaking, meeting simulation, group discussion and casual conversation), each with its own coaching tips, plus session history, engagement analytics and reports.
- Production-style backend: JWT auth, WebSocket streaming, PostgreSQL with Alembic migrations, Redis and Celery for background analysis.

**Skills:** `Speech AI (Whisper)` `MediaPipe` `NLP` `LLM coaching` `FastAPI` `WebSockets` `PostgreSQL` `Redis` `Celery` `Next.js` `TypeScript`

---

### OES Pro
**AI-proctored online examination platform**

**Overview.** A complete examination platform for Admin, Faculty and Student roles. It generates questions, proctors the exam through video and audio, grades answers and reports results.

**What makes it different**
- **Multi-modal proctoring:** MediaPipe Face Mesh (468 landmarks) for gaze, 3-D head-pose estimation (PnP) for pitch, yaw and roll, **DeepFace / FaceNet** identity checks throughout the exam, and multi-face detection.
- **Audio anomaly detection:** MFCC and spectral features (Librosa) separate normal speech from whispering and ambient noise, and filter out keyboard clicks.
- **RAG-based question generation** from the syllabus with **Gemini** (MCQ, essay, fill-in-the-blank), and semantic essay grading against a rubric.
- Lock-down exam client: tab-switch and copy/paste prevention, fullscreen enforcement and real-time violation logging. Frames are processed concurrently on a thread pool.

**Skills:** `Computer vision` `Audio signal processing` `Biometrics` `RAG` `Gemini` `Node.js` `Express` `MySQL` `Python` `TensorFlow` `RBAC`

---

### QuantaVerse
**An interactive platform to learn, build and simulate quantum algorithms**

**Overview.** A free educational resource with eight modules from the qubit to Shor's algorithm, a drag-and-drop circuit sandbox, graded circuit labs, an AI tutor and a student record that tracks progress.

**What makes it different**
- **Runs without a server:** a statevector simulator in the browser executes circuits on its own. The FastAPI service adds real **Qiskit, Cirq and PennyLane** backends when available.
- The **AI tutor explains your actual circuit**. Without a model key, it falls back to a Qiskit read-out instead of failing.
- Zero-config first run: the database is created automatically and every setting has a working default.

**Skills:** `Quantum computing` `Qiskit` `Cirq` `PennyLane` `Next.js` `TypeScript` `FastAPI` `LLM integration`

---

### GraphMind
**Code graphs, step-by-step tracing and empirical Big-O in eight languages**

**Overview.** A browser-based code inspector for Python, JavaScript, TypeScript, C, C++, Java, Go and R. It combines a Monaco editor, a React Flow structural graph, a variable and call-stack inspector, and a benchmark view.

**What makes it different**
- **Tracing in all eight languages.** Python uses `sys.settrace`. The other languages are instrumented with Tree-sitter, which inserts a trace hook before each statement *on the same line* so compiler errors keep their original line numbers.
- Each step records the call stack, variables and every array in scope (2-D tables included), and shows which cells the line compares or writes.
- **Measured complexity:** grows the input, counts executed statements and fits O(1) through O(N³) and O(2ᴺ).

**Skills:** `Tree-sitter` `Compilers and instrumentation` `Monaco` `React Flow` `Chart.js` `Next.js` `Docker`

---

<details>
<summary><b>More projects</b></summary>
<br/>

| Project | Overview | Key techniques |
|:--|:--|:--|
| **MoodSync** | Mood-aware, room-synced music | NLP emotion classification; shared WebSocket rooms whose queue follows the group's mood |
| **Human Healthcare Hub** | Conversational mental-health space | Chat flow driven by sentiment and context |

</details>

---

## Tech Stack

<div align="center">

<img src="https://skillicons.dev/icons?i=py,ts,js,java,c,cpp,dart,flutter&theme=dark" alt="Languages"/><br/>
<img src="https://skillicons.dev/icons?i=pytorch,tensorflow,sklearn,opencv,fastapi,nodejs,express,react,nextjs&theme=dark" alt="Frameworks"/><br/>
<img src="https://skillicons.dev/icons?i=postgres,mysql,sqlite,redis,docker,githubactions,jenkins,vercel,unreal&theme=dark" alt="Data and DevOps"/>

</div>

| Area | Technologies |
|:--|:--|
| **Languages** | Python, TypeScript, JavaScript, Java, C, C++, SQL, Dart, HTML5, CSS3 |
| **Machine Learning & Data Science** | PyTorch, TensorFlow, scikit-learn, XGBoost, SHAP, NumPy, Pandas, gradient boosting, IsolationForest, k-NN, HDBSCAN, uplift modelling (T-learner), demand forecasting |
| **Computer Vision** | YOLOv11m, SAHI sliced inference, OpenCV, MediaPipe (Face Mesh, pose), DeepFace / FaceNet, head-pose estimation (PnP), thermal imagery |
| **Speech & Audio** | OpenAI Whisper, Librosa (MFCC, spectral features), prosody and filler-word analysis |
| **LLMs & Agents** | OpenAI, Anthropic Claude and Google Gemini APIs, prompt engineering, RAG, LLM-as-judge, agent monitoring, contextual bandits (LinUCB), Hugging Face |
| **Quantum Computing** | Qiskit, Cirq, PennyLane, statevector simulation |
| **Backend & Real-Time** | FastAPI, Node.js, Express, WebSockets, REST API design, JWT auth, RBAC, Celery, Alembic, SQLAlchemy |
| **Databases** | PostgreSQL, MySQL, SQLite, Redis |
| **Frontend** | React, Next.js, TypeScript, Tailwind CSS, shadcn/ui, three.js, Monaco Editor, React Flow, Chart.js, Vite, Flutter |
| **Developer Tooling & Compilers** | Tree-sitter parsing and code instrumentation |
| **DevOps & Cloud** | Docker, Docker Compose, GitHub Actions, Jenkins, Render, Vercel, Google Cloud (Vertex AI, BigQuery) |
| **Simulation & Hardware** | Unreal Engine, Microsoft AirSim, NVIDIA CUDA |
| **Tools** | Git, GitHub, VS Code, Google Colab, Jupyter, Anaconda, PowerShell |

---

## How I Build

| Principle | In practice |
|:--|:--|
| **Latency is a feature** | Async pipelines and WebSocket streaming end to end; HawkEye stays under 300 ms from frame to dashboard. |
| **Measure before you claim** | Held-out evaluation sets, precision/recall/FPR tables and predicted-vs-actual calibration. Numbers come with the method used to get them. |
| **Fallbacks everywhere** | In-browser simulation when the API is down, a Qiskit read-out when the LLM key is missing, model fallback when a contract fails. |
| **One-command onboarding** | Docker Compose, launch scripts and defaults that work out of the box. A reviewer shouldn't need a call with me to run my code. |
| **Structure and safety** | RBAC, schema-validated contracts, PII checks and indexed relational schemas. |

---

## Achievements & Certifications

- **TCS Hackathon Winner, JNTUH:** Prometheus, AI promotion and inventory planner
- **Google Cloud, Machine Learning Specialization:** Vertex AI pipelines, BigQuery
- **Generative AI Learning Certification:** prompt engineering, LLM tuning, agentic loops
- **Competitive programming** on LeetCode: data structures and algorithmic optimization

---

## Currently

- Upgrading **HawkEye AI**'s detection methods for **distant people**: targets only a few pixels tall in thermal frames from high altitude, the hardest case for border and perimeter surveillance
- Taking the agent-observability engine from simulated runs to **real production agent traces**
- Expanding **QuantaVerse** with more graded labs and noise-model simulation
- Reading about **open-set anomaly detection**, **contextual bandits** and **small-object detection in aerial imagery**
- **Open to** ML and AI-systems internships, research collaborations and hackathon teams

---

<div align="center">

### Let's build something that measures itself

<a href="https://www.linkedin.com/in/bhanuteja-amula-codewithtej1220"><img src="https://img.shields.io/badge/Connect%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
<a href="mailto:bhanuteja.amula@gmail.com"><img src="https://img.shields.io/badge/bhanuteja.amula%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white"/></a>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=120&section=footer" width="100%"/>

</div>
