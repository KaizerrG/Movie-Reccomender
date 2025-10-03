# Movie-Reccomender


 🎬 Movie Recommendation System

This Python project implements a **content-based movie recommendation system** using TF-IDF and cosine similarity.
It stores user input and recommended movies in a MySQL database.


## 📋 Features

* Imports and processes movie data from a CSV file.
* Combines selected movie features (genres, keywords, tagline, cast, director) into a single text vector.
* Uses **TF-IDF Vectorizer** to transform text data into numerical feature vectors.
* Computes **cosine similarity** between movies to recommend similar ones.
* Accepts user details (name, chosen movie, mobile number) and stores them in a MySQL database.
* Updates the database with top 5 movie recommendations.

---

## 🛠️ Technologies Used

* Python 
  Numpy
  Pandas
  MySQL Connector
  scikit-learn TF-IDF, cosine similarity
  difflib for close string matching


## 📂 Project Structure

```
project/
│
├── movies.csv           # Dataset of movies
├── recommendation.py    # Main Python script (the code you shared)
└── README.md            # Documentation
```



## ⚙️ Installation

1. Clone this repository or download the script.
2. Install required Python libraries:

```bash
pip install numpy pandas mysql-connector-python scikit-learn
```

3. Set up your MySQL database:

sql
CREATE DATABASE Customers_data;
USE Customers_data;

CREATE TABLE cinephiles (
    U_name VARCHAR(255),
    Mov_name VARCHAR(255),
    Mob_num VARCHAR(20),
    reco_1 VARCHAR(255),
    reco_2 VARCHAR(255),
    reco_3 VARCHAR(255),
    reco_4 VARCHAR(255),
    reco_5 VARCHAR(255)
);


4. Place your `movies.csv` file in the project directory.

---

## ▶️ Usage

Run the script:

```bash
python recommendation.py
```

The program will:

* Ask for user details (Name, Movie, Mobile number).
* Insert them into the database.
* Recommend 5 similar movies based on your input.
* Update the database with the recommendations.

Example input:


Enter the user_name: John
Enter the movie: Avatar
Enter the mobile num: 9876543210

Output:

Movies suggested are and their genre:
1. Interstellar , Adventure ,, <homepage_url>
2. Gravity , Science Fiction ,, <homepage_url>


---

## 📝 Notes

* Ensure the `movies.csv` file has the following columns:
  `index`, `title`, `genres`, `keywords`, `tagline`, `cast`, `director`, `homepage`.
* Update your MySQL credentials in the script:

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="YOUR_PASSWORD",
  database="Customers_data"
)

* The script uses the first closest match if multiple titles are similar.

## 🚀 Future Improvements

* Add a web interface for movie recommendations.
* Support multiple user queries at once.
* Improve similarity scoring with NLP techniques (Word2Vec, BERT).
