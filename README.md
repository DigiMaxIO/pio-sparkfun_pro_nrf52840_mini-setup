This is an updated version of the original branch, with updated bootloader, variant, and json files.
The original was causing errors resulting in it not compiling in my PlatformIO IDE (latest build as of today is Core 4.3.4 & Home 3.2.2). I believe this is due to an updated structure requirement in the json and variant files. 

# pio-sparkfun_nrf52840_mini-setup
Instructions for setting up PlatformIO for [SparkFun Pro nRF52840 Mini](https://www.sparkfun.com/products/15025) development.

## Prerequisites

PlatformIO IDE is installed.

## Setup

All files needed to copy to PlatformIO directories are contained in this project's `files_to_install` directory.

1. Download this Git project.
2. Navigate to the PlatformIO [core_dir](https://docs.platformio.org/en/latest/projectconf/section_platformio.html#projectconf-pio-core-dir). This is `~/.platformio` on Unix and `%HOMEPATH%\.platformio` on Windows.
3. Within the `files_to_install` directory:
    * Copy the file from this project:`.\files_to_install\platforms\nordicnrf52\boards\sparkfun_pro_nrf52840_mini.json` to your .platformio core directory at: `.\core_dir\platforms\nordicnrf52\boards`
    * Copy the directory from this project named "sparkfun_pro_nrf52840_mini" from: `.\files_to_install\packages\framework-arduinoadafruitnrf52\variants\sparkfun_pro_nrf52840_mini` to your platformio core directory at:`.\core_dir\packages\framework-arduinoadafruitnrf52\variants\`
    * Again, but slightly different, copy the directory from this project named "sparkfun_pro_nrf52840_mini" from: `.\files_to_install\packages\framework-arduinoadafruitnrf52\bootloader\sparkfun_pro_nrf52840_mini`
to your platformio core directory at: `.\core_dir\packages\framework-arduinoadafruitnrf52\variants\sparkfun_pro_nrf52840_mini`
7. Install boards.txt data.
    * Edit the text document at your core directory: `.\core_dir\packages\framework-arduinoadafruitnrf52\boards.txt`
    * Copy the contents of this file: `.\files_to_install\packages\framework-arduinoadafruitnrf52\boards_sparkfun.txt` into the `boards.txt` file at the very bottom and save it.
8. Build the project and test the new setup. It should compile successfully. You can test the program by uploading to the board and connecting to the device over bluetooth with this iphone/android app: [NRF Connect](https://itunes.apple.com/us/app/nrf-connect/id1054362403). See the Sparkfun guide [nRF52840 Development with Arduino and CircuitPython](https://learn.sparkfun.com/tutorials/nrf52840-development-with-arduino-and-circuitpython#arduino-examples) for more details.
