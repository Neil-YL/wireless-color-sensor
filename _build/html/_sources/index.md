# Getting started guide for wireless color sensor

## Overview 

This documentation provides a guide to assemble and test a color sensor package with a wireless charging port that could be implemented to the OT-2 liquid handling robot. Following is a video of liquid color matching demo run on OT-2 with this wireless color sensor:

(Youtube link to be added)

The estimated time of the hardware assembly is around:

<br>

## Prerequisites

This documentation assumes that readers have completed [Course 1: Hello World](https://ac-microcourses.readthedocs.io/en/latest/courses/hello-world/index.html#) and possess basic knowledge of electronic soldering and wiring techniques.
<br>

## Bill of materials

### Electronic parts: 

  - **Sensor Package:**

    <div style="float: right; margin-left: 10px; width: 500px;">
      <img src="_static/images/Electronic-parts-sensor.png" width="500">
    </div>

    - [<span class="color-red">① PicoW</span>](https://www.digikey.com/en/products/detail/raspberry-pi/SC0919/18713315)
    - [<span class="color-blue">② Pico LipoSHIM</span>](https://www.digikey.com/en/products/detail/pimoroni-ltd/PIM557/15851380)
    - [<span class="color-magenta">③ AS7341 color sensor</span>](https://www.digikey.com/en/products/detail/adafruit-industries-llc/4698/13162109)
    - [<span class="color-orange">④ Picowbell P5905</span>](https://www.digikey.com/en/products/detail/adafruit-industries-llc/5905/22596390)
    - [<span class="color-purple">⑤ STEMMA QT Wire</span>](https://www.digikey.com/en/products/detail/sparkfun-electronics/PRT-17258/13629029)
    - [<span class="color-green">⑥ Wireless charger receiver</span>](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/317010008/5487684)

    - [<span class="color-yellow">⑦ Lipo battery with 2-pole JST connector wire</span>](https://www.amazon.ca/EEMB-Battery-Rechargeable-Lithium-Connector/dp/B08FD3V6TF/)

    - [<span class="color-cyan">⑧ 1 Pin male connector jumper wires (2x)</span>](https://www.digikey.ca/en/products/detail/adafruit-industries-llc/4482/11594500)

   <br style="clear: both;"> 

  - **Wireless charging port (Dual charging):**

    <div style="float: right; margin-left: 10px; width: 500px;">
      <img src="_static/images/Electronic-parts-charging.png" width="500">
    </div>

    - [<span class="color-red">① Wireless charger transmitters (2x) </span>](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/113030020/5487569)
    - <span class="color-orange"> ② Mirco-USB to USB Type-A cables ([1 short](https://www.amazon.ca/gp/product/B073PQWY2B/) and [1 long](https://www.digikey.ca/en/products/detail/stewart-connector/SC-2AMK003F/8544577)) </span>
    - [<span class="color-blue">③ Power supply (5V 2A) </span>](https://www.digikey.ca/en/products/detail/xp-power/VEL05US050-US-BB/5023710)
   
    <br style="clear: both;"> 

### 3D printed parts: 

  - **Sensor package:**

     <div style="float: right; margin-left: 10px; width: 500px;">
      <img src="_static/images/Printed-parts-sensor.png" width="500">
     </div>

    - <span class="color-red">① Microcontroller backboard</span>
    - <span class="color-orange">② Sensor stand</span>
    - <span class="color-blue">③ Sensor package main enclosure</span>
    
    <br style="clear: both;"> 

  <br>

  - **Wireless charging port:** 

     <div style="float: right; margin-left: 10px; width: 500px;">
      <img src="_static/images/Printed-parts-charging.png" width="500">
     </div>

    - <span class="color-red">① Enclosure A side</span>
    - <span class="color-orange">② Enclosure B side</span>
    - <span class="color-blue">③ Base</span>
    - <span class="color-magenta">④ Transmitter supports (2x) </span>

    <br style="clear: both;"> 

  All the 3D printing files can be found in [this link](https://github.com/Neil-YL/wireless-color-sensor/tree/07829dd6418d59315a7711e57d3ba6ff898b8a76/CAD-File/STEP). If your 3D printer is Bambu Lab series, [project files](https://github.com/Neil-YL/wireless-color-sensor/tree/c080448a7fcbc0e26ace216282e9614ede66aa17/CAD-File/BamBu-File) are available for BambuStudio.

### Mechanical components and tools: 

  - **Mechanical components:**

     <div style="float: right; margin-left: 10px; width: 500px;">
      <img src="_static/images/Mechanical-Components.png" width="500">
     </div>

    - <span class="color-red">① M2.5-10mm screws (4x)</span>
    - <span class="color-orange">② M2.5 hex nuts (4x)</span>
    - <span class="color-blue">③ Painter's tape</span>

    <br style="clear: both;"> 

  - **Tools required:**
     <div style="float: right; margin-left: 10px; width: 500px;">
      <img src="_static/images/Bolt-nut-tape.png" width="500">
     </div>

    - <span class="color-red">Phillips-head #0 screwdriver</span>
    - Soldering set 
  
  <br style="clear: both;"> 

  - **Tools nice to have:**
    - Tools to remove 3D printing supports and deburr surface
    - Multimeter for electronic connection troubleshooting
   
  <div style="text-align: center; margin-top: 10px;">
    <img src="_static/images/Soldering.png" style="width: 750px;">
  </div>
 
 <br>
 
## Hardware assembly:

  ### Preparation / Before you begin assembling: 
  (Note: photos will be added for each step starting from here)
  #### 3D printed parts preparation:

   Remove all printing supports from the 3D-printed parts. Deburr all the supported surface, especially heighted areas (<span class="color-red">inner walls of the sensor package</span> and <span class="color-orange">those of the charging port enclosure A/B</span>) that will be used for assembly.

  <div style="text-align: center; margin-top: 10px;">
    <img src="_static/images/inner-wall.png" style="width: 500px;">
  </div>

:::{hint}
<span style="padding-left: 10px;">Use wirecutters to remove most of the supports from the printed parts.</span>  
<span style="padding-left: 10px;">Clean up remaining spikes with sharp utility knives or scissors.</span>
:::

 
   <br>

  #### Electronic parts soldering:
   
  1. **LipoSHIM:** 

     Place the LipoSHIM on the back of the PicoW, ensure <span class="color-red">the power button</span> of the LipoSHIM and <span class="color-blue">the micro-USB port</span> on the PicoW are on the same side.

     <div style="text-align: center; margin-top: 10px;">
       <img src="_static/images/PicoShim-soldering-1.png" style="width: 500px;">
     </div>

     <br>
     
     Solder <span class="color-orange">8 pins on each row</span> on the PicoW.

     <div style="text-align: center; margin-top: 10px;">
       <img src="_static/images/PicoShim-soldering-3.png" style="width: 500px;">
     </div>
     
     <br>

     You may connect the PicoW to a micro-USB power supply and use the power button to check the soldering connection; <span class="color-red">the white LED indicator</span> on the LipoSHIM should light up.
     
     <div style="text-align: center; margin-top: 10px;">
       <img src="_static/images/PicoShim-power-check.png" style="width: 500px;">
     </div>
     
     
  <br>

  
  2. **Battery connnector:**
     
     If you are working with the battery from the link provided in BOM section or if <span class="color-blue">the polarity of your battery</span> 2-pin JST connector is opposite to <span class="color-red">that of the LipoSHIM</span>:

     <div style="text-align: center; margin-top: 10px;">
       <img src="_static/images/Battery-soldering-1.png" style="width: 500px;">
     </div>

     :::{warning}
      Never connect your battery to PicoSHIM with wrong polarity!
     :::
      
     <a id="battery-connector"></a>
     You can correct it by cutting off the connector, swapping the wires, and then resoldering them to match the correct polarity.

     <div style="text-align: center; margin-top: 10px;">
       <img src="_static/images/Battery-soldering-2.png" style="width: 500px;">
     </div>

<br>

  3. **Wireless charging unit:** 

     Solder a jumper wire to <span class="color-blue">the GND pad</span> and another to <span class="color-red">the C1+ (or C2+) pad</span> on the receiver board.

     <div style="text-align: center; margin-top: 10px;">
       <img src="_static/images/Receiver-soldering-1.png" style="width: 500px;">
     </div>     

     <div style="text-align: center; margin-top: 10px;">
       <img src="_static/images/Receiver-soldering-2.png" style="width: 500px;">
     </div>   

     <br>

     Connect the transmitter to a power supply via micro-USB port and place the receiver on top of the transmitter (coils faced with coils). Check if <span class="color-blue">the blue LED charging indicator</span> on the transmitter board lights up. You may use a multimeter to measure the voltage between the two jumper wires; the reading should be approximately 5V.

     <div style="text-align: center; margin-top: 10px;">
       <img src="_static/images/Receiver-soldering-3.png" style="width: 500px;">
     </div>      


  #### Dual charging connection check:

   You may also check the connection of the dual wireless charging setup before start assembling. Use the short micro-USB/USB Type-A cable to connect both transmitters and connect the transmitter that has a free micro-USB port to a power supply. Test the receiver with the same procedure above for the wireless charging unit, the receiver should give a voltage reading of approximately 5V on each transmitter.

  <div style="text-align: center; margin-top: 10px;">
    <img src="_static/images/Dual-charging-test.png" style="width: 500px;">
  </div>      
  
  <br>
      
  ### Assembling:

  #### Sensor Package assembling:

  1. Connect battery to Picow and LipoSHIM assembly: 
  
      Ensure the polarity of the battery matches the +/- markings on the LipoSHIM, if you are using the battery from the link provided in BOM section, [reverse](#battery-connector) the polarity before connecting it to the LipoSHIM. 
     
     :::{warning}
       Never connect your battery to PicoSHIM with wrong polarity!
     :::

      Connect the battery to the LipoSHIM with the JST connector. Adjust the wires of the battery to through <span class="color-red">a row of pins</span> on the PicoW. 

     <div style="text-align: center; margin-top: 10px;">
       <img src="_static/images/Battery-Picow-1.png" style="width: 500px;">
     </div>   
    
     <br>

      Test connection: Press the button on the LipoSHIM to power on the PicoW; <span class="color-blue">the white LED indicator</span> on the LipoSHIM should light up. Connect the PicoW to a power supply via the micro-USB port; <span class="color-red">the red LED charging indicator</span> on the LipoSHIM should also light up. 

     <div style="text-align: center; margin-top: 10px;">
       <img src="_static/images/Battery-Picow-2.png" style="width: 500px;">
     </div>   

     <br>

      Power off and disconnect the power supply before proceeding with following steps.

  2. Mount PicoW on Picowbell: 
  
      Place the PicoW on the top of the Picowbell sockets; the micro-USB port on PicoW should be at the same side as the STEMMA QT port on Picowbell. Carefully align the pins and press down the PicoW to secure it onto the Picowbell. 
      
   :::{hint}  
   Since the power button on the PicoSHIM will interfere with the STEMMA QT port on the Picowbell, you don’t need to push the PicoW pins all the way down.
   :::

  3. Connect wireless charging receiver to Picowbell: 
  
      Connect the GND jumper wire from the receiver to the GND socket (third on the right) on the Picowbell. 
      
      Connect the positive jumper wire to the VBUS socket (first on the right) on the Picowbell. 
      
      Place the receiver on the powered transmitter, the red LED indicator on LipoSHIM and the blue LED indicator on the transmitter should light up.
 
  4. Connect AS7341 to Picowbell: 

      Connect AS7341 to Picowbell with a STEMMA QT wire. Turn on the Picow (using the button on the LipoSHIM), the green LED indicator on AS7341 should light on.

      Test the color sensor (software testing should come in here)


  5. Assemble Picowbell to the backboard: 

      Align the assemble holes on Picowbell to those on the backboard, ensuring that the micro-USB port on Picow is positioned on the side of the backboard's opening slot. Secure the screws and nuts with a screwdriver.

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


        



        

      


    


