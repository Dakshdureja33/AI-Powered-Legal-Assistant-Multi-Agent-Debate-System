# ⚖️ AI-Powered Legal Assistant: Multi-Agent Debate System

A hybrid AI framework that uses autonomous agents to debate complex legal and policy questions. The system combines rule-based scoring, machine learning, and LLMs to evaluate arguments and deliver transparent, bias-reduced decisions.

---

## 🚀 Features

- **Multi-Agent Debate** — Autonomous Pro and Con agents generate structured arguments (Point → Reason → Impact) in parallel using multi-threading.
- **3-Tier Hybrid Judge** — Rule-based scoring → ML prediction → LLM tiebreaker for conflict resolution.
- **FAISS Vector Memory** — Debates are embedded with `sentence-transformers` and stored in a live FAISS index for semantic retrieval and deduplication.
- **LoRA Fine-Tuning** — Custom-trained lightweight adapter outperforms base models on structure and reasoning depth.
- **SHAP Explainability** — ML predictions are explained using SHAP values for transparency.
- **Streamlit Dashboard** — Interactive UI with live debate arena, RAG search, evaluation metrics, and real-time model comparison.

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| Frontend | Streamlit |
| Vector DB | FAISS |
| Embeddings | sentence-transformers |
| ML Model | scikit-learn |
| Fine-Tuning | LoRA (PEFT) |
| Explainability | SHAP |
| Evaluation | BLEU, ROUGE |
| Data | pandas, JSON |
| Concurrency | concurrent.futures |

---

## 📂 Project Structure
├── agents/               # Pro and Con argument generation
├── dataset/              # Training data and feature engineering
├── evaluation/           # BLEU/ROUGE scoring and baseline comparisons
├── finetune/             # LoRA fine-tuning scripts and adapter
├── judge/                # Rule-based judge and LLM tiebreaker
├── ml/                   # ML model for argument prediction
├── orchestrator/         # Core hybrid pipeline
├── vector_db/            # FAISS store and memory management
├── app.py                # Streamlit frontend
└── README.md
---

## ⚙️ How It Works

1. **Input** — User submits a legal or policy question.
2. **Retrieval** — FAISS searches for similar past debates to provide context.
3. **Generation** — Pro and Con agents generate structured arguments in parallel.
4. **Evaluation** — The hybrid judge scores arguments via:
   - Rule-based structural scoring
   - ML pattern prediction
   - LLM tiebreaker (on conflict or near-equal scores)
5. **Memory** — Non-duplicate debates are saved to the FAISS index.
6. **Output** — Winner, scores, reasoning, and SHAP explanation are displayed.

---

## 📊 Evaluation Results

| Metric | Score |
|---|---|
| BLEU | 0.49 |
| ROUGE-1 | 0.66 |
| ROUGE-2 | 0.51 |
| ROUGE-L | 0.60 |

Hybrid pipeline outperformed raw LLM baseline by **3×** on structure and reasoning metrics (3.8/4 vs. 1.2/4).

---

## 🌍 Real-World Application

Designed for **policy decision support** — helps stakeholders analyze complex issues by automating the dialectical process, reducing cognitive bias, and providing a transparent, evidence-driven breakdown of both sides.

---

## ⚠️ Limitations

- Output quality depends heavily on prompt design.
- ML model trained on a synthetic dataset, which may introduce bias.
- No external RAG; agents lack real-time factual grounding.
- BLEU/ROUGE measure lexical overlap, not logical depth.
- Uses lightweight local models due to computational constraints.

---

## 💻 Getting Started

bash
# Clone the repository
git clone https://github.com/your-username/Ai-Powered-Legal-Assistant.git
cd Ai-Powered-Legal-Assistant

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run app.py

---

## 📄 License

This project is licensed under the MIT License.
