-------------------
Package Requiments: 
--------------------
keras
keras.models - Sequential, Model
keras.layers - Dense, Dropout, Flatten, Activation, Embedding, LSTM, GRU, TimeDistributed
keras.callbacks - ModelCheckpoint, EarlyStopping, Callback
keras.utils.np_utils - to_categorical
keras.optimizers - Adam
matplotlib
os
time
google.colab - files
collections
tensorflow 
numpy
math
tf

--------------------
Model Architecture:
--------------------
Based on Zremba et al. (2014)

Zaremba, W., Sutskever, I., & Vinyals, O. (2014). 
Recurrent neural network regularization. 
arXiv preprint arXiv:1409.2329.þ
(https://arxiv.org/pdf/1409.2329.pdf)

----------------------
How to load the files:
----------------------
i) The files required for this code are the "Penn Tree Bank" data:
ptb.test.txt
ptb.train.txt
ptb.valid.txt

ii) Run the 1-2 cells and then select the files using the browsing button.

--------------------
How to train Model:
--------------------
Before training the model you should first load the files. See the above section.
In this code there are 4 network types -
Follow this steps to train a new model:
** Pick one of the following regularization types, for example:
type_1 = {"L":"none"} - for LSTM without dropout
type_2 = {"LD":"0.5"} - for LSTM with dropout (in this example dropout=0.5)
type_3 = {"G":"none"} - for GRU without dropout
type_4 = {"GD":"0.5"} - for GRU with dropout (in this example dropout=0.5)

** Run the "train_type" function. For example:
checkpoint_path_type_1, history_1 = train_type(type_1, train_data, valid_data, test_data, num_stepss, batch_size, vocabulary,num_epochs)
** Use the path of the trained model ("checkpoint_path_type_1") as a parameter for the test_validation_type function. For example:
test_validation_type(type_1, test_data, vocabulary, num_steps, batch_size, checkpoint_path_type_1,dataset_type="test")


--------------------
How to Load Model:
--------------------
The test_validation_type function uses the checkpoint_path_type parameter to load weigths for the trained model,
just run the function!

