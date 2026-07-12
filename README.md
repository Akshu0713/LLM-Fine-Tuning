# 🚀 LLM Fine-Tuning with LoRA on Google Colab (Text-to-SQL)

Fine-tune an open-source Large Language Model using **LoRA (Low-Rank Adaptation)** on a **Text-to-SQL** dataset with **Google Colab GPU**.

This project demonstrates the complete workflow of parameter-efficient fine-tuning (PEFT), allowing a small LLM to generate SQL queries from natural language questions without updating all model parameters.

---

## 📌 Project Overview

Large Language Models are expensive to train from scratch.

Instead of retraining billions of parameters, this project uses **LoRA**, which adds a small number of trainable adapter weights while keeping the original model frozen.

The notebook covers:

- Loading a pre-trained TinyLlama model
- Running inference before fine-tuning
- Preparing a Text-to-SQL dataset
- Fine-tuning using LoRA
- Evaluating the model after training
- Saving LoRA adapters

---

## 🛠 Tech Stack

- Python
- Google Colab
- PyTorch
- Hugging Face Transformers
- PEFT (LoRA)
- TRL (SFTTrainer)
- Datasets
- Accelerate

---

## 🤖 Base Model

**TinyLlama-1.1B-Chat-v1.0**

A lightweight open-source LLM suitable for experimentation and fine-tuning on consumer GPUs.

---

## 📂 Dataset

Dataset used:

**b-mc2/sql-create-context**

The dataset contains:

- Database schema/context
- Natural language question
- Expected SQL query

Example:

**Question**

> Show all employees whose salary is greater than 50,000.

**Expected Output**

```sql
SELECT * FROM employees
WHERE salary > 50000;
```

---

## 📖 Workflow

### 1. Environment Setup

- Install required libraries
- Configure Google Colab GPU

---

### 2. Load Base Model

- Load TinyLlama
- Tokenizer initialization
- FP16 inference

---

### 3. Test Base Model

Evaluate the original model on Text-to-SQL prompts to observe its initial performance.

---

### 4. Dataset Preparation

- Load Text-to-SQL dataset
- Format prompts
- Prepare training samples

---

### 5. Apply LoRA

Attach LoRA adapters to the attention layers using PEFT.

Typical target modules include:

- q_proj
- k_proj
- v_proj
- o_proj

---

### 6. Fine-Tune

Train the model using:

- SFTTrainer
- LoRA adapters
- Small subset of the dataset
- Google Colab GPU

---

### 7. Evaluate

Compare model outputs:

- Before Fine-Tuning
- After Fine-Tuning

Observe improvements in SQL generation quality.

---

### 8. Save Adapters

Save the trained LoRA adapters for later inference or merging with the base model.

---

## 📁 Project Structure

```
LLM_Fine_Tuning_with_LoRA_on_Google_Colab_Text_to_SQL.ipynb
README.md
```

---

## 🚀 Features

- Parameter-Efficient Fine-Tuning (PEFT)
- LoRA implementation
- Google Colab compatible
- Text-to-SQL application
- Before vs After comparison
- Adapter saving
- Beginner-friendly notebook

---

## 💡 Learning Outcomes

This project demonstrates:

- How LoRA works
- PEFT workflow
- Hugging Face model loading
- Prompt formatting
- Dataset preprocessing
- Fine-tuning LLMs
- Evaluating LLM outputs
- Saving and reusing LoRA adapters

---

## 📸 Sample Workflow

```
Natural Language Question
            │
            ▼
      Prompt Formatting
            │
            ▼
      TinyLlama Model
            │
            ▼
       LoRA Fine-Tuning
            │
            ▼
     SQL Query Generation
```

---

## 🎯 Future Improvements

- QLoRA implementation
- Larger datasets
- Multiple SQL benchmarks
- Evaluation metrics
- Streamlit web application
- Model deployment using FastAPI
- RAG + Text-to-SQL pipeline

---

## ⭐ If you found this project useful

Consider giving this repository a ⭐ to support the project!

---

## 👨‍💻 Author

**Akshat Gupta**

AI Engineer | Generative AI | LLMs | Agentic AI | RAG | MCP | Python | LangChain | LangGraph | Hugging Face
