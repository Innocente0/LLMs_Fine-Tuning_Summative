# Medical Q&A Assistant  
**Domain-Specific LLM Fine-Tuning with LoRA (TinyLlama + MedQuAD)**

This repository contains a complete end-to-end pipeline for fine-tuning a Large Language Model (LLM) into a **medical question-answering assistant** using **parameter-efficient fine-tuning (LoRA)** on the **MedQuAD** dataset.  

The implementation is designed to run on **Google Colab** with limited GPU resources and includes:

- Data preprocessing for a medical QA dataset  
- 4-bit quantized TinyLlama model loading  
- LoRA-based fine-tuning (PEFT)  
- Evaluation with ROUGE, BLEU, and perplexity  
- Interactive chatbot demo via **Gradio**

> ⚠️ **Disclaimer:** This assistant is for **educational/demo purposes only**. It does **not** provide medical advice, diagnosis, or treatment.

## 1. Project Overview

The goal of this project is to specialize a pre-trained LLM (TinyLlama-1.1B-Chat) for the **healthcare domain**, specifically medical question answering.

General-purpose LLMs can:

- Hallucinate medical facts  
- Provide unsafe or misleading answers  
- Be too generic or off-topic  

By fine-tuning on **MedQuAD**, this project aims to:

- Improve **domain alignment** to medical Q&A  
- Produce **structured, clearer responses**  
- Encourage **safe and conservative behavior**  
- Stay focused on **medical topics only**

## 2. Dataset: MedQuAD

**Dataset:** MedQuAD – Medical Question Answering Dataset (NIH-derived)  

Key characteristics:

- **16,000** original medical Q&A pairs  
- **3,000 cleaned samples** selected for training  
- Columns used:
  - `question`
  - `answer`
  - `focus_area`

### 2.1 Preprocessing Steps

In the notebook, the following preprocessing is applied:

- Remove rows with missing `question` or `answer`  
- Strip extra whitespace and normalize text  
- Remove duplicate Q/A pairs  
- Filter out extremely short entries  
- 3,000 examples for Colab efficiency  

### 2.2 Instruction–Response Formatting

Each example is converted into an instruction-style prompt:

**Instruction:**
[Topic: HIV] What are the symptoms of HIV?

**Response:**
Early HIV symptoms may include fever, fatigue, swollen lymph nodes...

Student: Aline Innocente
Project: Medical Q&A LLM Fine-Tuning Summative Assessment

**This project demonstrates modern LLM fine-tuning practices (LoRA + quantization) applied in healthcare, with clear metrics, safety considerations, and an interactive user experience.**