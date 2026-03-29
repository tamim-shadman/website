# Sentiment Analysis On Women's Clothing Reviews

A web application that uses Natural Language Processing (NLP) and machine learning to predict whether a women's clothing review recommends the product or not.

## Overview

This project performs sentiment analysis on women's clothing reviews from an e-commerce dataset. It predicts customer recommendations based solely on the review text, using trained machine learning models served through a Flask API and a simple web frontend.

The dataset contains 23,486 rows and 10 feature variables. Models were trained on 22,641 rows using the **"Review Text"** variable.

## Features

- Enter a clothing review in the text field
- Click **Evaluate** to get a recommendation prediction
- The app returns either **"Recommended"** or **"Not Recommended"**

## Tech Stack

- **Frontend:** HTML, CSS, JavaScript (Fetch API)
- **Backend:** Python, Flask
- **ML Models:** Naive Bayes, LightGBM
- **NLP:** Scikit-learn `CountVectorizer`
- **ML Algorithms evaluated:** Logistic Regression, Naive Bayes, Support Vector Machine (SVM), Random Forest, AdaBoost, RNN with GRU (Deep Learning)

## Project Structure

```
├── index.html          # Main page with review input form
├── about.html          # About page describing the project
├── style.css           # Stylesheet for the frontend
├── script.js           # Frontend logic (calls the prediction API)
├── app.py              # Flask backend serving the prediction API
├── NaiveBayes_model.pkl    # Trained Naive Bayes model
├── lightGBM_model.pkl      # Trained LightGBM model
└── CountVectorizer.pkl     # Fitted CountVectorizer for text transformation
```

## Getting Started

### Prerequisites

- Python 3.x
- pip

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/tamim-shadman/website.git
   cd website
   ```

2. Install the required Python packages:
   ```bash
   pip install flask scikit-learn lightgbm
   ```

### Running the Application

1. Start the Flask backend:
   ```bash
   python app.py
   ```
   The API will be available at `http://127.0.0.1:5000`.

2. Open `index.html` in your browser (or serve it with a local HTTP server).

3. Update the `apiUrl` in `script.js` to point to your running Flask server:
   ```js
   const apiUrl = "http://127.0.0.1:5000/predict";
   ```

### API Endpoint

**POST** `/predict`

Request body:
```json
{
  "review_text": "The dress fits perfectly and the fabric is amazing!"
}
```

Response:
```json
{
  "recommended_ind": 1
}
```

- `1` → Recommended
- `0` → Not Recommended

## Team

**Team Quantum Leap**