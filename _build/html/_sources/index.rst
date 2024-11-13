.. wireless color sensor documentation documentation master file, created by
   sphinx-quickstart on Thu Nov  7 10:53:02 2024.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Getting started guide for wireless color sensor
=================================================
.. toctree::
   :maxdepth: 2
   :caption: Contents:

Overview
--------

This documentation provides a guide to assemble and test a color sensor package with a wireless charging port that could be implemented to the OT-2 liquid handling robot. The estimated time (tba)

Prerequisites
-------------

This documentation assumes that readers have completed the Light Color Sensor microcourse and possess basic knowledge of electronic soldering and wiring techniques.

Bill of materials
-----------------

**Electronic parts**:

.. raw:: html

   <div style="float: right; margin-left: 10px; width: 500px;">
       <img src="_static/images/Electronic-parts-sensor.png" alt="Electronic parts" width="500">
   </div>

* **Sensor Package**:

  
  * .. raw:: html

      <div class="color-red">PicoW</div>
  * .. raw:: html

      <div class="color-blue">Pico LipoSHIM</div>
  * .. raw:: html

      <div class="color-orange">Picowbell P5905</div>
  * .. raw:: html

      <div class="color-green">Wireless charger receiver</div>
  * .. raw:: html

      <div class="color-magenta">AS7341 color sensor</div>
  * .. raw:: html

      <div class="color-yellow">Lipo battery with 2-pole JST connector wire</div>
  * .. raw:: html

      <div class="color-purple">STEMMA QT Wire</div>
  * .. raw:: html

      <div class="color-cyan">1 Pin male connector jumper wires (2x)</div>



.. raw:: html

   <br>


.. raw:: html

   <div style="float: right; margin-left: 10px; width: 500px;">
       <img src="_static/images/Electronic-parts-charging.png" alt="Electronic parts" width="500">
   </div>

* **Wireless charging port (Dual charging)**:
  
  * .. raw:: html

      <div class="color-red"> Wireless charger transmitters (2x)</div>
  * .. raw:: html

      <div class="color-orange"> Micro-USB to USB Type-A cables (1 short and 1 long) </div>
  * .. raw:: html

      <div class="color-blue"> Power supply (5V 2A)</div>

.. raw:: html

   <br>
   <br>
   <br>
   <br>
   <br>
   <br>
   <br>

**3D printed parts:**

.. raw:: html

   <div style="float: right; margin-left: 10px; width: 500px;">
       <img src="_static/images/Printed-parts-sensor.png" alt="Electronic parts" width="500">
   </div>

* **Sensor package**:

  * .. raw:: html

      <div class="color-red"> Microcontroller backboard </div>
  * .. raw:: html

      <div class="color-orange"> Sensor stand </div>
  * .. raw:: html

      <div class="color-blue"> Sensor package main enclosure</div>

.. raw:: html

   <br>
   <br>
   <br>
   <br>
   <br>

.. raw:: html

   <div style="float: right; margin-left: 10px; width: 500px;">
       <img src="_static/images/Printed-parts-charging.png" alt="Electronic parts" width="500">
   </div>

* **Wireless Charging port**:

  * .. raw:: html

      <div class="color-red"> Enclosure A side </div>
  * .. raw:: html

      <div class="color-orange"> Enclosure B side </div>
  * .. raw:: html

      <div class="color-blue"> Base</div>
  * .. raw:: html

      <div class="color-magenta"> Transmitter supports (2x)</div>

  *(Note: More details about 3D printing files should be added here)*

.. raw:: html

   <br>
   <br>
   <br>
   <br>
   <br>
   <br>
   <br>
   <br>

**Tools**:

* **Required**:

  * Soldering set
  * Phillips-head #0 screwdriver
  * M2.5-10mm screws and M2.5 hex nuts (4x each)
  * Painter's tape

* **Nice to have**:

  * Tools to remove 3D printing supports and deburr surface
  * Multimeter for electronic connection troubleshooting

Hardware assembly
-----------------

**Preparation / Before you begin assembling**:

