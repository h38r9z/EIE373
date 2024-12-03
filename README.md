java c
Department   of   Electrical   and   Electronic   Engineering
EIE373 Microcontroller Systems and Interface
Laboratory Exercise   1: Introduction to AVR
(Deadline: Check the course information)
Objectives:
1.       To familiarize students with the use of   an AVR   microcontroller.
2.       To develop C programs under the Arduino platform.
Equipment:
Atmel   Studio and Arduino IDE (software; check the version in the course   information)   The Arduino   Starter Kit (hardware)
   
Important Notices:
1.       Download   the   ATmega328p   datasheet   from   the   Blackboard   before   doing   the   laboratory   exercises.
2.       You can buy a kit and bring   it to   the   lab   sessions   or   leave   your   student   identity   card   in   the   box   beside   the   kits   to   borrow   one   kit   box. You   get   the   card back   when   you   return   the   box.   Note   that   you   must   return   the   box   five   minutes   before   the   end   of   the   laboratory   sessions.
3.       All components you need can be found in the kit box.
Introduction:This   experiment   introduces   some   simple   applications   of an   AVR   microcontroller   to perform   arithmetic and I/O operations.   Students develop C   programs and   build simple electronic circuits   for such simple   applications.Atmel   Studio   is   the   integrated   development   platform   (IDP)   for   developing   and   debugging   Atmel   AVR   microcontroller   (MCU)   applications.   It   gives   you   a   seamless   and   easy-to-use   environment to write, build,   and debug your   applications   written   in   C/C++   or   assembly   code.   Atmel    Studio    supports    all    8-    and    32-bit    AVR    MCUs    and    connects    seamlessly    to    Atmel   debuggers and development kits.The Arduino Start Kit teaches you the basics of   using the Arduino hands-on. You will learn by   building several creative projects. The kit includes a   selection   of   the most   common   and useful   electronic components.
Procedure:
Section   A: Create   your   first   simple   application
1.       Open Atmel   Studio: Double-click the icon of   Atmel   Studio.
2.          Change the mode from “Standard” to “Advanced”   .                                                                                     
   
3.       Go to the main menu.   Select   “Tools”   →   “External   Tools”   .   Type   in   “Arduino   Uno”   in   the
field “Title”. Type in the following paths into the fields   “Command”   and   “Arguments”   :
C:\Users\??\AppData\Local\Arduino15\packages\arduino\tools\avrdude\6.3.
0-arduino17/bin/avrdude.exeC"C:\Users\??\AppData\Local\Arduino15\packages\arduino\tools\avrdude\6.   3.0-arduino17/etc/avrdude.conf"   -v -V   -patmega328p   -carduino "-PCOM4"   -   b115200   -D "-Uflash:w:$(ProjectDir)Debug\$(TargetName).hex":iNote    that      ?? is    your    username    (e.g.,    22123456d).      These    two    paths      are      in      the      text      file   ArduinoUno.txt, which can be found in the zip file “EIE3373   Course Materials.zip”, which can   be      downloaded      from      Blackboard.      Read      “Important      information”      on      Page      4      before   downloading your program to your Arduino.Atmel   Studio and Arduino IDE are freeware, and you   can   download them   from the   Internet   to   your computer. You can follow the steps below to find the "Command"   and   "Argument" paths   using the Arduino IDE on your computer:
1.       Open the Arduino IDE: Launch the Arduino IDE on your   computer.
2.       Access the Blink Example: Go to   File   → Examples   → 01.Basics   → Blink.
3.       Select the Arduino Uno Board: Go to   Tools   → Board   → Arduino Uno.
4.       Enable       Detailed      Upload       Output:       Got      to       File →       Preferences.       In       the   Preferences window,      check    the      box       labeled    “   Show    verbose    output   during: upload”. Click OK   to   save the   settings.
5.       Upload the Blink Sketch: Click the Upload   button   (the right   arrow   icon)   to   compile   and upload the Blink sketch to your   Arduino Uno.
6.       Check the Output Window: Observe the output window at the bottom of   the Arduino   IDE after uploading. Look for some lines similar to the following texts (usually around   line   3):
"C:\Users\YourUsername\AppData\Local\Arduino15\packages\arduino\tools   \avrdude\6.3.0-arduino17/bin/avrdude" "-
CC:\Users\YourUsername\AppData\Local\Arduino15\packages\arduino\tools
\avrdude\6.3.0-arduino17/etc/avrdude.conf" -v -V -patmega328p   -   carduino   "-PCOM4"   -b115200   -D   "-
Uflash:w:C:\Users\YourUsername\AppData\Local\Temp\arduino\sketches\F3   4549723ED32139E374C1C89CFACE38/Blink.ino.hex:i"
7.       Extract the Command and Argument: Copy the lines to   a   text   file   and   modify   its
contents to create the command and argument paths.   The lines:
"C:\Users\YourUsername\AppData\Local\Arduino15\packages\arduino\tools   \avrdude\6.3.0-arduino17/bin/avrdude" "-
CC:\Users\YourUsername\AppData\Local\Arduino15\packages\arduino\tools   \avrdude\6.3.0-arduino17/etc/avrdude.conf" -v -V -patmega328p   -
carduino   "-PCOM4"   -b115200   -D   "-
Uf代 写EIE373 Microcontroller Systems and Interface Laboratory Exercise 1: Introduction to AVRC/C++
代做程序编程语言lash:w:C:\Users\YourUsername\AppData\Local\Temp\arduino\sketches\F3   4549723ED32139E374C1C89CFACE38/Blink.ino.hex:i"
Command path:
C:\Users\YourUsername\AppData\Local\Arduino15\packages\arduino\tools\   avrdude\6.3.0-arduino17/bin/avrdude.exe
Argument path:
C"C:\Users\YourUsername\AppData\Local\Arduino15\packages\arduino\tool   s\avrdude\6.3.0-arduino17/etc/avrdude.conf" -v -V -patmega328p   -
carduino   "-PCOM4"   -b115200   -D   "-
Uflash:w:$(ProjectDir)Debug\$(TargetName).hex":i
Replace YourUsername   with your actual username in the file paths.
Important   information:
a.       Note that   “COM4”   in the above path   shows   the   port   the   Arduino   Uno   plugs   into   your computer. Thus, later, when   you   plug   in   the   Arduino   Uno   to   your   computer,   you   need to   check   whether   the   port   is   “COM4”   or   not   (Double   click   the   icon   “Computer”   and   Select “Properties” → “Device Manager”   → “Ports”. Check the position of   the port for   the Arduino Uno). You may need to change the port number if   it is not “COM4”   .
b.       Moreover,you may goto Blackboard to download the text file “ArduinoUno.txt” in the   course   material   (in   the   folder   “AVR   Programming   Materials”).   This   file   stores   these   two paths. Then, you can copy and paste them into   such two   fields.After   that,   click   the   checkboxes   “Use   Output   window”   and   “Prompt   for   arguments”   and   then   click   the   button   “OK”   .   When   you   finish   the   setting,   a   new   field,   “Arduino   Uno”   is   created under the menu item “Tools”.   Note that the above setting must go through once you   have opened Atmel   Studio for the first time.
   
