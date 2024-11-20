# Student Score Prediction System

This repository contains the code for a machine learning-based system designed to predict student math scores based on various features such as reading and writing scores, demographic details, and more. It uses machine learning models to predict the student's math score based on input data and provides the predicted results.

## Features

- **Data Ingestion:** Loads and splits data into training and test datasets.
- **Data Transformation:** Applies preprocessing steps to handle missing values, scale numerical features, and encode categorical features.
- **Model Training:** Trains different machine learning models and selects the best-performing model based on the R-squared score.
- **Prediction:** Uses the trained model to make predictions based on new input data.
- **Flask API:** Exposes a web-based interface to interact with the trained models and make predictions.

## Technologies Used

- **Python:** The main programming language for implementing the solution.
- **Scikit-learn:** Used for machine learning model training and preprocessing.
- **CatBoost, XGBoost, RandomForest, AdaBoost, and other ML models:** For model training.
- **Flask:** To create a web application for predictions.
- **Pandas:** For data manipulation and transformation.
- **NumPy:** For numerical operations.
- **Pickle:** For saving and loading trained models.
- **HTML/CSS:** For building the front-end web interface.

## Structure

- `src/` - Contains the core components of the project, including data ingestion, transformation, and model training.
  - `exception.py` - Custom exceptions.
  - `logger.py` - Custom logger for logging activities.
  - `components/` - Contains various components like data ingestion, transformation, and model trainer.
  - `utils.py` - Utility functions for saving/loading objects and evaluating models.
  - `pipeline/` - Contains code for prediction pipeline and custom data processing.
- `artifact/` - Stores the trained models, preprocessing objects, and other artifacts.
- `notebook/` - (Optional) Contains any exploratory analysis or data processing notebooks.
- `templates/` - Contains HTML files for the Flask web interface.
- `app.py` - The entry point for the Flask application.

## Setup and Installation

To get started with this project, follow the steps below.

### Prerequisites

1. Python 3.x
2. Install the required libraries.

### Installation Steps

1. Clone the repository:
    ```bash
    git clone https://github.com/Astrrokid/MLproject1.git
    cd student-score-prediction
    ```

2. Install the necessary packages:
    ```bash
    pip install -r requirements.txt
    ```

3. Run the Flask application:
    ```bash
    python app.py
    ```

4. The application will run locally at `http://localhost:5000/`.

## Deployed Application

You can access the deployed version of the Student Score Prediction System here:

- **Deployed URL:** [https://mlproject1-fx7f.onrender.com/predictdata](https://mlproject1-fx7f.onrender.com/predictdata)

## API Endpoints

### `/predictdata`
- **Method:** `POST`
- **Description:** Takes user input data and returns the predicted math score.
- **Input:** Form data for `gender`, `race_ethnicity`, `parental_level_of_education`, `lunch`, `test_preparation_course`, `reading_score`, and `writing_score`.
- **Output:** The predicted math score.

### Example Request:

Send a POST request to `/predictdata` with the following fields:

- `gender`: The gender of the student.
- `race_ethnicity`: The student's race/ethnicity.
- `parental_level_of_education`: The highest level of education achieved by the student's parents.
- `lunch`: The student's lunch type.
- `test_preparation_course`: Whether the student took a test preparation course.
- `reading_score`: The student's reading score.
- `writing_score`: The student's writing score.

### Example Response:

```json
{
    "result": 78.5
}
