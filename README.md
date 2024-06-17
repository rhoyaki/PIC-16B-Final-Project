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
Addition of new dataset to previous training data to experiment with using more data to train. Additional data only applies to this section/model. Three hidden dense layers of 258 neurons with a dropout layer of with rate = 0.2 after the first and second hidden layers and a dropout layer with rate = 0.1 after the third hidden layer. All hidden layers used ReLU activation function with he_normal kernel initializer.

**Classification Model**
Turn target labels from continous numerical column and try classification approach. Three hidden dense layers of 64 neurons with a dropout layer of with rate = 0.3 between the second and third hidden layers. All hidden layers used ReLU activation function with he_normal kernel initializer.

## Performance
**FNN Preliminary Model**
33.2% ± 0.051% MAPE on unseen data.

**FNN Model Type 2**
 26.0% -  28.0% MAPE on the validation set, and a 27.0% MAPE on unseen data. 

 **FNN Model Type 3**

**XGBoost Model**
33-36% MAPE on unseen data **with** 'rating' column
30-33% MAPE on unseen data **without** 'rating' column

**Lasso Model**
~38.4% MAPE on validation data.

**Additional Data Model (FNN)**
50 - 53% MAPE on the validation set, and a 52.0% MAPE on unseen data.

**Classification Model**
30-35% accuracy on validation set, and a 40% accuracy on unseen data.
~40% accuracy for hyperparameter tuned classification model.

## Conclusion
While our custom neural network perfomed better compared to some of the sklearn models, it is nowhere near perfect. The limitations of the model perfoming better can be because of failing to determine better features in predicting lifetime gross. It is possible that features not included in our dataset plays a big part in determining the movie success, such as the economy of when the movie was released, competition in the market, and marketing, which is difficult to quantify. The movie industry itself is difficult to predict because of that, and the specific features such as the runtime, number of votes, etc, might not be sufficient enough. There are a number of features that we dropped because we were unable to quantify them in a way that made sense, for example the director of a film or the company that produced the film. For a feature like ‘genre’ it is hard to objectively rank and quantify difference between each genre but we could bring in outside data that ranks genre’s based on a measure such as vote popularity or total number of films of that genre and use this ranking to manually encode numerical values for each genre. This approach is a bit difficult for features such as actors or directors where we might have to deal with thousands of unique values in these columns.
Many of the papers and projects approached the problem of predicting film gross as a classification task, so it makes it somewhat difficult to compare apples to apples. One advantage of our regression approach is the ability to take any movie, given its details such as budget, score, votes, etc, and use our model to give us the most interpretable form of a prediction in a dollar amount. Since our topic is by nature a linear regression problem, a classification approach needs to in some way abstract the continuous numerical data. Classification predicts a range of how much a film will make, our model can also give a range since we know the average relative error as it is our measure of performance. 
