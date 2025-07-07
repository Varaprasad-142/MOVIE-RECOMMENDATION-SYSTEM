# 🎮 Movie Recommendation System

This project implements a **Collaborative Filtering** based movie recommendation system using the MovieLens dataset. It suggests movies based on user ratings by finding similarities between movies using a K-Nearest Neighbors (KNN) algorithm and cosine similarity.

---

## 📌 Overview

The goal of this project is to recommend movies that are similar to a selected movie, based on user behavior. It does **not** use genres, descriptions, or other movie metadata—instead, it relies entirely on how users rated movies.

This makes it a **Content-Based Recommendation System** .

---

## 📂 Dataset

We use two CSV files from the [MovieLens dataset on Kaggle](https://www.kaggle.com/datasets/grouplens/movielens-20m-dataset):

* `movies.csv`: Contains movie `movieId`, `title`, and `genres`.
* `ratings.csv`: Contains user ratings with columns `userId`, `movieId`, `rating`, and `timestamp`.

---

## 💠 Tools & Libraries

* Python
* Pandas
* NumPy
* SciPy
* Scikit-learn (`NearestNeighbors`)

---

## 🚀 How It Works

1. **Data Preparation**

   * Merge `movies.csv` and `ratings.csv`.
   * Remove unneeded columns (`genres`, `timestamp`).
   * Count how many ratings each movie received.
   * Keep only movies with at least **10,000 ratings** for better recommendations.

2. **Pivot Table Creation**

   * Create a pivot table with movie titles as rows and userIds as columns.
   * Fill missing ratings with 0.
   * Convert the matrix to a sparse format using `csr_matrix` for efficiency.

3. **Model Training**

   * Use `NearestNeighbors` with `cosine` similarity.
   * Fit the model on the movie-user rating matrix.

4. **Making Recommendations**

   * Pick a random movie from the dataset.
   * Find its top 10 most similar movies based on rating patterns.
   * Return those as recommendations.

---

## 🧠 Example Output

```
Recommendation for a movie: Lord of the Rings: The Return of the King, The (2003)

1: Lord of the Rings: The Two Towers, The (2002)
2: Lord of the Rings: The Fellowship of the Ring, The (2001)
3: Matrix, The (1999)
4: Pirates of the Caribbean: The Curse of the Black Pearl (2003)
...
```

---

## 🏷️ Type of Recommendation

✅ **Collaborative Filtering**

--=

## 📌 Future Improvements

* Add **content-based filtering** using genres, directors, etc.
* Combine both into a **hybrid recommendation system**.
* Build a **web interface** to let users interact with the recommender.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 🙌 Acknowledgements

Thanks to [GroupLens](https://grouplens.org/) and [Kaggle](https://www.kaggle.com/) for providing the MovieLens dataset.

---

## 📃 Usage

### 1. 📁 Clone the Repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. 🛠️ Install Dependencies

Make sure you have Python 3.7+ installed, then install required packages:

```bash
pip install -r requirements.txt
```

### 3. 📊 Prepare the Dataset

Download the MovieLens 20M dataset from Kaggle:

[Kaggle Dataset Link](https://www.kaggle.com/datasets/grouplens/movielens-20m-dataset)

Place the downloaded `movies.csv` and `ratings.csv` in the root directory of the project (or adjust file paths in the code).

### 4. ▶️ Run the Script

If you're using a Jupyter notebook:

```bash
jupyter notebook
```

Then open the notebook file and run the cells.

Or if using a `.py` script:

```bash
python movie_recommender.py
```

### 5. 🎉 View Output

You’ll see movie recommendations printed in the console based on user rating similarities.
