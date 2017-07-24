# ECG-with-bluetooth
Measuring ECG and sending it via Bluetooth module 

We used this ECG sensor: https://www.vernier.com/products/sensors/ekg-bta/ Offset of 1V was grate for measuring with Arduino, because Arduino only works with voltage between 0 and 5V. We used HC06 Bluetooth module. We used sensor that I have mentioned above, and Arduino platform as analog to digital converter. Then we just used Arduino command: Serial.println() that is used for sending data to COM port. Our COM port was that Bluetooth.


Next, we used Matlab to get data from Bluetooth, with some commands that you will see in our code. I add some comments in English just you can understand what command is doing what. Also, I have to say that we tested distance from which we can send data and it was around 5 meters.
