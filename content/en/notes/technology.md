---
title: "Radio Network Technology"
date: 2021-10-26T23:05:49+02:00
---
The primary radio network technology that seems to be suitable is called
LPWAN (Low Power Wide Area Network). LoRa (Long Range, Low Radiation) radio
technology is an open industry standard and is readily available due to its
popularity. The "Internet of Things" IOT is based on this technology.
However, the following star-shaped structure is used in these networks,
known as LoRaWAN:
``` 
 Nodes  o))   LoRaWAN
               >O -------- Internet ------- Application
        o))   Gateway                       Server
```
The 'things' also called nodes communicate with a LoRaWAN gateway which is 
connected to the Internet and in turn communicates with the application 
associated with the nodes on a server. However, we want to form a LoRa Mesh 
network:
```
      o)    >o)     >o)     >o
```
Here, the message is passed from the sending node via the intermediate nodes 
on to the recipient.

## Article

[A LoRa-Based Mesh Network for Peer-to-Peer Long-Range Communication](https://www.mdpi.com/1424-8220/21/13/4314/htm)
