# **Topic Modelling of Ukraine Conflict Discourse on Twitter (June 2023)**

This repository contains the full implementation and report for an NLP project analysing public discourse on the Russia–Ukraine conflict using **unsupervised topic modelling**.  
The project applies multiple machine learning techniques to a curated dataset of tweets, comparing their ability to extract meaningful themes from short, noisy social media text.

---

## **📌 Project Overview**

Social media platforms like Twitter provide real‑time insight into public sentiment during major geopolitical events.  
This project investigates **10,000 English‑language tweets** related to the Ukraine conflict (10–14 June 2023) to answer:

> **What dominant themes emerge in Ukraine‑related Twitter discussions, and how effectively can different topic modelling methods capture them?**

The analysis includes:

- Data cleaning & preprocessing  
- Feature extraction (TF‑IDF, transformer embeddings)  
- Multiple topic modelling algorithms  
- Quantitative & qualitative evaluation  
- Visualisation of clusters and topic structure  

---

## **📂 Repository Structure**

```
📁 project-root
│
├── 📄 ICT202-Assignment2-Report.docx     # Final written report
├── 📄 assignment2.py                      # Python code (cleaned, commented)
├── 📄 README.md                           # This file
└── 📁 figures/                            # Topic visualisations & PCA/UMAP plots
```

---

## **🧵 Dataset**

- Source: **Kaggle – Ukraine Conflict Twitter Dataset (2023)**  
- A random sample of **10,000 English tweets** was extracted  
- Preprocessing included:
  - Language filtering  
  - Removing duplicates, URLs, mentions, punctuation  
  - Tokenisation, stopword removal, stemming  
  - Lowercasing and short‑tweet filtering  

These steps ensured a clean, consistent corpus suitable for modelling.

---

## **🧠 Topic Modelling Methods**

The project compares **five** unsupervised methods:

### **1. BERTopic**
- Transformer embeddings + HDBSCAN + c‑TF‑IDF  
- Best semantic coherence  
- Captured major themes:  
  - Kakhovka dam destruction  
  - NATO diplomacy  
  - Counteroffensive updates  
  - US political commentary  

### **2. K‑Means (TF‑IDF)**
- Baseline clustering  
- Full dataset coverage  
- Clear but sometimes mixed clusters  

### **3. DBSCAN**
- Density‑based clustering  
- Identified micro‑clusters and bot‑like repetitive tweets  
- High noise fraction due to sparse TF‑IDF vectors  

### **4. Latent Dirichlet Allocation (LDA)**
- Conceptual baseline  
- Struggled with short tweets  
- Lower topic coherence  

### **5. Fuzzy C‑Means**
- Soft clustering with membership probabilities  
- Revealed overlapping themes  
- Sensitive to sparsity  

---

## **📊 Evaluation Metrics**

### **Topic Coherence (c_v)**

| Model      | Coherence |
|------------|-----------|
| DBSCAN     | 0.875     |
| BERTopic   | 0.619     |
| K‑Means    | 0.504     |

### **Internal Validity Metrics**

Silhouette, Davies‑Bouldin, and Calinski‑Harabasz scores were used to assess cluster structure.  
Each model captured different aspects of the data, reinforcing the value of a multi‑model approach.

---

## **📈 Visualisations**

The repository includes:

- BERTopic top‑word bar charts  
- PCA projections for K‑Means, DBSCAN, LDA  
- UMAP visualisations for BERTopic, Fuzzy C‑Means, DBSCAN  
- Cluster distribution tables  

These visualisations help interpret the thematic structure of the dataset.

---

## **📝 Key Findings**

- Major themes (dam disaster, Bakhmut, NATO, anti‑Putin sentiment) appeared consistently across models.  
- BERTopic produced the most interpretable and semantically rich topics.  
- DBSCAN revealed repetitive or coordinated messaging patterns.  
- Fuzzy C‑Means captured blended themes common in short tweets.  
- LDA was less effective due to tweet length and sparsity.

---

## **🚀 Future Work**

Potential extensions include:

- Temporal topic evolution  
- Sentiment analysis  
- Bot detection  
- User‑level metadata analysis  
- Using UMAP for embedding‑based models  

---

## **📚 References**

All references used in the report are included in the final document.

---

## **👤 Author**

**Manar Ibrahim**  
Murdoch University Dubai  
ICT202 – Machine Learning  

