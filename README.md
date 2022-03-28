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

# Step 4:
After clicking on create thing, you can give your thing a name by clicking on Untitled, on this window, we will be able to define variables that our thing will be sending to the cloud, we will choose our device type and also set up connectivity. On this page, there are three tabs to work on, Setup, Sketch and Serial Monitor, the first tab we will be working on is Setup, here we can define our variables. Variables depends on the kind of data you will be receiving from your device, if its temperature, volume, Boolean etc. you will define it in the variable. To add a variable, click on Add Variable

![image](https://user-images.githubusercontent.com/55460620/160307089-2383d7e9-8e3c-4c65-8c51-3cdd22dc7144.png)

Give your Variable a name and select the type of data it will hold, leave everything else as default and click on Add Variable. Repeat this step for all variables you will take from your IoT device.
 
![image](https://user-images.githubusercontent.com/55460620/160307164-fa5a6aba-4640-4611-af55-901ea7da37e5.png)

# Step 5: 
After adding all needed variables, the next things is to link your IoT device with the Cloud. Under device, click on the link button and click on Set up New Device, then select Third party device. 

![image](https://user-images.githubusercontent.com/55460620/160307198-a5334a7a-acf0-4c19-933a-a1debbf35020.png)

![image](https://user-images.githubusercontent.com/55460620/160307258-69480857-566d-475c-a68d-1175b753f029.png)

![image](https://user-images.githubusercontent.com/55460620/160307265-0666b70b-14d4-40ff-8471-85cce4e93749.png)
 
Select ESP8266 as device type and NodeMCU as device model. After that click on continue and you will be asked to give your device a name, type in a suitable name and it must not contain any special character and click on Next.

![image](https://user-images.githubusercontent.com/55460620/160307365-1ec0aae8-1654-47bf-a446-3e3cbec84c72.png)

![image](https://user-images.githubusercontent.com/55460620/160307369-b98a2c1a-a10d-4245-8357-bd6aa11a72f6.png)

After this you will be presented with your device ID and key, copy these two down as you will need them in your code. There is also an option for you to download them as PDF.

![image](https://user-images.githubusercontent.com/55460620/160307383-9b00cd72-17e3-4725-a6a1-84104793f05c.png)

If you are able to achieve this, you are all set. You have successfully added your device to the cloud. Offline status will be showed meaning you have not connected your device to the cloud.

![image](https://user-images.githubusercontent.com/55460620/160307405-25323aab-3556-4789-a4b9-88b95bfa5d9e.png)

# Step 6: 
The next thing to set up is the network, click on the network button, Type in your network details and paste the secret key you copied earlier.

![image](https://user-images.githubusercontent.com/55460620/160307429-e6e1aec5-0d3c-45cc-93d5-28b30ba7ea21.png)

![image](https://user-images.githubusercontent.com/55460620/160307437-5ba635ef-7b67-45b5-a871-a1acc3463f33.png)

# Step 7: 
Go to the Sketch tab and click on generate new sketch, your IoT cloud will generate a new sketch based on the variables you inputted.

![image](https://user-images.githubusercontent.com/55460620/160307468-459e6726-70db-44d7-9ee9-983314d82ba4.png)

![image](https://user-images.githubusercontent.com/55460620/160307471-c1322df4-82e1-4e2d-b756-77dcfbb2be46.png)

To better work on your sketch, click on Open full Editor. Here, I have to point out that if you haven’t work with Arduino cloud before, you have to download Arduino cloud agent, in most cases, on you first time of accessing the Arduino cloud, you will be guided on how to install this. If not, just search for Arduino cloud Agent from google and you will be guided on how to set it up.

# Step 8: 
The next thing you want to do is to set up your dashboard, go back to IoT Cloud and click on Dashboard. Click on Build Dashboard and you will be able to add widgets through the add button.

![image](https://user-images.githubusercontent.com/55460620/160307496-a00471fa-68d6-4463-a891-e94d118b490f.png)

![image](https://user-images.githubusercontent.com/55460620/160307505-7e07cb89-59da-4c58-9f52-85f6d00e015a.png)

For this tutorial, I will be adding Switch for controlling and LED, chart and a gauge. After selecting Switch, you can give it a name, then click on Link Variable and select the right variable and click Done. Follow the same procedure to link other widgets you want.

![image](https://user-images.githubusercontent.com/55460620/160307514-e3eba7d4-1bc4-42f7-9a36-bd995219b7d3.png)

![image](https://user-images.githubusercontent.com/55460620/160307519-7f2be916-89bf-4ca2-b4a3-1097bfd6efe9.png)

![image](https://user-images.githubusercontent.com/55460620/160307529-dd19c3a3-2c45-45a5-9496-e4e4ad531337.png)

Finally, I have:
![image](https://user-images.githubusercontent.com/55460620/160307545-2e40a1b1-4b9c-44a8-b93e-5abf6b3dac8d.png)

# Step 9:  
Go back to the full monitor and include DHT 11 library from the library manager. Copy the code from my GitHub page, https://github.com/adesolasamuel/NodeMCU-DHT-Data-to-Arduino-IoT-Cloud  and edit all necessary credentials, connect your board to the computer and upload the code. Go back to your Dashboard and you should see the charts reading showing data has been successfully sent to the Dashboard from our IoT device. You can also monitor the data on your mobile phone by downloading IoT Remote (Arduino Cloud) from your app store. Check out the Video Link below for a step by step 

![image](https://user-images.githubusercontent.com/55460620/160307564-e8e4618e-404e-4a89-a717-045aa47edafa.png)

![image](https://user-images.githubusercontent.com/55460620/160307571-3316c17c-07ba-4e9a-a030-4c22310910e7.png)

![image](https://user-images.githubusercontent.com/55460620/160307583-b5d9e768-84d1-476a-bcb5-62d24bde81f2.png)

![image](https://user-images.githubusercontent.com/55460620/160307593-9a6a030c-4827-4ae7-b861-9a4443277389.png)


FOR VIDEO GUIDE, GO TO: https://www.youtube.com/watch?v=wPsBiOMytGA 




