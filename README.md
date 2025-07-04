Fraud Detection: Threshold Tuning on Imbalanced Data

🎯 Objective

This project explores how tuning the **classification threshold** can significantly affect the **precision**, **recall**, and **F1-score** of a fraud detection model using the popular **Credit Card Fraud Detection dataset**. Instead of simply using a default threshold of 0.5, we investigate the trade-offs across different thresholds to find the optimal one.

📊 Dataset

Source: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
Rows: 284,807 transactions
Class Distribution: Highly imbalanced (frauds are \~0.17%)

⚙️ Model & Methodology

Model: Random Forest Classifier (no scaling needed)   
Key Step: Instead of using `.predict()`, we use `.predict_proba()` to get the probability of fraud.
Loop through thresholds from 0.0 to 1.0 in steps of 0.05.
For each threshold, compute:
    Precision
    Recall
    F1 Score
Identify the threshold with highest F1 Score (best balance of precision and recall).

📈 Results

Best Threshold: `0.35`
Precision: `0.93`
Recall: `0.83`
F1 Score: `0.88`

> The sweet spot lies around 0.35, where the model maintains a strong balance between catching frauds (recall) and avoiding false alarms (precision).

🧠 Key Takeaways

* Default threshold (0.5) is not always optimal in real-world applications like fraud detection.
* F1 Score gives a better indication of performance when dealing with **imbalanced datasets**.
* Plotting these metrics can help in **model explainability and tuning**.

📦 Folder Structure

fraud-threshold-tuning/
  README.md
  requirements.txt
  notebooks/
    fraud_threshold_tuning.ipynb
  images/
    threshold_plot.png
  data/
    creditcard.csv (download manually from Kaggle and place here)


▶️ To Run This Project

1. Clone this repository.
2. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) and place it in the `data/` folder.
3. Open and run the notebook in `notebooks/fraud_threshold_tuning.ipynb`.

bash -> pip install -r requirements.txt

👨‍💻 Author
This project was developed as part of my personal learning journey in **data science**, specifically focusing on **model evaluation and deployment considerations**. It reflects how I approach practical problems with not just model accuracy, but also real-world trade-offs in mind.
Feel free to fork, star, or reach out with questions!
