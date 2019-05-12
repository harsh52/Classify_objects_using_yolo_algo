#Classify objects in a wirelessly transmitted video.
---
This was our class project in 2nd semester,
Our aim was to classify objects in a video that was wirelessly transmitted from Raspberry Pi-3

##Idea and Method of Execution
---
To classify objects in a video, we are going to use Darkflow which is based on darknet, which in turn is written in C and uses the YOLO algorithm.

Here is a basic idea as to how the YOLO algorithm works:

YOLO looks at the image just once, and hence the name. It divides the image into a 13x13 grid and each of the cells is responsible for predicting 5 bounding boxes. It also outputs a confidence score that tells us how certain it is about the prediction; higher the confidence score, the thicker the box. For each bounding box, the cell also predicts a class. The confidence score for the bounding box and the class prediction are combined into one final score that tells us the probability that this bounding box contains a speciic type of object. 

In total, we have 845 bounding boxes, of which most have very low confidence score. So we only consider the bounding boxes of confidence score > 30%. The neural network is run just once.

For an in-depth knowledge of the algorithm, refer to the resources listed below:

Youtube link: https://www.youtube.com/watch?v=4eIBisqx9_g
Research paper: https://pjreddie.com/media/files/papers/yolo.pdf

Let's come to most exciting part.
#Execution
---
First setup darkflow repository in your local computer and install all dependencies, eg., Tensorflow, Numpy, OpenCV etc., as described in the Darkflow repository link: https://github.com/thtrieu/darkflow

OR we can also follow this youtube tutorial: https://www.youtube.com/watch?v=PyjBd7IDYZs&t=699s

Play with darkflow in order to understand its functionality.

Hopefully by now we can classify objects in a video by following these tutorials.

In order to trasmit video wirelessly from Raspberry Pi, here are some configurations we need to make in raspberry pi.

First, we need to make some changes in the wpa-supplicant file so that it automatically connect with our desired WiFi address every time.

To do this task automatically just run this python script.
"python3 network.py"

This script will update our RPI and also generate our required wpa-supplicant file

##Note: Make sure to change you wifi name and password in network.py programme.

After that, connect your camera with RPI and make some more configurations.

"sudo raspi-config"

and enable camera in interface option.

After that run
"python3 Transmit.py" file
 
It will start transmitting video to your Raspberry Pi IP address. After that, connect your computer with same WiFi network and open VLC media player and connect with "your_rpi_ip:8061"

Voila! Your video is now streaming from RPI directly to our computer.




