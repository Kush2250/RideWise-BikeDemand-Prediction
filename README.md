# RideWise: Bike Rental Prediction System

A machine learning application that predicts bike rental demand based on weather conditions and temporal factors.

## Project Overview

RideWise is a comprehensive bike rental prediction system that uses historical data to forecast the number of bike rentals based on various factors such as weather conditions, time of day, season, and more. The application provides an intuitive user interface for users to input parameters and receive predictions.

## Features

- **Predictive Analytics**: Uses Random Forest Regression to predict bike rental demand
- **Interactive UI**: User-friendly interface with sliders and selectors for input parameters
- **Hourly Predictions**: Option to view predicted rentals for all hours of the day
- **Prediction History**: Tracks and displays previous predictions
- **Data Visualization**: Graphical representation of hourly predictions

## Technical Stack

- **Python**: Core programming language
- **Pandas & NumPy**: Data manipulation and processing
- **Scikit-learn**: Machine learning model implementation
- **Streamlit**: Web application framework
- **Matplotlib**: Data visualization
- **Joblib**: Model serialization

## Project Structure

- `hour.csv`: Raw dataset containing bike rental information
- `create_model.py`: Script for data preprocessing and model training
- `app.py`: Streamlit application for user interaction
- `ridewise_model.pkl`: Serialized trained model
- `x_columns.pkl`: Feature columns for prediction
- `Project.ipynb`: Jupyter notebook with initial data exploration

## Data Processing Workflow

1. **Data Preprocessing**:
   - Column renaming for better readability
   - Log transformation of the target variable
   - Removal of unnecessary columns
   - One-hot encoding of categorical features

2. **Model Training**:
   - Random Forest Regressor with 100 estimators
   - 80/20 train-test split
   - Model serialization for later use

3. **Prediction Process**:
   - User input collection through the UI
   - Input preprocessing to match model requirements
   - Prediction using the trained model
   - Conversion of log predictions back to original scale

## How to Use

1. **Install Dependencies**:
   ```
   pip install streamlit pandas numpy scikit-learn matplotlib joblib
   ```

2. **Run the Application**:
   ```
   streamlit run app.py
   ```

3. **Input Parameters**:
   - Adjust sliders for temperature, humidity, and wind speed
   - Select season, month, hour, and other categorical variables
   - Click "Predict Rentals" to get results

4. **View Results**:
   - See the predicted number of bike rentals
   - Optionally view hourly predictions
   - Track prediction history

## Model Performance

The Random Forest Regressor was chosen for its ability to handle both numerical and categorical features effectively. The model was trained on historical bike rental data with the following preprocessing steps:

- Log transformation of the target variable to handle skewness
- One-hot encoding of categorical features
- Feature selection to remove redundant information

## Future Improvements

- Integration with real-time weather data
- Addition of more advanced models for comparison
- Geographic visualization of rental predictions
- User authentication and personalized predictions

## License

This project is open-source and available for educational and commercial use.

## Acknowledgements

The dataset used in this project is the Bike Sharing Dataset from the UCI Machine Learning Repository.