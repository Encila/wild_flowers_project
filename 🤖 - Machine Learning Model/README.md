# 🤖 Machine Learning Model

Welcome to the Machine Learning Model directory. This folder contains the machine learning model and associated files used for detecting and recognizing wild plants.

## Contents

### 1. Model Files
- **model.tflite**: The exported model file in TensorFlow Lite format.
- **labels.txt**: The labels associated with the model, listing the classes it can recognize.
- **model_file**: The original Teachable Machine file used for training the model.

## Model Details

This model is specifically trained to recognize:
- **Orchids**: Various types of orchids, including pyramidal orchids and other varieties.
- **Humans**: To distinguish between plants and humans in the frame.

## Generating a Model with Teachable Machine

To generate a machine learning model using Google's Teachable Machine, follow these steps:

1. **Access Teachable Machine**:
   - Go to [Teachable Machine](https://teachablemachine.withgoogle.com/).

2. **Create a New Project**:
   - Click on "Get Started" and choose "Image Project" to create a new image classification project.

3. **Add Classes**:
   - Add the different classes you want your model to recognize. For this project, add classes for various types of orchids and humans.

4. **Upload Images**:
   - For each class, upload a sufficient number of images. Ensure the images used for training are of high quality and similar to those that the model will see during recognition.

5. **Train the Model**:
   - Once you have uploaded the images, click on "Train Model." Teachable Machine will process the images and train the model based on your input data.

6. **Export the Model**:
   - After training is complete, click on "Export Model." 
   - Choose "TensorFlow Lite" as the export format. This format is required to use the model in the recognition program.
   - Download the `model.tflite` file and the `labels.txt` file. These files will be used in your recognition program.

## Note on Project Status

Due to issues with the camera quality, the project could not be fully completed. However, the process above can be followed to generate new models once a more reliable camera setup is obtained.