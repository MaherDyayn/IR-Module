An Infrared wireless module PCB created using Altium designer 2020

components used

1)IR sensors(2)

2)74HC595D shift register(1)

3)D flip flop(8)

4)MC14028BDR2G decoder(1)

5)NOT gates(2)

An Arduino or any other microcontroller has a limited number of I/O pins. And for applications that require more pins, we use a shift register. The shift register usually takes up 3-I/O pins of the microcontroller but gives 8 in return. The only downside of a shift register is that the 8-I/O pins that it provides cannot be individually controlled. In order to change one pin to a high/low, all 8 pins will be quickly reset as well. Hence a lot of extra code is needed to get the pins to behave as normal Arduino I/O pins. This project adds extra hardware to the shift-register to tackle this issue.

This module allows you to receive IR signals from a remote or an arduino.
The two IR sensors are connected to the shift register, one to the serial data pin and the other to the shift register clock. At its core this is basically
a SIPO shift register with additional parts like Dlatches and decoders to enanble us to latch the shift register outputs. Latching the shift register output allows
us to use the shift-register output as a regular output pin. The shift register is connected to a D latch through a decoder.
Outputs 0,1 and 2 of the shift register become inputs to the decoder and  detremine the index of the final output pin,
eg: if output pins 0,1,2 read-000 then output pin with index '0' is selected.
output pin 3 of the shift register assigns a value for the pin selected above
and output pin 4 of the shift register will trigger the storage register clock
