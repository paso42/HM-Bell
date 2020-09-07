# HM-Bell

![Projektbild](/images/HM-Bell_v2_3D_view_2to3.jpg)

Klingelplatine für die Homematic Smart-Home Steuerung

Zur Unterputzmontage und zum Signalabgriff sowie zum Ein- und Ausschalten einer konventionellen Haustürklingel.

Das Projekt basiert auf der Software für den HM-LC-Sw2-FM (2-Ch. Input/Output) von papa aus der Asksinpp Library und dient zur aktiven Benachrichtigung beim Betätigen der Klingel per Pushdienst und zur Deaktivierung der Haustürklingel über Nacht.

![Homematic-Forum](https://homematic-forum.de/forum/viewtopic.php?f=76&t=60687)

# Hardware
* Arduino Nano (alternativ Pro Mini 5V oder 3V3) (1x)
* CC1101 Funkmodul (1x)
* Signalrelais G6K-2P-Y (2x)
* Gleichrichter (2x)
* Festspannungsregler (2x)
* Elko 22µF (2x)
* Elko 1000µF (1x)
* Anschlussblock 8-fach (1x)
* Microtaster (1x)
* SMD Widerstände, Dioden, Kondensatoren, eine LED und ein Transistor
* SMA Stecker (optional)

*Das Ausgangslevel des µC ist mit 4,2 - 5 V über dem von TI spezifizierten 3,9 V an den Signaleingängen. Daher wurden in der Version 2.1 die Logikpegel des AT Mega 328P und des CC1101 durch einen Spannungsteiler unidirektional herunter gebrochen (MOSI, CLK, CS). 
Um dieses Problem ganz zu umgehen kann anstelle eines Nano auch ein 3V3 Pro Mini verendet werden, dazu muss jedoch das entsprechende Relais für 3,3V ausgelegt, oder mittels Transistor geschaltet werden.*

![Schematic](/images/HM-Bell_V2_1_scm.png)

![TopLayer](/images/HM-Bell_V2_1_top.png)

![BottomLayer](/images/HM-Bell_V2_1_bot.png)

# Sketch

Der verwendete Sketch HM-LC-Sw2-FM.ino von papa ist im Repo hinterlegt.

# HM Steuerung

![HomematicProgramm](/images/HM-Bell_CCU-Programm.png)

Channel 1 (Aktor): Klingel ein(off) / aus(on) (invertierte Belegung)
Channel 2 (sensor): wenn betätigt, Status in CCU aktualisieren

Homematic Programm:
Push Benachrichtigung senden
Automatisches zurücksetzen des Ch. 2 (verzögerung um 10s verhindert mehrfach Benachrichtigung bei mehrfachem Klingeln) 

# Changelog
Version 2.1
*Korrektur der Levelanpassung zwischen 5V µC und Funkmodul mittels Spannungsteiler

Version 2
* Korrektur der Masseführung für Signaleingang

Version 1
* Erster Aufbau

# Lizenz:
Creative Commons BY-NC-SA 4.0 DE (https://creativecommons.org/licenses/by-nc-sa/4.0/deed.de)
