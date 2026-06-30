# NeoPixel-Einführung für Anfänger*innen

```package
neopixel=github:PasAlt/pxt-neopixel-matrix-extension
```

## Besorge das benötigte Material

Du brauchst:
* eine 4.5 V Batterie (z.B. LR12)
* ein NeoPixel-Streifen mit 8 NeoPixeln
* 4 Kabel, um die Battrie und den Neopixel-Streifen zu verbinden
* ein Micro:Bit mit passendem USB-Kabel

![equipment](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/docs/static/tutorial-equipment.jpg)

### ~ hint

Manchmal haben die NeoPixel keine gute Kontakte, um die sie einfach zu verbinden. Du wirst eine passenden Verbindung anlöten müssen (oder jemanden fragen die/der das für dich macht).

### ~

### ~ avatar

Du hast nun alles zusammen, um mit dem Tutorial zu starten.

### ~

## Erstelle den NeoPixel Treiber

Öffne den NeoPixel-Reiter auf der linken Seite. Ziehe das Element mit dem Namen **``||neopixel:Setze strip auf..||``** in den bereits vorhandenen **``||basics:beim Start||``** Block.

Dein NeoPixel Streifen enthält 8 NeoPixel. Du musst also die Anzahl NeoPixel auf 8 setzten. Das machst du indem auf auf weisse Feld nach dem **``mit``** drückst und auf der Tastatur die Nummer 8 drückst.

Den Rest kannst du so lassen wie es ist.

### ~ avatar

Du hast jetzt ein Objekt zum Steuern deiner NeoPixel erstellt. Ein Objekt, dass Hardware, wie deinen NeoPixel, steuert nennen wir Treiber. Diese Objekt hast du in der Variable ``strip`` gespeichert.

### ~

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
```

## Setze dir Farben deines NeoPixel Streifen

Ziehe den Block **``||neopixel:setzte alle NeoPixel auf Farbe||``** aus dem Tab NeoPixel unter den Block **``||neopixel:Setze strip auf..||``** Block. 

Wähle eine Farbe aus indem du auf das Farbelement drückst. 

Mit dem bisherigen Programm werden deine NeoPixel noch nicht aufleuchten, wenn du Download drückst. Wir haben bisher die Farbe nur gespeichert und müssen sie nun noch auf den NeoPixel Streifen übertragen.

### ~ avatar

Du hast jetzt deine Farbe im Zwischenspeicher abgelegt. Im nächsten Schritt lassen wir nun deine NeoPixel aufleuchten.

### ~

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
strip.setColor(0xff0000)
```

## Show 

Öffne den NeoPixel Tab erneut. Ziehe das Element **``||neopixel:Veränderungen anzeigen||``** unterhalb deiner bisherigen Blücke.

Drücke "Start", um deine NeoPixel im Simulator auf der linken Seite leuchten zu sehen.

### ~ avatar

Du hast nun dein Programm, um die NeoPixel leuchten zu lassen, fertig geschrieben. Nun ist es an der Zeit, dass du deinen NeoPixel Streifen mit dem Micro:Bit verbindest.

### ~

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
strip.setColor(0xff0000)
strip.show()
```

## Connect NeoPixel strip with Micro:Bit

In diesem Abschnitt verbindest du Micro:Bit mit dem NeoPixel.

### Connect both of the ground cable.

Der Anschluss mit dem Namen GND direkt neben dem Anschluss mit dem Namen VCC (manchmal auch VDC) wird mit dem Minuspol der Batterie verbunden.
The one right beside the "5 VCC" label goes to the battery.
The one right beside the "DIN" label goes to the ground of the Micro:Bit called GND.

### ~ hint

We use black cables for ground of the power supply. A white cable for the ground of the signal cable. 

The longer flap of the battery is usually the negative pol of the battery.

### ~

### ~ avatar

You have now the two ground cables connected: One for the power supply cicuit and one for the signal circuit. In the next step we will have to close both of them.

### ~

### Connect power cable then the signal cable

Connect a cable from the battery (+) to the "5 VCC" labelled connection.

Connect a cable from the Micro:Bit to the "DIN" labelled connection. This is our signal that we will use to control the NeoPixels with our Micro:Bit.

![Shows the connected Micro:Bit](/img/connected-micro-bit.png)

### ~ hint

We use red cables from the power source to the device and green cables for the signal.

The shorter flap of the battery is usually the positive pol of the battery.

### ~

### ~ avatar

You have now closed both circuits. The power supply circuit with the red cable and the signal cicuit with the white cable.

### ~

### Connect your Micro:bit with your computer

Connect your Micro:Bit with your computer, press "Download" and see your NeoPixels glow.

Your NeoPixel do not glow? Check next part for trouble shooting.

### ~ avatar

Congratulations! You finished your first small project with NeoPixels by letting them glow in one color.

### ~

## Troubleshooting 

That your NeoPixels are not glowing can have multiple reasons.

Check the following:
* Your code, especially that you have added **``show``** as the last block
* All the cables are correctly and well connected. Trace each connection and compare with the image. Use colors to distinguish the different cables.
* The command to glow is only send at the start. Resend the command by pressing "Download" again 
* Your battery has enough power: If unsure, use another battery.

![Shows the connected Micro:Bit](/img/connected-micro-bit.png)

Still not working? Ask somebody for support (e.g. your teacher).

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
strip.setColor(0xff0000)
strip.show()
```