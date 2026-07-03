# NeoPixel-Einführung für Anfänger*innen

```package
neopixelExtended=github:PasAlt/pxt-neopixel-matrix-extension
```

## Besorge das benötigte Material

Du brauchst:
* eine 4.5 V Batterie (z.B. LR12)
* ein NeoPixel-Streifen mit 8 NeoPixeln
* 4 Kabel, um die Battrie und den Neopixel-Streifen zu verbinden
* ein Micro:Bit mit passendem USB-Kabel

![Zeigt das Equipment von oben. Die vier Kabel sind rot, schwarz, weiss und grün.](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/docs/static/tutorial-equipment.jpg)

### ~ hint

Manchmal haben die NeoPixel keine gute Kontakte, um die sie einfach zu verbinden. Du wirst eine passenden Verbindung anlöten müssen (oder jemanden fragen die/der das für dich macht).

### ~

### ~ avatar

Du hast nun alles zusammen, um mit dem Tutorial zu starten.

### ~

## Erstelle den NeoPixel Treiber

Öffne den NeoPixel-Reiter auf der linken Seite. Ziehe das Element mit dem Namen **``||neopixelExtended:Setze strip auf..||``** in den bereits vorhandenen **``||basics:beim Start||``** Block.

Dein NeoPixel Streifen enthält 8 NeoPixel. Du musst also die Anzahl NeoPixel auf 8 setzten. Das machst du indem auf auf weisse Feld nach dem **``||neopixelExtended:mit||``** drückst und auf der Tastatur die Nummer 8 drückst.

Den Rest kannst du so lassen wie es ist.

### ~ avatar

Du hast jetzt einen Treiber zum Steuern deiner NeoPixel erstellt. Ein Objekt, dass Hardware, wie deinen NeoPixel, steuert nennen wir Treiber. Diesen Treiber hast du jetzt in der Variable ``strip`` gespeichert.

### ~

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 8, neopixelExtended.Format.RGB)
```

## Setze dir Farben deines NeoPixel Streifen

Ziehe den Block **``||neopixelExtended:setzte alle NeoPixel auf Farbe||``** aus dem Tab NeoPixel unter den Block **``||neopixelExtended:Setze strip auf..||``** Block. 

Wähle eine Farbe aus indem du auf das Farbelement drückst. 

Mit dem bisherigen Programm werden deine NeoPixel noch nicht aufleuchten, wenn du Download drückst. Wir haben bisher die Farbe nur gespeichert und müssen sie nun noch auf den NeoPixel Streifen übertragen.

### ~ avatar

Du hast jetzt deine Farbe im Zwischenspeicher abgelegt. Im nächsten Schritt lassen wir nun deine NeoPixel aufleuchten.

### ~

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 8, neopixelExtended.Format.RGB)
strip.setColor(0xff0000)
```

## Farben auf dem NeoPixel anzeigen

Öffne den NeoPixel Tab erneut. Ziehe das Element **``||neopixelExtended:Veränderungen anzeigen||``** unterhalb deiner bisherigen Blücke.

Drücke "Start", um deine NeoPixel im Simulator auf der linken Seite leuchten zu sehen.

### ~ avatar

Du hast nun dein Programm, um die NeoPixel leuchten zu lassen, fertig geschrieben. Nun ist es an der Zeit, dass du deinen NeoPixel Streifen mit dem Micro:Bit verbindest.

