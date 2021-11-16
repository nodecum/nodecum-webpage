---
title: "Technologie de réseaux par ondes"
date: 2021-10-26T23:05:49+02:00
---
La technique de réseau radio à utiliser en premier recours et qui semble appropriée est 
appelée LPWAN (Low Power Wide Area Network). 

La technique d’ondes radio LoRa (Long Range, Low Radiation) est un standard industriel 
ouvert et est bien disponible en raison de sa popularité. L'"Internet des choses" 
IOT (Internet of Things) est basé sur cette technologie. Toutefois, la structure en 
étoile suivante est utilisée dans ces réseaux appelés LoRaWAN :
``` 
 Nœuds  o))   LoRaWAN
               >O -------- Internet ------- Application
        o))   Passerelle                       Serveur
```
Les 'élements', également appelées nœuds, communiquent avec une passerelle LoRaWAN 
qui est connectée à Internet et communique à son tour avec l'application attribuée 
aux nœuds sur un serveur.

Cependant, nous voulons créer un réseau LoRa Mesh (maille) :
```
         o)    >o)     >o)     >o
```
Ici, le message est transmis du nœud émetteur (node) au récepteur en passant par 
« des entres-noeuds » par les nœuds intermédiaires.


