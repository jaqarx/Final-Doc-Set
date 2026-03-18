# **Building a Creature-like, Face-Detection Robot Using Raspberry Pi**

## **Introduction**

I created this project to teach myself the basics of computer vision, practice hardware and software integration, and express my love for robotics and creatures. This guide is designed for beginner to intermediate programmers who want to gain hands-on skills by building their own version of this robot.

**What you’ll need to know:**

* Basic Python programming (know what variables, functions, and loops are)  
* How to create and edit files in Visual Studio Code

| Table of Contents | Related Documents |
|---|---|
| [Introduction](#) | [Required Materials](Required%Materials.md) |
| [Robotics Introduction](#) | [Setting up the Hardware](Setting%Up%the%Hardware.md) |
| [Technical Details](#) | [Setting up the Raspberry Pi and the Raspberry Pi Camera]("Setting%Up%the%Raspberry%Pi%and%the%Raspberry%Pi%Camera.md) |
| **Hardware** | [Setting up the Robot's Vision](Setting%20Up%20the%20Robot's%20Vision.md) |
| &nbsp;&nbsp;[Sensors](#) | [Setting up the "Ear Motors"](Setting%20Up%20the%20"Ear"%20Motors.md) |
| &nbsp;&nbsp;[Computer](#) | [Frequently Answered Questions](FAQ.md) |
| &nbsp;&nbsp;[Chassis](#) | |
| &nbsp;&nbsp;[Motors](#) | |
| **Software** | |
| &nbsp;&nbsp;[Computer Vision](#) | |
| &nbsp;&nbsp;[Motor Actuation](#) | |
| [Software Development Environment](#) | |

### **Robotics Introduction**

Robotics is an emerging field with applications in manufacturing, hospitality, companionship, and beyond. Some examples of robots suited for these applications is [Boston Dynamics’ Atlas](https://bostondynamics.com/products/atlas/%20), which is currently being employed to manufacture cars for Hyundai, or your standard [Roomba](https://www.irobot.com/en_US/shop/vacuum.html), which has been cleaning floors since September 2002\. 

What makes robots particularly interesting is when they take on life-like or creature-like qualities, as this makes them more approachable and expressive. Examples include [Vector by Anki](https://anki.bot/pages/meet-vector%20) or [Disney’s Bi-pedal Robotic Character](https://la.disneyresearch.com/publication/design-and-control-of-a-bipedal-robotic-character/). This project explores the creature-like end of the spectrum by building a robot that can "see" faces and react with animated movements, giving it personality and presence.

## **Technical Details**

The project consists of two parts: hardware and software. The hardware side of this project consists of a simple assembly of parts that can be purchased online. The software side operates the robot’s vision used for facial detection as well as its “ears” used to signal that the robot can detect a face from live video feed.

**Through this project, you’ll be able to create a robot that can:**

* Detect human faces in real-time using the camera feed  
* Distinguish between when a face is present or not present  
* Indicate whether it detects a face with servo movements  
* Operate continuously while powered on

**The robot will NOT be able to:**

* Identify specific individuals (it detects faces generically, not who the face belongs to)  
* Track multiple faces simultaneously  
* Recognize facial expressions or emotions

### **Hardware** 

For this project, the hardware can be broken into 4 main components: sensors, computer, motors, and chassis.

#### **Sensors**

Sensors allow robots to receive information about their physical environment. For this project, a camera module acts as the robot's "eyes," capturing live video feed to be checked for faces.

#### 

#### **Computer**

A computer is needed to receive input, process it, and send commands to other components, essentially acting as the brain. This project uses a Raspberry Pi, which is a small, affordable computer about the size of a credit card. It has GPIO (General Purpose Input/Output) pins, which are physical connectors that allow it to send electrical signals directly to other hardware components like motors and LEDs. In this project, the Raspberry Pi both runs the face-detection software and controls the servo motors.

#### **Motors**

For robots to move, they require motors. This project uses servo motors, which are used for precise, controlled movement (typically within a 180 degree range of motion). Unlike standard motors that spin continuously, servos can be commanded to move to exact positions, making them ideal for robotics.

In this project, two servos are used to control the creature's "ears," providing the robot with a way to physically express that it has detected a face.

#### **Chassis**

The chassis is the physical frame of the robot. For this project, the chassis consists of custom 3D-printed parts to hold the camera and servos, with 3D-printed servo attachments to create the creature-like appearance.

### **Software**

For this project, the software can be broken into 2 main components: computer vision and motor actuation.

#### **Computer Vision**

Computer vision is a subfield of artificial intelligence that allows computers to detect and categorize objects within pictures, videos, or live video feed. In other words, it allows computers to detect things visually in its environment like humans do.

The general library used for the robot’s vision is called [OpenCV](https://opencv.org/), which stands for “Open Source Computer Vision Library.” A library is a collection of pre-written code that provides other programmers with functions for common tasks. To access specific commands for the camera, we will be using the [Picamera2](https://pip-assets.raspberrypi.com/categories/652-raspberry-pi-camera-module-2/documents/RP-008156-DS-2-picamera2-manual.pdf?disposition=inline) library.

#### **Motor Actuation**

For robots to move, they require motors. This project uses servo motors, which are specialized for precise, controlled movement. Unlike standard motors that spin continuously, servos can be commanded to move to exact positions, making them ideal for creating expressive, animated movements.

In this project, two servos are used to control the creature's "ears," which are commanded to move in response to face detection to give the robot personality and provide visual feedback that it has recognized a face. We will use the [gpiozero](https://gpiozero.readthedocs.io/en/stable/) library to program the servos.

#### **Software Development Environment**

This project requires using a code editor for writing the Python scripts that control the robot. I used [Visual Studio Code](https://code.visualstudio.com/) (VSCode), though any Python-compatible editor will work.
