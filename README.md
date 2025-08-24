# 🚑 Medicine Data Chatbot — LLM Fine-Tuning Project  

## 📖 Overview  
This project demonstrates how to **fine-tune a Large Language Model (LLM)** on a **medicine knowledge dataset** curated from 1mg and other sources.  
The end goal is a **chatbot** that provides structured answers (uses, side effects, precautions) while respecting safety guardrails.  

The system integrates:  
- Web scraping for data collection  
- Data cleaning & enrichment using Ollama Mistral  
- Fine-tuning Phi-4B with **LoRA/QLoRA** via [Unsloth](https://github.com/unslothai/unsloth)  
- Evaluation & monitoring of outputs  
- Gradio interface for user interaction  

---

## 🎯 Objectives  
- Build a clean medicine knowledge dataset  
- Fine-tune a compact LLM (Phi-4B) with LoRA/QLoRA  
- Run training on a single GPU with 4-bit quantization  
- Provide a simple chatbot UI for domain queries  
- Ensure safety and disclaimers for medical data  

---

## 🛠️ Data Pipeline  

### 1. Scraping  
- Collected medicine data from [1mg.com](https://www.1mg.com/)  
- Automated pagination (fixed bug where “next” was clicked inside detail pages)  
- Extracted: Name, salt, price, uses, side effects  

### 2. Cleaning  
- Removed HTML & duplicates  
- Normalized fields into JSON/CSV  
- Repaired noisy entries using **Ollama Mistral**  

### 3. Format  
- Converted dataset into **instruction-style JSON** for fine-tuning  

### 4. Fine-Tuned the Phi-4B Model 
- Finedtuned the Phi-4B model with the help of unsloth and get a good accuracy

### 5. Made a local ChatBot using Gradio
- Made a Chatbot for user interaction so that any user can go and talk to it.

# Install dependencies
pip install unsloth trl peft accelerate bitsandbytes gradio
