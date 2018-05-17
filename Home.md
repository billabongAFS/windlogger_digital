## **How to bootload the card**

**Introduction :**

  Maybe you will receive a microprocessor which is not bootload or with an old version, so you will have to do it yourself. 

  This instruction is here to help you :

  If it's to hard you can watch these websites, the first is in english, the second in french :

  https://maniacbug.wordpress.com/2011/11/27/arduino-on-atmega1284p-4/

  http://menututo.com/mettre-un-bootloader-arduino-dans-un-atmega1284p/

**First step :**

You msut have the good software, files, equipment :
 
-Arduino 1.0 :
 https://www.arduino.cc/en/Main/OldSoftwareReleases

-The files of the bootloader : [https://github.com/netbomo/mighty-1284p](https://github.com/netbomo/mighty-1284p)

Copy the bootlarder file in the arduino like this /Arduino/hardware/mighty-1284p 

-An arduino card

**Second step :**

Open the IDE Arduino, Tools, board and select the Windlogger_digital_Board

If you didn't see the board, go back in your arduino files and copy the interior of the folder apr in the mightu-1284 folder and delete the apr folder (normally it is with your other file and empty) 

Retry the operation and select the good board.

**Third step :**

The pins P3 allows to connect the arduino board to the digital board, you have to follow this schema :

![enter image description here](https://lh3.googleusercontent.com/uk3z80O8MOMe3Dzf8qs7rvqAPUlIvrpjzQTqk697UeeQfWwP5RhbFrHKrtw1gvPiiMRCkvZkESY)

  The pin gnd is at the top left, below it is the reset, the below schema is not in the right direction

![enter image description here](https://lh3.googleusercontent.com/vHSzOA3EjlX3zTws7DFrAcSgW9J0YmXPu1F4kXJQM1enJ_3yHBBP2mcTK1HOyE-Gl_MBs-jtgTmm)

![enter image description here](https://lh3.googleusercontent.com/Fwd7KRHudcT5a8WTRBDDMDEyH-f3yiDgeCtTRRkaJa0N7L_c21o4DKkyp9hqbp4Riox4VmLmqEk)

If you didn't have an arduino uno card you have to change the pins like this :

![enter image description here](https://lh3.googleusercontent.com/JimEepc4uwe4fULmB3Ilf9zJw9Vz0zjsRfvTrYIEuQUx71MM3y4JDfVWRzrj2kcwRPtj0asNXi8)

**Fourth step :**

Connect your arduino card (log on your digital board) to your computer, open the ISP exemple you can find it in your arduino folder > Exemples > ArduinoISP and burn the sketch onto a regular Ardunio (select your board in Tools/board/"your arduino bord")

After change the board for the windlogger_digital_Board, the programmer for « Arduino as ISP » and do "Burn the bootloader".

 You have successfully bootloaded your card

