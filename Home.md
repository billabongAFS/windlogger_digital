Welcome to the windlogger_digital wiki!

## **Power Converter Building Manual**
Luiz Fernando Lavado Villa 

 **The Windlogger: A Brief Introduction** 
  This datalogger is the result of 4 years of work of Gilles Longuet from Tripalium. 
  
   **What is a datalogger
  Inside the black-box: Functions of a wind logger** 

## **The digital board**

 

## **Block Digital 1 - Datalogger Feeder**

The feeder is responsible for providing energy to the components of the data logger. The architecture chosen for this data logger is illustrated in the figure below:  
![enter image description here](https://lh3.googleusercontent.com/IEJRo6kj6-iHpJTeFNZvExtw1wAZDk8CMjgDJnK6cTffRYCYLjF66M_ggfa8L2feTU1lD9TPMiw=s0 "The architecture of the feeder")


![enter image description here](https://lh3.googleusercontent.com/g3tH5ELa8TtkwIyGOJ0LqK-mRGPgBK3ph_msIWE-Q5WaEuGkOla4WqQqZlu15CQhOwbs5YNX-Ps=s0 "The characteristics of the data logger")
   
    **Table 2: The components of this block** 
     ![enter image description here](https://lh3.googleusercontent.com/TaLKtB9eaTHH4sF5o8txQ_EKrYjgiz3dU7MNMmsvEly-KSusKFy7GeeFxsVjl5I1TuD9kl-nyD0=s0 "Table 2: The components of this block")  


The component map below shows where the components of the feeder are placed on the digital board.  

![enter image description here](https://lh3.googleusercontent.com/--vAjj_p1HOyaynUmK7KKdcFNFlN1VFdau9KtCO_JQr4ieJ7-TUeP0zgos4aliNntzVvcIC0MPc=s0 "Figure 2: Components map")  Figure 2: Components map 




 **Assembly procedure** 
 Follow the procedures below to assemble the feeder block.
 
 1. **Separate the components** - Identify and separate all the components on the list in table 4. 
 2. **Solder the LM2672** -TheLM2672 regulatesthe5V outputvoltage whichwill feed mostof the components. This component is surface mounted, which requires care during soldering. Be careful**: If you destroy this component, the board will not function properly**  
  ![enter image description here](https://lh3.googleusercontent.com/w1bwMkUo9fNNX3NkcX1ndYDMc9ICpVCmfhpVY0nxG9swpG3WJXLWmLhsFwODh1lNXLPwiUpxrXo=s0 "Figure 3: The 5V Converter with the LM2672 in detail") 
  Figure 3: The 5V Converter with the LM2672 in detail  
  
 3. **Solder the rest of the 5V converter**- Solder all the components around the **LM2672** as shown in ﬁgure 3.  
  
 **Be careful  with the orientation of the polarized capacitors (C14 and C15)!** C14 and C15 are big capacitors that must be folded to the side during assembly. The white part of the footprint denotes where to solder the negative pin of the capacitor. When soldering the diodes, be careful with the orientation of the cathodes. The inductor does not have a speciﬁc orientation. 
 
 4. **Solder the MCP1700**- This component should be soldered and ﬂatenned aginst the board as shown in ﬁgure 4.  
 ![enter image description here](https://lh3.googleusercontent.com/SjnA_W1ZsbhbjEISsOzhOUJFotnv6LV3QFvPGBFrIoGq0V62yUR1TxnhfllQfL_zb_B-f7xW2hA=s0 "Figure 4: The 3V regulator with the MCP1700 in its center") 
 Figure 4: The 3V regulator with the MCP1700 in its center  

**IMPORTANT DETAIL:** The MCP1700 shown in ﬁgure 4 had problems during soldering. In the V1.1.1 of the PCB you can solder the MCP1700 and fold it so its ﬂat part touches the board.  

 5. **Solder the rest of the 3V regulator**- Solder the remaining components of the 3V regulator.
 6. **Solder the test pins**- The feeder has 4 test pins denoted “Vin PWR”, “+5V PWR”, “+3V PWR”, “GND PWR” and “GND”, which can be seen on the right hand side of ﬁgure 3. They must be soldered for testing the feeder.

## **Testing procedure**

 The test procudure has the objective of verifying that the feeder output 5V and 3V DC. The connection scheme is shown in ﬁgure 5.  
 ![enter image description here](https://lh3.googleusercontent.com/jwSdmJnjmpXPw5LL-SqAzo1Pjefn5x7wDBH5E8k2H2HSJO3wONAjrrpz1rFkrQ741Zg6zN4TquA=s0 "Figure 5: The connection scheme for testing the digital board feeder")  
 Figure 5: The connection scheme for testing the digital board feeder
 

 1. Connect a voltage source to **Vin PWR**. DO NOT TURN IT ON YET! 

 2. Connect the Ground of the multimeter to **GND PWR**  
 3. Connect the + of multimeter 1 to **+5V PWR**. Make sure the multimeter is in DC Voltage position. 
 4.  Connect the + of multimeter 2 to **+3V PWR**. Make sure the multimeter is in DC Voltage position.  
 5.  Make sure your voltage source is at **0V** to start the test. 
 6.  Slowly increase the voltage from 0V up to 30V and verify that the output voltage is +5V and +3V.
 
  Notes: 

## **Block 2 - USB Interface**

 The USB interface allows the user to upload his or her code into the Windlogger. The Windlogger can, thus, be either fed by the USB or the input DC voltage. This block contains the circuit that automatically chooses which energy source will power the microcontroller. By default it is the USB that will power the Windlogger. Once connected to a DC voltage source, the auto switch will automatically switch the power supply.  The Auto-Switch architecture is shown in the ﬁgure below.
 
![enter image description here](https://lh3.googleusercontent.com/JTUbTseHHXtBW-LTpImX0xcwcZ4kBTNrI1PlbltNtERWRstOQk-pLohhTa2XcT98nvSdW00E4i4 "Figure 6: The architecture of the auto-switch of the USB interface")

The components relative to this block are shown in the ﬁgur below.

![enter image description here](https://lh3.googleusercontent.com/DjEA8HRsidwOaAqUqngx5GXtNogP0T6Xy7-9oTZfKjWKvQGNTjZvYD3wHZJXZAww94ti9ym755E "Figure 7: Components map")

**Assembly procedure** 
Follow these steps to assemble the USB interface. 
1. **Separate the components** - Identify and separate all the components on the list in table 4. 

2.  **LM350** - The ﬁrst element to be soldered is the LM350, which is surface mounted. 
Care must be taken in the process to be sure that the component is not compromised during the assembly procedure.
 The LM350 and the rest of the circuit is shown in ﬁgure 9.
3.  **NDT2955** - The second element to be soldered is the NDT2955, which is also surface mounted. 
Care must be taken in the process to be sure that the component is not compromised during the assembly procedure.
 The NDT2955 and the rest of the circuit is shown in ﬁgure 9. 
4. **Button and test pin**- Solder the button and the test pin.
5. **USB interface** - To simplify the design of the circuit, the USB is soldered as a small PCB onto the Windlogger. Two details are important during its soldering and are shown in ﬁgure x. First, solder its sides to reinforce is mechanical hold. Second, solder it ﬂat on the digital PCB.
**Warning !** Be careful to not put tin into the USB plug.

![enter image description here](https://lh3.googleusercontent.com/Z0l9LDVYgHfxj7f03D3PNW0KrZTP2sPbmQb_5nWOTNTCJNMeqbhaVZuPijImd-SblSekBQTP1ok "Figure 8: The USB interface soldering details")

 6.  **Solder Zener diode**- Solder the Zener diode. Be careful with its sense! 

7. **Solder the rest**- Solder all the capacitors and the resistor.

![enter image description here](https://lh3.googleusercontent.com/Y4q0wosq7oKDurQ5Svbm1c7lLHQBzsSiORHPd5TqPKljP2K03FopELsa5rPelmwWoaxEwMN7GVY "Figure 9: The USB interface soldered with the detail of the LM350")

## Testing procedure
Follow the steps below to test the USB block
1. Connect a multimeter between the W2 pin and the GND pin.
2.  Connect a micro-USB cord connected to a computer to the USB interface of the digital board 
3. Verify the voltage

Notes:

## **Block 3 - Microcontroller connectors and Arduino**

 The microcontroller is the brain of the Windlogger.

![enter image description here](https://lh3.googleusercontent.com/82uZId1eTjqqk9Zj341PEmP6aEW7P2XS1XeKw_cqVEg5uAoCRup0DJYvFjYeVLbaeVjlV7T0qYY "Table 6: The components of this block")

The components relative to this block are shown in the ﬁgur below.

![enter image description here](https://lh3.googleusercontent.com/hj1Grc6q8vGgTZj1sAOTB9dnPCCT7fep3Y4qpAgu9VvQf1grBrE-QOb4j8hj0Wk6-eHs9knDCKI "Figure 10: Components map")

## **Assembly procedure**

 Follow these steps to assemble the microcontroller block.
  1. **Separate the components** - Identify and separate all the components on the list in table 6. 
  2. **Solder the oscillators** - There are two oscillators to this microcontroller. **BE SURE TO SOLDER THE CORRECT CAPACITORS WITH EACH OSCILLATOR**. Oscillator X1 uses 18pF capacitors and Oscillator X2 uses 12pF capacitors as shown in ﬁgure 12.
![enter image description here](https://lh3.googleusercontent.com/_ow23i47MrDtQHHw5YeqdhHCURjOc_yCXV06-sZPcRYWmSffkMNY4g1uxlwuyCNtfy6XkHQsOCQ "Figure 11: The Oscillators soldering details")
3. **Solder the LED, resistance, C4,C5 and C6** - Solder the rest of the components BEFORE soldering the Microcontroller.

4. **Solder the ATMEGA1284P-P** microcontroller-Solder the Microcontroller being careful to not use too much solder.

![enter image description here](https://lh3.googleusercontent.com/jGGx7fm14z-ME-YdsyrdE9cGz0qpdpKvrKMtoKn2slLI0_8pdtjy6wtRgeVYZYN6AbqPieRv0ww "Figure 12: The microcontroller and connectors soldered onto the digital board")

5. **Solder the digital board connectors**- Soldering the connectors can be quite challenging. **BE SURE THAT THE CONNECTOR IS VERTICAL AND THEN SOLDER ONE PAD TO HOLD IT IN PLACE.** Once the connector is ﬁrmly in place, solder the other pads.
6.  **Solder U1 and C9** - Solder the 74HC4050 Level shifter BEFORE soldering the C9 capacitor.

## **Testing procedure**

 Follow the steps below to test the microcontroller block: 
 1. Connect the USB port to a computer
 2. Validate that the LED is blinking and that you can have access to the microcontroller. 

Notes:
