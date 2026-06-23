# 🎬 Netflix Recommender System using Singular Value Decomposition (SVD)

## 📌 Overview

This project implements a **Movie Recommendation System** using the famous **Netflix Prize Dataset** and the **Singular Value Decomposition (SVD)** algorithm from the Surprise library.

The goal is to analyze user-movie interactions, clean and preprocess large-scale rating data, identify active users and popular movies, and generate personalized movie recommendations based on collaborative filtering techniques.

---

## 🚀 Features

* 📊 Exploratory Data Analysis (EDA) on Netflix ratings data
* 🧹 Data cleaning and preprocessing
* 📈 Rating distribution visualization
* 🎭 User and movie activity analysis
* 🔍 Filtering inactive users and infrequently rated movies
* 🧮 Creation of User-Movie Rating Matrix
* 🤖 Collaborative Filtering using SVD
* 📉 Performance evaluation using:

  * RMSE (Root Mean Squared Error)
  * MAE (Mean Absolute Error)
* 🎯 Personalized movie recommendation generation
* 🎬 Movie title mapping for human-readable recommendations

---

## 📂 Dataset

This project uses the **Netflix Prize Dataset**, which contains:

* Millions of movie ratings
* Thousands of movies
* Hundreds of thousands of users

### Dataset Files

```text
combined_data_1.txt
movie_titles.csv
```

### Data Format

#### Ratings Dataset

```text
MovieID:
CustomerID, Rating, Date
CustomerID, Rating, Date
...
```

#### Movie Metadata

```text
Movie_Id, Year, Movie_Name
```

---

## 🏗️ Project Workflow

### 1. Data Loading

* Load Netflix ratings data
* Convert ratings to numerical format
* Inspect dataset structure

### 2. Exploratory Data Analysis

* Count:

  * Total Movies
  * Total Users
  * Total Ratings
* Visualize rating distributions

### 3. Data Transformation

Since movie IDs are stored as:

```text
1:
1488844,3,2005-09-06
822109,5,2005-05-13

2:
...
```

Movie IDs are extracted and assigned to every rating entry.

### 4. Data Cleaning

To improve recommendation quality:

* Remove rarely rated movies
* Remove inactive users
* Retain only meaningful interactions

This reduces noise and sparsity in the dataset.

### 5. User-Movie Matrix Creation

A pivot table is created:

| User   | Movie 1 | Movie 2 | Movie 3 |
| ------ | ------- | ------- | ------- |
| User A | 5       | NaN     | 3       |
| User B | 4       | 2       | NaN     |

This matrix forms the foundation for collaborative filtering.

### 6. Model Training

The project uses:

```python
from surprise import SVD
```

SVD factorizes the user-item interaction matrix into latent features that capture hidden preferences and movie characteristics.

### 7. Model Evaluation

Performance is measured using:

* RMSE
* MAE

Cross-validation is performed to ensure model reliability.

### 8. Recommendation Generation

After training:

* Predict ratings for unseen movies
* Rank movies based on estimated ratings
* Recommend top movies for a specific user

---

## 🛠️ Technologies Used

### Programming Language

* Python

### Libraries

* NumPy
* Pandas
* Matplotlib
* Scikit-Surprise

### Machine Learning Technique

* Collaborative Filtering
* Singular Value Decomposition (SVD)

---

## 📊 Sample Pipeline

```text
Raw Netflix Data
        ↓
Data Cleaning
        ↓
Movie ID Extraction
        ↓
User Filtering
        ↓
Movie Filtering
        ↓
User-Movie Matrix
        ↓
SVD Training
        ↓
Model Evaluation
        ↓
Personalized Recommendations
```

---

## 📈 Results

The SVD model learns latent user preferences and movie characteristics, enabling:

* Accurate rating prediction
* Personalized recommendations
* Better handling of sparse rating matrices
* Scalable collaborative filtering

---

## 🎯 Example Use Case

For a given user:

```python
User ID: 712664
```

The system:

1. Identifies previously watched movies
2. Learns preference patterns
3. Predicts ratings for unseen movies
4. Recommends the highest-rated unseen titles

---

## 📁 Project Structure

```text
Netflix-Recommender-System/
│
├── Recommender_System_Bibek.ipynb
├── combined_data_1.txt
├── movie_titles.csv
├── README.md
│
└── outputs/
    ├── rating_distribution.png
    ├── evaluation_results.png
    └── recommendations.csv
```

---

## 🔮 Future Improvements

* Content-Based Filtering
* Hybrid Recommendation System
* Deep Learning Recommenders
* Matrix Factorization Optimization
* Real-Time Recommendation API
* Streamlit Web Application
* Recommendation Explainability

---

## 📚 Learning Outcomes

Through this project, the following concepts were explored:

* Recommender Systems
* Collaborative Filtering
* Matrix Factorization
* Data Cleaning at Scale
* User-Item Interaction Modeling
* Recommendation Evaluation Metrics
* Netflix Prize Dataset Analysis

---

## 👨‍💻 Author

**Bibek Kundu**

AI/ML Enthusiast | Data Science | Machine Learning | Recommender Systems

If you found this project useful, consider giving it a ⭐ on GitHub.
