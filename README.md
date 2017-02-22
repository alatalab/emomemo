# emomemo

### Description
Trains on messages received in Facebook chat and remembers your emotional state depending on the message.
Next replies with chatbot based on it.

### Prerequisites
To <a href="https://www.facebook.com/help/131112897028467/">download your Facebook data</a>, click on your FB profile and choose **Download a copy of your Facebook data** under **General Account Settings**. A link will be sent to your email associated with your Facebook account.

To run Python Notebook, you need:
* Python3, 
* <a href="https://www.tensorflow.org/install/">Tensorflow</a>, 
* and ```pip3 install -r requirements.txt```

You also need to set up paths to the downloaded Facebook data and usernames which were used in Facebook conversations. 

If you want a chatbot (latest cell), you also need to setup a FB page, API keys, SSL, and async call model.


### The Model

The model is based on <a href="https://arxiv.org/pdf/1408.5882.pdf">Convolutional Neural Networks for Sentence Classification by Yoon Kim</a> with static *word2vec* embedding trained on text received.
It performs with over 90% accuracy on IMDB 50000 movie reviews. However, to recognize your emotion statement, it has to be trained on a large number of conversations.

There are a few problems with other existing *Keras* implementations. Some of them use deprecated Graph API, some don't use external static word2vec, some are limited to Convolution1D, single category. Additionally, most cannot be called via web service.

**Possible improvements for future work**: add learning from additional parameters like conversation replies, external word2vec or glove, mixed emotion state, Redis for async call.
