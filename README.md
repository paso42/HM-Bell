# HM-Bell

![Projektbild](/images/HM-Bell_v2_3D_view_2to3.jpg)

Klingelplatine für die Homematic Smart-Home Steuerung

Zur Unterputzmontage und zum Signalabgriff sowie zum Ein- und Ausschalten einer konventionellen Haustürklingel.

Das Projekt basiert auf der Software für den HM-LC-Sw2-FM (2-Ch. Input/Output) von papa und dient zur aktiven Benachrichtigung beim Betätigen der Klingel per Pushdienst und zur Deaktivierung der Haustürklingel über Nacht.

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
* SMD Widerstände, Dioden, Kondensatoren
* SMA Stecker (optional)

*Achtung: Die Logikpegel des AT Mega 328P und des CC1101 sind hier nicht angeglichen! Das Ausgangslevel des µC ist mit 4,2 - 5 V über dem von TI spezifizierten 3,9 V an den Signaleingängen. Durch die kurzen Signalzeiten des SPI und der internen Clampdioden des CC1101 funktioniert das allerdings trotzdem. Dies kann mit einem Spannungsteiler, externen Schutzdioden, oder einem Pegelwandler auch sauber aufgebaut werden.  
Um dieses Problem zu umgehen kann anstelle eines Arduino Nano auch ein Pro Mini verendet werden, dann müssen auch die Relais für 3,3V ausgelegt, oder mittels Transistor geschaltet werden. Eine aktuelle Version die dies berücksichtigt liegt noch nicht vor.*


![Schematic](/images/HM-Bell_v2_shematic.jpg)

![TopLayer](/images/HM-Bell_v2_toplayer.jpg)

![BottomLayer](/images/HM-Bell_v2_bottomlayer.jpg)


# HM Steuerung

![HomematicProgramm](/images/HM-Bell_CCU-Programm.png)

Channel 1 (Aktor): Klingel ein(off) / aus(on) (invertierte Belegung)
Channel 2 (sensor): wenn betätigt, Status in CCU aktualisieren

Homematic Programm:
Push Benachrichtigung senden
Automatisches zurücksetzen des Ch. 2 (verzögerung um 10s verhindert mehrfach Benachrichtigung bei mehrfachem Klingeln) 

# Lizenz:
Creative Commons BY-NC-SA 4.0 DE (https://creativecommons.org/licenses/by-nc-sa/4.0/deed.de)
