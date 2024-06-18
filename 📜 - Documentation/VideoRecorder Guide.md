
# VideoRecorder Project Documentation

## Prerequisites

- Raspberry Pi 5 set up as per the [[Raspberry Pi Installation Guide]]
- Modul 3 IR or visible camera connected
- The flower_detection conda environment set up per the [[RPi5-flower-detection Guide]]
- ***⚠️THE MODIFIED VERSION OF PICAMERA2*** (more info [here](#^2dce5f)) 

## Project Overview

The VideoRecorder project was developed to facilitate the collection of visual data using videos. This data is then split into numerous photos for training a machine learning model on Teachable Machine. The project required recording videos in a square format using the same camera for both data collection and the recognition program.

## Goal

The primary goal of the VideoRecorder project was to create a Python script capable of recording videos using a specific camera. These videos would be used to extract frames for training a machine learning model. The key requirements included:
- Recording videos in a square format.
- Using the same camera for both data collection and the recognition program.

## Issues Encountered

### Picamera2 Library Challenges
The main issue encountered was with the Picamera2 library, which is still in its beta form. Specific problems included:
- **Beta State of Picamera2:** The library had several bugs that required manual patches.
- **Manual Patching:** The user had to manually modify the library files to resolve these issues.

### Video Quality Issues
- **Low-Quality Videos:** The recorded videos were of poor quality with significant fluctuations due to weather conditions.
- **Low Frame Rate:** The videos had a very low frame rate, capturing only 1 or 2 images per second.
- **Insufficient Data for Training:** The quality and frame rate of the videos were insufficient for training a reliable model.

## Outcome

Despite the challenges, the project resulted in a functional script that could record videos using the specified camera. However, the low quality and frame rate of the videos indicated that this approach might not be viable for reliable model training. Key outcomes included:
- Successful creation of a video recording script.
- Identification of significant issues with video quality and frame rate.
- Recognition of the need for an alternative data collection method.

## Recommendations

Based on the outcomes and issues encountered, the following recommendations are made for future improvements:

### Alternative Data Collection Methods
1. **Photo Capture Script:**
   - Develop a script to capture photos instead of videos.
   - Photos would likely provide better quality and consistency for training data.

2. **Camera Upgrade:**
   - Consider using a different camera that provides higher quality and more stable video output.

### Library and Script Improvements
1. **Library Updates:**
   - Monitor updates to the Picamera2 library and integrate any patches or fixes as they are released.
   - Consider contributing to the library to help address the issues encountered.

2. **Script Enhancements:**
   - Refactor the script to improve its robustness and error handling.
   - Implement additional features such as automated quality checks on the recorded videos.

## Step-by-Step VideoRecorder Setup

1. **Clone the VideoRecorder Repository:**
   - Clone the repository containing the video recording scripts:
```sh
git clone https://github.com/Encila/VideoRecorder.git
cd VideoRecorder
```
   - The README file will guide you through the installation process.

2. **Activate MiniConda and the Required Dependencies:** 
   - Make sure the paths are correct.
   - Use the setup file :
```sh
source setup.sh
```
   - Ensure there are no problems during the installation.
   
3. **Run the VideoRecorder Script:**
    - Execute the main video recording script :
   ```sh
python main.py
   ```
    - You can use the `--duration`, `--width`, and `--height` args to change the recording settings.
    - You can also use the shortcut on the Desktop.
    
4. **Error Handling and Debugging:** 
    -  The current Picamera2 version contains an issue about previews. To patch it, you'll have to correct this files :
```sh
cd ~/miniconda3/envs/flower_detection//lib/python3.11/site-packages/picamera2/encoders
nano libav_h264_encoder.py
nano libav_mjpeg_encoder.py
```
    In the `_encode_`function, you will have to replace this line :
```py
frame = av.VideoFrame.from_ndarray(m.array, format=self._av_input_format, width=self.width)
```
    For this line : 
```py
frame = av.VideoFrame.from_ndarray(m.array, format=self._av_input_format)
```
    The error will be then patched from now on.
    - Common issues include camera not detected or poor image quality.
    - Ensure cameras are properly connected and use the `vcgencmd` or `rpicam-hello` commands to verify detection.
