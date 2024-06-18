# 📚 Databases

Welcome to the Databases directory. This folder contains all the images and videos used for training and testing our wild plant detection and recognition models.

## Contents

- ~~**Infrared (IR) Database**: Collection of infrared images.~~ *(Could not be created due to the poor quality of the IR Module 3 Camera)*
- **Visible Light Database**: Collection of visible light images.
- **Videos and Photos**: Various video and photo files taken with different devices.

## Importance of Consistency in Camera Usage

To ensure better recognition accuracy, it is crucial to use the same camera for both the learning (training) phase and the recognition (testing) phase. Consistency in the imaging device helps maintain uniformity in image quality and characteristics, which is vital for the performance of machine learning models.

### Main Issues with the Modul 3 Camera

During our project, we encountered several issues with the Modul 3 Camera:

1. **Poor Video Quality**: The video quality produced by the Modul 3 Camera was subpar, leading to difficulties in accurately training our models.
2. **Overexposure**: The camera often overexposed the images, resulting in loss of crucial details needed for plant recognition.
3. **Weather Sensitivity**: The camera was highly sensitive to weather conditions, which caused significant variability in the captured images. This variability made it challenging to obtain reliable data over time.
4. **IR Dataset Limitation**: We were unable to create a usable infrared (IR) dataset because the only IR camera we had was the IR Modul 3 Camera, which was of too poor quality to produce reliable images.

These issues highlighted the need for a more consistent and reliable camera setup to achieve our project goals.

## Data Sources

### Raspberry Pi 5 with Modul 3 Camera

- **Videos**: Videos taken using the Raspberry Pi 5 and the Modul 3 Camera. These videos were primarily used for initial testing and experimentation.

### iPhone 11 Pro

- **Photos and Videos**: High-quality photos and videos captured using an iPhone 11 Pro. These were used to supplement the dataset and provide a comparison to the Modul 3 Camera output. The iPhone 11 Pro photos, especially the orchid photos, were used for training the model in this repository.

## Conclusion

For future projects, it is recommended to use a camera with consistent performance and reliable image quality. The data in this directory will serve as a valuable resource for understanding the limitations of the Modul 3 Camera and the importance of using a robust imaging device for machine learning applications.

Feel free to explore the files in this directory and use them for further research and development.
