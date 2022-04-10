Overview
############

This version of the PCB based reflow plate aims to be as modular as
possible to allow for many configurations and parts to be replaced.
There are 5 main boards in the project:

* MCU board
* Power board
* I/O board
* Heating board
* Backplane
  
Each of these boards interconnect in order to create a fully functional
reflow plate. The standard interfaces that these boards provide allow
for more boards to be added in the future and for boards to be swapped
in and out allowing for a great range of expandability. As well as the
boards being swappable, the backplane also provides a number of GPIO
pins for extra expandability beyong the 5 boards.
