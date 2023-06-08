# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure
Step1:

Use from robomaster import robot.


Step2:

Choose the x,y,z - axis movement distance(meters).


Step3:

Give ep_chassis.move to move straight.


Step4:

Give time.sleep() for a break.


Step5:

Give ep_chassis.drive_speed to have a circular movement.


## Program 1
```
#DEVELOPED BY :ANANDHAMOORTHY.k
#REG NO. : 212222100004

from robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera
          
    print("Video streaming started.....")
    ep_camera.start_video_stream(display=True, resolution = camera.STREAM_360P)
    ''' 
    x = x-axis movement distance,( meters) [-5,5]
    y = y-axis movement distance,( meters) [-5,5] 
    z = rotation about z axis ( degree)[-180,180]
    xy_speed = xy axis movement speed,( unit meter/second)  [0.5,2]

    '''
    ep_chassis.move(x=4, y=0, z=0, xy_speed=1).wait_for_completed()
 
    ep_chassis.move(x=0, y=0, z=55, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=124,b=112,effect="on")  
    ep_chassis.move(x=3, y=0, z=0, xy_speed=1).wait_for_completed() 

    '''
    x = speed in x direction( meter/second) [-3.5,3.5]
    y = speed in y direction( meter/second) [-3.5,3.5]
    z = rotation about z axis ( degree/second)[-300,300]
    '''
    ep_led.set_led(comp="all",r=255,g=220,b=70,effect="on")  
    ep_chassis.drive_speed(x=0.4,y=0,z=-20)
    time.sleep(12)
    ep_led.set_led(comp="all",r=0,g=255,b=0,effect="on") 
    ep_chassis.move(x=2.95, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=0,b=128,effect="on") 
    
    
    ep_chassis.move(x=0.1, y=0, z=60, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=170,g=0,b=0,effect="on") 
    ep_chassis.move(x=0.8, y=0, z=0, xy_speed=1).wait_for_completed()

    ep_chassis.drive_speed(x=0.2,y=0,z=-20.5)
    time.sleep(4)
    
    ep_chassis.move(x=2.8, y=0, z=0, xy_speed=1).wait_for_completed()

    
    
    

    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")

    ep_robot.close()

```
## Program 2
```
#DEVELOPED BY : ANANDHAMOORTHY.K
#REG NO. : 212222100004

from robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera
          
    print("Video streaming started.....")
    ep_camera.start_video_stream(display=True, resolution = camera.STREAM_360P)
    ''' 
    x = x-axis movement distance,( meters) [-5,5]
    y = y-axis movement distance,( meters) [-5,5] 
    z = rotation about z axis ( degree)[-180,180]
    xy_speed = xy axis movement speed,( unit meter/second)  [0.5,2]

    '''
    ep_chassis.move(x=3, y=0, z=0, xy_speed=1).wait_for_completed()
 
    ep_chassis.move(x=0, y=0, z=90, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=140,b=75,effect="on")  
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=0,g=255,b=0,effect="on")  
    time.sleep(2)
    ep_chassis.move(x=-2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=0,b=255,effect="on")  
    ep_chassis.move(x=0, y=0, z=-90, xy_speed=1).wait_for_completed()
    ep_chassis.move(x=-3, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=124,b=112,effect="on")  
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=180,g=180,b=180,effect="on")  
    ep_chassis.move(x=0, y=0, z=30, xy_speed=1).wait_for_completed()
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=0,b=255,effect="on")  
    ep_chassis.move(x=0, y=0, z=90, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=0,b=0,effect="on") 
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=69,b=0,effect="on") 
    ep_chassis.move(x=-2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=170,g=0,b=0,effect="on") 
    ep_chassis.move(x=0, y=0, z=-90, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=69,b=0,effect="on") 
    ep_chassis.move(x=-2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=69,b=0,effect="on") 
    ep_chassis.move(x=0, y=0, z=-30, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=47,g=79,b=79,effect="on") 
    ep_chassis.move(x=-3, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=16,g=78,b=139,effect="on") 



   

    


    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")

    ep_robot.close()
```

## MobileRobot Movement Image:

![robo](./img/robomaster.png)

![Screenshot 2023-06-08 092107](https://github.com/AnandhamoorthyKarthikeyan/mobilerobot-openloopcontrol/assets/119475998/b8315356-558b-4f6a-9573-9d98a7bdf776)
![Screenshot 2023-06-08 092037](https://github.com/AnandhamoorthyKarthikeyan/mobilerobot-openloopcontrol/assets/119475998/096667cd-ad8c-4f99-9636-6d8e860ea98a)




<br/>
<br/>
<br/>
<br/>

## MobileRobot Movement Video:

Upload your video in Youtube and paste your video-id here
https://youtube.com/shorts/Xbq9WofmPYA?feature=share
https://youtu.be/cuKoiNgrwSU

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg)](https://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)

<br/>
<br/>
<br/>
<br/>

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.


<br/>
<br/>

```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
