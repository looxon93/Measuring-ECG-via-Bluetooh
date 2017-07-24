# ECG-with-bluetooth
Measuring ECG and sending it via Bluetooth module 

We used this ECG sensor: https://www.vernier.com/products/sensors/ekg-bta/ Offset of 1V was grate for measuring with Arduino, because Arduino only works with voltage between 0 and 5V. We used HC06 Bluetooth module. We used sensor that I have mentioned above, and Arduino platform as analog to digital converter. Then we just used Arduino command: Serial.println() that is used for sending data to COM port. Our COM port was that Bluetooth.


Next, we used Matlab to get data from Bluetooth, with some commands that you will see in our code. I add some comments in English just you can understand what command is doing what. Also, I have to say that we tested distance from which we can send data and it was around 5 meters.

# Hardware

Mentioned sensor was used for measuring ECG. We used disposable Ag/AgCl electrodes that are pre-gelled. Arduino was used for reading signals from ECG sensor by converting analog to digital signal. It was powered with 9V battery. Arduino TX pin is connected to two resistors that are connected in series first restitor has value: 1kΩ and second: 2kΩ. 2k resistor is connected with other end to the ground. That was used because logical high value is 5V, and RX pin receives logical high value of 3.3V. Signal that goes into RX pin is signal from point where two resistors are connected. Platform would work either way, but it is recommended to work this way.

Image of scheme can be seen here: https://user-images.githubusercontent.com/26125722/28544745-a4587074-70c4-11e7-8b55-54bd1bce63a3.JPG

Pin RX from platfrom goes directly to TX pin of module. Source for powering Bluetooth module is 5V pin on Arduino platform. Also there is GND pin on platform. Pin from connector that has SIG1 label is going to A0 pin on Arduino platform. That pin is used for reading signals. That signal needs to be in range from 0 to 5 V. A/D converter is 10-bit, so there is 1024 levels which means that smallest change of voltage that can be detected is 4.88 mV. Arduino command for reading input voltages is implemented that it reads levels, so in code there is conversion to voltage. With delay() command, sampling frequency is defined. Argument of delay function is miliseconds, which will be used for delaying code implementation.  


# Connection of Bluetooth module with PC
Bluetooth module should be paired with PC in order to work. That can be done with few steps. First in visible devices bluetooth module should be found (e.g. HC-06) and password for pairing is: 1234. This password can be changed like other parameters for initialisation of Bluetooth module. Once paired it will be remembered. When module is paired, PC will recognize module as COM port. In device manager in PC there should be HC-06, where number of serial port is written, and it can be changed in time. 
