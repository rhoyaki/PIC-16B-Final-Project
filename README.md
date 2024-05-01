# Prediction of Movie Financial Performance based on Features
  In a time where there are a menagerie of  movies being produced and shown in theaters and many of them being box office “flops” despite the best efforts of marketing and publicity, we wish to analyze the possible reasons as to why certain movies do not perform well while others do. In essence we wish to use a neural network to predict the financial performance of films using attributes/features such as who worked on the film (actors and directors), length of the film, genre, etc.

Ryan: As a student of the School of Sciences, I’m not as familiar with the math/engineering side of computer science. That said, I am a Cognitive Science major and I do have an interest in how humans and machines learn. To me, the most interesting application of machine learning to me is the ability to find trends and novel patterns/combinations that humans cannot easily perceive. My interest in this project lies in wanting to know what the best predictors of a box office hit are, as this would be a painstaking task to collect data by hand, and then to try and look for patterns at a surface level, if that would even be possible for a human.

Kyo: The relationship between this project and my major is evident through the shared focus of numbers. As a Mathematics of Computation major, I work with numbers in dealing with problems that require critical thinking in regards to analyzing, optimizing, and calculating. As with this project, the purpose is to predict the financial performance of films, which adds an extra step of “prediction” with the help of neural networks when approaching numerical problems. I am interested in this project because of a personal interest in movies. I wish to utilize this model to figure out which features about a film can effectively predict the popularity of a film. 

  The main resource needed is a dataset that contains a given film and some of its features, such as length, director, actors, genres, etc. This data set from Kaggle, https://www.kaggle.com/datasets/thegoanpanda/imdb-top-2000-movies
contains some of the necessary data. To get data such as final box office revenue, we would need to use data scraping on sites such as Wikipedia to obtain such information. We would also like to create a new variable that represents the prestige of the actors in the film either as a proportion of the total named characters/actors or a flat quantitative count.To do this we would need a bar to determine if an actor is considered “famous” and create a separate data frame for actors that can be consolidated into an actor_prestiege_score for our movie data frame. It also may prove insightful to do the same for directors. There are many other features about a film that we should look into, such as genre, country, budget, content rating, and duration. Having more features is better as it will allow us to figure out the best predictors for a movie’s financial performance from a large feature dataset. Therefore, another kaggle dataset is https://www.kaggle.com/datasets/danielgrijalvas/movies, which has many more features that we can look into. 
Previous related work includes Predicting box-office success of motion pictures with neural networks | Request PDF, which uses a Multi Layer Perceptron (MLP) neural network model with two hidden layers, and aims to categorize a film in one of the nine categories, which symbolizes how successful a movie was. The results were that the “neural networks employed in this study can predict the success category of a motion picture before its theatrical release with pinpoint accuracy (i.e. Bingo) with 36.9% and within one category with 75.2% accuracy”. Further experimentation should be done with these results, as it is not very good. Some improvements that we can make for our project is to include production budget and advertising budget, as those variables are important in determining the success of a movie. 
Another article, Performance Predictions of Sci-Fi Films via Machine Learning, which uses multiple KNN variants, including fine KNN, medium KNN, and weighted KNN to determine the performance prediction of Sci-fi films. The results show that the “fine KNN algorithm provides the highest accuracy of 93%, but it has the lowest speed among the three classes. On the other hand, the Medium KNN classifier has the highest accuracy for the Average class, with a value of 98%, but the lowest for the Hit class, with a value of 48%. The most consistent classifier is the weighted KNN classifier, which provides consistent estimates for average, below average, and flop at rates of 97%, 94%, and 93%, respectively. However, it did not perform as well with the Hit class as it did with others. The three classifiers somehow provide excellent accuracy, ranging from 90.3–93%”. An improvement for this project to reduce the error is to include more data scraping from other sources such as Wikipedia. 

### The required tools and skills include: 
Data scraping to obtain relevant information
Data preprocessing to clean and format data
Pandas and Matplotlib for data wrangling and visualization 
Feature selection/engineering to pick the best features to use in the final model
Error visualization/analysis to understand where the model makes mistakes

### From this project we will learn:
Data scraping from web
Working with Neural Networks:
- Neural network architect
- Multilayer perceptron
- Convolutional Neural Networks
- Backpropagation
Tensorflow and PyTorch for Deep Learning
Linear Algebra:
- Matrix and Vector calculations
- Minimization of loss function

# Group Members and Timeline:

### Timeline:
- Acquisition of data
- Web scraping for additional features
- Combination of data/dataframes into one dataframe
- Feature Selection
- Neural Network training
- Evaluation
- Visualization of Error
  
Ryan Hu:
By May 10th: Acquisition of target data (financial data)
By May 20th: Creation of director_score and actor_score variables for complete dataframe
By May 30th: Evaluation, Visualization of Error

Kyo Imura:
By May 10th: Acquisition of data, web scraping, preprocessing?
By May 20th: Feature selection, NN training, optimization
By May 30th: Evaluation, Visualization of Error