### ~

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, neopixelExtended.Format.RGB)
strip.setColor(0xff0000)
strip.show()
```

## Verbinde den NeoPixel-Streifen mit dem Micro:Bit

In diesem Abschnitt verbindest du Micro:Bit mit dem NeoPixel.

### Verbinde beide Massekabel

Der Anschluss mit dem Namen "GND" direkt neben dem Anschluss mit dem Namen "VDC" (manchmal auch "VDC") wird mit dem Minuspol der Batterie verbunden.
Der Anschluss mit dem Namen "GND" direkt neben dem Anschluss mit dem Namen "DIN" (manchmal auch "DI") wird mit dem Micro:Bit verbunden am Anschluss "GND".

### ~ hint

Für den negativen Pol der Stromverbindung verwenden wir oft schwarze Kabel. Für die Masse ("GND") bei Datenverbindungen verwenden wir oft ebenfalls schwarze Kabel.

Die Masse ist oft verbunden miteinander. NeoPixel haben oft der Einfachheit halber zwei Masseanschlüsse. Einer wird mit der Batterie verbunden und der andere mit dem Micro:Bit.

Die längere Lasche bei einer 4.5 Volt-Batterie ist normalerweise der negative Pol.

### ~

### ~ avatar

Du hast nun zwei Massekabel verbunden: Eines für den Energieversorgungsstromkreislauf und eines für Signalstromkreislauf. Im nächsten Schritt schliessen wir nun beide Kreisläufe.

### ~

### Verbinden zuerst das Strom- und dann das Datenkabel

Verbinde ein Kabel mit der Batterie am Pluspol mit dem Micro:Bit am Anschluss mit dem Namen "VDC" (manchmal auch "VCC").

Verbinde ein weiteres Kabel mit dem Micro:Bit am Pin 0 mit dem NeoPixel am Anschluss mit dem Namen "DIN" (manchmal auch "DI"). Dies ist unser Datensignal mit dem wir den NeoPixel-Streifen mit unserem Micro:Bit steuern.

![Zeigt den komplett angeschlossenen Micro:Bit](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/docs/static/connection-4.jpg)

### ~ hint

Für die den positiven Pol der Energieversorgung wird normalerweise ein rotes Kabel verwendet. Für das Signalkabel wird normalerweise gelb verwendet.

Die kürzere Lasche bei einer 4.5 Volt-Batterie ist normalerweise der positive Pol.

### ~

### ~ avatar

Du hast nun beide Stromkreisläufe erfolgreich geschlossen. Den Stromkreislauf für die Energie mit dem roten Kabel und den Signalkreislauf mit dem gelben Kabel.

### ~

### Verbinde deinen Micro:Bit mit dem Computer

Verbinde deinen Micro:Bit mit dem Computer. Drücke dann "Herunterladen". Nun siehst du deine NeoPixel aufleuchten.

Deine NeoPixel leuchten nicht? Schaue im nächsten Kapitel, um das Problem zu lösen.

### ~ avatar

Herzliche Gratulation! Du hast deine erstes Projekt mit dem NeoPixel beendet und die NeoPixel zum Leuchten gebracht.

### ~

## Probleme lösen

Dass deine NeoPixel nicht leuchten, kann verschiedene Gründe haben.

Überprüfe:
* deinen Code, insbesondere, dass du am Schluss **``neopixelExtended:Änderungen anzeigen``** eingefügt hast.
* all deine Kabelanschlüsse, insbesondere dass sie richtig und gut angeschlossen sind. Überprüfe alle Verbindungen und vergleich sie mit dem Bild. Verwende Farben, um die verschiedenen Verbindungen auseinanderhalten zu können.
* das Signal. Das Signal wird nur einmal am Anfang versendet. Versende das Signal nochmal indem du erneut "Herunterladen" drückst.
* deinen Batteriestand. Falls du unsicher bist, ob sie genügend Energie hat, dann verwende eine neue Batterie.
* deine NeoPixel. Manche NeoPixel können kaputt gehen. Wenn du unsicher bist, dann verwende einen anderen NeoPixel-Streifen.

![Zeigt den komplett verbundenen NeoPixel](/img/connected-micro-bit.png)

Funktioniert es noch immer nicht? Frage jemanden zur Unterstüztung, z.B. eine Mitschüler:in oder deine Lehrperson.

```blocks
let strip = neopixelExtended(DigitalPin.P0, 8, neopixelExtended.Format.RGB)
strip.setColor(0xff0000)
strip.show()
```