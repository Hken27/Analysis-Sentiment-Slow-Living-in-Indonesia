<div align="center">
    <img src="Img/slowlife.jpg" width="350">
</div>

# <div align="center">**Sentiment Analysis of the *Slow Live* Lifestyle on Twitter (X)**</div>

<p align="center">
The image above illustrates the conceptual framework of the <i>Slow Live</i> lifestyle, which serves as the foundation of this research.
</p>

---

## 📌 Background

The rapid growth of social media, particularly Twitter (X), has created a public space for discussions on various social phenomena, including the emerging trend of the <i>Slow Live</i> lifestyle. This concept emphasizes a more mindful, balanced, and meaningful way of Live amid the fast-paced modern culture.

This study aims to analyze public sentiment toward the <i>Slow Live</i> lifestyle as expressed through tweets.

---

## 🎯 Research Objectives

1. To identify public sentiment toward the <i>Slow Live</i> lifestyle.
2. To classify tweets into four categories: Positive, Negative, Neutral, and Others.
3. To compare the performance of various feature extraction methods and machine learning models.

---

## 🧠 Methodology Overview

- **Data Source**: Twitter (X)
- **Research Stages**:
  - Data Crawling (January 1, 2020 – January 1, 2025)
  - Manual Labeling (Positive, Negative, Neutral, Others)
  - Preprocessing
  - Feature Extraction (BoW, N-gram, TF-IDF, IndoBERTweet)
  - Modeling & Evaluation
- **Experimental Scenarios**:
  - Binary Classification (Others vs Non-Others)
  - Multi-Class Classification (Positive, Negative, Neutral)
  - Multi-Class (Original vs Augmented Data: Positive, Negative, Neutral, Others)

---

## 📊 Experimental Data Distribution

<div align="center">

<table>
<tr>
<td align="center">
<img src="Img/1.png" width="150"><br>
<b>Binary Classification</b><br>
Training data distribution between <i>Others</i> and <i>Non-Others</i>.  
This experiment aims to separate relevant and irrelevant tweets related to the <i>Slow Live</i> topic.
</td>

<td align="center">
<img src="Img/2.png" width="150"><br>
<b>Multi-Class</b><br>
Training data distribution across <i>Positive</i>, <i>Negative</i>, and <i>Neutral</i> categories, excluding the <i>Others</i> class.
</td>

<td align="center">
<img src="Img/3.png" width="150"><br>
<b>Multi-Class (Original Data)</b><br>
Distribution of <i>Positive</i>, <i>Negative</i>, <i>Neutral</i>, and <i>Others</i> classes  
using the original dataset <i>(imbalanced data)</i>.
</td>

<td align="center">
<img src="Img/4.png" width="150"><br>
<b>Multi-Class (Data Augmentation)</b><br>
Distribution after applying <i>Synonym Replacement</i>  
using the <i>XLM-RoBERTa</i> language model to reduce class imbalance.
</td>
</tr>
</table>

</div>

---

## 🔎 Error Analysis of Model Predictions

Below are selected examples of model misclassifications across different experimental scenarios:

| No | Classification Scenario | Sample + True Label | Predicted Label | Analysis |
|----|--------------------------|---------------------|-----------------|----------|
| 1 | **Binary Classification** (Others vs Non-Others) | **Tweet:** @kennyivan wkwkwkwk coba diriset... efek lebaran haji ken slow life dulu… <br> **True Label:** Non-Other (Positive) | Other | The sample contains the keyword *“slow life”*. However, the model failed to understand the implicit sentiment. Although it recognizes the term, it does not capture the positive contextual meaning related to post-holiday relaxation. |
| 2 | **Multi-Class** (Neutral, Positive, Negative) | **Tweet:** Yo.opo se slow Living iku <br> **True Label:** Neutral | Negative | This sentence is a question about *slow living*. The model failed to recognize that the phrase indicates a question rather than a complaint or sarcasm. |
| 3 | **Multi-Class** (Neutral, Positive, Negative, Others) | **Tweet:** slow living tidak berlaku untuk yang hidup dalam tekanan dan tuntutan warga sekitar. <br> **True Label:** Negative | Neutral | The sentence contains clearly negative expressions such as “not applicable,” “pressure,” and “demands.” However, the model interpreted it as a neutral social description. |
| 4 | **Multi-Class** (Neutral, Positive, Negative, Others) | **Tweet:** memang slow living di klaten tidak tergantikan <br> **True Label:** Positive | Negative | The model misinterpreted the phrase “not replaceable” as negative due to focusing solely on the negation word “not.” This indicates difficulty in understanding implicitly positive expressions formed through negation. |

---
