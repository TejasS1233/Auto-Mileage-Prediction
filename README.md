# Auto MPG Prediction using Multiple Linear Regression

This project demonstrates how to build, train, and evaluate a multiple linear regression model to predict the fuel efficiency (Miles Per Gallon - MPG) of a car based on its features.

## 📝 Project Description

The goal of this project is to predict a car's MPG using various attributes such as its number of cylinders, weight, horsepower, and country of origin. This serves as a classic introductory machine learning project that covers the entire data science workflow, from data cleaning and feature engineering to model evaluation.

## 📊 Dataset

The project utilizes the "Auto MPG" dataset, a well-known public dataset from the UCI Machine Learning Repository. It was loaded directly from the Seaborn library for convenience.

The dataset includes the following features:

- **mpg**: The target variable we want to predict (continuous)
- **cylinders**: Number of cylinders in the engine (multi-valued discrete)
- **displacement**: Engine displacement in cubic inches (continuous)
- **horsepower**: Engine horsepower (continuous)
- **weight**: Vehicle weight in pounds (continuous)
- **acceleration**: Time to accelerate from 0 to 60 mph (continuous)
- **model_year**: Year of manufacture (multi-valued discrete)
- **origin**: The car's country of origin (categorical: USA, Europe, Japan)
- **name**: The unique name of the car (identifier)

## ⚙️ Methodology

The project followed a structured machine learning workflow:

### 1. Data Loading & Inspection

The dataset was loaded into a pandas DataFrame. Initial inspection was performed to check for data types and missing values.

### 2. Data Cleaning

The horsepower column contained a few missing values, which were handled by filling them with the median value of the column.

### 3. Feature Engineering

- The **origin** column, being categorical, was converted into numerical format using one-hot encoding. This created new binary columns (japan, europe) for the model to use.
- The **name** column was dropped as it's a unique identifier and provides no predictive value.

### 4. Model Preparation

- The data was split into features (X) and the target variable (y)
- The dataset was then divided into a training set (80%) and a testing set (20%) to allow for unbiased model evaluation

### 5. Model Training

A Multiple Linear Regression model from the scikit-learn library was trained on the training data.

### 6. Model Evaluation

The trained model was used to make predictions on the unseen test set. Its performance was evaluated using the following metrics:

- **R-squared (R²)**: Measures the proportion of the variance in the target variable that is predictable from the features
- **Root Mean Squared Error (RMSE)**: Indicates the average magnitude of the prediction error, in the same units as the target (MPG)

## 🚀 How to Run

1. **Clone the repository** or download the source code.

2. **Install the required libraries**. Make sure you have Python installed, then run the following command in your terminal:

   ```bash
   pip install pandas numpy seaborn matplotlib scikit-learn
   ```

3. **Execute the Python script** or Jupyter Notebook. Run the main file to perform the data processing, model training, and evaluation steps.

## 📈 Results

The final model demonstrated strong predictive performance on the test data:

- **R-squared (R²): 0.85**  
  This indicates that our model can explain approximately 85% of the variability in car MPG.

- **Root Mean Squared Error (RMSE): 3.23 MPG**  
  This means that, on average, the model's predictions are off by about 3.23 miles per gallon.

The scatter plot of actual vs. predicted values visually confirms that the model's predictions are closely aligned with the actual MPG values.

## 🛠️ Technologies Used

- **Python 3.x**
- **pandas** - Data manipulation and analysis
- **numpy** - Numerical computing
- **seaborn** - Statistical data visualization
- **matplotlib** - Plotting library
- **scikit-learn** - Machine learning library

## 📊 Key Insights

- Vehicle weight and horsepower are the strongest predictors of fuel efficiency
- Cars from Japan tend to have better fuel efficiency compared to American and European cars
- The model performs well across different car types and years
- Feature engineering (one-hot encoding for categorical variables) significantly improved model performance

## 🤝 Contributing

Feel free to fork this project and submit pull requests for any improvements or additional features.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
