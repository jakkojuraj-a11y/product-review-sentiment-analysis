
# product-review-sentiment-analysis
# 📊 Sentiment Analysis of Flipkart Product Reviews  
### YONEX MAVIS 350 Nylon Shuttle

---

## 📌 Project Overview
This project implements an **end-to-end Sentiment Analysis system** for Flipkart product reviews of **YONEX MAVIS 350 Nylon Shuttle**.  
The application classifies customer reviews as **Positive** or **Negative**, displays a **confidence score**, highlights **negative keywords**, and provides insights into **customer pain points**.

The trained model is deployed as a **Flask web application** and hosted on **AWS EC2**.

---

## 🎯 Objectives
- Perform sentiment classification on product reviews  
- Display prediction confidence using probability scores  
- Highlight negative keywords for explainability  
- Analyze customer pain points from negative reviews  
- Deploy the application on AWS EC2  

---

## 📂 Dataset Description
- Source: Provided pre-scraped Flipkart dataset  
- Product: **YONEX MAVIS 350 Nylon Shuttle**  
- Total Reviews: **8,518**  

### Features Used:
- Review Text  
- Review Title  
- Ratings  
- Place of Review  
- Date  
- Upvotes / Downvotes  

> ⚠️ Note: No web scraping was performed. Only the provided dataset was used.

---

## 🧹 Data Preprocessing
- Converted text to lowercase  
- Removed punctuation, numbers, and special characters  
- Removed stopwords using NLTK  
- Applied lemmatization  
- Sentiment labeling:
  - Rating ≥ 4 → Positive  
  - Rating ≤ 2 → Negative  
  - Rating = 3 excluded  

---

## 🔢 Feature Engineering
- TF-IDF (Term Frequency–Inverse Document Frequency)  
- Unigrams and bigrams  
- Same vectorizer reused during inference  

---

## 🤖 Model Building
- Algorithm: Logistic Regression  
- Evaluation Metric: F1-Score  
- Probability estimation using `predict_proba()`  

---

## 🚦 Model Explainability
- Confidence score (%) shown for each prediction  
- Negative keyword highlighting in review text  
- Improves transparency for business users  

---

## 📊 Pain-Point Analysis (Key Insights)
Analysis of negative reviews revealed:
- Poor durability  
- Low product quality  
- Not value for money  
- Short lifespan during play  

### Business Recommendations:
- Improve material durability  
- Re-evaluate pricing strategy  
- Clearly define intended usage (practice vs tournament)  

---

## 🌐 Web Application
- Backend: Flask  
- Frontend: HTML + CSS  
- Input: User-entered product review  
- Output:
  - Sentiment (Positive / Negative)  
  - Confidence Score  
  - Highlighted negative keywords  

---

## ☁️ AWS EC2 Deployment

### Step 1: Create EC2 Instance
- AMI: Ubuntu 22.04 LTS  
- Instance type: t2.micro (Free Tier)  
- Allow inbound traffic:
  - SSH (22)  
  - Custom TCP (5000)  

---

### Step 2: Connect to EC2
```bash
ssh -i your-key.pem ubuntu@<EC2_PUBLIC_IP>
