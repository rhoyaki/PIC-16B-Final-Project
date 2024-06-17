# Prediction of Movie Financial Performance based on Features

## Project Overview
  In a time where there are a menagerie of movies being produced and shown in theaters and many of them being box office “flops” despite the best efforts of marketing and publicity, we wish to analyze the possible reasons as to why certain movies do not perform well while others do. In essence we wish to use a neural network to predict the financial performance of films using attributes/features such as who worked on the film (actors and directors), length of the film, genre, etc.

## Group Contributions

Ryan: Data scraping, Data consolidation, Standardization, Feature Engineering for ‘years_since_oldest’ and ‘rating’, Preliminary model, Second Model, XGBoost model, Additional Data model, Classification

Kyo: Lasso, Feature Importance, Second Model, Third Model, Ensemble Modeling using Stacking, Random Search, Data Cleaning, Exploratory Data Analysis

## Models
**FNN Preliminary Model**
Two hidden dense layers with 20 neurons each and ReLU activation function with he_normal kernel initializer

**FNN Model Type 2**
The fully connected neural network (FNN) model constructed is designed to handle inputs of a specified shape and produce outputs of another specified shape. This type of neural network, also known as a dense network, connects each neuron in one layer to every neuron in the subsequent layer. The model architecture begins with an input layer comprising 64 neurons, using the ReLU (Rectified Linear Unit) activation function and He Normal kernel initializer. This is followed by a series of hidden layers: the first hidden layer consists of 128 neurons with ReLU activation and He Normal initializer, followed by a dropout layer with a 10% dropout rate to prevent overfitting. The second hidden layer also contains 128 neurons with ReLU activation and He Normal initializer. Subsequent layers include a dense layer with 64 neurons and ReLU activation, another dropout layer with a 20% dropout rate, and additional dense layers with 64 and 32 neurons respectively, both using ReLU activation and He Normal initializer. The model concludes with an output layer whose number of neurons matches the specified output shape, without an explicitly defined activation function, which is suitable for regression tasks. Constructed using the TensorFlow Keras Sequential API, the model is named "FNN_Model." It is designed for tasks requiring complex data representations and multiple layers of abstraction, such as regression, classification, and other predictive modeling scenarios.

**FNN Model Type 3**
Hyperparameter tuning with keras tuner for the following model structure:

**XGBoost Model**

**Lasso Model**

**Additional Data Model (FNN)**

**Classification Model**


## Performance
**FNN Preliminary Model**
33.2% ± 0.051% MAPE on unseen data.

**FNN Model Type 2**
 26.0% -  28.0% MAPE on the validation set, and a 27.0% MAPE on unseen data. 

 **FNN Model Type 3**

**XGBoost Model**
33-36% MAPE on unseen data **with** 'rating' column
30-33% MAPE on unseen data **without** 'rating' column

**Additional Data Model (FNN)**
50 - 53% MAPE on the validation set, and a 52.0% MAPE on unseen data.

## Conclusion

While our custom neural network perfomed better compared to some of the sklearn models, it is nowhere near perfect. The limitations of the model perfoming better can be because of failing to determine better features in predicting lifetime gross. It is possible that features not included in our dataset plays a big part in determining the movie success, such as the economy of when the movie was released, competition in the market, and marketing, which is difficult to quantify. The movie industry itself is difficult to predict because of that, and the specific features such as the runtime, number of votes, etc, might not be sufficient enough. Another error that could have occured that hindered our result could have been the mismatch between our features and our model. We dropped many features that seemed to not have strong correlation with lifetime gross. Because of that, we were left with only several columns, and the model might have perfomed better with more amounts of features.
