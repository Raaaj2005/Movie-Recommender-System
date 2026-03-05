# 🎬 Movie Recommender System

A content-based machine learning recommender system built entirely in Python using a Jupyter Notebook. This project analyzes movie metadata to recommend similar films based on user preferences.

---

## 📝 Overview

This project demonstrates an end-to-end data science workflow, from raw data extraction to the deployment of a similarity-based recommendation algorithm. By analyzing textual data such as movie overviews, genres, keywords, and cast/crew details, the engine identifies and suggests the top 5 most similar movies to any given input.

## 📊 Dataset

The model is trained on the **TMDB 5000 Movie Dataset** from Kaggle, which contains detailed attributes of 5000 diverse movies.
* `tmdb_5000_movies.csv`: Contains movie metrics like budget, genres, overview, and title.
* `tmdb_5000_credits.csv`: Contains cast and crew details.

## 🧠 Methodology & Pipeline

1. **Data Preprocessing:** * Merged the movies and credits datasets on the `title` attribute.
   * Extracted relevant columns: `movie_id`, `title`, `overview`, `genres`, `keywords`, `cast`, and `crew`.
   * Handled missing values and removed duplicate entries.
2. **Feature Engineering:**
   * Parsed JSON-like string columns into standard Python lists.
   * Extracted the top 3 actors from the cast and the Director from the crew.
   * Removed spaces from names/genres to create unique, distinct tags (e.g., "Science Fiction" -> "ScienceFiction").
3. **Text Vectorization:**
   * Concatenated all extracted text into a single `tags` column.
   * Applied stemming using NLTK to reduce words to their root forms (e.g., "actions", "acting" -> "act").
   * Converted the text corpus into vectors using the **Bag of Words** technique.
4. **Similarity Calculation:**
   * Computed the **Cosine Similarity** between all movie vectors to mathematically determine the angle (distance) between different films.

## 🛠️ Tech Stack

* **Language:** Python
* **Environment:** Jupyter Notebook
* **Data Manipulation:** `pandas`, `numpy`
* **Natural Language Processing (NLP):** `nltk`
* **Machine Learning:** `scikit-learn` (CountVectorizer, Cosine Similarity)
* **Serialization:** `pickle`

---

## 🚀 How to Run Locally

### 1. Clone the repository
```bash
git clone [https://github.com/Raaaj2005/Movie-Recommender-System.git](https://github.com/Raaaj2005/Movie-Recommender-System.git)
cd Movie-Recommender-System
```

### 2. Download the Data
Due to file size limits, the raw datasets are not included. 
* Download `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv` from Kaggle.
* Place them in the root directory of this project.

### 3. Run the Notebook
Launch Jupyter Notebook or open the file in VS Code:
```bash
jupyter notebook Movie-Recommender-System.ipynb
```
Execute the cells sequentially to build the model and test the `recommend()` function at the bottom.

---

## 👨‍💻 Author

Name: **Raj Fatehveer Singh Brar** <br>
Roll No.: **102317090**

Feel free to explore the notebook or reach out if you have any questions regarding the implementation!
