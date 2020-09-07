# HM-Bell

Klingelplatine für die Homematic Smart-Home Steuerung

Zur Unterputzmontage und zum Signalabgriff sowie zum Ein- und Ausschalten einer konventionellen Haustürklingel.

Das Projekt basiert auf der Software für den HM-LC-Sw2-FM (2-Ch. Input/Output) von papa und dient zur aktiven Benachrichtigung beim Betätigen der Klingel per Pushdienst und zur Deaktivierung der Haustürklingel über Nacht.

# Hardware
* Arduino Nano (alternativ Pro Mini 5V oder 3V3)
* CC1101 Funkmodul
* Signalrelais G6K-2P-Y (2x)
* Gleichrichter 2x
* Festspannungsregler 2x
* Elko 2x 22µF
* Elko 1x 1000µF
* Anschlussblock 8-fach
* Microtaster
* SMD Widerstände, Dioden, Kondensatoren
* SMA Stecker (optional)

*Achtung: Die Logikpegel des AT Mega 328P und des CC1101 sind hier nicht angeglichen! Das Ausgangslevel des µC ist mit 4,2 - 5 V über dem von TI spezifizierten 3,9 V an den Signaleingängen. Durch die kurzen Signalzeiten des SPI und der internen Clampdioden des CC1101 funktioniert das allerdings trotzdem. Dies kann mit einem Spannungsteiler, externen Schutzdioden, oder einem Pegelwandler auch sauber aufgebaut werden.  
Um dieses Problem zu umgehen kann anstelle eines Arduino Nano auch ein Pro Mini verendet werden, dann müssen auch die Relais für 3,3V ausgelegt, oder mittels Transistor geschaltet werden. Eine aktuelle Version die dies berücksichtigt liegt noch nicht vor.*

# HM Steuerung

Channel 1 (Aktor): Klingel ein(off) / aus(on) (invertierte Belegung)
Channel 2 (sensor): wenn betätigt, Status in CCU aktualisieren

Homematic Programm:
Push Benachrichtigung senden
Automatisches zurücksetzen des Ch. 2 (verzögerung um 10s verhindert mehrfach Benachrichtigung bei mehrfachem Klingeln) 

# Lizenz:
Creative Commons BY-NC-SA 4.0 DE (https://creativecommons.org/licenses/by-nc-sa/4.0/deed.de)
