<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/catiaspsilva/README-template">
    <img src="images/gators.jpg" alt="Logo" width="150" height="150">
  </a>

  <h3 align="center">README Template</h3>

  <p align="center">
    A README template to jumpstart your projects!
    <br />
    <a href="https://github.com/catiaspsilva/README-template/blob/main/images/docs.txt"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="#usage">View Demo</a>
    ·
    <a href="https://github.com/catiaspsilva/README-template/issues">Report Bug</a>
    ·
    <a href="https://github.com/catiaspsilva/README-template/issues">Request Feature</a>
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#dependencies">Dependencies</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#authors">Authors</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

In this project, we utilized transfer learning to design a Convolutional Neural Network architecture (with the ResNet50 pre-trained model) to classify 10 different image brand logos. The 10 classes are as follows: Nike, Adidas, Ford, Honda, General Mills, Unilever, McDonald's, KFC, Gator, 3M.

<!-- GETTING STARTED -->
## Getting Started

Clone this repository or the files you are interested in using.

`train.ipynb` is used to train our model using your dataset.

`test.ipynb` is used to test the model's performance by making inference on your test set; this file expects all of the test images to be a part of the classes that the model was trained on.

`test_unknown.ipynb` is also used to test the model's performance by making inference on your test set; however, this file can handle test images that are not a part of the classes that the model was trained on. These classes will be classified as class -1.

### Dependencies

This project can be run on HiPerGator using Juyter Notebook using the `Tensorflow-2.7.0` kernel. 

<!-- USAGE EXAMPLES -->
## Usage

This project consisits of three functions: `train`, `test` and `test_unknown`

ATTENTION: If the `best_model.h5` file is not in the repository that is because it is too large. Please download from canvas to verify our model.

### Train Function:
This is the function that trains the model. 

The function has all imports already declared in the first cell of the function.

Note: This function expects there to be 10 classes. If you wish to train the model with a different number of classes, you must change the line of code `outputs = tf.keras.layers.Dense(10, activation='softmax')(x)`, change the '10' to the number of classes you wish to train on. This architecture was designed to classify 10 classes of specific image brand logos, we cannot speak to the performamce of the architecture on a different number of classes or different genre of images.

Step 1:
This function takes a numpy array data set in the form (Features x Number of Samples), specifically in this case it is expecting 270,000 features correspondning to a 300x300 RGB image. The default file path is input here in the form `data_train.npy` which should be in the same root directory as the `train.ipynb` file, please update if the file name is changed.

Step 2:
The next step is to load the labels which is expecting a one-dimensional array in the form (Number of Samples,). The default file path is input here in the form `labels_train_corrected.npy` which should be in the same root directory as the `train.ipynb` file, please update if the file name is changed.

Note 1: 
This is the filepath to which the train_test_split will save the resulting test data and label data, for testing later using the `test` and `test_unknown` functions .

Step 3:
The filepath to the saved model is specified here, which by default is `best_model.h5`, please update if the file name is changed.

Step 4: This will load a previously saved model specified in Step 3, please comment out this line if there is no saved model (this would be the case if you are training the model for the first time).

### Test Function:
 This function uses the previously trained model to make inference on the test data when there are no unknown classes.

ATTENTION: If grading our model, this is the function you will use to evaluate performance (without unknown classes). Please make sure to have our weights downloaded from canvas to your path with the name `best_model.h5`.

Step 1:
This function takes a numpy array test set in the form (Features x Number of Samples), specifically in this case it is expecting 270,000 features correspondning to a 300x300 RGB image. The default file path is input here in the form `x_test.npy` which should be in the same root directory as the `test.ipynb` file, please update if the file name is changed.

Step 2:
The next step is to load the labels which is expecting a one-dimensional array in the form (Number of Samples,). The default file path is input here as `t_test.npy` which should be in the same root directory as the `test.ipynb` file, please update if the file name is changed.

Step 3:
The filepath to the saved model is specified here, which by default is `best_model.h5`, please update if the file name is changed.

Note 1:
This will output both a Classification Report and a Confusion Matrix.
The classification report will return the metrics: precision, recall, f1-score, support and accuracy.
The confusion matrix will return both the correctly and incorrectly classfied samples based on their labels.

### Test_Unknown Function:
 This function uses the previously trained model to inference on the test data when there is an unknown class or class not a part of the 10 logos our model was trained on.

ATTENTION: If grading our model, this is the function you will use to evaluate performance (with unknown classes). Please make sure to have our weights downloaded from canvas to your path with the name `best_model.h5`.

Step1:
This function takes a numpy array test set in the form (Features x Number of Samples), specifically in this case it is expecting 270,000 features correspondning to a 300x300 RGB image. The default file path is input here in the form `x_test.npy` which should be in the same root directory as the `test.ipynb` file, please update if the file name is changed.

Step 2:
The next step is to load the labels which is expecting a one-dimensional array in the form (Number of Samples,). The default file path is input here as `t_test.npy` which should be in the same root directory as the `test.ipynb` file, please update if the file name is changed.

Step 3:
The filepath to the saved model is specified here, which by default is `best_model.h5`, please update if the file name is changed.

Note 1:
This will output both a Classification Report and a Confusion Matrix.
The classification report will return the metrics: precision, recall, f1-score, support and accuracy.
The confusion matrix will return both the correctly and incorrectly classfied samples based on their labels.


<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.


<!-- Authors -->
## Authors

Bryan Etzine - bryanetzine@ufl.edu  
Dean Ward - dward2@ufl.edu  
Daniel Giraldo - danielgiraldo@ufl.edu  

<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements

* [Catia Silva](https://faculty.eng.ufl.edu/catia-silva/)

## Thank you

<!-- If this is useful: [![Buy me a coffee](https://www.buymeacoffee.com/assets/img/guidelines/download-assets-sm-1.svg)](https://www.buymeacoffee.com/catiaspsilva) -->
