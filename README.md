# CityTweetClassifier
This program is a Naive Bayes classifier for classifying the city from which a given tweet originated. The program takes in a training dataset, a test dataset, and an output file to write the predicted labels.

## Requirements
* Python 3.7 or higher
* pandas
* numpy
* nltk

## Installation
Clone the repository: git clone https://github.com/Abhi-Muvva/CityTweetClassifier.git
Navigate to the project directory: cd your-project
Install required packages: pip install pandas numpy nltk

## Usage
The program can be run from the command line with the following arguments:

python main.py <train_file> <test_file> <output_file>

<train_file>: Path to the training dataset file containing tweets and their corresponding city labels.
<test_file>: Path to the test dataset file containing tweets to be classified.
<output_file>: Path to the output file where the predicted labels will be written.
The training and test datasets should be text files where each line represents a single tweet in the following format:

<city_label> <tweet_text>

The city label should be one of the following: Los_Angeles,_CA, San_Francisco,_CA, San_Diego,_CA, Houston,_TX, Chicago,_IL, Philadelphia,_PA, Toronto,_Ontario, Atlanta,_GA, Boston,_MA, Orlando,_FL, Washington,_DC, Manhattan,_NY. The tweet text should be a string containing the text of the tweet.

The program uses a Naive Bayes classifier to classify the test tweets based on the words they contain. The words are first pre-processed by removing punctuation marks, converting to lowercase, removing stop words, and stemming. The program then calculates the frequencies of each word by city in the training dataset and stores them in a pandas DataFrame. The program then calculates the prior probability of each city based on the frequency of tweets from each city in the training dataset.

For each test tweet, the program calculates the posterior probability of each city given the words in the tweet using the Naive Bayes formula. The predicted city label for the tweet is then the city with the highest posterior probability.

The program writes the predicted labels for each test tweet to the specified output file in the following format:

<predicted_city_label> <tweet_text>

In addition to the predicted labels, the program also prints the top five words for each city based on their frequency in the training dataset.
