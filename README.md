## Installation

- Install dfu-programmer:

    Linux: sudo apt-get install dfu-programmer
    Mac:   brew install dfu-programmer

- Python 2.7+ to run Easy AVR

## Steps

1. Startup [Easy AVR](https://github.com/dhowland/EasyAVR)

    ./EasyAVR/easykeymap.sh & <-- run on a background thread

2. Make modifications to the .dat file

3. Run File > Save Layout As...

4. Run File > Build Firmware

5. Hold PCB reset button for 10 seconds

6. Run these commands:

    **Note**: once the keyboard enters flash mode it won't work - have a backup keyboard or wrap this script in a timer

    sudo dfu-programmer atmega32u4 erase
    sudo dfu-programmer atmega32u4 flash /path/to/firmware.hex
    sudo dfu-programmer atmega32u4 start