Note: Photos will be added for each step starting from here

**3D printed parts preparation**:

Remove all printing supports from the 3D-printed parts. Deburr the inner walls of the sensor package and the charging port enclosure, especially areas that will be used for assembly.

Electronic soldering:

1. **LipoSHIM**:

   Place the LipoSHIM on the back of the PicoW. Ensure the button on the LipoSHIM is on the same side as the micro-USB port on the PicoW. Solder 8 pins on each row on the PicoW.

2. **Battery connector**:

   If the polarity of your battery's 2-pin JST connector is opposite to that of the LipoSHIM, you can correct it by cutting off the connector, swapping the wires, and resoldering them to match the correct polarity.

3. **Wireless charging unit**:

   Solder a jumper wire to the GND pad and another to the C1+ (or C2+) pad on the receiver board. Connect the transmitter to a power supply via USB cable and place the receiver on top of the transmitter (coils to coils). Check if the blue LED charging indicator on the transmitter board lights up. You may use a multimeter to measure the voltage between the two jumper wires; the reading should be approximately 5V.

**Dual charging connection check**:

  You may check the connection of the dual wireless charging setup before start assembling. Use the short micro-USB/USB Type-A cable to connect both transmitters and connect the transmitter with a free micro-USB port to a power supply. Test the receiver using the same procedure above; the voltage reading should be approximately 5V on each transmitter.

Assembling
----------

Sensor Package assembling:

1. **Connect battery to PicoW and LipoSHIM assembly**:

   Ensure the battery connector's polarity matches the +/- markings on the LipoSHIM. Connect the battery to the LipoSHIM with the JST connector. Adjust the wire of the battery to pass through a row of pins on the PicoW.

   Test connection: Press the button on the LipoSHIM to power on the PicoW; the white LED indicator on the LipoSHIM should light up. Connect the PicoW to a power supply via the micro-USB port; the red LED charging indicator on the LipoSHIM should light up as well. Power off and disconnect the power supply before proceeding.

2. **Mount PicoW on Picowbell**:

   Place the PicoW on the top of the Picowbell sockets; the micro-USB port on PicoW should be at the same side as the STEMMA QT port on Picowbell. Carefully align the pins and press down the PicoW to secure it.

3. **Connect wireless charging receiver to Picowbell**:

   Connect the GND jumper wire from the receiver to the GND socket (third on the right) on the Picowbell. Connect the positive jumper wire to the VBUS socket (first on the right) on the Picowbell. Place the receiver on the powered transmitter; the red LED indicator on LipoSHIM and the blue LED indicator on the transmitter should light up.

4. **Connect AS7341 to Picowbell**:

   Connect AS7341 to Picowbell with a STEMMA QT wire. Turn on the PicoW (using the button on the LipoSHIM); the green LED indicator on AS7341 should light on.

5. **Assemble Picowbell to the backboard**:

   Align the assembly holes on Picowbell to those on the backboard, ensuring that the micro-USB port on PicoW is positioned at the opening slot side of the backboard. Secure the screws and nuts with a screwdriver.

6. **Place sensor stand to the main enclosure end**:

   Position the sensor stand with the thinner edge close to the enclosure's opening and spikes on the top. Insert it into the sensor end of the main enclosure.

7. **Secure the color sensor to the stand**:

   Face down the AS7341, aligning the assemble holes with the spikes, and secure it to the stand.

8. **Place wireless charger receiver on the inner wall of the enclosure and secure with painter's tape.**

9. **Aligning and assembling the backboard to the main enclosure.**


Dual Charging port assembling:

1. **Join the A and B sides of the charging port enclosure and secure both parts together.**

2. **Plug the short micro-USB cable into one transmitter.**

 Place the transmitter onto the transmitter support, route the coil wire down, and insert the support into the port enclosure.

3. **Thread the long micro-USB cable into the assembly and place the second transmitter similarly.**

4. **Arrange the cables and secure the base board to the port enclosure.**

Software part
-------------
*(Additional software instructions will be provided here)*