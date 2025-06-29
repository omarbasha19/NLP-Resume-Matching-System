# NLP Resume Matching System

An intelligent, end-to-end system for matching candidate resumes with job descriptions using state-of-the-art Natural Language Processing (NLP) and machine learning techniques.


---

## 🎯 Objective

Manual resume screening is time-consuming, error-prone, and often biased. This project introduces a smart automated matching system that:
- Reads and processes raw resume text.
- Extracts key information using NLP techniques.
- Calculates the degree of match with specific job descriptions.
- Outputs ranked matches using hybrid similarity models and classifiers.

---

## 📁 Dataset Summary

| Metric                      | Value                   |
|----------------------------|-------------------------|
| Number of Resumes          | 962                     |
| Job Categories             | 25                      |
| Most Frequent Category     | Data Science (43 resumes) |
| Resume Length (avg chars)  | ~6,000                  |
| Resume Length (avg words)  | ~1,000                  |
| Longest Resume             | ~15,000 characters      |
| Shortest Resume            | ~500 characters         |

The dataset is provided in `UpdatedResumeDataSet.csv` and covers a diverse set of job roles.

---

## 🧹 NLP Pipeline: Preprocessing Steps

Each resume undergoes a multi-stage NLP transformation to normalize and prepare data for analysis:

| Stage              | Description |
|-------------------|-------------|
| **Normalization** | Remove accents and special characters to ensure text uniformity. |
| **Cleaning**       | Strip out punctuation, numbers, and non-alphabetic characters. |
| **Tokenization**   | Split text into individual tokens (words). |
| **Lemmatization**  | Reduce words to their root form (e.g., "running" → "run"). |
| **Stopword Removal** | Remove non-informative words like "the", "and", etc. |

> 🔍 *Result:* Reduced vocabulary size by ~30%, improved focus on meaningful keywords, and boosted computational efficiency.

---

## 📊 Feature Extraction Techniques

Three primary methods were used to extract meaningful features from text:

1. **TF-IDF Vectorization**
   - Transforms resumes and job descriptions into 3,000-dimensional vectors.
   - Highlights frequent, informative terms such as `python`, `project`, `skills`, `experience`.

2. **Named Entity Recognition (NER)**
   - Extracts structured entities such as:
     - `PERSON`: Names
     - `ORG`: Employers
     - `DATE`: Experience durations
     - `GPE`: Geographic entities

3. **YAKE Keyphrase Extraction**
   - Captures domain-specific concepts:
     - Data Science: `machine learning`, `predictive modeling`
     - HR: `employee engagement`, `recruitment process`
     - DevOps: `CI/CD pipelines`, `cloud infrastructure`

---

## 🧮 Similarity Approaches

We implemented and compared three models to assess the similarity between job descriptions and resumes.

| Method      | Description                                      | Strengths                              | Weaknesses                    |
|-------------|--------------------------------------------------|----------------------------------------|-------------------------------|
| **TF-IDF**  | Vectorized word frequency matching               | Fast, interpretable                    | No context awareness          |
| **BERT**    | Contextual embeddings from deep language models  | Understands semantics and synonyms     | Computationally expensive     |
| **Hybrid**  | Weighted combination (TF-IDF 60%, BERT 40%)      | Balances speed and depth               | Requires tuning & integration |

> ✅ *Outcome:* The hybrid model achieved the best balance between contextual understanding and speed.

---

## 🧠 Classification Models for Suitability Prediction

To move beyond raw similarity scores, we trained supervised classifiers to predict suitability between resumes and jobs.

| Model               | Accuracy | Notes                               |
|---------------------|----------|-------------------------------------|
| Random Forest       | 100%     | Best generalization & interpretability |
| Logistic Regression | 100%     | Lightweight and fast                |
| Naive Bayes         | 56%      | Weak with long, sparse documents    |

> 🔑 *Top Predictive Features:* TF-IDF score, resume length, and keyword overlap count.

---

## 🧾 Sample Output

**Job Description Example**:  
> *Looking for a Senior Data Scientist with expertise in Python, machine learning, and cloud platforms. Big data experience preferred.*

**Matching Result (Top Match)**  
- **Category**: Data Science  
- **Similarity Score**: 0.87 (Hybrid)  
- **Suitability Probability**: 92%  
- **Candidate Snippet**:
  > "Data scientist with 5+ years developing machine learning models in Python. AWS Certified. Built scalable ML solutions in production."

---

## 🛠 Future Enhancements

- 📁 Add multilingual support and broader job domains.
- 🔍 Fine-tune BERT on job recruitment corpora.
- 🖥️ Develop a user-friendly web-based interface for recruiters.
- 📊 Integrate dashboard analytics for match insights.

---

## 📂 Files Included

| File Name                | Purpose                                  |
|--------------------------|------------------------------------------|
| `NLP_Code.ipynb`| Full annotated code for end-to-end system |
| `UpdatedResumeDataSet.csv` | Raw resume data (25 job categories)     |       |
| `demo.zip`           | Demonstration video            |
| `README.md`              | This project description file            |


---

