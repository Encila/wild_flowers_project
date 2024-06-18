
# RPi5-Flower-Detection Project Documentation

## Project Overview

The RPi5-Flower-Detection project utilizes the Raspberry Pi Camera Module 3 on a Raspberry Pi 5 along with TensorFlow Lite and OpenCV to detect and classify flowers using a pre-trained model. The application displays the video feed with annotations using PyQt for visualization.

## Goal

The primary goal of this project is to develop a Python-based application capable of detecting and classifying flowers using a Raspberry Pi 5. The application aims to assist in the identification of various flower species, leveraging machine learning models trained with Teachable Machine.

## Issues Encountered

1. **Library Compatibility**: The project faced several compatibility issues with the Picamera2 library, which is still in beta.
2. **Camera Integration**: OpenCV couldn't work with the Raspberry Pi Camera Module 3, so an alternative solution using Picamera2 and PyQt was implemented.
3. **Power Usage**: The powerbanks used were insufficient for the power demands of the project, causing power alerts.
4. **Model Training Data**: The discrepancy in image quality between training and testing data impacted the model's performance.

## Outcome

The project resulted in a functional application capable of detecting and classifying flowers. However, several areas for improvement were identified, particularly regarding image quality and the robustness of the detection algorithm.

## Recommendations

1. **Alternative Data Collection Methods**: Develop a photo capture script to improve the quality of training data.
2. **Library and Script Improvements**: Monitor updates to the Picamera2 library and contribute patches if possible.
3. **Model Training Enhancements**: Collect more training data using the Raspberry Pi Camera Module 3 to improve model accuracy.
4. **Application Enhancements**: Improve the UI/UX of the application, potentially using Kivy instead of PyQt, and consider integrating more advanced detection algorithms like YOLO or Detectron2.
5. **Hardware Improvements**: Use higher quality cameras and ensure sufficient power supply for the Raspberry Pi setup.

## Detailed Setup Instructions

### Prerequisites

- Raspberry Pi 5 set up as per the [[Raspberry Pi Installation Guide]]
- Modul 3 IR or visible camera connected

### Step-by-Step Detection Setup

1. **Clone the Flower Detection Repository:**
   - Clone the repository containing the flower detection scripts:
   ```sh
   git clone https://github.com/Encila/RPi5-flower-detection.git
   cd RPi5-flower-detection
   ```
   
   The README file will guide you through the installation process.

2. **Install MiniConda and the Required Dependencies:**

   Make sure the paths are correct.
   Use the setup files ⚠️ FROM THE ROOT DIRECTORY :
   ```sh
   # If not installed
   source setup/setup-miniconda.sh

   source setup/setup.sh
   ```
   Ensure there are no problems during the installation.

3. **Run the Detection Script:**

   Execute the main detection script ⚠️ FROM THE ROOT DIRECTORY :
   ```sh
   python src/main.py
   ```
   You can use the `--model` and `--labels` args to change what's detected. Both arguments must be used simultaneously, or it won't work.
   You can also use the shortcut on the Desktop.

4. **Error Handling and Debugging:**

   Common issues include camera not detected or poor image quality.
   Ensure cameras are properly connected and use the `vcgencmd` or `rpicam-hello` commands to verify detection.
   For now, OpenCV doesn't work well with the Modul 3 cameras (`cv2.imshow()` and `cv2.imread()`). Picamera2 and PyQt will become unnecessary in this project once this issue is patched.

### Development

- **Branches:**
  - The `test` branch contains the beginning of a Kivy interface instead of a PyQt one. It can be used to develop UX/UI for the project.
  - The `dev` branch is dedicated to potential reworks.

### Usage

- **Running the Application:**
  To run the application with customs parameters:
  ```sh
  python src/main.py --model=model.tflite --labels=labels.txt
  ```

- **Exporting the Model from Teachable Machine:**
  Train your model on Teachable Machine.
  Export as TensorFlow Lite.
  Place the `.tflite` and `labels.txt` files in the models directory.
  Run the application with the new model.

### Troubleshooting

- **Library Compatibility:** Ensure libraries are correctly installed in the conda environment.
- **SSH Issues:** Consider running the application directly on the Raspberry Pi instead of over SSH.
