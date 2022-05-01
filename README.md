# Deep Learning Chatbot 

The goal of this notebook is to create a chatbot, which can retain context during a conversation. 

## Dataset 
The dataset used for this model is the movie dialogue corpus dataset which is created and maintained by Cornell University. This dataset contains dialogue information and lines from various movies. The dataset is cleaned (removal of stop words) and structured properly in the notebook. The dataset into 2 parts, one consisting of questions and the other consisting of answers. This data structure is essential for the deep learning model used. 

## Model Architecture
The model used for creating the conversational chatbot is sequence to sequence ([Seq2Seq](https://arxiv.org/abs/1409.3215)). The Seq2Seq model uses the concepts from LSTM (Long Short Term Memory) for understanding and retaining "context". This model generates a sequence of data from input data which is also sequential. Using this architecture, we can solve a variety of problems such as image captioning, language translation, and of course, building a chatbot. The most important components in this architecture are the encoders and the decoders. Encoders process the whole sentence in one go, using an architecture like LSTM. They output a word vector when the EOS (End of Stream) is reached. Using that word vector representation, the decoder predicts what the output should look like. And after comparing it to the actual output, loss values are generated which are then reduced by backpropagation. For training, we feed the question list as encoder data while the answer list is fed as the decoder data. Here is a visual representation of the Seq2Seq model. 

<img src="https://docs.chainer.org/en/v7.8.1/_images/seq2seq.png" width="750" height="500">

## Model Training

The training for the model ran for 150 epochs, where the accuracy steadily increased. This is because there are over 2 million trainable parameters in the neural network. Some of the outputs from the decoder model when we had a conversation are tagged below. Some questions are answered better than others. The steep training curve is also attached below, showing the rate of learning and eventual convergence. 


<img src="https://drive.google.com/uc?export=view&id=1CTYJcJJABhwMPot3Qfo_R4ReKLPNnr1O" width="400" height="400">
<img src="https://drive.google.com/uc?export=view&id=1U2QtqJB1Mg3qH7HbrBqJMQl2L-5TEJug" width="400" height="300">
