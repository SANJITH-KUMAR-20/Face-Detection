# Face-Detection
Real Time Face Detection using Tensorflow and OpenCV

This repository has 5 different files
  1. Image_Collection.ipynb
  2. Augmentation.ipynb
  3. Checking.ipynb
  4. Loading_images_and_preparing_labels_and_training.ipynb
  5. Face_detection.ipynb

--->Image_Collection.ipynb:
  Here we use opencv to collect images from the camera and store it in appropriate folders.

Then use the labelme software to label every images based on having a face or not having a face, these labels and boundry boxes are stroed as JSON files.
--->Augmentation.ipynb:
  Now to create a larger dataset we augment the data using albumentations module and redefine the bounding boxes and labels.
  
--->Loading_images_and_preparing_labels_and_training.ipynb:
  1. Here we load in the data and preprocess it to prepare for training.
  2. We load in an existing CNN model called vgg16 (https://www.geeksforgeeks.org/vgg-16-cnn-model/)
  3. we create a Functional model to define our own custom training loop
  4. This model uses a custom localization loss (https://www.einfochips.com/blog/understanding-object-localization-with-deep-learning/)
  5. we then compile and fit the model to predict the label and the boundary boxes
  6. After the model is optimized we save the model in .h5 format

--->Face_detection.ipynb:
   1. We load in the model
   2. Using opencv we bring in data as images
   3. pass it to the model and display the result
