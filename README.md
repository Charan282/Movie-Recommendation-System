# Movie-Recommendation-System
This is a **content-based movie recommendation system** built using the **TMDB 5000 Movie Dataset**. It analyzes movie metadata such as title, overview, cast, crew, and genres to recommend similar movies. The project includes a user-friendly interface built using **Streamlit** and integrates with the **TMDB API** to display movie posters.

---

## 📁 Project Structure

```
Movie_Recommendation_System/
├── app.py                            # Streamlit web app for movie recommendations
├── Movie_Recommendation_System.ipynb # Jupyter notebook with full data processing
├── movie_dict.pkl                    # Pickled movie metadata used in app
├── movies.pkl                        # Intermediate movie data
├── similarity.pkl                    # Cosine similarity matrix for recommendations
├── tmdb_credits.csv                  # Credits data from TMDB
├── tmdb_movies.csv                   # Movie metadata from TMDB
```

---

## 💡 Key Features

- 🔍 **Content-Based Filtering** using combined metadata (`overview`, `genres`, `cast`, `crew`)
- 🎯 **Cosine Similarity** algorithm to measure movie similarity
- 🖼️ **Poster Fetching** via TMDB API
- 🌐 **Interactive Web App** built with Streamlit
- 💾 **Preprocessed Model Files** for instant recommendations

---

## ⚙️ How It Works

1. **Data Preparation (in notebook)**:
   - Load and clean data from `tmdb_movies.csv` and `tmdb_credits.csv`
   - Extract key columns and merge into a single `tags` field
   - Vectorize text using `CountVectorizer`
   - Compute cosine similarity between movie vectors
   - Save processed data to `movie_dict.pkl` and `similarity.pkl`

2. **Streamlit App (in `app.py`)**:
   - Loads model files
   - Takes a movie title input
   - Recommends 5 similar movies
   - Fetches and displays their posters using the TMDB API

---

## 🚀 Getting Started

### 🧩 Install Dependencies

```bash
pip install streamlit pandas numpy scikit-learn requests
```

### ▶️ Run the App

```bash
streamlit run app.py
```

Then open the browser window that appears or go to:
```
http://localhost:8501
```

---

## 🔐 TMDB API Key

To display posters, the app uses TMDB's free API.

### Replace the Key in `app.py`:

```python
# Inside fetch_poster()
url = f"https://api.themoviedb.org/3/movie/{movie_id}?api_key=YOUR_API_KEY&language=en-US"
```

👉 [Get your free TMDB API key here](https://www.themoviedb.org/settings/api)

> **Security Tip**: If you're pushing this to GitHub, do NOT hardcode your API key. Use `st.secrets` in Streamlit Cloud or environment variables.

---

## 🌟 Sample Output

- ✅ Selected: **Inception**
- 🔁 Recommended: **Interstellar, The Prestige, Memento, The Dark Knight, Shutter Island**
- 🖼️ Posters displayed using TMDB image URLs

---

## 🛠 Tech Stack

- Python
- Pandas, NumPy, Scikit-learn
- Streamlit
- TMDB API
- Jupyter Notebook

---

## 📎 Acknowledgements

- Dataset: [Kaggle - TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)
- API: [The Movie Database (TMDB)](https://www.themoviedb.org/)
- Inspired by: YouTube ML tutorials
---

## 👨‍💻 Author

**Sri Naga Charan Gampala**  
🎓 Master’s in Data Science, University at Buffalo  
📬 [LinkedIn]([https://www.linkedin.com/](https://www.linkedin.com/in/srinagacharang)) 
