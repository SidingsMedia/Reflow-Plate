Overview
########

This version of the PCB based reflow plate aims to be as modular as
possible to allow for many configurations and parts to be replaced.
There are 5 main boards in the project:

* MCU board
* Power board
* I/O board
* Heating board
* Backplane
  
Pinout
======

Each of these boards interconnect in order to create a fully functional
reflow plate. The boards are stackable allowing for multiple boards to
be added. The standard interface between the boards is shown below.

.. code-block::

                          +----------------------+----------------------+
                   5V ----+                      |                      +---- SDA
                          | LOGIC POWER          |                  I2C |
                  3V3 ----+                      |                      +---- SCL
                          +----------------------+----------------------+
              SENSE A ----+                      |                      +---- TX0
                          |                      |                UART0 |
              SENSE B ----+                      |                      +---- RX0
                          |                      +----------------------+
              SENSE C ----+ TEMPERATURE SENSORS  |                      +---- TX1
                          |                      |                UART1 |
              SENSE D ----+                      |                      +---- RX1
                          |                      +----------------------+
              SENSE E ----+                      |                      +---- GPIO0
                          +----------------------+                      |
              SENSE A ----+                      |                      +---- GPIO1
                          |                      |                      |
              SENSE B ----+ CURRENT SENSING      |                      +---- GPIO2
                          |                      |                 GPIO |
              SENSE C ----+                      |                      +---- GPIO3
                          +----------------------+                      |
                RESET ----+ SYSTEM RESET         |                      +---- GPIO4
                          +----------------------+                      |
                   NC ----+                      |                      +---- GPIO5
                          |                      +----------------------+
                   NC ----+                      |                      +---- SCLK
                          |                      |                      |
                   NC ----+                      |                      +---- MOSI
                          +----------------------+                      |
    HEATER CONNECTION ----+                      |                      +---- MISO
                          | HEATER CONNECTIONS   |                      |
    HEATER CONNECTION ----+                      |                      +---- SS1
                          +----------------------+                  SPI |
                  12V ----+                      |                      +---- SS2
                          |                      |                      |
                  12V ----+                      |                      +---- SS3
                          |                      |                      |
                  12V ----+                      |                      +---- SS4
                          | PCB HEATER POWER     |                      |
                  GND ----+                      |                      +---- SS5
                          |                      +----------------------+
                  GND ----+                      |                      +---- GND
                          |                      |            LOGIC GND |
                  GND ----+                      |                      +---- GND
                          +----------------------+----------------------+

Mechanical Specifications
=========================

In order to maintain mechanical compatibility between all boards, a
specification has been created to stipulate the positioning of the
inter-board connections. The headers have been set at the spacing of a
standard 2.54mm breadboard allowing for easy development of custom
boards without the cost of PCB manufacture.

.. figure:: /_images/structure/mechanical.png
    :scale: 75%
    :alt: Mechanical drawing of board

    The mechanical drawing of the stackable board.