# i-spy
Play the [I Spy] game with the [Kinova Gen3] Robot!

## Main Software/Library Requirements:
- [Ubuntu 18.04.6]
- [ROS Melodic]
  - [rospy]
  - [roslaunch]
  - [smach]
  - [actionlib]
  - [sensor_msgs]
  - [cv_bridge]
- [darknet_ros]
- [ros_kortex_vision]
- [OpenCV]
- [opencv-python] v4.2.0.32
- [SpeechRecognition]
  - [PyAudio]
- [pyttsx3]
  - [espeak]

## Build

```sh
$ cd ~/catkin_ws/src
$ git clone https://github.com/soroush-msd/i-spy.git
$ cd ~/catkin_ws/
$ catkin_make
```
## Run

In one terminal:
```sh
$ roscore
```
And in another terminal:
```sh
$ cd ~/catkin_ws/
$ source devel/setup.bash
$ rosrun i-spy stateMachine.py [f]emale/[m]ale [h]uman/[r]obot/[g]reeting
```
## How To Play?
This is a voice-based interaction. You need to have three components connected to your system:
1. A microphone through which you will speak to the robot.
2. A speaker through which the robot will speak to you.
3. The Kinova Gen3 Robotic Arm with a working camera to enable the robot to see and detect objects in the environment.

There are two/three-ish different scenarios you can play the game with two distinct voices (male/female).
1. The robot looks around, chooses one random object, picks its first letter and then you will guess the matching object.
2. You look around, choose one random object within the robot's FOV and pick its first letter. The robot then asks you for the letter and tries to guess the matching object.
3. The robot greets you, introduces itself, and then starts scenario 1.


So, for example, if you run:
```sh
$ rosrun i-spy stateMachine.py f r
```
The robot will play scenario 1 with the female voice.


If you run:
```sh
$ rosrun i-spy stateMachine.py m h
```
The robot will play scenario 2 with the male voice.


Similarly, if you run:
```sh
$ rosrun i-spy stateMachine.py m g
```
The robot will play scenario 3 with the male voice.

## State Machine Interactions

<img src="https://user-images.githubusercontent.com/83174840/176863533-5570e49f-d987-4cc4-bc51-cee35bc2f47f.png" width="350" height="350" />


  [darknet_ros]: <https://github.com/leggedrobotics/darknet_ros>
  [OpenCV]: <https://docs.opencv.org/4.x/d7/d9f/tutorial_linux_install.html>
  [SpeechRecognition]: <https://pypi.org/project/SpeechRecognition/>
  [pyttsx3]: <https://pypi.org/project/pyttsx3/>
  [cv_bridge]: <http://wiki.ros.org/cv_bridge>
  [smach]: <http://wiki.ros.org/smach>
  [opencv-python]: <https://pypi.org/project/opencv-python/>
  [actionlib]: <http://wiki.ros.org/actionlib>
  [sensor_msgs]: <http://wiki.ros.org/sensor_msgs>
  [roslaunch]: <http://wiki.ros.org/roslaunch/API%20Usage>
  [rospy]: <http://wiki.ros.org/rospy>
  [ROS Melodic]: <http://wiki.ros.org/melodic/Installation/Ubuntu>
  [Ubuntu 18.04.6]: <https://releases.ubuntu.com/18.04/>
  [Kinova Gen3]: <https://www.kinovarobotics.com/product/gen3-robots>
  [ros_kortex_vision]: <https://github.com/Kinovarobotics/ros_kortex_vision>
  [espeak]: <http://espeak.sourceforge.net>
  [PyAudio]: <http://people.csail.mit.edu/hubert/pyaudio/#downloads>
  [I Spy]: <https://en.wikipedia.org/wiki/I_spy>
