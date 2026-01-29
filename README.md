
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18420197.svg)](https://doi.org/10.5281/zenodo.18420197)



# Job Market Skill Trends using NLP

This project analyzes **in-demand skills in data and analytics job postings** using **Natural Language Processing (NLP)**.

The goals are to:
- Identify the most frequently requested technical and soft skills.
- Compare skill demand across roles:
  - Data Analyst
  - Data Scientist
  - ML Engineer
  - Business Analyst
- Explore common phrases (n-grams) used in job descriptions.
- Discover latent topics in job postings using topic modeling.

---

## 🔍 Dataset

The sample dataset consists of synthetic job postings for data-related roles, with the following columns:

- `job_title`
- `job_description`
- `location`
- `role_group` (Data Analyst, Data Scientist, ML Engineer, Business Analyst)
- `skills` (comma-separated list of skills per posting)

File: `data/job_postings_muskan.csv`

This dataset is small but designed to demonstrate the complete NLP pipeline in a clear and reproducible way.

---

## 🧠 Methods

The analysis is implemented in Python (Google Colab) and includes:

### 1. Exploratory Data Analysis (EDA)
- Role distribution
- Location distribution
- Skill frequency counts
- Skill vs role matrix (which skills are most common in each role group)

### 2. Text Preprocessing
- Lowercasing
- Removal of punctuation and special characters
- Stopword removal using `nltk`
- Lemmatization using `WordNetLemmatizer`

### 3. NLP and Feature Extraction
- **TF-IDF** (unigrams + bigrams) to extract important terms
- **N-gram analysis** (bigrams and trigrams) to find common phrases
- **Topic Modeling (LDA)** using a document-term matrix

### 4. Topic Modeling
Latent Dirichlet Allocation (LDA) is applied to uncover latent topics in the job descriptions.  
Each job posting is also assigned a dominant topic, which can be analyzed by role.

---

## 📁 Repository Structure

```text
data/
  job_postings_muskan.csv                    # sample dataset
notebooks/
  01_job_market_skill_trends_nlp.ipynb       # main analysis (EDA + NLP + topics)
requirements.txt                             # Python dependencies
README.md                                    # project documentation
