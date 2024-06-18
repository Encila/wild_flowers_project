# Hardware Requirements

- Raspberry Pi 5
- Modul 3 IR and visible cameras
- SD card
- Power supply / 2 PowerBanks
- HDMI cable and monitor
- USB keyboard and mouse
- 7' Touchscreen

# Step-by-Step Installation

1. **Prepare the SD Card:**
   - Download the latest Raspberry Pi OS from the official website.
   - Use Raspberry Pi Imager to flash the OS image onto the SD card.
   - Insert the SD card into the Raspberry Pi.

2. **Initial Setup:**
   - Connect the Raspberry Pi to a monitor using an HDMI cable.
   - Attach the USB keyboard and mouse.
   - Plug in the power supply to boot the Raspberry Pi.
   - Follow the on-screen instructions to complete the initial setup (set up language, Wi-Fi, etc.) if not initiated before.

3. **Change Keyboard Version :**
   -   In the Preferences > Mouse and Keyboard Seetings > Keyboard > Keyboard Layout,  choose French (AZERTY) for Variant
   
4. **Update the System :**
   - Open the terminal and run the following commands:
     ```sh
     sudo apt update
     sudo apt upgrade
     ```
   -  The admin account logs are : _fablabensefea / rpi5fablab_ 

5. **Set Up Cameras:**
   - Connect one of the Modul 3 cameras to the Raspberry Pi (only two MIPI connectors).
   - Ensure the cameras are detected using the command:
     ```sh
     rpicam-hello
     ```

6. **Install the Touchscreen:**
   - Use the command to install a virtual keyboard
```bash
	sudo apt install wvkbd
```
   - In File Manager > Edit > Preferences > General, take out the tick of "Do not ask option on executable launch" and put one on "Open files with single click" to avoid confirmation popups and be able to open the shortcup from the touchscreen easily.
   - A toggle script can be created on the homepage.
   
 7. **Information about the PowerBanks:**
   - The RPi5 needs 27W to work well. The touchscreen needs 1W to work well. An alert appears when the touchscreen and the RPi5 are interconnected and wired on one powerbank. 
   - We discovered even with a powerbank for each component (RPi5 and touchscreen) we still have this alert about 10 min after launching the nano-controller.
   - The solution would be to use a better powerbank.