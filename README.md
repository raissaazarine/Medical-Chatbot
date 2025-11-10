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

# ⚙️ Behavior Design: Retrieval vs LLM Fallback

The system is designed with a hybrid knowledge retrieval architecture, combining structured medical databases with the reasoning capability of a Large Language Model (LLM).

When a user asks a question, the workflow is as follows:

        ┌──────────────────────────┐
        │        User Query        │
        └────────────┬─────────────┘
                     │
             (1) Text Embedding
                     │
                     ▼
        ┌──────────────────────────┐
        │  Vector Database (RAG)   │
        │  • Retrieves top-k docs  │
        │  • Computes relevance    │
        └────────────┬─────────────┘
                     │
     ┌───────────────┼────────────────┐
     │ Relevant docs found?           │
     │ (Context Recall > threshold)   │
     └───────────────┬────────────────┘
                     │
          Yes        │                     No
      ┌────────┐     │               ┌──────────────┐
      │ LLM +  │     │               │ Base LLM     │
      │ Context│     │               │ (Fallback)   │
      └────┬───┘     │               └─────┬────────┘
           │         │                     │
           ▼                               ▼  
    Generates context-aware  Generates general explanation
      medical response              with warning


# 📊 Results
 **1. Successfully deployed a web-based chatbot prototype:**   
      👉 https://medicalchatbot-raissa.streamlit.app
       (the website remains accessible, but the Q&A feature is currently inactive as the API connection has been disabled)

<img width="1220" height="666" alt="image" src="https://github.com/user-attachments/assets/6fa2da09-b875-48ba-ac6e-0ece4932710d" />
<img width="1168" height="634" alt="image" src="https://github.com/user-attachments/assets/b4ac3035-1a91-4fa2-b447-be318c1f15b9" />


  **2. Previously achieved high Answer Relevance (0.9072) and strong faithfulness after integrating the RAG pipeline.**
<img width="1134" height="622" alt="image" src="https://github.com/user-attachments/assets/c098613c-ea5f-4c1f-9526-2b8a0a868b2c" />
<img width="760" height="396" alt="image" src="https://github.com/user-attachments/assets/23fcd138-f0dc-4644-9899-eff385398a45" />



  **3. Demonstrated improvement in context recall and accuracy of dosage/treatment recommendations during evaluation.**
<img width="1122" height="592" alt="image" src="https://github.com/user-attachments/assets/080d1f71-f5c8-463c-9f1a-d71e09dc649a" />

  **4. Fallback mode (RAG inactive):**
    If no relevant data are found, the system automatically reverts to the base LLM (OpenAI API) to generate a general medical explanation, displaying a visible warning that the answer is not based on verified medical data.
  <img width="1084" height="404" alt="image" src="https://github.com/user-attachments/assets/d813879b-5fd6-4005-ac7b-74bb18703490" />

