# Phishing Website Detection (Content-Based)

![Project Banner](screenshots/banner.png) <!-- Replace with your actual banner image -->

## Overview
This project is an end-to-end machine learning application that detects phishing websites using content-based features extracted from HTML. The app is built with Streamlit for an interactive web interface and uses several machine learning models to classify websites as phishing or legitimate.

## Features
- Extracts content-based features from website HTML using BeautifulSoup
- Supports multiple machine learning models:
  - Support Vector Machine (SVM)
  - Gaussian Naive Bayes
  - Decision Tree
  - Random Forest
  - AdaBoost
- Visualizes model performance (accuracy, precision, recall, confusion matrix)
- Interactive web app for predictions and data exploration

## Demo
![App Screenshot](screenshots/app_demo.png) <!-- Replace with your actual screenshot -->

## Project Structure
```
app.py                      # Streamlit web app
machine_learning.py         # ML model training and evaluation
feature_extraction.py       # Feature extraction logic
features.py                 # Feature definitions
requirements.txt            # Python dependencies
structured_data_legitimate.csv  # Legitimate websites data
structured_data_phishing.csv    # Phishing websites data
tranco_list.csv                 # Source URLs (legitimate)
verified_online.csv             # Source URLs (phishing)
data_collector.py           # Script to collect and structure data
```

## Dataset
- **Phishing URLs:** `verified_online.csv` (from phishtank.org)
- **Legitimate URLs:** `tranco_list.csv` (from tranco-list.eu)
- **Structured Data:**
  - `structured_data_legitimate.csv`
  - `structured_data_phishing.csv`

## How It Works
1. **Data Collection:**
   - URLs are collected from CSV files.
   - Each URL is fetched using the `requests` library.
   - HTML content is parsed with BeautifulSoup.
2. **Feature Extraction:**
   - Content-based features are extracted and converted into numerical vectors.
   - Data is labeled (1 for phishing, 0 for legitimate).
3. **Model Training:**
   - Data is split into training and test sets (or K-fold cross-validation).
   - Five ML models are trained and evaluated.
4. **Evaluation:**
   - Confusion matrix and performance metrics are computed and visualized.

## Setup Instructions
1. **Clone the repository:**
   ```sh
   git clone <your-repo-url>
   cd Phising_Detection-main
   ```
2. **(Recommended) Create a Python 3.11 environment:**
   ```sh
   conda create -n phishing python=3.11
   conda activate phishing
   ```
3. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```
4. **Run the Streamlit app:**
   ```sh
   streamlit run app.py
   ```

## Results
- The app displays model performance for each algorithm.
- Example performance visualization:

![Performance Screenshot](screenshots/performance.png) <!-- Replace with your actual screenshot -->

- In this project, Naive Bayes performed best on the dataset.

## References
- [PhishTank](https://phishtank.org/)
- [Tranco List](https://tranco-list.eu/)
- [BeautifulSoup Documentation](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
- [Streamlit Documentation](https://docs.streamlit.io/)

## Notes
- This project is for educational purposes only.
- For more details, see the code and comments in each file.
- Based on a YouTube video series: [Watch here](https://www.youtube.com/watch?v=-Aldptec9Xs&list=PL8Uzrd8g1md8kdvNJy0BNRc3cJfVP8QEf)

---

> **Tip:** Replace the screenshot placeholders with your actual images (place them in a `screenshots/` folder in your project directory).


