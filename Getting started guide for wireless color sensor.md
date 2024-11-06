# Getting started guide for wireless color sensor

## Overview 

This documentation provides a guide to assemble and test a color sensor package with a wireless charging port that could be implemented to the OT-2 liquid handling robot. The estimated time (tba)
<br>

## Prerequisites

This documentation assumes that readers have completed the Light Color Sensor microcourse and possess basic knowledge of electronic soldering and wiring techniques.
<br>

## Bill of materials

### Electronic parts: 

  - Sensor Package:
    - <span style="background-color: #FF2600; color: #FFFFFF;"> PicoW </span>
    - <span style="background-color: #3366FF; color: #FFFFFF;"> Pico LipoSHIM  </span>
    - <span style="background-color: #FFA500; color: #FFFFFF;"> Picowbell P5905  </span>
    - <span style="background-color: #008000; color: #FFFFFF;"> Wireless charger receiver  </span>
    - <span style="background-color: #FF00FF; color: #FFFFFF;"> AS7341 color sensor  </span>
    - <span style="background-color: #FFFF00; color: #000000;"> Lipo battery with 2-pole JST connector wire  </span>
    - <span style="background-color: #800080; color: #FFFFFF;"> STEMMA QT Wire  </span>
    - <span style="background-color: #00FFFF; color: #000000;"> 1 Pin male connector jumper wires (2x)  </span>

  - Wireless charging port (Dual charging):
    - <span style="background-color: #FF2600; color: #FFFFFF;"> Wireless charger transmitters (2x) </span>
    - <span style="background-color: #FFA500; color: #FFFFFF;"> Mirco-USB to USB Type-A cables (1 short and 1 long) </span>
    - <span style="background-color: #3366FF; color: #FFFFFF;"> Power supply (5V 2A) </span>

### 3D printed parts: 

  - Sensor package: 
    - <span style="background-color: #FF2600; color: #FFFFFF;"> Microcontroller backboard</span>
    - <span style="background-color: #FFA500; color: #FFFFFF;"> Sensor stand</span>
    - <span style="background-color: #3366FF; color: #FFFFFF;"> Sensor package main enclosure</span>

  - Wireless Charging port: 
    - <span style="background-color: #FF2600; color: #FFFFFF;">Enclosure A side</span>
    - <span style="background-color: #FFA500; color: #FFFFFF;"> Enclosure B side</span>
    - <span style="background-color: #3366FF; color: #FFFFFF;">Base</span>
    - <span style="background-color: #FF00FF; color: #FFFFFF;"> Transmitter supports (2x) </span>

   (Note: More details about 3D printing file should be added here)
### Tools: 

  - Required:
    - Soldering set
    - Phillips-head #0 screwdriver
    - M2.5-10mm screws and M2.5 hex nuts (4x each)
    - Painter's tape
    
  - Nice to have:
    - Tools to remove 3D printing supports and deburr surface
    - Multimeter for electronic connection troubleshooting
  
 
 <br>
 
