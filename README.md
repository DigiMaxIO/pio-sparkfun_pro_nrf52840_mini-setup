# note
This is an updated version of the original branch, with updated core & project files.
The original files were causing errors resulting in it not compiling in my PlatformIO IDE (latest build as of today is Core 4.3.4 & Home 3.2.2). I believe this is due to an updated structure requirement in the json and variant files. I have only tested this on MacOS, as that is my preferred OS for development, but this should work just fine on Windows as well.

# Sparkfun Pro nRF52840 Mini
Below are the instructions to setup PlatformIO for [SparkFun Pro nRF52840 Mini](https://www.sparkfun.com/products/15025) development.

## Prerequisites

PlatformIO IDE is installed.

## Installation/Setup

All files needed to add this board to PlatformIO are contained in this project's `files_to_install` directory. Everything outside of that is an actual PlatformIO project you can open in PlatformIO and use to test it!

1. Download this Git project.
2. Navigate to the PlatformIO [core_dir](https://docs.platformio.org/en/latest/projectconf/section_platformio.html#projectconf-pio-core-dir). This is `~/.platformio` on MacOS and `%HOMEPATH%\.platformio` on Windows.
3. Within the `files_to_install` directory:
    * Copy the file named "sparkfun_pro_nrf52840_mini.json" within this project from:`.\files_to_install\platforms\nordicnrf52\boards\` to your .platformio core directory at: `.\core_dir\platforms\nordicnrf52\boards`
    * Copy the directory within this project named "sparkfun_pro_nrf52840_mini" from: `.\files_to_install\packages\framework-arduinoadafruitnrf52\variants\` to your platformio core directory at:`.\core_dir\packages\framework-arduinoadafruitnrf52\variants\`
    * Again, but slightly different, copy the directory within this project named "sparkfun_pro_nrf52840_mini" from: `.\files_to_install\packages\framework-arduinoadafruitnrf52\bootloader\`
to your platformio core directory at: `.\core_dir\packages\framework-arduinoadafruitnrf52\variants\`
7. Add to the boards.txt data. (Optional, PlatformIO does not use this file at all but if you want to be thorough)
    * Edit the text document at your core directory: `.\core_dir\packages\framework-arduinoadafruitnrf52\boards.txt`
    * Copy the contents of the file within this project at: `.\files_to_install\packages\framework-arduinoadafruitnrf52\boards_sparkfun.txt` into the `boards.txt` file at the very bottom and save it.
8. Build the project and test the new setup. It should compile successfully. You can test the program by uploading to the board and connecting to the device over bluetooth with this iphone/android app: [NRF Connect](https://itunes.apple.com/us/app/nrf-connect/id1054362403). See the Sparkfun guide [nRF52840 Development with Arduino and CircuitPython](https://learn.sparkfun.com/tutorials/nrf52840-development-with-arduino-and-circuitpython#arduino-examples) for more details.
