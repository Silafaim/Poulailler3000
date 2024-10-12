# Poulailler3000
Simple ESP32 Door Opening and closing at certain (Hard-coded) times of the day

Based on an ESP32.
A table of the opening and closing times is hard inputed in the code, that you can find and edit in the Horaires_avec_offset.csv file.

Controls 2 pins of the GPIO, themselves controling 2 2P2T relays.
1rst controls the powering or not of a drill motor.
2nd controls the way the motor is powered, either normal or inverted. This ables to run it in one direction or the other, enabling to roll a rope in or out, thus pulling or letting down, the final door that we want to open.

TL;DR : A pin says "Up / Down", the other says "Motor On / Off".

The opening sequence is then "Up" > "On" > Wait > "Off".


## Hardware
- ESP32
- Links to a WAP connected to internet to get tim
## Software

- Connects via Wi-Fi to an NTP Server to get time and date
- Gets from it's inner table if it should be open or closed
- Makes the appropriate sequence to be in the state it should be.
- Powered via USB.


## DEBUGGING

### SERIAL PORT ONLY USED TO DISPLAY IP ADRESS

- The serial and logs are done via the WebSerial library. To access the WebSerial interface, refer to the WebSerial ReadMe or simply access (while ont hte same network as the AP you connected the ESP32 to) :


 ```bash
"yourIpAdressDiplayedInSerialMonitorAtTheSetup"/WebSerial
```