## Hardware assembly:

  ### Preparation / Before you begin assembling: 
  (Note: photos will be added for each step starting from here)
  #### 3D printed parts preparation:

   Remove all printing supports from the 3D-printed parts. Deburr the inner walls of the sensor package and the charging port enclosure, especially heighted areas that will be used for assembly.

  #### Electronic soldering:
   
  1. LipoSHIM: 

     Place the LipoSHIM on the back of the PicoW, ensure the button of the LipoSHIM on the same side of the micro-USB port on the PicoW, solder 8 pins on each row on the PicoW.

  2. Battery connnector: 
     
     If the polarity of your battery’s 2-pin JST connector is opposite to that of the LipoSHIM, you can correct it by cutting off the connector, swapping the wires, and then resoldering them to match the correct polarity.

  3. Wireless charging unit: 

     Solder a jumper wire to the GND pad and another to the C1+ (or C2+) pad on the receiver board. Connect the transmitter to a power supply via USB cable and place the receiver on top of the transmitter (coils to coils). Check if the blue LED charging indicator on the transmitter board lights up. You may use a multimeter to measure the voltage between the two jumper wires; the reading should be approximately 5V. 
  
  #### Dual charging connection check:

   You may check the connection of the dual wireless charging setup before start assembling. Use the short micro-USB/USB Type-A cable to connect both transmitters and connect the transmitter that has a free micro-USB port to a power supply. Test the receiver using the same procedure above for the wireless charging unit, the receiver should give a voltage reading of approximately 5V on each transmitter.
      
  ### Assembling:

  #### Sensor Package assembling:

  1. Connect battery to Picow and LipoSHIM assembly: 
  
      Ensure the battery connector’s polarity matches the +/- markings on the LipoSHIM. Connect the battery to the LipoSHIM with the JST connector. Adjust the wire of the battery to through a row of pins on the PicoW. 
      
      Test connection: Press the button on the LipoSHIM to power on the PicoW; the white LED indicator on the LipoSHIM should light up. Connect the PicoW to a power supply via the micro-USB port; the red LED charging indicator on the LipoSHIM should also light up. 
      
      Power off and disconnect the power supply before proceeding with following steps.

  2. Mount PicoW on Picowbell: 
  
      Place the PicoW on the top of the Picowbell sockets; the micro-USB port on PicoW should be at the same side as the STEMMA QT port on Picowbell. Carefully align the pins and press down the PicoW to secure it onto the Picowbell.

  3. Connect wireless charging receiver to Picowbell: 
  
      Connect the GND jumper wire from the receiver to the GND socket (third on the right) on the Picowbell. 
      
      Connect the positive jumper wire to the VBUS socket (first on the right) on the Picowbell. 
      
      Place the receiver on the powered transmitter, the red LED indicator on LipoSHIM and the blue LED indicator on the transmitter should light up.
 
  4. Connect AS7341 to Picowbell: 

      Connect AS7341 to Picowbell with a STEMMA QT wire. Turn on the Picow (using the button on the LipoSHIM), the green LED indicator on AS7341 should light on.

      Test the color sensor (software testing should come in here)


  5. Assemble Picowbell to the backboard: 

      Align the assemble holes on Picowbell to those on the backboard, ensuring that the micro-USB port on Picow is positioned on the side of the backboard’s opening slot. Secure the screws and nuts with a screwdriver.

  6. Place sensor stand to the main enclosure end: 
  
      The sensor stand is a thin board with four spikes, designed with a thinner edge and a thicker edge. Position the sensor stand with the thinner edge close to the opening of the main enclosure and spikes on the top. Insert it into the sensor end of the main enclosure. 

  7. Secure the color sensor to the stand: 
  
      Face down the AS7341, with the yellow square on AS7341 close to opening of the main enclosure, align the assemble holes with four spikes, secure AS7341 to the stand.

  8. Place wireless charger receiver on the inner wall of the enclosure and secure with painter's tape. 

  9. Aligning the sliding tips on both ends of the backboard to the sliding slot on the main enclosure, assemble the backboard to the main enclosure. 

  #### Dual Charging port assembling:

  1. Join the A and B sides of the charging port enclosure, aligning them properly, and secure both parts together.

  2. Plug the short micro-USB cable into the micro-USB port on one transmitter. Place the transmitter onto the transmitter support with the coils facing outward. Route the coil wire down from the thinner side of the support. Insert the transmitter support into the port enclosure assembly, ensuring there is no gap between the transmitter and the wall of the sensor slot.

  3. Thread the long micro-USB cable through the square hole into the charging port assembly with the microusb head.

  4. Place another transmitter on the transmitter support with the coils facing outward. Route the coil wire down from the thicker side of the support through the routing slot. Insert the transmitter support into the port enclosure assembly, ensuring there is no gap between the transmitter and the wall of the sensor slot. 
        
  5. Connect the short USB cable to the USB type-A port on the second transmitter. Connect the long micro-USB cable to the micro-USB port of the second transmitter. If you find any difficulties with cable connections, try swapping two transmitters to rearrange cable.
        
  6. Connect the long cable to a power supply. The LED indicators on both transmitters should light up in the following sequence: blue, red, blue, and red. If either indcator does not flash, you may check the cable connections.

  7. Arrange the cables inside the enclosure and assemble the base board to the port enclosure. Place the sensor package on the slot of the charging port, the red indicator on the sensor package should light up.

## Software part


        



        

      


    


