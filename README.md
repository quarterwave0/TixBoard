# TixBoard - Digital Communications Education Board
### Schematic and idea derived from a [April 2022 thread from @m_ou_se on Twitter.](https://twitter.com/m_ou_se/status/1511091323612413965)

The TixBoard is a hands-on digital communications demonstration and education tool designed for everyone passionate about learning. From absolute beginners looking for a tactile introduction to how various flavors of digital communication function to experienced makers, educators, precocious cats, or bacteria looking for a unique perspective on the protocols that make our digital world tick.

![plot](./product.jpg)

## Operation

The TixBoard features a single RCA socket as its medium of communication. It utilizes inexpensive RCA cables and splitters to make arbitrary and easily reconfigurable networks of TixBoards, whether point-to-point or on a shared bus. On the board side, it features three switches that allow for the rapid and straightforward reconfiguration of any TixBoard. It is powered by two AA batteries, which should last a long time **provided that the output not be high during storage, as this will result in the LED running and draining the battery.** It is best to set the board to Hi-Z and disable the Pull-Up switch before storing your TixBoard. The "Status" LED serves as a visual indicator of both the input received by the TixBoard in input mode and the output of the TixBoard in output mode. The "Short" LED alerts the user when they have connected TixBoards in a way that will result in excessive battery drainage.

### Input(Hi-Z)/Output Switch
The Input/Output switch is used to change the behavior of the TixBoard. The TixBoard can be configured to **Input(Hi-Z)**, where the TixBoard will act as an input, simply allowing the LED to flash with the input. Input(Hi-Z) can also be used as part of three-state logic so that when it is switched to Hi-Z[^1], it will effectively not influence the communication system. When switched to output, the behavior of the TixBoard is determined by the Low/High switch.

### Low/High Switch
The **Low/High** switch determines whether the TixBoard outputs logical high or low. When set to high, the TixBoard will output a logical high. When set to low, it will bring its output to ground. If two TixBoards are connected so that the logical high output of one is sunk directly into the logical low output of another, the short LED will illuminate. Do not fear- your boards are not in peril. It is just a warning that the rate of battery drain will increase.

### Pull-Up Switch
The **Pull-Up** switch is used to make the output of the TixBoard default to logical high with the onboard 22kΩ pull-up resistor. A real-world example would be the I²C protocol, which grounds the output to produce a logical low and toggles Hi-Z to let the pull-up resistor take the output to a higher voltage to make a logical high. If the output is enabled and is low, the pull-up will sink into the low, however, the drain rate will be very low.

### Examples

For some example operations, here are some Youtube videos I made that cover two good examples: Morse code and I2C.

[Morse Code](https://youtu.be/1-J6O0SY3v4)

[I2C](https://youtu.be/L52Stvm2y-I)

### License
Hardware is covered under CERN-OHL-P v2, meaning there are some restrictions on how this can be used. Read more [here](https://choosealicense.com/licenses/cern-ohl-p-2.0/).

This file, README.md, the primary source of documentation for this device,  is covered under CC0 1.0, meaning it is free for literally anything you could dream of.

[^1]: Fancy engineering speak for high impedance, a state where the output will let minimal current through. Think of it as a floating wire, as there is no path to ground. Quite literally, the Hi-Z/Input path is a dead end.