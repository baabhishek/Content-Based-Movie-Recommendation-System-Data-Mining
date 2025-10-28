# 🎬 Content-Based Movie Recommendation System (Data Mining)

---

![Movie Recommendation Banner](https://i.insider.com/658b1ba01c5c7b8c9a0c0dc5?width=1200&format=jpeg&auto=webp)

---

Build a personalized movie recommendation system using **content-based filtering** powered by **cosine similarity**.  
Performed detailed **EDA using ydata_profiling** and created an interactive recommendation system that suggests the **top 5 similar movies** based on user input.

---


## Project Overview

- Developed a **content-based recommendation model** using cosine similarity.
- Conducted **exploratory data analysis (EDA)** with `ydata_profiling` to identify trends and data quality.
- Built a **recommendation function** that suggests movies most similar to a selected title.
- Focused on **NLP-based feature extraction** from movie metadata like title, genres, and overview.
- Designed for **instant movie recommendations** without relying on user history.

---
## About Dataset:

### `movies`
Contains information about each movie: Frontend details

| Column | Description |
|---------|--------------|
| `id` | Unique identifier for each movie |
| `title` | Name of the movie |
| `overview` | Short story summary |
| `genres` | List of genres |
| `keywords` | Keywords describing the movie |
| `cast` | Main actors involved |
| `crew` | Key people like directors and producers |

### `credits`
Contains cast and crew details for each movie: Backend details

| Column | Description |
|---------|--------------|
| `cast` | Names of actors and their roles |
| `crew` | Names of directors, editors, and other staff |

Both datasets are merged using the **`title`** column to form a single combined dataset for model building.
And extensive ***cleaning and preprocessing***.

---

## Workflow

1. **Data Collection & Cleaning | Data Preprocessing**  
- Merged **`movies.csv`** and **`credits.csv`** using the common `title` field.  
- Converted JSON-like columns (`genres`, `keywords`, `cast`, `crew`) into Python lists.  
- Removed unwanted spaces to prevent token confusion.  
- Tokenized the `overview` column using `split()` to prepare for text vectorization.
---
2. **Exploratory Data Analysis (EDA)**  
- Used `ydata_profiling` for automated data profiling.  
---
3. **Feature Engineering**  
- Combined key text-based features (`overview`, `genres`, `keywords`, `cast`, `crew`) into a single **`tags`** column.   
- Applied **`CountVectorizer`** to convert textual data into numerical feature vectors.
---

4. **Model Building**  
- Computed **Cosine Similarity** between movie vectors.  
- Created a function `recommendation_system(movie_name)` to:
  1. Find the index of the selected movie.  
  2. Retrieve similarity scores for all other movies.  
  3. Sort them in descending order of similarity.  
  4. Display the **top 5 most similar movies**.
 ---    
**Recommendation Function**  
   ```python
   def recommendationsystem(movie):
       index = new[new['title'] == movie].index[0]
       distance = sorted(list(enumerate(similarity[index])), reverse=True, key=lambda x: x[1])
       for i in distance[1:6]:
           print(new.iloc[i[0]].title)
```
---
## Technologies Used

| TYpes | Libraries |
|-----------|----------------|
| Programming | Python |
| Data Manipulation | Pandas, NumPy |
| EDA | ydata_profiling |
| Machine Learning | Scikit-learn (CountVectorizer, cosine_similarity) |
| Environment | Jupyter Notebook |

---
## Conclusion

This project demonstrates how **textual metadata** can be transformed into meaningful vectors to recommend movies.  
Using **cosine similarity** ensures that recommendations are based on **content similarity**, not user ratings — making it ideal for **new users or small datasets**.

---
## Sample Output of Movie Recommendation

```python
recommendationsystem("Veer-Zaara")

Recommended Movies:
1. Sunshine State
2. All That Jazz
3. Good Intentions
4. Blood and Wine
5. Crossroads

---
