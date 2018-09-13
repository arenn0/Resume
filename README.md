# Information Retrieval - Homework 1
This is the first assignment for UIC - CS 582 Information Retrieval. This project is about processing the CiteSeer document 
collection, in order to extract some basic information about the distribution of words in the library.
## Getting Started
These instructions will provide a copy of the project up and running on your local machine for development and testing 
purposes. See _Installing_ for notes on how to deploy the project on a system.
### Requirements
* Python 3.6 or 2.7 https://www.python.org/downloads/
* `pip` should be already installed by default. Installation instructions 
[here](https://www.makeuseof.com/tag/install-pip-for-python/)
* List of the [stopwords](https://www.dropbox.com/s/5789sj8v07j2id0/stopwords.txt) to remove.
### Installing
* [Anaconda](https://www.anaconda.com/download/) (requires Python versions 3.6, 2.7)
Or
* [NLTK](https://pypi.org/project/nltk/) (requires Python versions 2.7, 3.4, 3.5, or 3.6)
Or
* `pip install nltk` installs NLTK via pip.

Check the installation by typing `import nltk`. If this command is executed with an error, be sure to include NLTK in 
the python path of execution. If you are using PyCharm you can aso configure PATH by navigating the File tab, clicking 
on Settings and adding NLTK package in the tab Project Interpreter.
##Running the Program
This program requires a folder which contains the corpus of documents to analyze **and** a file that contains the list 
of stopwords to remove in order to work properly. The program takes as first argument the path (absolute or relative) of
 the directory and as second argument the path (absolute or relative) of the stopwords file.
 ###Tasks
1. Preprocess the collection. This preprocessing stage includes a function that _only_ tokenizes the text on 
whitespace and _removes_ punctuation. Everything that is included in Python `string.punctuation` is considered 
punctuation and it is deleted **without** replacement. <br>This implies that words like model-based or quick-start become 
modelbased and quickstart. On one hand, this reduces the syntactical meaning of the term, on the other it does not 
reduce the semantic meaning, which is extremely useful when we want to process words like those ones, that can be also
quite relevant. <br>
For this preliminary function I decided not to convert the uppercase words in lowercase, because I wanted to highlight 
the difference between a sketchy function and a more precise one. 

2. Run the code to answer the following questions:
    1. What is the total number of words in the collection? <br>
        The total number of words in the collection is: 476173
    2. What is the vocabulary size? (i.e., number of unique terms). <br> The total number of unique words is: 24683
    3. What are the top 20 words in the ranking? (i.e., the words with the highest frequencies). <br> The top 20 words 
    are:
        [('the', 22235), ('of', 18586), ('and', 14069), ('a', 12099), ('to', 11224), ('in', 8018), ('for', 7033), 
        ('is', 6556), ('that', 4801), ('are', 3730), ('on', 3546), ('The', 3421), ('with', 3091), ('an', 2936), 
        ('as', 2838), ('this', 2720), ('by', 2645), ('we', 2603), ('We', 2535), ('be', 2498)]
    4. From these top 20 words, which ones are stop-words? <br> All the 20 words are stopwords
    5. What is the minimum number of unique words accounting for 15% of the total number of words in the collection? 
    <br> The number is: 5 {'the': 0.04669, 'of': 0.03903, 'and': 0.02955, 'a': 0.02541, 'to': 0.02357}

3. Integrate the Porter Stemmer (from NLTK library) and a stopword eliminator. In this phase I assured that **uppercase** 
words were **converted** in lowercase, because it produced a more reliable result (One of the most frequent tokens -before 
 conversion- was 'We', which is eliminated after conversion because it is part of the stopwords). 
 Finally, run the code to answer the following questions:
    1. What is the total number of words in the collection? <br>
        The total number of words (without stopwords) in the collection is: 259362, if we do not remove stopwords the 
        number of words remains 476173
    2. What is the vocabulary size? (i.e., number of unique terms). <br> The total number of unique words is: 13458
    3. What are the top 20 words in the ranking? (i.e., the words with the highest frequencies). <br> The top 20 words 
    are:
       [('system', 3741), ('data', 2691), ('agent', 2688), ('inform', 2398), ('model', 2315), ('paper', 2246), 
       ('queri', 1905), ('user', 1756), ('learn', 1740), ('algorithm', 1584), ('1', 1551), ('approach', 1544), 
       ('problem', 1543), ('applic', 1522), ('present', 1507), ('base', 1486), ('web', 1439), ('databas', 1424), 
       ('comput', 1411), ('method', 1223)]
    4. From these top 20 words, which ones are stop-words? <br> All the 20 words are stopwords
    5. What is the minimum number of unique words accounting for 15% of the total number of words in the collection? 
    <br> The number is: 21 {'system': 0.01442, 'data': 0.01038, 'agent': 0.01036, 
    'inform': 0.00925, 'model': 0.00893, 'paper': 0.00866, 'queri': 0.00734, 'user': 0.00677, 'learn': 0.00671, 
    'algorithm': 0.00611, '1': 0.00598, 'approach': 0.00595, 'problem': 0.00595, 'applic': 0.00587, 'present': 0.00581, 
    'base': 0.00573, 'web': 0.00555, 'databas': 0.00549, 'comput': 0.00544, 'method': 0.00471, 'result': 0.00463}
    
    
 ##Built With
1. [Python](https://docs.python.org/3/) v3.7
2. [NLTK](https://www.nltk.org/install.html) library
3. [Pycharm](https://www.jetbrains.com/pycharm/) IDE By JetBrains
##Author
* **Alessandro Rennola**, M.Sc. University of Illinois at Chicago