4.       Go    to    the    main    menu    and    create    a    new    project.    Then    select    “C/C++”    and    “GCC    C   Executable Project” to create anew project. Type in the project name “Lab1A”. After that,   select “ATmega328p”   .
   Note   that   the   I/O   ports   of the   AVR   microcontroller   are   bit-accessible,   but   the   AVR   C   compiler does not support this feature. Thus, you should use a mask to set, clear, and check   some bits in the I/O ports.
   
5.       Type in the following program into “Lab1A.c”   .
#include   
int   main(void)   {
DDRD   =   0xFF;   while(1)
{
PORTD   =   0x55;   }
}
6.       Go to the main menu.   Select “Build” → “Build   Solution” to   compile the program.
7.       Build the circuit below on the Arduino Uno and the breadboard. Check the pinout diagram   in the appendix or some files   in   the   course material.

8.       Go   to   the   main   menu.   Select   “Tools”   →   “Arduino   Uno”   to   burn   the   program   into   the   ArduinoUno.   You should see some LEDs are on. If   it does not work, check   the   “Important
Information” below.
Important   information:Note that you should remove any connections topin 0 (RX) and pin   1 (TX) of   the Arduino Uno    before    you    burn    your    program    into    it;      otherwise,    your      program      may      not      burn successfully.
9.       Repeat the above steps, but this time, Port D is toggled between 0x55 and 0xAA with a one   to two-second time delay. It would be best to use looping   to   generate   the   delay   and   set   the   optimization level to the first one (level zero). Show the   calculation   of   how to   generate the   delay.   Note   that   the   clock   frequency   of   the   Arduino   Start   Kit   is    16   MHz.   When   your   program works correctly, all LEDs connected to Port D   are   flash.
Section B: Simple applications
1.       Connect   a   switch   to   PB0;   the   pin   diagram   is   shown   in   Step   7   of Section   A.       Connect   an   LED to the switch. When the switch is pressed, the LED is on. When the switch is released,   the   LED   is   off.   Connect   an   LED to   PD2.   When the   switch   is pressed, the   LED   in   PD2   is   on. When the switch is released, the LED in PD2   is   off. You   may   connect   an   LED   serially   with R1 to check whether the circuit to connect the switch   is   correct.
2.       Use the circuit in Section A and the connection in Step   1. There are two states in the switch:   States   0   and   1.   When   it   is   in   State   0,   all   LEDs   connected to   Port   D   are   off.   When   it   is   in   State   1,   all   LEDs   are   on.   At   the beginning,   the   switch   is   in   State   0.   When   (1) the   current   state   is   0   and   (2)   the   switch   is   pressed   and   then   released,   it   goes   from   State   0   to   State   1.   When (1) the current state is   1 and (2) the   switch is pressed   and then   released,   it   goes   from   State   1 to   State   0.
Demonstrate   Section   A   (Steps   8 and   9) and   B   (Steps   1 and   2) to   our   student   helpers.
Instructions:
1.       You are required to demonstrate your   programs to our student helpers.
2.       Zip all programs (including the whole projects) in Sections A   and   B   to   a   single   file.   Please   submit it to Blackboard.
3.       Deadline: Check the course information.



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
