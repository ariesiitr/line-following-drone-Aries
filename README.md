Line Following Drone

The Line Following Drone is an autonomous flying robot designed to follow a line on the ground using computer vision algorithms. It can be used for various applications such as warehouse automation, object tracking, and robotic competitions.

This project aims to provide a simple and efficient solution for line tracking using a drone. 

Features
Autonomous line tracking: The drone uses computer vision algorithms to track and follow a line on the ground.
Customizable line detection: The line detection algorithm can be customized to adapt to different line colors and patterns.

Acknowledgments
The Line Following Drone project was inspired by the work of several researchers and open-source contributors in the field of autonomous drones.
We would like to thank the open-source community for their valuable contributions and support.
Contact

Happy line following with your drone!

Line following drone
How this is useful in daily life:
Uses:
1.In shopping malls:as for particular identity the drone picks up the product and send it to user on counter.
2.For identification of cracks in certain line(such as roads)and preventing any accidents.
How to work on it?
The work presented here ﬁnds an application within the IFAC2020 MathWorks Minidrone competition [19], where the use of a model-based design approach is the aim of the speciﬁc contest. Path error and mission time are used as evaluation metrics for the algorithm. The whole process is the following: a quad-rotor UAV follows a pre-established red path by using its downward facing camera to get feedback from the environment. Images are updated according to the position and orientation of the vehicle simulated in the MATLAB VR world. No prior knowledge on the path and
the surrounding scenario is given. The drone takes off and starts its motion looking at the path, and the mission stops with the recognition of an end-marker. At that time, the drone lands staying within the delimited area. Figure 2 shows the considered scenario
Where the use of a model-based design approach is the aim of the speciﬁc contest. Path error and mission time are used as evaluation metrics for the algorithm. The whole process is the following: a quad-rotor UAV follows a pre-established Redpath by using its downward-facing camera to get feedback from the environment. Images are updated according to the position and orientation of the vehicle simulated in the theMATLAB VR world. No prior knowledge on the path and the surrounding scenario is given. The drone takes off and starts its motion looking at the path, and the mission stops with the recognition of an end-marker. At that time, the drone lands staying within the delimited area.
TOOLS USED IN THIS PROJECT:
1.Matlab R2022A
2.Simulink
3.Add-ons
  (i)Simulink Support package for Parrotminidrones
  (ii)UAV toolbox
  (iii)Control system toolbox
  (iv)Stateflow
  (v)Image processing toolbox
  (vi)Computer vision toolbox
  (vii)Aerospace toolbox
  (viii)Aerospace blockset
1.Image processing toolbox: the main aim is to identify the path as follows.
![image](https://github.com/rajaniket2021/line-following-drone-Aries/assets/99840744/c8165376-ced3-4ec1-8701-ee841729c620)

Using image processing we can binarize the picture and get the specified picture.
Using code:
I = imread("IMG_006.jpg");
gs = im2gray(I);
gsAdj = imadjust(gs);
BW = imbinarize(gsAdj,"adaptive","ForegroundPolarity","dark");
imshowpair(I,BW,"montage")
F = fspecial("average",n)
This converts the image into binarize and adjustable iso to correctly identify the path.
![image](https://github.com/rajaniket2021/line-following-drone-Aries/assets/99840744/e66648a3-c214-40c2-87df-f570fad71a78)
![image](https://github.com/rajaniket2021/line-following-drone-Aries/assets/99840744/57005d0a-582f-4cce-86be-9b1e2115553f)
  
I = imread("IMG_002.jpg");
gs = im2gray(I);
gs = imadjust(gs);
H = fspecial("average",3);
gs = imfilter(gs,H,"replicate");
SEdisk = strel("disk",8);
Ibg = imclose(gs,SEdisk);
gsSub =  Ibg - gs; 
BW = ~imbinarize(gsSub);
imshowpair(I,BW,"montage")

2.Simulink
![image](https://github.com/rajaniket2021/line-following-drone-Aries/assets/99840744/52ac569e-0795-4101-a832-3bd0cc3fb8e1)
 
Using simulink we created a flow how the components re connected across the Pixhawk and how it functions to follow a certain path.
(flight control system)
![image](https://github.com/rajaniket2021/line-following-drone-Aries/assets/99840744/fd37edbf-1380-403c-85fb-0b5a9f0efd9b)
![image](https://github.com/rajaniket2021/line-following-drone-Aries/assets/99840744/d625ba87-c195-4bbf-a342-e239dde1e022)
![image](https://github.com/rajaniket2021/line-following-drone-Aries/assets/99840744/02d0bfd6-7375-4db3-9ba6-f6a73c3c4b18)



