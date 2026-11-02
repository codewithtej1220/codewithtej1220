<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:08060e,55:2a1458,100:9a5cff&height=210&section=header&text=Amula%20Bhanuteja&fontSize=54&fontColor=ffffff&fontAlignY=36&desc=AI%20Systems%20%7C%20Computer%20Vision%20%7C%20Real-Time%20ML&descAlignY=58&descSize=18&animation=fadeIn" width="100%" alt="Amula Bhanuteja"/>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&duration=3200&pause=900&color=A78BFA&center=true&vCenter=true&width=760&lines=I+build+AI+that+watches+other+AI;Drones+that+see+in+thermal;Promotions+that+respect+inventory;Quantum+circuits+you+can+drag+and+drop;Sub-300ms+pipelines%2C+end+to+end" alt="Typing intro"/>

<p>
  <a href="https://amula-bhanuteja.vercel.app"><img src="https://img.shields.io/badge/Portfolio-9A5CFF?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio"/></a>
  <a href="https://amula-bhanuteja.vercel.app/resume.pdf"><img src="https://img.shields.io/badge/R%C3%A9sum%C3%A9-F0386B?style=for-the-badge&logo=readthedocs&logoColor=white" alt="Résumé"/></a>
  <a href="https://www.linkedin.com/in/bhanuteja-amula-codewithtej1220"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="mailto:bhanuteja.amula@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>
</p>

<p>
  <img src="https://img.shields.io/badge/TCS%20Tech%20Day-Winner%2C%201st%20of%2045%20teams-9A5CFF?style=flat-square" alt="TCS Tech Day winner"/>
  <img src="https://img.shields.io/badge/Smart%20India%20Hackathon%202026-National%20Round-F472B6?style=flat-square" alt="SIH 2026 national round"/>
  <img src="https://img.shields.io/badge/Amazon%20ML%20Challenge-F0.5%20%3D%200.992-FF9900?style=flat-square" alt="Amazon ML Challenge"/>
  <img src="https://img.shields.io/badge/Google%20Cloud-ML%20Specialization-38BDF8?style=flat-square" alt="Google Cloud ML Specialization"/>
</p>

</div>

---

## About Me

```python
class AmulaBhanuteja:
    university = "JNTU Hyderabad, B.Tech in Computer Science & Engineering (2024-2028), CGPA 8.03"
    focus      = ["LLM and agent reliability", "Computer vision", "Real-time systems", "Applied ML for decisions"]
    building   = "Observability and intervention for LLM agents that fail silently"
    wins       = ["TCS Tech Day Hackathon winner, 1st of 45 teams", "Smart India Hackathon 2026 national round"]
    mission    = "HawkEye AI: thermal surveillance aimed at India's border and perimeter security"
    philosophy = "If it can't be measured, traced, or replayed, it isn't finished."
```

I like problems where **the obvious signal lies**. An agent run returns `200 OK` while it loops forever. A thermal frame looks empty while a 20-pixel person walks across it. A discount looks profitable until you count the customers who would have bought anyway. Most of my projects come from that gap: I build the instrument that shows what is really happening, then the system that acts on it.

---

## Featured Projects

