Package Requiments: 
--------------------
keras
keras.models - Sequential, Model
keras.layers - Dense, Dropout, Flatten, Activation, BatchNormalization, regularizers, Conv2D, MaxPooling2D
keras.callbacks - ModelCheckpoint, EarlyStopping
keras.utils - np_utils
keras - backend
matplotlib
keras.datasets - fashion_mnist
os 
time

--------------------
Model Architecture:
--------------------
Lenet5

--------------------
How to train Model:
--------------------
In this 6 code block there are 4 network types - each for every regularization type.
Follow this steps to train a new model:
- Pick one of the following regularization types:
type_1 = {"weight_decay":"0.001"}
type_2 = {"batch_normalization":"0.9"}
type_3 = {"with_dropout":"0.25"}
type_4 = {"without_regularization":"none"}
- Run the "train_type" function. For example:
checkpoint_path_type_1 = train_type(type_1, train_data, train_labels, test_data, test_labels)
- Use the path of the trained model ("checkpoint_path_type_1") as a parameter for the test_type function. For example:
test_type(type_1, test_data, test_labels, checkpoint_path_type_1)

--------------------
How to Load Model:
--------------------
The test_type function uses the checkpoint_path_type parameter to load wigths for the trained model,
just run the function!

