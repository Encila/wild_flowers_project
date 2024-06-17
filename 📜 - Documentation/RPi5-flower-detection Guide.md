# Prerequisites

- Raspberry Pi 5 set up as per the [[Raspberry Pi Installation Guide]] 
- Modul 3 IR or visible camera connected

# Step-by-Step Detection Setup

1. **Clone the Flower Detection Repository:**
   - Clone the repository containing the flower detection scripts:
```sh
git clone https://github.com/Encila/RPi5-flower-detection.git
cd RPi-flower-detection
```
   - The README file will guide you through the installation process.

3. **Install MiniConda and the Required Dependencies :** 
   - Make sure the paths are correct.
   - Use the setup files ***⚠️ FROM THE ROOT DIRECTORY***  :
     ```sh
     # If not installed
     source setup/setup-miniconda.sh
     
     source setup/setup.sh
     ```
   - Ensure there are no problem during the installation. 

4. **Run the Detection Script:**
   - Execute the main detection script  ***⚠️ FROM THE ROOT DIRECTORY*** :
     ```sh
     python src/main.py
     ```
   -  You can use the `--model` and `--labels` args to change what's detected. Both arguments must be used simultaneously, or it won't work.
   - You can also use the shortcut on the Desktop.

5. **Error Handling and Debugging:**
   - Common issues include camera not detected or poor image quality.
   - Ensure cameras are properly connected and use the `vcgencmd` or `rpicam-hello` commands to verify detection.
   - For now, OpenCV doesn't work well with the Modul 3 cameras (`cv2.imshow()`and `cv2.imread()`). `Picamera2` and `PyQt` will become unnecessary in this project once this issue is patched.

# Development 

1. **Branches:**
   - The `test` branch contains the beginning of a `Kivy` interface instead of a `PyQt` one. It can be use to develop UX/UI for the project.
   - The `dev` branch is dedicated to potential reworks.