### PromoForge (Prometheus)
**AI planner for promotions that respect inventory** &nbsp;|&nbsp; *Winner, 1st of 45 teams at TCS Tech Day, JNTUH* &nbsp;|&nbsp; [Code](https://github.com/codewithtej1220/PromoForge---Prometheus)

**Overview.** A decision-support system that recommends personalized promotions that are profitable and won't run the shelves empty, and explains every recommendation. It covers the whole workflow: ranked recommendations, live what-if simulation, audience targeting, guardrails, multi-team approval and learning from past campaigns. Awarded a Certificate of Appreciation by TCS.

**What makes it different**
- **Uplift modelling, not response modelling:** a T-learner trained on 175K treated/holdout exposures targets *persuadable* customers only, which cuts discount leakage to people who would have bought anyway.
- **Stock-aware economics:** demand is forecast per city and SKU from 90-day sales × festival multipliers × search intent. Inventory is projected forward with inbound purchase orders, and stock-out probability is estimated before a promo is approved.
- **Guardrail Court:** blocked promotions come with the evidence against them and what would make them admissible.
- **Three-lens approval** (Marketing, Merchandising, Store Ops) on one shared readiness score, plus predicted-vs-actual ROI calibration across 134 past campaigns.

| Diwali plan on a synthetic retail twin (8,000 customers) | Result |
|:--|:--:|
| Promotions tested | **1,944** |
| Blocked for margin or stock | **899** |
| Extra profit from the 15 selected | **₹11.6 L** |

**Skills:** `Causal ML / uplift modelling` `Demand forecasting` `scikit-learn` `Pandas` `FastAPI` `Next.js` `Data visualization`

---

### Agent Observability System
**Real-time monitoring and intervention for LLMs and LLM agents** &nbsp;|&nbsp; *Solo build* &nbsp;|&nbsp; [Code](https://github.com/codewithtej1220/agent-observability-system)

**Overview.** Traditional monitoring sees a `200 OK` and normal latency. This system looks at the *behavior* of each run, step by step. It detects infinite loops, tool thrashing, hallucinated tool calls and token waste while the run is still going, then recommends an intervention.

**What makes it different**
- **Three learning paradigms fused:** rule detectors, unsupervised models (IsolationForest, k-NN, HDBSCAN) and supervised gradient boosting on run prefixes, behind an open-set gate. Each covers the others' blind spots: rules and novelty alone flag about a quarter of healthy runs; fused, false positives drop to about 1%.
- **Learned interventions:** a **LinUCB contextual bandit** with guardrails chooses to reflect, retry, escalate, ask a human or stop, earning **41% higher reward** than a fixed playbook. Human review outcomes are fed back as reward.
- **LLM gateway with prompt contracts:** OpenAI, Claude and Gemini through their official SDKs, integrated by changing one base URL. Responses that break schema, PII, refusal or LLM-judge rules can be monitored, blocked or auto-repaired with model fallback.

| Fused engine, 1,500 held-out simulated runs | Precision | Recall | False-positive rate | Caught within 2 steps of onset | Failing-run tokens flagged |
|:--|:--:|:--:|:--:|:--:|:--:|
| **v1** | **97.3%** | **98.1%** | **0.9%** | **89%** | **70%** |

**Skills:** `Anomaly detection` `Contextual bandits` `scikit-learn` `HDBSCAN` `FastAPI` `React` `Python SDK design` `Docker`

---

### HawkEye AI
**Real-time thermal drone surveillance for human and weapon detection** &nbsp;|&nbsp; *Team of 4, JNTUH* &nbsp;|&nbsp; [Code](https://github.com/codewithtej1220/hawkeye-ai)

```
AirSim drone -> thermal capture -> YOLOv11m + SAHI slicing -> threat scoring -> WebSocket -> live dashboard
                                                              Clear | Elevated | High | Critical
```

**Overview.** A project aimed at surveillance for India's border and perimeter security, where people must be spotted at night and from altitude. An autonomous quadcopter, simulated in Unreal Engine and AirSim, detects humans and weapons in thermal imagery at altitudes of 5 to 30 m and streams scored threats to a live dashboard.

**My role.** ML engineer: dataset creation, YOLOv11m training, the dual-model detector and system integration.

**What makes it different**
- **SAHI sliced inference** on top of YOLOv11m recovers tiny, low-resolution targets that full-frame detection misses: **+20% recall** on low-res thermal data.
- **265 ms end-to-end latency** from frame to dashboard (152 ms of it inference) over an async WebSocket pipeline, with **99.998% uptime** in a 48-hour stress test.
- **98.3% human-detection precision** on 80 test images.
- Live feed and on-demand analysis of uploaded photos and videos in one dashboard. A single launcher starts the backend, frontend, simulator and capture pipeline.

**Skills:** `PyTorch` `YOLOv11m` `SAHI` `OpenCV` `CUDA` `AirSim` `Unreal Engine` `FastAPI` `WebSockets` `React`

---

### CredX
**AI-powered corporate credit intelligence for Indian lending** &nbsp;|&nbsp; *Team project* &nbsp;|&nbsp; [Code](https://github.com/codewithtej1220/CredX)

**Overview.** An underwriting workspace that takes a corporate borrower from a pile of PDFs to an explainable, committee-ready credit decision: document extraction, secondary research, fraud screening, scoring, loan sizing and pricing, a Credit Appraisal Memo (CAM) and an analyst copilot.

**What makes it different**
- **Built for Indian lending:** GST forensics (GSTR-2A/2B vs 3B), MCA and NCLT/IBC context, and a fraud graph for circular trading, shared control and shell companies.
- **Explanations that add up:** XGBoost with monotone constraints and exact TreeSHAP, so every score's contributions sum precisely. Validation AUC is **0.88** (Gini 0.77) on a synthetic portfolio.
- **Built for real analyst workflows:** maker-checker overrides, a grounded AI copilot with a local fallback, and CAM export to PDF, DOCX and HTML.
- Tested end to end, from upload through analysis to CAM, with Docker, PostgreSQL, Redis and Celery for production.

**Skills:** `FinTech / credit risk` `Document AI` `Fraud analytics` `XGBoost` `TreeSHAP` `LLM copilot` `FastAPI` `Next.js` `TypeScript` `Docker`

---

### DialogAI
**AI presentation coach and examiner** &nbsp;|&nbsp; [Code](https://github.com/codewithtej1220/DialogAI)

**Overview.** You present to your camera and DialogAI coaches you the way a strict audience would. It analyses what you say, how you say it and how you look while saying it, scores the session, and asks the follow-up questions a real examiner would. A full report arrives in **under 15 seconds**, with **94% accuracy** on landmarks and filler words.

**What makes it different**
- **Three channels analysed together:** speech transcribed with **Whisper**; prosody and filler words from the audio; body language, gaze and gestures through **MediaPipe**; and an NLP clarity score on the content.
- **Examiner mode:** an LLM coach generates context-aware follow-up questions about *your* presentation instead of generic tips.
- **Six practice scenarios** (interview simulation, presentation practice, public speaking, meeting simulation, group discussion and casual conversation), each with its own coaching tips, plus session history, engagement analytics and reports.
- Production-style backend: JWT auth, WebSocket streaming, PostgreSQL with Alembic migrations, Redis and Celery for background analysis, and a multi-threaded pipeline that made video analysis **40% faster**.

**Skills:** `Speech AI (Whisper)` `MediaPipe` `NLP` `LLM coaching` `FastAPI` `WebSockets` `PostgreSQL` `Redis` `Celery` `Next.js` `TypeScript`

---

### Exam-Ethos (OES Pro)
**AI-proctored online examination platform** &nbsp;|&nbsp; *Team project* &nbsp;|&nbsp; [Code](https://github.com/codewithtej1220/Online-Examination-System)

**Overview.** A complete examination platform for Admin, Faculty and Student roles. It generates questions, proctors the exam through video and audio, grades answers and reports results. LLM grading **cut manual grading by 70%** at **92% correlation** with human graders, with responses **under 200 ms**.

**What makes it different**
- **Multi-modal proctoring:** MediaPipe Face Mesh (468 landmarks) for gaze, 3-D head-pose estimation (PnP) for pitch, yaw and roll, **DeepFace / FaceNet** identity checks throughout the exam, and multi-face detection.
- **Audio anomaly detection:** MFCC and spectral features (Librosa) separate normal speech from whispering and ambient noise, and filter out keyboard clicks.
- **RAG-based question generation** from the syllabus with **Gemini** (MCQ, essay, fill-in-the-blank), and semantic essay grading against a rubric.
- Lock-down exam client: tab-switch and copy/paste prevention, fullscreen enforcement and real-time violation logging. Frames are processed concurrently on a thread pool.

**Skills:** `Computer vision` `Audio signal processing` `Biometrics` `RAG` `Gemini` `React` `Node.js` `Express` `MySQL` `Python` `TensorFlow` `RBAC`

---

### QuantaVerse
**An interactive platform to learn, build and simulate quantum algorithms** &nbsp;|&nbsp; *Team project, SIH 2026 national round* &nbsp;|&nbsp; [Live prototype](https://quantaverse-nu.vercel.app/) · [Demo video](https://www.youtube.com/watch?v=-_SifbaUqAA) · [Code](https://github.com/codewithtej1220/quantaversegit)

**Overview.** A free educational resource with eight modules from the qubit to Shor's algorithm, a drag-and-drop circuit sandbox, graded circuit labs, an AI tutor and a student record that tracks progress.

**What makes it different**
- **Runs without a server:** a statevector simulator in the browser executes circuits on its own. The FastAPI service adds real **Qiskit, Cirq and PennyLane** backends when available.
- **Graded on physics, not text:** labs check state fidelity and unitary equivalence, with a hint naming the first difference.
- The **AI tutor explains your actual circuit**. Without a model key, it falls back to a Qiskit read-out instead of failing.
- Zero-config first run: the database is created automatically and every setting has a working default.

**Skills:** `Quantum computing` `Qiskit` `Cirq` `PennyLane` `Next.js` `TypeScript` `FastAPI` `LLM integration`

---

### GraphMind
**Code graphs, step-by-step tracing and empirical Big-O in eight languages** &nbsp;|&nbsp; *Lead developer, team of 3* &nbsp;|&nbsp; [Code](https://github.com/codewithtej1220/GraphMind)

**Overview.** A browser-based code inspector for Python, JavaScript, TypeScript, C, C++, Java, Go and R. It combines a Monaco editor, a React Flow structural graph, a variable and call-stack inspector, and a benchmark view.

**What makes it different**
- **Tracing in all eight languages.** Python uses `sys.settrace`. The other languages are instrumented with Tree-sitter, which inserts a trace hook before each statement *on the same line* so compiler errors keep their original line numbers.
- Each step records the call stack, variables and every array in scope (2-D tables included), and shows which cells the line compares or writes.
- **Measured complexity:** grows the input, counts executed statements and fits O(1) through O(N³) and O(2ᴺ).

**Skills:** `Tree-sitter` `Compilers and instrumentation` `Monaco` `React Flow` `Chart.js` `Next.js` `Docker`

---

### ProjectPulse
**Reviewed, persistent memory for AI coding agents** &nbsp;|&nbsp; *Team project, HackwithHyderabad 3.0* &nbsp;|&nbsp; [Code](https://github.com/codewithtej1220/Project-Pulse)

**Overview.** Every AI coding session starts cold, so the next agent can re-propose an approach the team already rejected. ProjectPulse turns what one session learned into approved project decisions, briefs the next session with only the rules that apply, and checks its output against them.

**What makes it different**
- **A human review gate:** candidate memories need evidence and approval before they become project records, which keeps noise out of the memory.
- **Works over MCP:** a native server gives coding agents the project's memory, with Hindsight as the memory layer.
- **Memory Check:** verifies that an agent's output actually respects the team's decisions.

**Skills:** `MCP` `LLM agents` `Agent memory` `Hindsight` `FastAPI` `React` `three.js`

---

<details>
<summary><b>More projects</b></summary>
<br/>

| Project | Overview | Key techniques |
|:--|:--|:--|
| **Amazon ML Challenge 2026** | Business entity resolution | Blocking plus a LightGBM matcher over 60K+ candidate pairs: F0.5 = 0.992, 99.5% precision, 98.0% recall |
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
| **Languages** | Python, TypeScript, JavaScript, Java, C, C++, SQL, R, Dart, HTML5, CSS3 |
| **Machine Learning & Data Science** | PyTorch, TensorFlow, scikit-learn, XGBoost, LightGBM, SHAP, NumPy, Pandas, gradient boosting, IsolationForest, k-NN, HDBSCAN, uplift modelling (T-learner), demand forecasting |
| **Computer Vision** | YOLOv11m, SAHI sliced inference, OpenCV, MediaPipe (Face Mesh, pose), DeepFace / FaceNet, head-pose estimation (PnP), thermal imagery |
| **Speech & Audio** | OpenAI Whisper, Librosa (MFCC, spectral features), prosody and filler-word analysis |
| **LLMs & Agents** | OpenAI, Anthropic Claude and Google Gemini APIs, MCP, prompt engineering, RAG, LLM-as-judge, agent monitoring, contextual bandits (LinUCB), Hugging Face |
| **Quantum Computing** | Qiskit, Cirq, PennyLane, statevector simulation |
| **Backend & Real-Time** | FastAPI, Node.js, Express, WebSockets, Socket.IO, REST API design, JWT auth, RBAC, Celery, Alembic, SQLAlchemy |
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

- **Winner, TCS Tech Day Hackathon, JNTUH:** 1st of 45 teams with Prometheus (PromoForge); Certificate of Appreciation from TCS
- **National round, Smart India Hackathon 2026:** QuantaVerse
- **Amazon ML Challenge 2026:** business entity resolution, F0.5 = 0.992
- **HackwithHyderabad 3.0:** ProjectPulse, persistent memory for AI coding agents
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

### Let's build what others miss

<a href="https://amula-bhanuteja.vercel.app"><img src="https://img.shields.io/badge/View%20my%20portfolio-9A5CFF?style=for-the-badge&logo=vercel&logoColor=white" alt="View my portfolio"/></a>
<a href="https://www.linkedin.com/in/bhanuteja-amula-codewithtej1220"><img src="https://img.shields.io/badge/Connect%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"/></a>
<a href="mailto:bhanuteja.amula@gmail.com"><img src="https://img.shields.io/badge/bhanuteja.amula%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:9a5cff,45:2a1458,100:08060e&height=120&section=footer" width="100%" alt=""/>

</div>
