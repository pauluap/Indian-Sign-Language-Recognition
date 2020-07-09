# Indian-Sign-Language-Recognition
Communication is very significant to human beings as it facilitates the spread of knowledge and forms relationships between people. We communicate through speech, facial expressions, hand signs, reading, writing or drawing etc. But speech is the most commonly used mode of communication. However, people with hearing and speaking disability only communicate through signs, which makes them highly dependent on non-verbal forms of communication. India is a vast country, having nearly five million people deaf and hearing impaired. Still very limited work has been done in this research area, beacuse of it's complex nature. Indian Sign Language (ISL) is predominantly used in South Asian countries and sometimes, it is also called as Indo-Pakistani Sign Language (IPSL). The purpose of this project is to recognize all the alphabets (A-Z) and digits (0-9) of Indian sign language using bag of visual words model and convert them to text/speech. Dual mode of recognition is implemeted for better results. Ths system is tested using various  machine learning classifiers like KNN, SVM, logistic regression and a convolutional neural network (CNN) is also implemented for the same. The dataset for this system is created manually in different hand orientations and a train-test ratio of 80:20 is used. The model gives very high accuracy rate.

## Getting Started
### Pre-requisites
Before running this project, make sure you have following dependencies - 
* [pip](https://pypi.python.org/pypi/pip)
* [Python 3.7](https://www.python.org/downloads/)
* [OpenCV 3.4.2.16](https://docs.opencv.org/3.0-beta/doc/py_tutorials/py_setup/py_setup_in_windows/py_setup_in_windows.html)
* [opencv contrib python 3.4.2.16](https://pypi.org/project/opencv-contrib-python/)

### Dataset
 Download the images from [here](https://drive.google.com/drive/folders/1SY67sDO2ROoOoBhTBIIDn17gStS0AvCB?usp=sharing)

Some images of the datset are shown below:
<img align="center" src="https://github.com/shag527/Indian-Sign-Language-Recognition/blob/master/Images/dataset.png" width="800" height="750">   

Now, using ```pip install``` command, include the following dependencies 
+ Numpy 
+ Pandas
+ Sklearn
+ Tensorflow
+ Keras
+ Opencv
+ Tkinter
+ Sqlite3
+ Pyttsx3
+ SpeechRecognition (Google speech API)

### Run Project
To run the project, perform the following steps -

#### To use our project
1. Take all the files and folders and put them in the same folder.
2. Now, go to the main.py file (Code folder->Predict signs folder) and run the file.
3. A tkinter window like this will open.
<img align="center" src="https://github.com/shag527/Indian-Sign-Language-Recognition/blob/master/Images/login.png">


4. Create your account to access the system.
5. Now, the main tkinter window will open.
<img align="center" src="https://github.com/shag527/Indian-Sign-Language-Recognition/blob/master/Images/main.png" >


6. Click on the desired button to access the respective service.

#### To create your own recognition system
1. To use our dataset, go to the dataset link given above and download the images.
2. To create your own dataset, following the steps given above, go to the create signs panel and create your own dataset of signs.
3. Now, divide the dataset into train and test by running the Dividing_Datset.py file in the preprocessing folder.
4. To create histograms and saving them to .csv file, run the create_train_hist and create_test_hist respectively by extrating the SURF features and clustering them using MiniKbatchMeans.
5. Lastly, go to the classification folder and run different python files to check the results. 
6. You can also train your model using a convolutional nueral network by running the CNN.py file in the classification folder.


## Workflow

### Preprocessing
Here 2 methods for preprocessing are used. First one is the background subtraction using additive method, in which first 30 frames are considered as background and any new object in the frame is then filtered out. Second one uses the skin segmentation concept, which is based on the extraction of skin color pixels of the user.

<p align="center">
  <br>
<img align="center" src="https://github.com/shag527/Indian-Sign-Language-Recognition/blob/master/Images/mask.png">       <img align="center" src="https://github.com/shag527/Indian-Sign-Language-Recognition/blob/master/Images/after mask.png">       <img align="center" src="https://github.com/shag527/Indian-Sign-Language-Recognition/blob/master/Images/canny.png">
  <br>
 Mask &nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp        After applying mask &nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp  Canny Edge Detection
</p>
  <br>
  
### Feature Detction and Extraction:
The Speeded Up Robust Feature (SURF) technique is used to extract descriptors from the segmented hand gesture images. These descriptors are then clusterized to form the similar clusters and then the histograms of visual words are generated, where each image is represented by the frequency of occurence of all the clustered features. The total classes are 36.
<p align="center">
  <br>
  <img align="center" src="https://github.com/shag527/Indian-Sign-Language-Recognition/blob/master/Images/surf.png">
</p>

### Classification
In this phase, various classifers are used in order to check the best classifier for prediction. The classifiers used are:

+ Naive Bayes
+ Logistic Regression 
+ K-Nearest Neighbours (KNN)
+ Support Vector Machine (SVM)
+ Convolution Neural Network (CNN)

### Results
Results can be visualized by running file [visualize_submissions.py](https://github.com/imRishabhGupta/Indian-Sign-Language-Recognition/blob/master/Visualization/visualize_submissions.py).

#### Accuracy without SURF

<p align="center">
  <br>
  <img align="center" src="https://github.com/imRishabhGupta/Indian-Sign-Language-Recognition/blob/master/Visualization/accuracy_without_surf.png">
        <br>  
  </p>
  
#### Accuracy with SURF

<p align="center">
  <br>
  <img align="center" src="https://github.com/imRishabhGupta/Indian-Sign-Language-Recognition/blob/master/Visualization/acuracy_with_surf.png">
</p>

### Credits
If there are any doubts or queries with the process, refer these posts, they are amazing -

+ [Post 1](https://ianlondon.github.io/blog/how-to-sift-opencv/)
+ [Post 2](https://ianlondon.github.io/blog/visual-bag-of-words/)

