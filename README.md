# Assignment-5-FakeNews-Detection

#  Fake News Detection using Spark MLlib

This project implements a machine learning pipeline using Apache Spark to detect whether a news article is **FAKE** or **REAL** based on its text content.

---

##  Dataset

Before running the pipeline, you must generate a sample dataset.

### ➤ Step 1: Generate Dataset

Run the following script to create a synthetic dataset:

```bash
python Dataset_Generator.py
```

This will create a file called:

- `fake_news_sample.csv`

### Dataset Columns:

- `id` – Unique article ID  
- `title` – Title of the news article  
- `text` – Full content of the article  
- `label` – Ground truth (`FAKE` or `REAL`)  

---

## How to Run the Pipeline

Once the dataset is generated, run the complete pipeline using:

```bash
spark-submit fake_news.py
```

This script performs all tasks from data loading to model evaluation and saves the output of each task into separate CSV files.

---

##  Tasks Breakdown

### Task 1: Load and Explore Dataset
- Load the dataset into Spark.
- Display first 5 rows, total count, and distinct labels.
- **Output:** `task1_output.csv`

---

###  Task 2: Text Preprocessing
- Convert text to lowercase.
- Tokenize the text.
- Remove stopwords.
- **Output:** `task2_output.csv`

---

###  Task 3: Feature Extraction
- Use `HashingTF` and `IDF` to compute TF-IDF vectors.
- Encode text labels using `StringIndexer`.
- **Output:** `task3_output.csv`

---

###  Task 4: Model Training and Prediction
- Train a `LogisticRegression` classifier.
- Split dataset into training and testing sets.
- Generate predictions.
- **Output:** `task4_output.csv`

---

### Task 5: Model Evaluation
- Evaluate the model using Accuracy and F1 Score.
- **Output:** `task5_output.csv`

---

##  Output Files

After running the pipeline, the following files will be created:

- `task1_output.csv` – Sample records and basic stats  
- `task2_output.csv` – Preprocessed tokens  
- `task3_output.csv` – Extracted TF-IDF features  
- `task4_output.csv` – Predictions on test set  
- `task5_output.csv` – Evaluation metrics  

---

