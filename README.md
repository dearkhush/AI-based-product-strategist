# AI-based-product-strategist

🤖A Hybrid Multi-Agent Sentiment Intelligence Platform🤖

The AI Based Product Strategist is a production-style, real-time AI system designed to process large-scale customer feedback, auto-correct sentiment inconsistencies, and generate clean, business-friendly product insights.

Built using a Hybrid Multi-Agent Architecture, the platform combines the speed of local ML inference with the reasoning capabilities of a cloud-hosted LLM — resulting in faster, more accurate, and cost-efficient sentiment intelligence.

📌 Key Features

🔹 Hybrid Multi-Agent Pipeline

🎯Local Agent (DistilBERT):
Fast, offline 1–5 sentiment scoring with confidence.

🎯Cloud Agent (Qwen 2.5–7B):
Acts as a “Strategist Auditor” to correct rating mistakes and generate 3-word insights.

🎯LangGraph Orchestration:
Controls agent states, conflict detection, and audit flow.

🔹 Real-Time Big Data Integration
    Even though not pushed to the repo yet, the system is designed with:
      -Apache Kafka for high-velocity streaming ingestion
      -PySpark for distributed text preprocessing & ETL

🔹 Streamlit Product Dashboard
    -Clean UI for entering reviews
    -Displays rating, confidence, audit correction, and 3-word product insight
    -Real-time results

🔹 Self-Correcting AI Logic
    -Detects sentiment mismatches
    -Automatically triggers LLM re-evaluation
    -Ensures accuracy and avoids false positives

[ Kafka Stream ] → [ PySpark ETL ] → [ Local DistilBERT ] → Conflict? → [ Cloud Qwen 7B Supervisor ] → [ Sanitization Layer ] → [ Streamlit Insights Dashboard ]

🛠 Tech Stack

🔹AI & NLP
  -DistilBERT (Hugging Face)
  -Qwen 2.5–7B (Cloud LLM Endpoint)
  -PyTorch

🔹Transformers Library
  -Big Data Layer
  -Apache Kafka (for ingestion)
  -PySpark (for preprocessing)

🔹Agentic Workflow
  -LangChain
  -LangGraph

🔹Application Layer
  -Python 3.10+
  -Streamlit

💡AI-based-product-strategist/
│── FinalProject.ipynb         # Main hybrid pipeline (DistilBERT + Qwen + LangGraph)
│── sparkETL.ipynb             # PySpark preprocessing pipeline
│── images/                    # Architecture diagrams
│── README.md                  # Project documentation

⚙️ How It Works (Short Explanation):
1) User enters a text review in Streamlit.
2) Local DistilBERT predicts sentiment + confidence.
3) Negative keywords + high rating → conflict flag.
4) Conflicted reviews sent to Cloud Qwen LLM for correction.
5) Qwen outputs:
  -Corrected rating
  -Three-word heading
6) Regex cleans & formats the output.
7) Dashboard shows final insights.
