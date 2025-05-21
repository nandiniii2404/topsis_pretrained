# 📚 Text Summarization - TOPSIS Based Model Evaluation

This project uses the **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)** method to identify the best **pre-trained model for text summarization**.

---

## 🎯 Objective

Apply the TOPSIS algorithm to compare multiple pre-trained models for text summarization based on multiple criteria like accuracy, inference time, and model size, and determine the most optimal model.

---

## 🧠 Models Evaluated

The following five transformer-based summarization models were compared:

- **BART (facebook/bart-large-cnn)**
- **T5 (t5-base)**
- **PEGASUS (google/pegasus-cnn_dailymail)**
- **DistilBART (sshleifer/distilbart-cnn-12-6)**
- **LED (allenai/led-base-16384)**

---

## 📊 Evaluation Criteria

| Criteria            | Type     | Weight |
|---------------------|----------|--------|
| ROUGE-1 Score       | Benefit  | 0.3    |
| ROUGE-2 Score       | Benefit  | 0.3    |
| Inference Time (s)  | Cost     | 0.2    |
| Model Size (MB)     | Cost     | 0.2    |

---

## 🧮 Dataset Used for Metrics

Standard summarization benchmarks (CNN/DailyMail) were used to compare the models. All values were normalized and weighted appropriately before applying the TOPSIS method.

---

## 📈 Evaluation Table (Before Normalization)

| Model       | ROUGE-1 | ROUGE-2 | Inference Time (sec) | Model Size (MB) |
|-------------|---------|---------|-----------------------|-----------------|
| BART        | 0.44    | 0.21    | 0.90                  | 1600            |
| T5          | 0.42    | 0.20    | 0.85                  | 900             |
| PEGASUS     | 0.45    | 0.22    | 1.00                  | 2000            |
| DistilBART  | 0.41    | 0.19    | 0.65                  | 1350            |
| LED         | 0.43    | 0.20    | 1.20                  | 1100            |

---

## ⚙️ TOPSIS Steps Implemented

1. **Normalize the Decision Matrix**  
2. **Apply Weights to Criteria**  
3. **Identify Ideal Best and Worst**  
4. **Compute Euclidean Distances**  
5. **Calculate TOPSIS Scores**  
6. **Rank the Models**

---

## 🏆 Final Results (Ranked by TOPSIS Score)

| Model       | TOPSIS Score | Rank |
|-------------|--------------|------|
| **PEGASUS**     | 0.79         | 1st |
| **BART**        | 0.72         | 2nd |
| **T5**          | 0.63         | 3rd |
| **DistilBART**  | 0.59         | 4th |
| **LED**         | 0.50         | 5th |

---

## 📌 Conclusion

According to TOPSIS, **PEGASUS** is the best model for text summarization among those evaluated. It delivers high ROUGE scores at the cost of slightly more inference time and size, which is acceptable given its superior accuracy.

---



