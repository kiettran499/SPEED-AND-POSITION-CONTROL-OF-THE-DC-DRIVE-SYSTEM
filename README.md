# SPEED-AND-POSITION-CONTROL-OF-THE-DC-DRIVE-SYSTEM

<p align="center">
  <img width="500" src="https://github.com/kiettran499/Arduino-Robot-Car/blob/main/z5180520920529_c3d4ea2d488c9f2a5ef04b0775e67005.jpg">
  
## Description

- The goal of this project is to design the DC motor whose speed and the position of the motor movement can be controlled:
- The first task is separated into 2 cases to control the speed:
  - Open loop:
    - Open loop control as known as the system has no feedback loop in which the input signal is generated through the system and produce the output signal.     - In this task, we designed the open loop that can manage the speed of the rotor in the range 0 to 255 pwm and transfer to code then run and display by Arduino and the DC motor.
  - Closed loop:
    - Closed loop control is a control system in which the output affects the amount of input in such a way that the amount of input will adjust itself based on the output produced. For the closed loop control in this task, we are required to design a controller to control the speed of the DC motor. A potentiometer is applied to set the reference speed which is from 0 to maximum speed. The requirements for this controller are the speed error is under 3% and the overshoot of the step response is under 10% when step reference speed is half of the maximum speed.
    - 
    - We chose PID controller as the controller of the closed loop control system. To find the gains of the PID controller, firstly we find the transfer function of the system. After the transfer function is got, we design the gains Kp, Ki, Kd of PID controller with the support of Tuning Software in MATLAB. Then we put the values of gain in the code that we generate in Arduino IDE.
- The second task is to control the position of the Rotor’s movement, there're 2 cases:
  - Closed loop:
    - In this task we designed the controller for the position control loop with step position reference from zero to 270 degree. And the requirements are the overshoot under 15%, steady stead error of less than 2 degrees. Similar to task 1 - Closed loop control, the transfer function and the gains of the PID controller are the same. The different is the code that we generate in Arduino to control the position instead of speed control.
  - Two cascaded loops:
    - Cascade control is mostly used to quickly remove disturbance before it propagates to the other parts of the plant. The simplest cascade control system consists of two control loops (inner and outer). Design specifications and requirements are step position reference from zero to 270 degrees and the overshoot under 15%, steady stead error of less than 2 degrees.
    - 
<p align="center">
  <img width="500" src="https://github.com/kiettran499/Arduino-Robot-Car/blob/main/z5180520920529_c3d4ea2d488c9f2a5ef04b0775e67005.jpg">
  
  - Our team choose to design a cascade control system with two PID controllers. The process is we design inner loop to get the inner feedback loop and then use result of inner feedback loop to design outer loop. As the requirement is the speed loop is inside the position loop, we take transfer function from task 1.2 as the inner loop. Then we find the inner negative feedback loop by using syntax in MATLAB. After that we find the gains of the first PID controller with the support of Tuning Software in MATLAB. The result of gain Kp, Ki, Kd using two cascade loops is determined by multiplying the inner loop with Process block. Finally, we will design a program to run the position control using two cascaded loops via Arduino IDE. After that we put gains of first and second controller to that program.

## Hardware

- Arduino Uno R3 Board
- L293 Motor Drive Shield
- DC motor

## Software

- Arduino IDE
- MATLAB/Simulink
 
## Result

- Demonstration video for line following, obstacle avoidance and Bluetooth control functions: https://youtu.be/9Wb20bIvZSg
