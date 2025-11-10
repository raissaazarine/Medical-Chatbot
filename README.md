# 📖 Overview
This project presents the development of a Virtual Medical Assistant powered by Large Language Models (LLM) and Retrieval-Augmented Generation (RAG).

The system is designed to support healthcare professionals in Indonesia by providing accurate, up-to-date, and contextually relevant medical recommendations — addressing the limitations of generic language models that often produce non-clinical or hallucinated outputs.

# 🧩 Background
Conventional LLMs are trained on diverse, global datasets that may not align with Indonesian clinical standards.
They often:
  1. Lack logical medical reasoning
  2. Rely on statistical text patterns
  3. Risk generating inaccurate (“hallucinated”) answers
     
Meanwhile, existing virtual assistants (e.g., Alni, Google Assistant, Siri) show low clinical relevance — a 2021 study found only 29% of responses about postpartum depression met clinical standards.

# 🚀 Solution
To overcome these challenges, this project integrates:
  1. LLM (OpenAI-based): as the core language understanding engine
  2. RAG Pipeline: to fetch domain-specific, verified medical data before generating responses
  3. LangChain Framework: for efficient retrieval, context management, and interaction with external medical databases

# 🎯 Research Objectives
  1. Develop an AI-based virtual assistant that combines LLM and medical databases to deliver relevant, accurate information.
  2. Design an integrated architecture using RAG for external knowledge retrieval.
  3. Evaluate system performance using RAGAS and ROUGE metrics.
  4. Compare LLM performance with vs. without RAG augmentation.

# ⚙️ Methods
  1. Data sources: curated medical guidelines, treatment protocols, and drug information (non-personal, anonymized).
  2. Frameworks: LangChain, Streamlit, FAISS (vector store), and OpenAI API.
  3. Evaluation:
     
     a. RAGAS — Faithfulness, Context Precision, Context Recall, Answer Relevance

     b. ROUGE — linguistic similarity to expert references

# 📊 Results
Successfully deployed a web-based chatbot prototype:
👉 https://medicalchatbot-raissa.streamlit.app
 (the website remains accessible, but the Q&A feature is currently inactive as the API connection has been disabled)

Previously achieved high Answer Relevance (0.9072) and strong faithfulness after integrating the RAG pipeline.

Demonstrated improvement in context recall and accuracy of dosage/treatment recommendations during evaluation.

