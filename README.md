#Classify objects in a wireless transmitted video.
---
This was our class project in 2nd semester,
our Aim was to classify objects in a video that was wirelessly transmitted from Raspberrypi-3

##Idea and Method of execution
---
To classify objects in a video we are going to use Darkflow which are based on darknet. Darknet is written in c and using YOLO algorithm.

Here are some resouces how yolo algorithm works.

youtube link: https://www.youtube.com/watch?v=4eIBisqx9_g

Research paper: https://pjreddie.com/media/files/papers/yolo.pdf



Let's come to most exciting part 
#Execution
---
First setup darkflow repository into your local computer and install all dependencies eg. Tensorflow, Numpy, Opencv etc. as described in darkflow repository link: https://github.com/thtrieu/darkflow
or we can also follow this youtube tutorial: https://www.youtube.com/watch?v=PyjBd7IDYZs&t=699s
Play with darkflow in order to understand it's functionality.

Hopefully upto here we can classify objects in a video by following these tutuorials.

In order to trasmit video wirelessly from raspberry pi here are some configuration we need to do in raspberry pi.
"Here we are going to tansmit video in our local area."


First, we need to make some changes in wpa-supplicant file so that every time it automatically connect with our desired wifi address.
To do this task automatically just run this python script.
"python3 network.py"
this script will update our RPI and also generate our required wpa-supplicant file
##Note: Make sure to change you wifi name and password in network.py programme.

after that connect your camera with rpi and do some configuration.

"sudo raspi-config"
and enable camera in interface option.

After that run
"python3 Transmit.py" file
 it will start transmitting video on your raspberry pi ip address.
After that connect your computer with same wifi network and open vlc media player and connect with "your_rpi_ip:8061"

Viola video is now streaming from rpi to directly into our computer.




