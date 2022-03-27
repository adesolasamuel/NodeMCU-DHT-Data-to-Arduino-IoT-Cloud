# NodeMCU-DHT-Data-to-Arduino-IoT-Cloud
How to send DHT Data to Arduino Cloud Using ESP8266

FOR VIDEO GUIDE, GO TO: https://www.youtube.com/watch?v=wPsBiOMytGA 

IoT being an integral part of cloud computing, several cloud vendors make IoT part of the services they render. Also, with the emergence of IoT, there are different platform that makes IoT implementation available even to individuals. In this tutorial, I will be taking you through steps in sending data from NodeMCU, an IoT development platform to Arduino Cloud.
To ensure all necessary things are in place, you will have to set up your computer to communicate with NodeMCU or ESP8266 before you can follow along this tutorial.
In this tutorial, we will be using DHT 11 sensor to send Temperature and Humidity data to Arduino Cloud. 
Materials Needed
1.	NodeMCU or ESP8266
2.	DHT 11 sensor
3.	10K resistor
4.	Personal Computer
5.	Arduino IDE software
6.	Jumper Wires

# Step 1:
The very first step is to ensure that your PC has been configured to communicate with ESP 8266. If you haven’t did this already, now is the time. Once you have configured your PC, come right back to continue following this tutorial.
# Step 2:
Hardware Setup: Connect the NodeMCU and the DHT 11 to the breadboard, depending on your model of DHT 11, it can be a 3-pin ready made model or a 4-pin model, in this tutorial, I am using a 3-pin model. If you are using a 3-pin model, connect the VCC to 3V of the NodeMCU, GND of the DHT 11 to GND on the NodeMCU and connect the data pin to Pin 4 of the NodeMCU. If it is 4-pin model you are using, connect Pin 1 of the DHT11 to 3V of the NodeMCU, connect the 10K resistor between pin 1 and pin 2 of the DHT 11, leave pin 3 of the DHT 11 sensor unconnected and connect pin 4 of the DHT 11 to GND on the NodeMCU. Connect the NodeMCU via a USB cable to your computer and you are good to go.

![NodeMCU Azure (Time 0_01_46;11)](https://user-images.githubusercontent.com/55460620/160305727-67795581-2639-4d12-8e4c-750a0bdfc8f0.jpg)

# Step 3: 
After setting up the hardware connection, the next thing is to configure the cloud environment. To access Arduino IoT cloud, open your browser and type the URL cloud.arduino.cc, you will be presented with the Arduino IoT Cloud interface, on the webpage, click on the 9-dot option button at the right-hand corner and select IoT Cloud, a new page will be presented to you where you can define all your cloud parameters, the tabs on the page are Things, Dashboard, Device, Integrations and Template. To add a new IoT device to the cloud, under Things click on Create Thing.
![Screenshot 2022-03-26 214702](https://user-images.githubusercontent.com/55460620/160305778-968a002b-d312-45a7-94e8-f74047609288.png)

![Screenshot 2022-03-26 215058](https://user-images.githubusercontent.com/55460620/160305779-4efb1c06-e5c3-43c1-99d7-e3869e80b434.png)


