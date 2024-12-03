java c
Department   of   Electrical   and   Electronic   Engineering
EIE373 Microcontroller Systems and Interface
Laboratory Exercise 2: AVR Timer/Counter Programming
(Deadline: Check the course information)
Objective:
1.       To develop C programs with timers under the Arduino platform.
2.       To develop a C program with a   counter under the Arduino platform.
Introduction:This   experiment   introduces   the   use   of timers   and   a   counter   inside   the   AVR   microcontroller.   Students MUST use the AVR timers in the delay function to finish this lab. Using simple loops   only without timers to count the delay or built-in functions is   not acceptable.
Equipment:
Atmel   Studio
The Arduino   Starter Kit
Procedure:
Section   A:   Write a   C   Program to toggle an LED by using a timer
1.       Write   a   C   program   to   toggle   an   LED   connected   to   PB0   (you   should   connect   the   LED   to   PB0   with   a   resistor)   every   second.   Use   the   timer   with   Normal   mode   to   generate   a   one-   second time delay. Note that the clock frequency of   the Arduino   Start Kit is   16 MHz.
2.       Repeat   Step   1, but the timer is in CTC mode this time.
DO NOT   skip Section A and goto Section B directly. You must   finish the laboratory   exercise   step by step; otherwise, you will find that it   is not   easy   to   follow.
Section B:   Write a   C   Program to   simulate the traffic lights
1.       Write a C program to simulate the traffic lights using different pins. You should use a timer   in Normal mode. Note that the Arduino   Start Kit's clock frequency is   16 MHz.
A set of   traffic lights for cars   (Light   3):   PB0,   PB1,   PB2   (3   LEDs)         A set of   traffic lights for cars   (Light   2):   PB3, PB4,   PB5   (3   LEDs)         A set of   traffic li代 写EIE373 Microcontroller Systems and Interface Laboratory Exercise 2: AVR Timer/Counter ProgrammingR
代做程序编程语言ghts for pedestrians (Light   1):   PC4,   PC5   (2   LEDs)
   
Implement the following   pattern:Current   stateLight   1Light   2Light 3TimedurationNext   state1RedGreenRed5   seconds22RedYellowRed1   second33RedRedRed1   second44RedRedRed + Yellow1   second55GreenRedGreen5   seconds66Green BlinkingRedYellow1   second77RedRedRed1   second88RedRed + YellowRed1   second1
2.       Repeat   Step   1, but the timer is in CTC mode this time.
Section   C:   Write a   C   program to count a switchConnect a switch to pin T0 (PD4, Counter 0) or T1 (PD5, Counter   1) and a LED to PC0.   There   are two   states   in the   switch:   State 0   and   1. When it   is   in   State   0,   the   LED   is   off.   When   it   is   in   State   1, the LED is   on. At   the   beginning,   the   switch   is   in   State   0.   When   the   switch   is   pressed   three times and in State 0, it goes to State   1. When the switch is pressed three times and in State   1,   it   goes   to   State   0.   You   should   use   counter   programming   in   CTC   mode   to   implement   this   application.You may find that sometimes the state may change, but you do not press the switch three   times.   It    is    because    of   the    bouncing    effect    of   the    switch.    Please    google      “bouncing      switch”    to   understand   the   bouncing   effect   and   “debouncing    switch”   to   find   a    solution   to   reduce   the   bouncing effect.
Demonstrate   Sections   B   and   C   to   our   student   helpers.
Instructions:
1.       You are required to demonstrate your   programs to our student helpers.
2.       Zip   all programs   (including the whole projects)   in   Sections   B   and   C   into   a   single   file   and submit it to Blackboard.
3.       Deadline: Check the course information.

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
