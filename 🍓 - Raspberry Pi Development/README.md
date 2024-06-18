# 🍓 Raspberry Pi Development

Welcome to the Raspberry Pi Development folder. This directory contains projects developed for the Raspberry Pi 5, focusing on flower detection and video recording.

## Contents

### 1. [RPi5-flower-detection](https://github.com/Encila/RPi5-flower-detection)
This is the main program designed to detect and recognize objects, here flowers. It uses a model trained on Teachable Machine to identify different species, especially orchids. For more detailed information on installation, setup, and usage, refer to the README in the project repository.

### 2. [VideoRecorder](https://github.com/Encila/VideoRecorder)
This project uses Picamera2 to record videos that are used for training the models. For more detailed information on installation, setup, and usage, refer to the README in the project repository.

## Development Notes

### OpenCV Compatibility Issues
At the time of development, OpenCV did not support the Modul 3 Camera. To work around this limitation, I used PyQt and Picamera2 to achieve the desired functionality. This involved several tricks to integrate the camera feed into the application.

### Video Recording Format
For the VideoRecorder project, videos are recorded in a square frame format by default. This format is specifically chosen to be compatible with the requirements of Teachable Machine, making it easier to use the recorded videos for training machine learning models.

## Installation
To install these projects, clone the respective repositories to your local machine:

```bash
git clone https://github.com/Encila/RPi5-flower-detection.git
git clone https://github.com/Encila/VideoRecorder.git
```

Follow the setup instructions in each repository's README file to get started.
