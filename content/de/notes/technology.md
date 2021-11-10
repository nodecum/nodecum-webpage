---
title: "Funknetz Technolgie"
date: 2021-10-26T23:05:49+02:00
---
Die primär einzusetzende Funknetz Technik die geeignet erscheint
wird als LPWAN (Low Power Wide Area Network) bezeichnet.
Eine gute Übersicht zu diesem Thema auf Deutsch findet sich in diesem 
[Artikel](https://www.elektronik-kompendium.de/sites/kom/2207181.htm).

Die LoRa (Long Range, Low Radiation) Funktechnik ist ein offener 
Industriestandard und durch seine Popularität gut verfügbar.
Das "Internet der Ding" IOT (Internet of Things) basiert auf dieser 
Technologie. Allerdings wird in diesen als LoRaWAN bezeichneten Netzwerken
die folgende sternförmige Struktur verwendet:

``` 
 Nodes  o))   LoRaWAN
               >O -------- Internet ------- Application
        o))   Gateway                       Server
```
Die "Dinge" auch Nodes (Knoten) genannt kommunizieren mit einem
LoRaWAN Gateway welches mit dem Internet verbunden ist und seinerseits
mit der den Nodes zugeordneten Anwendung auf einem Server kommuniziert.

Wir wollen jedoch ein LoRa Mesh (Masche) Netzwerk bilden:
```
      o)    >o)     >o)     >o
```
Hier wird die Nachricht vom sendenden Knoten (Node) über
die dazwischenliegenden Knoten bis zum Empfänger weitergegeben.


## Artikel

[A LoRa-Based Mesh Network for Peer-to-Peer Long-Range Communication](https://www.mdpi.com/1424-8220/21/13/4314/htm)
