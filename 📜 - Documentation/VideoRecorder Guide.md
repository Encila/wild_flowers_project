# Prerequisites

- Raspberry Pi 5 set up as per the [[Raspberry Pi Installation Guide]]
- Modul 3 IR or visible camera connected
- The flower_detection conda environment set up per the [[RPi5-flower-detection Guide]]
- ***⚠️THE MODIFIED VERSION OF PICAMERA2*** (more info [here](#^2dce5f)) 
  
# Step-by-Step VideoRecorder Setup

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