---
title: Wireless metereological system
weight: 30
---

The wireless meteorological system is composed of the meteorological
sensors (temperature, air pressure, humidity, irradiation and rain
amount), a LoRaWAN transceiver (transmitter/receiver) that sends data
every 10 minutes to an Internet connected LoRaWAN gateway, and the
back-end servers that process the data and make it available to the user
through a web page, accessible by any Internet browser.

The meteorological sensors are housed in a helical radiation shield to
minimize the effect of solar radiation in the temperature measurements,
as well as to protect the electronic circuitry powers the meteorological
station.

The gateway should be powered from the electrical grid if available, but
can also be powered by a suitable photovoltaic system

## System diagram

![](/en/Documentation/basics/images/img_wireless_metereological_system/media/image1.png)

The weather station has built in temperature, pressure, humidity and
irradiation sensors inside an helicoidal radiation shield that provides
a more accurate temperature reading. It has a LoRaWAN transceiver
(transmitter and receiver) that conveys the gathered data to any LoRaWAN
Gateway in range using the wireless medium. The weather station is
powered by a built-in solar panel and battery that will last over a year
in normal usage. The rain gauge (pluviometer) is a separate device
connected to the LoRaWAN transmitter through a cable. An external
photovoltaic module consisting of a solar panel, battery and regulator
can be used to supply power to the gateway. The gateway forwards the
data using the cellular network, Ethernet, WiFi or any other technology
to the TTN LoRaWAN servers on the Internet as well as to a dedicated
repository for long term storage; https://weather.allmeteo.com. Users
with proper credentials can access the data with any Internet browser
fitted device (smart phone, laptop, etc.).

The gateway also transmits configuration commands originating from the
LoRaWAN network server to the end node to change the operating frequency
and spreading factors and therefore the packet duration.

End of file.
