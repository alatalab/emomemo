# emomemo
Train on messages received in Facebook chat and remember your emotional state depends on message.
Next replies with chatbot based on it.

To <a href="https://www.facebook.com/help/131112897028467/">download your Facebook data</a> you need to click you profile and choose Download a copy of your Facebook data below your General Account Settings. Next wait for a link in email.

To run notebook you'll need Python3, 
<a href="https://www.tensorflow.org/install/">Tensorflow</a> and 

```pip3 install -r requirements.txt```


You need to setup paths to download data and usernames which used in conversation. 

If you want a chatbot (latest cell), you also need setup FB page, API keys, SSL and async call model.

The model is based on <a href="https://arxiv.org/pdf/1408.5882.pdf">Convolutional Neural Networks for Sentence Classification by Yoon Kim</a> with static word2vec embedding trained on text received.
It performs over 90% on IMDB 50000 movie reviews, however for recall your emotion statement it needs to be trained on big number of conversations.

There are some problems with other existing Keras implementations - some of them use deprecated Graph API, some don't use external static word2vec, some limited to Convolution1D, single category, most did not ready for call via web service.

Possible improvements : add learning from aditional parameters like text replied, external word2vec or glove, mixed emotion state, Redis for async call.
