# LLM Model Explanation Pipeline

## Project Overview

This project integrates a Machine Learning model with a Large Language Model (LLM) to generate clear and human-readable explanations for model predictions. The machine learning model was developed in Part 3 using a Random Forest Classifier, and in this project it is extended with prompt engineering, JSON validation, and input guardrails.

---

## Assignment Track

**Track C – Model Prediction Explanation Pipeline**

---

## Project Objectives

- Load a trained machine learning model.
- Generate predictions for employee data.
- Use an LLM to explain the prediction.
- Return structured JSON responses.
- Validate JSON responses using a predefined schema.
- Implement guardrails to detect Personally Identifiable Information (PII).
- Compare model responses using different temperature values.

---

## Dataset

**Dataset Name**

`cleaned_data.csv`

**Target Variable**

- Employment Status

**Features Used**

- Gender
- Department
- Job Title
- Annual Salary
- Performance Rating
- Satisfaction Score
- Hire_Year
- Hire_Month

---

## Machine Learning Model

- Algorithm: Random Forest Classifier
- Model Pipeline:
  - Simple Imputer
  - Standard Scaler
  - Random Forest Classifier
- Saved Model:
  - `best_model.pkl`

---

## Technologies Used

- Python
- Pandas
- Scikit-learn
- Joblib
- Requests
- OpenRouter API
- JSON Schema
- python-dotenv

---

## Project Structure

```
LLM_Model_Explanation/
│── LLM_Model_Explanation.ipynb
│── cleaned_data(3).csv
│── best_model.pkl
│── README.md
│── requirements.txt
│── .env (Not uploaded to GitHub)
```

---

## Installation

Install the required libraries using:

```bash
pip install -r requirements.txt
```

---

## API Configuration

Create a `.env` file in the project folder.

Example:

```text
LLM_API_KEY=your_openrouter_api_key
```

**Note:** Never upload your `.env` file to GitHub because it contains your private API key.

---

## Workflow

1. Load the dataset.
2. Apply the same preprocessing used in Part 3.
3. Load the trained Random Forest model.
4. Generate predictions.
5. Send prediction details to the LLM.
6. Receive prediction explanations in JSON format.
7. Validate the JSON response.
8. Display the explanation.

---

## Prompt Engineering

The LLM is instructed to:

- Explain predictions in simple language.
- Return only valid JSON.
- Include:
  - Prediction Label
  - Confidence Level
  - Top Reason
  - Second Reason
  - Next Step

---

## JSON Validation

The project validates every LLM response using a predefined JSON Schema.

If validation fails, a fallback JSON object is returned.

---

## Guardrails

The project detects and blocks:

- Email addresses
- Phone numbers

This prevents Personally Identifiable Information (PII) from being sent to the LLM.

---

## Temperature Comparison

The model responses are compared using:

- Temperature = 0
- Temperature = 0.7

This demonstrates the effect of temperature on response consistency and creativity.

---

## Sample Output

```
Prediction: Active

Probability: 0.95

{
    "prediction_label": "Active",
    "confidence_level": "High",
    "top_reason": "High performance rating",
    "second_reason": "High satisfaction score",
    "next_step": "Continue monitoring employee performance."
}
```

---

## Requirements

- pandas
- numpy
- scikit-learn
- joblib
- requests
- python-dotenv
- jsonschema

Install using:

```bash
pip install -r requirements.txt
```

---

## Conclusion

This project demonstrates how Machine Learning and Large Language Models can work together to provide accurate predictions along with meaningful and easy-to-understand explanations. The addition of prompt engineering, JSON validation, and guardrails improves the reliability, security, and usability of AI-powered prediction systems.

