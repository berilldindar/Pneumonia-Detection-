# Pneumonia-Detection-
Pneumonia Detection with CNN,VGG16,AlexNET,GoogLeNET,RES-NET
DataSet Link: https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia
Expected from the Project
1- The data set given in the link consists of two classes, Normal and Pneumonia. In addition, the data set is divided into train, validation and test. However, when Pneumonia folders are examined, images are named as bacterial and viral. You are expected to divide and classify this data set into 3 classes: normal, bacterial pneumonia and viral pneumonia. Rearrange the data accordingly. While editing the data, put the images under the val folder into the appropriate folders in the train and reserve 10% of the train folder for validation. Show with a table how many samples are in the train validation and test groups on the basis of class in the data set. Do not add data to the test data set in any way, you can only folder according to needs.
2- After making the necessary adjustments about the data set, train at least 4 CNN models. In this context, you can either retrain ready-made models using transfer learning or create your own original model. Under this question, please explain in detail which models you have trained using which hyper-parameters, and if necessary, support them with visuals.
3- Draw the train accuracy, validation accuracy, train loss and validation loss curves for each CNN as a result of the training and add the image here.

4- As a result of the training, test each CNN model with the test data, calculate the Accuracy, Recall, Precision and F1 score values. Calculate the complex matrix and add an image here.

5- Interpret your results, which CNN failed or why did it succeed?



Project Description
In computer vision projects, the important thing is to load the image itself. I imported tqdm in order to see the loading of images as a progress bar. I noticed that all the images in the folder were different sizes from each other, and I resized them all by resizing them to (200,200). Sizing of images is important when working with neural networks. Each image is stored in RGB with 3 channels. Since this is unnecessary for X-Ray images, I converted the X-Ray images to grayscale with Opencv.
I uploaded the grayscale images I made with Opencv back to my project. Since there are nearly 6000 images in my project, I separated the files in my project with code. I did not perform any manual operation on the files. Since opencv stores the image as uint8, I converted it. My project consists of 3 categories. I observed the categories and numbers of images in the Train dataset. Bacteria has 2538 images, 1349 normal images and 1345 virus-related X-Ray images. I observed the visuals in the X-train series.
    I performed the same operations for the test dataset. I observed the number of images found in x_test and y_test. I also noticed that it takes quite a long time to load the datasets and decided to save them in a separate file using the pickle module. Bacteria, virus or regular expression are expressed as strings in the images. Since the neural network won't accept it that way, I converted it with one hot encoder. In order to reshape the X data, I gave the shapes that I resized the images. (None,200,200,1) “1” is the number of channels I created because I performed the conversion of photo channels.
     I increased the number of data used with Image Data Generator and set the validation_split to 0.1. I set the batch_size to 32. After all these processes, I checked the shapes of the images. I started training my CNN model. I gave the dimensions of my images as Input shape. By applying Max Pooling after 2 layers, I reduced the size of the input layer's volume. MaxPool is also known as a method that prevents overfitting. I went through the flatten process. I used the 'relu' activation function in each layer. In the last layer, since we have 3 categories, I used the categorical_crossEntropy error function and used the softmax activation function.
     
     
     
     
     You can experience the created repo and report your problems. thanks.
