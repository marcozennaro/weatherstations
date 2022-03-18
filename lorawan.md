# What is LoRaWAN?

![LoRaWAN](images/img\_lorawan/lorawan.jpg)

<<<<<<< HEAD
![](images/img_lorawan/lorawan.jpg?width=100%)
=======
LoRaWAN is a communication protocol designed for long distance and low power consumption. To meet these goals it sacrifices transmission speed, so it is not good for video or high speed data, but it is well suited for infrequent and short messages, like meteorological data.
>>>>>>> 3ddd276cec2641d279c4aded5890ff780e9871ba

The modulation technique employed is adaptive, meaning that the same information can be sent in a short time to nearby nodes, while a longer transmission time needs to be allocated to reach far away nodes, or traverse heavily wooded areas that will absorb part of the signal.

The main difference with Cellular technologies is the usage of unlicensed frequencies, meaning that it can be deployed without a specific permit (avoiding the associated costs), providing that certain rules regarding the maximum transmitting power and maximum transmission time are followed.

In Africa and Europe the maximum transmission time at a given frequency is 1%. This means that if the transmission lasts, for instance, 1 second, the device must not transmit again in the following 99 seconds (1.65 minutes). Since there are 8 carrier frequencies available in the 868 MHz band usable in Africa and Europe, the device could nevertheless switch to a different frequency to start the timer from scratch.

A LoRaWAN network consists of end nodes (normally fitted with some kind of sensors) that communicate with one or more gateways. The gateways are controlled by a Network Server, which directs the traffic to the specific Application Server. Since the traffic is encrypted from the end node to the Application Server, only the authorized user of a given application will be able to access the respective data by means of a web browser.

The generic layout of a LoRaWAN network is the following:

![](images/img\_lorawan/media/image1.png)

The connection between the Gateways and the Network Server can be by means of an Ethernet Cable, Cellular service (2 G, 3G or 4G) WiFi or even by means of a Satellite link, normally employing the Internet Protocol (IP). The Network and Application servers can be located anywhere as long as there is connection among them and the Gateway. They can even be implemented in the same box together with the Gateway.

As an example, the end node is a Meteorological station installed at the ICTP in Italy. In this case, 3 different gateways were able to receive the same transmitted data, with the following parameters:

_"frequency": 867.9,_ (megahertz)

_"Air time 41 ms"_, actual time the packet spent on transmission of 24 data byes, so the real throughput is 4.683 kbit/s

_"modulation": "LORA"_,

_"data\_rate"_: "SF7BW125",(spreading factor 7, bandwidth 125 kHz, the raw data rate is 125/7 = 17.8 kHz)

_"coding\_rate": "4/5"_, (This means that an extra redundant bit is transmitted every 4 data bits to combat interference)

_"gateways"_ that received the transmission:

_"gtw\_id": "eui-b827ebfffebfbee2"_, This gateway is located close to the end node.

_"gtw\_id": "eui-58a0cbfffe801146"_, This gateway is located In the basement of the building

_"gtw\_id": "eui-ac1f09fffe0148c0"_, This gateway is located 2 kilometers away

Each of these gateways was connected to the Internet by means of an Ethernet cable. They sent the same message to _ttn-router-eu_, the TTN Network server for Europe encapsulated in an Internet Protocol message.

The network server reads the embedded application identifier and forwards the payload (meteo data) as another IP (Internet Protocol) message to the Barani Meteorological application server where the payload is decoded. The data is also sent to the Allmeteo server which makes it available as a web page to any authorized user as seen in the following image:

![](images/img\_lorawan/media/image2.png)

Note that the TTN network server in Europe is handling traffic from a great number of gateways, but it cannot read the payload that it is forwarding, it only reads the application identifiers and forwards the traffic to the respective application server.

In summary, the meteorological data captured by the sensors are sent as the payload of a LoRaWAN packet to the gateway, which reads only the application identifier, strips the LoRaWAN protocol and builds an IP packet containing the payload and the address of the application server. The application server decrypts the data with the application key supplied by the owner of the data and presents them accordingly.

End of file.
