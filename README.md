# diabetes_prediction

# Diabetes Prediction Streamlit App

## Overview
The **Diabetes Prediction Streamlit App** is a web-based application that predicts the likelihood of a person having diabetes based on key health parameters. The app utilizes a hybrid machine learning model consisting of:

1. **Random Forest Classifier** – Generates probability scores based on user input.
2. **Artificial Neural Network (ANN)** – Provides another probability estimate.
3. **XGBoost Meta-Learner** – Combines the predictions from the Random Forest and ANN models to make the final prediction.

## Architecture
The app follows a structured pipeline:

1. **User Input** – Users enter medical parameters such as glucose levels, BMI, and insulin levels.
2. **Feature Processing** – The input is converted into a structured format.
3. **Random Forest and ANN Predictions** – The input is fed into both models to generate probability scores.
4. **XGBoost Final Prediction** – The probability scores from the previous step are passed into an XGBoost meta-learner for the final classification.
5. **Result Display** – The app returns either "Diabetes Positive" or "Diabetes Negative" based on the final prediction.

## Features
- Simple and interactive UI built with **Streamlit**.
- Accepts user input for medical features including glucose levels, BMI, insulin, and age.
- Uses an ensemble approach combining **Random Forest, ANN, and XGBoost**.
- Provides a probability score for better interpretability.

## Installation and Setup
### Prerequisites
Ensure you have Python installed along with Anaconda (optional but recommended).

### Step 1: Clone the Repository
```bash
git clone https://github.com/your-repo/diabetes-prediction-app.git
cd diabetes-prediction-app
```

### Step 2: Install Dependencies
Install the required Python libraries using the following command:
```bash
pip install -r requirements.txt
```

### Step 3: Run the Streamlit App
To launch the application, use:
```bash
streamlit run app.py
```

This will start a local web server, and the app will open in your browser.

## Required Files
The following files are essential for the application to function:
- **models/random_forest_model (2).pkl** – Trained Random Forest model.
- **models/ann_model (2).h5** – Trained Artificial Neural Network model.
- **models/xgb_meta_model (2).json** – Trained XGBoost meta-learner model.
- **app.py** – Streamlit application script.
- **requirements.txt** – List of dependencies.

## Inputs and Expected Values
| Feature | Description | Expected Range |
|---------|------------|----------------|
| Pregnancies | Number of times pregnant | 0 - 20 |
| Glucose | Blood glucose level | 0 - 200 |
| Blood Pressure | Diastolic blood pressure | 0 - 150 |
| Skin Thickness | Skin fold thickness | 0 - 100 |
| Insulin | Insulin level | 0 - 1000 |
| BMI | Body Mass Index | 10.0 - 70.0 |
| Diabetes Pedigree Function | Diabetes risk factor | 0.0 - 2.5 |
| Age | Age of the person | 1 - 120 |

## Testing
To verify model predictions, use the following test cases:

### Diabetic Cases
| Pregnancies | Glucose | Blood Pressure | Skin Thickness | Insulin | BMI | DPF | Age |
|-------------|---------|---------------|---------------|---------|------|------|-----|
| 6 | 160 | 85 | 35 | 150 | 35.5 | 0.8 | 55 |
| 8 | 190 | 90 | 40 | 200 | 38.0 | 1.2 | 60 |

### Non-Diabetic Cases
| Pregnancies | Glucose | Blood Pressure | Skin Thickness | Insulin | BMI | DPF | Age |
|-------------|---------|---------------|---------------|---------|------|------|-----|
| 1 | 95 | 70 | 20 | 80 | 22.5 | 0.3 | 25 |
| 0 | 85 | 65 | 18 | 60 | 21.0 | 0.2 | 22 |

## Future Improvements
- Adding Explainable AI (XAI) to provide reasoning behind predictions.
- Deploying the model online using **Streamlit Sharing, AWS, or Heroku**.
- Implementing user authentication for data security.

## License
This project is open-source and available under the [MIT License](LICENSE).

## Contact
For any queries or contributions, please reach out to **your-email@example.com** or open an issue in the repository.

