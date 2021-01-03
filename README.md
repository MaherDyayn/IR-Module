An Infrared wireless module PCB created using Altium designer 2020

components used

1)IR sensors(2)

2)74HC595D shift register(1)

3)CD4043BDG4 S-R latch(1)

4)MC14028BDR2G decoder(1)

5)AND gates(4)

6)NOT gates(4)

This module allows you to receive IR signals from a remote or an arduino.
The two IR sensors are connected to the shift register, one to the serial data pin and the other to the shift register clock. At its core this is basically
a SIPO shift register with additional parts like S-R latches and decoders to enanble us to latch the shift register outputs. Latching the shift register output allows
us to use the shift-register output as a regular output pin.
