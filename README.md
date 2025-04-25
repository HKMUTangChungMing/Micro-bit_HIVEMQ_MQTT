# Micro-bit_HIVEMQ_MQTT
Micro-bit_HIVEMQ_MQTT


# **The University of Hong Kong Metropolitan University**

## S&T SUMMER INTERN

## Make Code Micro: Bit instructions

## Elec freaks Smart AI Lens Kit Wi-Fi Control LED with English

# DEMO

![t1swq-sn9cm.gif](https://s2.loli.net/2025/04/25/xQ4umOVt5jks8Za.gif)

# *Hardware*

First Micro:bit with Elec freaks Smart AI Lens Kit.(Publisher)

![image-20250425114805754](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425114805754.png)

Second Mirco:bit with LED.(Subscriber)

![image-20250425114816866](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425114816866.png)



# *Coding*

Regarding the Make Code *(Publisher )*

![image-20250425114839556](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425114839556.png)  

Regarding the MakeCode *(Publisher )*

![image-20250425114914500](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425114914500.png) 

![image-20250425114924787](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425114924787.png) 



Regarding the MakeCode *(Subscriber)*

![image-20250425114940760](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425114940760.png)

![image-20250425114952173](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425114952173.png)

Regarding the MakeCode *(Subscriber)*

![image-20250425115004611](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115004611.png)



# *Hardware contention*

Elec freaks Smart AI Lens KitD

![image-20250425115020361](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115020361.png)





![image-20250425115836736](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115836736.png)



LED & Breadboard

![image-20250425115040139](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115040139.png) 

![image-20250425115050230](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115050230.png)

# *Regarding the Broker*

We use HiveMQ to check the subscriber.

If we publish the message is 1, then the LED was turn on the Light.

If we publish the message is 0, then the LED was turn off the Light.

![image-20250425115102300](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115102300.png)

# *Training the AI by the image*

We teach the Elec freaks Smart AI Lens Kit to learn the image.

First we teach the close order, so we need to publish the 『關』image mean that is close order.

![image-20250425115857206](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115857206.png)



Second we teach the open order, so we need to publish the 『開』image mean that is open order.

![image-20250425115135310](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115135310.png) 

# *Show the result*

We use the Elec freaks Smart AI Lens Kit Camera to detect the image.

Below it detect the『開』image the signal is 1, so the the LED was turn on. Also, the Screen was show the “open”.

![image-20250425115152156](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115152156.png)

![image-20250425115159661](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115159661.png)

After it detect the 『關』image signal is 0, so the LED was turn off. Also, the Screen was show the “close”.

![image-20250425115214409](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115214409.png)

![image-20250425115226072](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115226072.png)

# *Deconstruct the code*

Now, we will deconstruct the makeCode by Micro:bit, let get started. 

We have both Publish part and Subscriber part. 

 

First, let’s discuss the Publish part, 

 

Since we need to confirm if the Wi-Fi is connected, we use the Boolean to check true or false.

If the Wi-Fi is connected, then Micro:bitwill display the “SMALL HEART” icon, otherwise, the icon will not be displayed.

![image-20250425115237504](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115237504.png) 

This block initializes the Elec freaks Smart AI Lens Kit Camera.

![image-20250425115255299](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115255299.png) 



Click button A, then the Elec freaks Smart AI Lens Kit Camera will capture the image, place the image model into the machine for training, and then publish the trained data to ID1. If successful, the micro:bit will display the "take" icon.

![image-20250425115310696](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115310696.png)

These blocks mean that if the Elec freaks Smart AI Lens Kit detects an image from the camera that matches the ID1 image, then the OLED (publisher) will display the string "open", and also send the message "1" to the broker. According to the rule, the topic needs to be input as "home/light", and QoS should be "1". Since the message is a string, we need to convert the string to an integer, so we use the "PARSE TO NUMBER MESSAGE" to do this. 

 

If the message is "1", it means that it is the "open" close signal from the pin blocks.

![image-20250425115323154](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115323154.png)



Same to the top, however the message is “0”, means that is the “close“signal by the pin blocks.

![image-20250425115334928](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115334928.png)




First, We input the correct Wi-Fi SSID and KEY, so we need to connect the Wi-Fi.

Since we use the MQTT protocol to transfer the data, then choose “TLS” by the scheme. 

Then ClientID is normal, also username and password need to confirm by broker, 

Finally, host need to input “Cluster URL” by the Cluster. Port also input 8883. 

![image-20250425115351281](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115351281.png)

![image-20250425115358655](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115358655.png)

Second, we take about Subscribe part,

![image-20250425115411972](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115411972.png)

 This is the Subscribe part, where we use the data sent back by the Broker and convert it on the Micro:bit to control the LED light and OLED screen. First, we need to input a topic that matches the Publisher, for example, "home/light", and the QoS needs to be set to "2". If the message sent from the Publisher is "1", the Subscriber's OLED screen will display "open". In addition, we use the value of the message to set Pin 1. If the value received by Pin 1 is 1, then the LED light on the breadboard will "light up".

![image-20250425115940456](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115940456.png)

Similarly, in another scenario, if the message sent from the Publisher is "0", the Subscriber's OLED screen will display "close". In addition, we use the value of the message to set Pin 1. If the value received by Pin 1 is 0, then the LED light on the breadboard will "turn off".

# *Summary*

We use this technology to implement the data transfer using Micro:bit between two different area or network. In this case, we using Elec freaks Smart AI Lens Kit to control the LED. 

Regarding the MQTT Protocol, we have Publisher, Broker, Subscriber. 

In this project, Elec freaks Smart AI Lens Kit with Micro:bit is Publisher, LED with Micro:bit is Subscriber. HiveMQ is Broker. First, we train the image, after we use the image to control the LED.

![image-20250425115503368](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115503368.png)

![image-20250425115956672](http://pdm888.oss-cn-beijing.aliyuncs.com/img/image-20250425115956672.png)
