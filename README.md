# 🎬 Movie Recommender System

A hybrid recommender system built on the MovieLens 25M dataset combining 
collaborative filtering, content-based filtering, and explainability.

---

## What it does

Given a user ID or a movie title, the system returns personalised movie 
recommendations using three complementary approaches:

- **SVD** (Surprise) — matrix factorisation on explicit ratings  
- **ALS** (implicit) — learns from watch behaviour, not just ratings  
- **Content-based** — TF-IDF similarity on genres, cast, director, keywords  

---

## Results

| Model | Metric | Score |
|---|---|---|
| SVD | RMSE (5-fold CV) | 0.857 |
| ALS | Precision@10 | 0.17 |
| Content-based | Manual evaluation | ✓ |

---

## Dataset

[MovieLens 25M](https://grouplens.org/datasets/movielens/25m/) — 25 million 
ratings from 162,000 users on 62,000 movies.

Pre-processing: filtered to users with ≥20 ratings and movies with ≥50 
ratings to remove cold-start noise. Final dataset: ~18M ratings.

---

## Project structure

notebooks/ ← one notebook per day/stage
assets/ ← plots and screenshots
requirements.txt ← dependencies


Data and model files are not committed (see .gitignore). 
Download the dataset from the link above to reproduce.

---

## How to run

```bash
git clone https://github.com/YOUR_USERNAME/movie-recommender
cd movie-recommender
pip install -r requirements.txt
```

Then download the MovieLens 25M dataset, place it in `data/`, and run the 
notebooks in order.

---

## Tech stack

Python · pandas · scikit-learn · Scikit-Surprise · implicit · 
scipy.sparse · matplotlib · seaborn

---

## Key learnings

- Sparse matrix representation for memory-efficient user-item storage  
- Difference between explicit (SVD) and implicit (ALS) feedback models  
- TF-IDF vectorisation for content similarity  
- Cold-start filtering as a practical data quality step