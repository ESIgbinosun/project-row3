# IT201/2-3(Fire Brigade)

## About this project
For this project we had to create a raspberryPi controlled car that can be used in rescue situations.
Our idea was a firebrigade assitance car that can be remotely controlled by an app on your phone.
Our project contains the following functionalities: <br>
- Orientation (magnetometer)
- Critical temperature warning (temperature sensor)
- Low/high water level
- Water Pump
- Movement water hose (servo)
- Siren (speaker/light)
- Speed in m/s (wheel encoder)
- Control application (Java)



## Before starting
Before starting with this product make shure you have an android device available for the application. The application was designed for a screen ratio of 3040 x 1440 pixels in landscape mode. If you use a smaller/bigger screen, the layout may not be optimal.

## Installation

First make shure your system is up-to-date by using the following commands:
sudo apt-get update
sudo apt-get upgrade

Enter the command sudo raspi-config on your raspberryPi and go to interface options. Now enable SPI, I2C and Camera. Now reboot.

For the use of this code the following external libraries are needed on the raspberryPi:
- wiringPi<br>
     sudo apt-get install wiringPi <br>
- OpenCV<br>
    https://solarianprogrammer.com/2019/09/17/install-opencv-raspberry-pi-raspbian-cpp-python-development/
- pigpio <br>   
     https://abyz.me.uk/rpi/pigpio/download.html
- fmod<br>
     https://wiki.debian.org/FMOD     


To download the application install AndroidStudio and open the Java app file from this directory. 

## Code explanation
-  Low/high water level is responsible for the measuring of the water level in the tank. Base on the level of water it gives a high or low waterlevel. The code is written in C. File https://gitlab.fdmci.hva.nl/balalib/project-row/-/blob/WaterPomp/Water_pomp/water_level_sensor.c contains the code of water level before running this code the Installation process must be done first. The libary that is needed is wiringPi. 
-  Water Pump is an essential part of the concept it make sure to pump the water out of the tank. The Code is pretty simple with a switch case on command you can turn the pump on/off. File https://gitlab.fdmci.hva.nl/balalib/project-row/-/blob/WaterPomp/Water_pomp/waterPomp.c contains the code and is written in C. The libary that is needed is wiringPi. 
- wheel encoder measure the speed of the rover itself. In the code there are uses of interupts to make sure that after every second a caculation takes place for the speed. The caculation gives back the value in RPM. File https://gitlab.fdmci.hva.nl/balalib/project-row/-/blob/Wheel-encoder/Wheel_encoder/speedo.c contains the code and is written in C. The libary that is needed is wiringPi. 

## How to use

## Important Information

## Contact information
Joris Brouwer: joris.brouwer2@hva.nl<br>
Aghead Bilal: aghead.bilal@hva.nl<br>
Bilal Malik: bilal.malik2@hva.nl<br>
Nassim Mengat: nassim.mengat@hva.nl<br>
Stefano Igbinosun: stefano.igbinosun@hva.nl
