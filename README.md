# Prediction of Movie Financial Performance based on Features

## Project Overview
  In a time where there are a menagerie of movies being produced and shown in theaters and many of them being box office “flops” despite the best efforts of marketing and publicity, we wish to analyze the possible reasons as to why certain movies do not perform well while others do. In essence we wish to use a neural network to predict the financial performance of films using attributes/features such as who worked on the film (actors and directors), length of the film, genre, etc.

## Models

The fully connected neural network (FNN) model constructed is designed to handle inputs of a specified shape and produce outputs of another specified shape. This type of neural network, also known as a dense network, connects each neuron in one layer to every neuron in the subsequent layer. The model architecture begins with an input layer comprising 64 neurons, using the ReLU (Rectified Linear Unit) activation function and He Normal kernel initializer. This is followed by a series of hidden layers: the first hidden layer consists of 128 neurons with ReLU activation and He Normal initializer, followed by a dropout layer with a 10% dropout rate to prevent overfitting. The second hidden layer also contains 128 neurons with ReLU activation and He Normal initializer. Subsequent layers include a dense layer with 64 neurons and ReLU activation, another dropout layer with a 20% dropout rate, and additional dense layers with 64 and 32 neurons respectively, both using ReLU activation and He Normal initializer. The model concludes with an output layer whose number of neurons matches the specified output shape, without an explicitly defined activation function, which is suitable for regression tasks. Constructed using the TensorFlow Keras Sequential API, the model is named "FNN_Model." It is designed for tasks requiring complex data representations and multiple layers of abstraction, such as regression, classification, and other predictive modeling scenarios.

## Performance



## Conclusion

