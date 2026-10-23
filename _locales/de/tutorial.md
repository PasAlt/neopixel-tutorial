# NeoPixel-Einführung für Anfänger*innen

### @explicitHints true

```package
neopixel-extended=github:PasAlt/pxt-neopixel-matrix-extension
```


## Besorge das benötigte Material

Du brauchst:
* eine 4.5 V Batterie (z.B. LR12)
* ein NeoPixel-Streifen mit 8 NeoPixeln
* 4 Kabel, um die Batterie und den Neopixel-Streifen zu verbinden
* ein Micro:Bit mit passendem USB-Kabel

![Zeigt das Equipment von oben. Die vier Kabel sind rot, schwarz, schwarz und gelb.](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/material.png)

---

**Hinweis**: Manchmal haben die NeoPixel keine passenden Kontakte, um sie ohne Probleme zu verbinden. Du wirst eine passenden Verbindung anlöten müssen (oder jemanden fragen die/der das für dich macht).


## Was du geschafft hast! @showdialog

Du hast nun alles zusammen, um mit dem Tutorial zu starten.


## Erstelle den NeoPixel Treiber

Öffne den NeoPixel-Reiter auf der linken Seite. Ziehe das Element mit dem Namen **``||neopixelExtended:Setze strip auf..||``** in den bereits vorhandenen **``||basics:beim Start||``** Block.

Dein NeoPixel Streifen enthält 8 NeoPixel. Du musst also die Anzahl NeoPixel auf 8 setzten. 

Das machst du indem auf auf weisse Feld nach dem **mit** auf dem Block drückst. Gib danach auf der Tastatur die Nummer 8 ein.

Den Rest kannst du so lassen wie es ist.

#### ~ tutorialhint

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 8, neopixelExtended.Format.RGB)
```


## Was du geschafft hast! @showdialog

Du hast jetzt einen Treiber zum Steuern deiner NeoPixel erstellt. Ein Objekt, dass Hardware, wie deinen NeoPixel, steuert nennen wir Treiber. Diesen Treiber hast du jetzt in der Variable ``strip`` gespeichert.


## Setze dir Farben deines NeoPixel Streifen

Ziehe den Block **``||neopixelExtended:setzte alle NeoPixel auf Farbe||``** aus dem Tab NeoPixel unter den Block **``||neopixelExtended:Setze strip auf..||``** Block. 

Wähle eine Farbe aus indem du mit der Maus auf das Farbelement drückst und eine Farbe auswählst. 

Mit dem bisherigen Programm werden deine NeoPixel noch nicht aufleuchten, wenn du Download drückst. Wir haben bisher die Farbe nur gespeichert und müssen sie nun noch auf den NeoPixel Streifen übertragen.

### ~ tutorialhint

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 8, neopixelExtended.Format.RGB)
strip.setColor(0xff0000)
```


## Was du geschafft hast! @showdialog

Du hast jetzt deine Farbe im Zwischenspeicher abgelegt. Im nächsten Schritt lassen wir nun deine NeoPixel aufleuchten.


## Farben auf dem NeoPixel anzeigen

Öffne den NeoPixel Tab erneut. Ziehe das Element **``||neopixelExtended:Änderungen anzeigen||``** unterhalb deine bisherigen Blöcke.

Starte den Simulator: Drücke auf das Startsymbol, den Pfeil nach reichts. Dann siehst du deine NeoPixel im Simulator unterhalb des dargestellten Micro:Bit leuchten.

