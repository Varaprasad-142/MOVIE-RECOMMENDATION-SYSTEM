# 🎬 Movie Recommendation System

This project implements a **Collaborative Filtering** based movie recommendation system using the MovieLens dataset. It suggests movies based on user ratings by finding similarities between movies using a K-Nearest Neighbors (KNN) algorithm and cosine similarity.

---

## 📌 Overview

The goal of this project is to recommend movies that are similar to a selected movie, based on user behavior. It does **not** use genres, descriptions, or other movie metadata—instead, it relies entirely on how users rated movies.

This makes it a **collaborative filtering** system.

---

## 📂 Dataset

We use two CSV files from the Kaggle datasets:

- `movies.csv`: Contains movie `movieId`, `title`, and `genres`.
- `ratings.csv`: Contains user ratings with columns `userId`, `movieId`, `rating`, and `timestamp`.

---

## 🛠️ Tools & Libraries

- Python
- Pandas
- NumPy
- SciPy
- Scikit-learn (`NearestNeighbors`)

---

## 🚀 How It Works

1. **Data Preparation**
   - Merge `movies.csv` and `ratings.csv`.
   - Remove unneeded columns (`genres`, `timestamp`).
   - Count how many ratings each movie received.
   - Keep only movies with at least **10,000 ratings** for better recommendations.

2. **Pivot Table Creation**
   - Create a pivot table with movie titles as rows and userIds as columns.
   - Fill missing ratings with 0.
   - Convert the matrix to a sparse format using `csr_matrix` for efficiency.

3. **Model Training**
   - Use `NearestNeighbors` with `cosine` similarity.
   - Fit the model on the movie-user rating matrix.

4. **Making Recommendations**
   - Pick a random movie from the dataset.
   - Find its top 10 most similar movies based on rating patterns.
   - Return those as recommendations.

---

## 🧠 Example Output

Recommendation for a movie: Lord of the Rings: The Return of the King, The (2003)

1: Lord of the Rings: The Two Towers, The (2002)
2: Lord of the Rings: The Fellowship of the Ring, The (2001)
3: Matrix, The (1999)
4: Pirates of the Caribbean: The Curse of the Black Pearl (2003)

----

## 📎 Future Improvements

- Add **content-based filtering** using genres, directors, etc.
- Combine both into a **hybrid recommendation system**.
- Build a **web interface** to let users interact with the recommender.
