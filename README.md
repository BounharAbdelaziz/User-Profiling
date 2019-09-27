# User-Profiling
In order to provide diverse, tailored and targeted solutions to a member, the system needs to get to know it better. The more active the person is on the social network, the more the system will learn to know it better and will offer him solutions more adapted to his profile. Thus, I start from the fact that knowing the Sentiment (feeling) of the person on each Topic after detecting it with the techniques of Topic Modeling will allow me to better know what she likes to offer more relevant results and more targeted advertising.

# Sentiment Analysis:
Is a **classification** Model between two classes '1' or '0' **(Positive or Negative Sentiment)**. After the data import stage, we use the
CountVectorizer that transforms our message into a token matrix with their number of occurrences and passes them to the model so it can
can train on these vectorized data. Once we have transformed our data, we divide our dataset into two parts, Train and Test.

The next step is to instantiate a new model and then call **fit (X_train, y_train)** so that the model can find the right parameters that describes the datas and will divide our two classes while maximizing performance.

A loop is then established on the size of the test set to see how the **accuracy** varies depending on the size of the test set.
We then notice that it is generally equal to **98,xx%** and reaches a maximum of **99.53%** for the **Logistic Regression** model,
**99.03%** for the **Naive Bayes Classifier**, and **98.21%** by combining the **TF-IDF** technique before starting the training on the dataset.
For the **Random Forest** it reaches **98.65%**.


# Sentiment Scoring :
Is an Algoithm based on the library **Afinn** in particular for its method ** Afinn () ** which returns a score in the intervale [| -5,5 |]
and allow us to use this score to describe the feeling. If the score is strictly less than 0, the feeling is negative,
otherwise if it is equal to 0 then the feeling is neutral. If not, the feeling is positive. The **quality()** method that I defined allows splitting between these values ​​to determine the degree of feeling.


# Topic Modeling - POS-Tagging:
This Algorithm is based on the **NLTK** library, the message is first tokenized using **tokenize(message)** this method will remove spaces and punctuation. Next comes the step of **remove_stopWords_msg(POS_TOKENS)** which will remove the stop words from the list of POS-Tags pre-established, after that we can apply the method **pos_tagging()** which will tag the elements of the list and then we finish with our list of elements that describe our message. At this moment we can use the **chunk_msg ()** method that will take chunks (end of the message) responding to the chosen pattern which is all of the nouns that come after the verb, as it turned out that in the majority of cases,Topics come after the verb.

The results are therefore stored in their precise column namely the column 'keywords_interests', the data is stored in the form
{name of the person, the list of topics}.

## License
[Copyright © 2019 All rights reserved. Created and designed by Abdelaziz Bounhar] (https://www.abdelazizbounhar.com/).