# Robotic Arm
A 3-joint robotic arm resembling a crab claw.

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Yash K | Dougherty Valley High School | Mechanical Engineering | Incoming Junior

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/h40wcs0yxLg?si=2LSU3shAOUOyhkr7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE



# Second Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/wNetQUnG5y0?si=vFPZT-OGsVVSfHdc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone 

# First Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/h40wcs0yxLg?si=2LSU3shAOUOyhkr7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

My project is a 3-joint robotic arm. It has a rotating base, an elbow joint, a wrist joint, and two fingers for grabbing and releasing objects. It also includes an Arduino Nano board, a Nano shield, a 9-volt battery power supply, and a double joystick controller. Since the default batteries for the project are two 18650 cells, I had to use a different Nano shield than the one originally intended.

The Nano board is a microcontroller that can store inputs and be programmed to interact with sensors, lights, motors, and other devices, similar to what you'd find in a smartphone. The shield is an extension that plugs directly into the board and provides additional ports for wiring and power. The robot is moved by servo motors, which are connected to the shield and receive commands from the Nano board. In short, inputs from the joysticks are sent to the Nano, which then controls the servos to move the robotic arm.

I faced a few challenges during this first milestone. First, I had to improvise by using a different Nano shield and power supply than the default project setup. Second, I’m currently dealing with some issues in the code. Specifically, the servos jolt back suddenly when I start the program, and there’s limited motion in the robot's first joint.

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
#include <Servo.h>

Servo servo1;
Servo servo2;
Servo servo3;
Servo servo4;

void setup() {
  Serial.begin(9600);
  servo1.attach(3);
  servo2.attach(5);
  servo3.attach(6);
  servo4.attach(9);

  // Set initial positions
  servo1.write(90);
  servo2.write(90);
  servo3.write(90);
  servo4.write(90);
}

void loop() {
  if (Serial.available()) {
    String command = Serial.readStringUntil('\n');
    command.trim();

    if (command.startsWith("S1:")) {
      int angle = command.substring(3).toInt();
      servo1.write(constrain(angle, 0, 180));
    } else if (command.startsWith("S2:")) {
      int angle = command.substring(3).toInt();
      servo2.write(constrain(angle, 0, 180));
    } else if (command.startsWith("S3:")) {
      int angle = command.substring(3).toInt();
      servo3.write(constrain(angle, 0, 180));
    } else if (command.startsWith("S4:")) {
      int angle = command.substring(3).toInt();
      servo4.write(constrain(angle, 0, 180));
    }
  }
}

```

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
