# TOPSIS-Based Selection of Pretrained Models for Text Classification

This repository implements a **multi-criteria decision-making (MCDM)** approach using **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)** to identify the most suitable **pretrained transformer model** for **text classification**.

Instead of relying on a single metric such as accuracy, the project evaluates models based on **performance, efficiency, and complexity** to provide a balanced and practical ranking.

---

## 📌 Objective

To rank and select the best pretrained NLP model for **sentiment classification** by considering multiple evaluation criteria:
- Accuracy
- Precision
- Recall
- F1-score
- Inference Time
- Model Size

---

## 🧠 Models Evaluated

The following pretrained transformer models from Hugging Face were evaluated:

- `distilbert-base-uncased`
- `bert-base-uncased`
- `roberta-base`
- `albert-base-v2`
- `cardiffnlp/twitter-roberta-base-sentiment`

---

## 📊 Dataset

- **SST-2 (Stanford Sentiment Treebank)**  
- Binary sentiment classification (Positive / Negative)  
- Loaded using Hugging Face `datasets` library

---

## ⚙️ Methodology

1. Load pretrained models and their respective tokenizers  
2. Evaluate models on the SST-2 validation set  
3. Compute evaluation metrics using `sklearn`
4. Measure inference time and model size
5. Construct a decision matrix
6. Apply **TOPSIS** for multi-criteria ranking

---

## 📐 Evaluation Criteria

| Criterion          | Type      |
|-------------------|-----------|
| Accuracy          | Benefit   |
| Precision         | Benefit   |
| Recall            | Benefit   |
| F1 Score          | Benefit   |
| Inference Time    | Cost      |
| Model Size (MB)   | Cost      |

---

## ⚖️ TOPSIS Weights

The following weights were used:

```text
Accuracy        → 0.25
Precision       → 0.15
Recall          → 0.15
F1 Score        → 0.25
Inference Time  → 0.10
Model Size      → 0.10
```

## 🏆 Results Summary

- **ALBERT-base-v2** achieved the highest TOPSIS score due to its strong recall and balanced efficiency.
- **DistilBERT** offered a good trade-off between speed and performance.
- **BERT-base** performed poorly without fine-tuning, highlighting the importance of task adaptation.
- The results demonstrate that **multi-criteria evaluation provides better insights** than relying on accuracy alone.

---

## 📌 Key Observations

- Pretrained models without fine-tuning may underperform on task-specific datasets.
- Lightweight models can outperform larger models when efficiency is considered.
- **TOPSIS** helps identify models that are closest to the ideal solution across all evaluation metrics.

---

## 🛠️ Tech Stack

- Python  
- Hugging Face Transformers  
- Hugging Face Datasets  
- Scikit-learn  
- NumPy  
- Pandas  

---

## 🚀 How to Run

```bash
pip install transformers datasets scikit-learn pandas numpy