### ~ tutorialhint

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, neopixelExtended.Format.RGB)
strip.setColor(0xff0000)
strip.show()
```


## Was du geschafft hast! @showdialog

Du hast nun dein Programm, um die NeoPixel leuchten zu lassen, fertig geschrieben. Nun ist es an der Zeit, dass du deinen NeoPixel Streifen mit dem Micro:Bit verbindest.

**Denke in Zukunft daran**: Um neue Farben anzuzeigen musst du immer den Block **``||neopixelExtended:Änderungen anzeigen||``** verwenden. Das geht oft vergessen.


## Verbinde das Massekabel vom NeoPixel zur Batterie

In diesem Abschnitt beginnen wir damit die NeoPixel mit der Batterie und dem Micro:Bit zu verbinden.

Der Anschluss mit dem Namen "GND" direkt neben dem Anschluss mit dem Namen "VDC" (manchmal auch "VDC") wird mit dem Minuspol der Batterie verbunden.

Benutze dazu ein schwarzes Kabel, wenn du eines hast.

![Zeigt die Batterie verbunden mit einem schwarzen Kabel vom negativ Pol (grosse Lasche) zum VDC pol des NeoPixels.](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/connections-battery-ground.png)

---

**Hinweise**: Die längere Lasche bei einer 4.5 Volt-Batterie ist normalerweise der negative Pol.

Für den negativen Pol der Stromverbindung verwenden wir oft schwarze Kabel. 

## Was du geschafft hast! @showdialog

Du hast nun das erste Massekabel für die Energieversorgung des NeoPixels verbunden.


## Verbinde das Massekabel vom NeoPixel zum Micro:Bit

Der Anschluss mit dem Namen "GND" direkt neben dem Anschluss mit dem Namen "DIN" (manchmal auch "DI") wird mit dem Micro:Bit verbunden am Anschluss "GND".

Benutze dazu ein schwarzes Kabel, wenn du eines hast.

![Gleiches Bild wie voher aber nun ist der Micro:Bit mit eine schwarzen Kabel mit dem NeoPixel über den Massepin verbunden (grosser Pin auf der rechten Seite mit dem Namen GND)](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/connections-microbit-ground.png)

---

**Hinweise**: Für die Masse ("GND") bei Datenverbindungen verwenden wir oft ebenfalls schwarze Kabel.

Die Masse ist oft verbunden miteinander. NeoPixel haben oft der Einfachheit halber zwei Masseanschlüsse. Einer wird mit der Batterie und der andere mit dem Micro:Bit verbunden.


## Was du geschafft hast! @showdialog

Du hast nun zwei Massekabel verbunden: Eines für den Energieversorgungsstromkreislauf und eines für Signalstromkreislauf. Im nächsten Schritt schliessen wir nun beide Kreisläufe.


## Verbinde die Energieversorgung mit NeoPixel

Verbinde ein Kabel mit der Batterie am Pluspol mit dem NeoPixel am Anschluss mit dem Namen "VDC" (manchmal auch "VCC"). Das unsere Energieverbindung für den NeoPixel.

Benutze dazu ein rotes Kabel, wenn du eines hast.

![Zeigt das gleiche Bild wie vorher aber nun ist ein rotes Kabel mit der Batterie (kurze Lasche) und mit dem "VDC (manchmal "VCC") Pin des NeoPixels verbunden.](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/connections-battery-plus.png)

---

**Hinweise**:  Für den positiven Pol der Energieversorgung verwenden wir normalerweise ein rotes Kabel

Die kürzere Lasche bei einer 4.5 Volt-Batterie ist normalerweise der positive Pol.


## Was du geschafft hast! @showdialog

Du hast nun den mit dem roten Kabel den ersten Stromkreis für die Energie geschlossen.


## Verbinde das Signalkabel und schliessen den Kreislauf
Verbinde ein Kabel mit dem Micro:Bit am Pin 0 mit dem NeoPixel am Anschluss mit dem Namen "DIN" (manchmal auch "DI"). Dies ist unser Datensignal mit dem wir den NeoPixel-Streifen mit unserem Micro:Bit steuern.

Benutze dazu ein gelbes Kabel, wenn du eines hast.

Achte darauf, dass alle Kabel sicher verbunden sind.

![Das gleiche Bild wie im letzten Abschnitt, jedoch ist jetzt das gelbe Kabel verbunden. Es läuft vom Signal des Neopixels "DI" (manchmal "DIN") zum Pin "0" am Micro:Bit (der grosse Pin auf der linken Seite)](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/connections-microbit-signal.png)
![Zeigt eine Nahaufnahme eines umgedrehten NeoPixel. Die Kabel sind von oben nach unten folgendermassen verbunden: schwarz, rot, gelb, schwarz. Die Kabel verlassen das Bild auf der rechten Seite.](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/neopixel-cables-closeup.png)

---

**Hinweis**: Für das Signalkabel verwenden wir normalerweise ein gelbes Kabel.


## Was du geschafft hast! @showdialog

Du hast nun beide Stromkreisläufe erfolgreich geschlossen. Den Stromkreislauf für die Energieversorgung mit dem roten Kabel und den Signalkreislauf mit dem gelben Kabel.


## Verbinde deinen Micro:Bit mit dem Computer

Verbinde deinen Micro:Bit mit dem Computer. Drücke dann "Herunterladen". Nun siehst du deine NeoPixel aufleuchten.

Deine NeoPixel leuchten nicht? Schaue im nächsten Kapitel, um das Problem zu lösen.


## Was du geschafft hast! @showdialog

Herzliche Gratulation! Du hast deine erstes Projekt mit dem NeoPixel beendet und die NeoPixel zum Leuchten gebracht.


## Probleme lösen

Dass deine NeoPixel nicht leuchten, kann verschiedene Gründe haben.

Überprüfe:
* deinen Code, insbesondere, dass du am Schluss **``||neopixelExtended:Änderungen anzeigen||``** eingefügt hast.
* all deine Kabelanschlüsse, insbesondere dass sie richtig und gut angeschlossen sind. Überprüfe alle Verbindungen und vergleiche sie mit dem Bild. Verwende Farben, um die verschiedenen Verbindungen auseinanderhalten zu können.
* das Signal. Das Signal wird nur einmal am Anfang versendet. Versende das Signal nochmal indem du erneut "Herunterladen" drückst.
* deinen Batteriestand. Falls du unsicher bist, ob sie genügend Energie hat, dann verwende eine neue Batterie.
* deine NeoPixel. Manche NeoPixel können kaputt gehen. Wenn du unsicher bist, dann verwende einen anderen NeoPixel-Streifen.

![Zeigt den komplett verbundenen NeoPixel](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/connections-microbit-signal.png)

Funktioniert es noch immer nicht? Frage jemanden zur Unterstüztung, z.B. eine Mitschüler:in oder deine Lehrperson.

### ~ tutorialhint

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 8, neopixelExtended.Format.RGB)
strip.setColor(0xff0000)
strip.show()
```