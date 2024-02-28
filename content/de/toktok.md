---
title: "TokTok"
menu: main
weight: 6
date: 2023-02-29
---
Das [TokTok](https://toktok.ltd) Netzwerk ist ein Peer to Peer (gleicher unter gleichen) Netzwerk
welches das Internet als Medium für den Informationsaustausch benutzt. Dabei müssen die beteiligten
Rechner (Nodes) nicht über eine öffentliche IP Adresse erreichbar sein. Die Verwaltung der 
Verbindungsinformationen erfolgt verteilt im Netz, ohne das Administrative Handlungen auszuführen sind.

Es soll hier die Installation und Benutzung auf einem embedded Linux Rechner dargelegt werden.
Der Grund das System auf einem solchem Rechner zu installieren ist, daß um zu jedem Zeitpunkt 
Nachrichten empfangen zu können der empfangende Rechner ständig erreichbar sein sollte.

## Die Hardware und das Betriebssystem
Prinzipiell eignet sich sicher jeder embedded Linux Rechner welcher eine Verbindung
mit dem Internet herstellen kann. Wir haben uns für einen ARM Server der Firma 
[Olimex](https://olimex.com)
entschieden: 
[A20-OLinuXino-LIME2](https://www.olimex.com/Products/OLinuXino/A20/A20-OLinuXino-LIME2/open-source-hardware).
Dieser kann mit oder ohne Festplatte betrieben werden.

### Das Abbild des Betriebsystems erzeugen
Wir nutzen die Version `Jammy` der [Armbian](https://armbian.com) ARM Linux Distribution.
Dies ist eine für ARM Boards angepasste Version von 
[Ubuntu 22.04, Jammy Jellyfish](https://www.releases.ubuntu.com/jammy/).
Sie muß aber für unser konkretes Board `A20-OLinuXino-LIME2` gebaut werden.
Die Anleitung dazu findet sich unter 
[Building Armbian](https://docs.armbian.com/Developer-Guide_Build-Preparation).

Da der Bau nur unter einem speziell eingerichtetm Betriebssystem erfolgt, 
wird dieses auf einem virtuellem Rechner eingerichtet. Dazu wird 
die Virtualisierungs-Software [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
installiert. Das virtuelle Laufwerk sollte mindestens 50GB groß sein.
```bash
$ sudo adduser myuser vboxusers
$ wget https://www.releases.ubuntu.com/jammy/ubuntu-22.04.3-live-server-amd64.iso
```
Will man `ssh` benutzen um auf dem virtuellen System zu arbeiten, dann 
sollte z.B. auf dem virtuellen Rechner unter der Einstellung Netzwerk die Einstellung
`Netzwerkbrücke` mit dem Namen `wls6` gewählt werden. Dann kann man den
Server im lokalen Netz auffinden und mittels ssh kontaktieren.

Dann bauen wir Armbian:
```bash
$ sudo apt-get -y -qq install git  
$ git clone --depth=1 --branch=main https://github.com/armbian/build  
$ cd build  
$ ./compile.sh BOARD=lime2 BRANCH=current RELEASE=jammy
```
Das sollte unser gewünschtes Betriebssystem-Abbild erzeugen,
welches wir dann mittels `scp` auf unseren realen Rechner kopieren:
```
Armbian-unofficial_24.2.0-trunk_Lime2_jammy_current_6.6.11_minimal.img
```
  
### Micro-SD Karte beschreiben 
Das Abbild des Betriebssystems wird mit dem Programm 
[Balena Etcher](https://etcher.balena.io/) auf die Micro-SD 
Karte geschrieben und überprüft.

   

