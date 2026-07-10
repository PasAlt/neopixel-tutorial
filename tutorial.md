# NeoPixel Beginner Tutorial

### @explicitHints true

```package
neopixel-extended=github:PasAlt/pxt-neopixel-matrix-extension
```

## Get the necessary equipment

You will need
* 4.5 V battery (e.g. LR12)
* NeoPixel strip with 8 NeoPixels
* 4 cables to connect battery and NeoPixel strip
* Micro:bit with USB cable

![Shows equipment from above. The four cables are red, twice black and yellow.](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/material.png)

~hint Pins are hard to connect to
Sometimes NeoPixel strips don't have pins that can easily be connected to.  You will have to solder that part on yourself (or ask your teacher to do it).
hint~

## What you achieved @showdialog

You now have everything you need to start this tutorial

## Initialize NeoPixel Object

Open the NeoPixel tab on the left-hand side. Drag the top block called **``||neopixelExtended:set strip to..||``** into the already existing **``||basics:on start||``** block. 

Your NeoPixel is 8 elements long. Therefore, change the number of LEDs to 8 NeoPixels by clicking in it and pressing 8 on your keyboard.

You can leave the rest as it is.

#### ~ tutorialhint

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 8, neopixelExtended.Format.RGB)
```

## What you achieved @showdialog

You have now created an object (in our case a so-called driver) called 'strip' that represents your NeoPixels.

## Set Colors for the NeoPixels

Drag the block **``||neopixelExtended:setColor||``** from the tab NeoPixel below the **``||neopixelExtended:set strip||``** block. Choose a color you like by clicking on the color element. 

This part will not make the NeoPixels glow immediately but store the selected color.

#### ~ tutorialhint

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 8, neopixelExtended.Format.RGB)
strip.setColor(0xff0000)
```
## What you achieved @showdialog

You have now stored the color of your NeoPixels in the buffer. See the next step to make the NeoPixels glow.

## Make NeoPixels glow

Open the tab NeoPixel again and drag the element **``||neopixelExtended:show||``**  below your current blocks.

Press the |Start| button of the simulator on the left-hand side to watch your NeoPixels glow in the simulator.

#### ~ tutorialhint

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 8, neopixelExtended.Format.RGB)
strip.setColor(0xff0000)
strip.show()
```

## What you achieved @showdialog

You finished your code to make your NeoPixels glow. It is now time to connect your NeoPixels to the micro:bit.

## Connect power circuit ground cable

The pin named GND beside the "VDC" label (sometimes "VCC") goes to the negative terminal of the battery.

![Shows battery connected with a black cable from the batteries negative terminal (longer flap) to the ground pin of the NeoPixel.](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/connections-battery-ground.png)

~hint Battery terminals

The longer flap of a 4.5V battery is usually the negative terminal of the battery. Check for the minus sign (-) to make sure.

hint~

## Connect signal circuit ground cable

The pin named GND right beside the "DIN" label (sometimes "DI") goes to the ground pin of the micro:bit called "GND".

![Shows same picture as in last section but additionaly with the micro:bit connected with a black cable from the NeoPixels ground pin to the ground pin of the micro:bit (large pin on the left)](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/connections-microbit-ground.png)

~hint Cable colors

We use black cables for the ground of the power supply and a black cable for the ground of the signal cable. 

hint~

~hint Ground pins are connected

All ground pins are in most cases connected. NeoPixels often have two ground pins for convenience because you have to connect them to the ground of the micro:bit and to the ground of the power source (in our case the battery).

hint~

## What you achieved @showdialog

You have now connected the two ground cables: One for the power supply circuit and one for the signal circuit. In the next steps we will close both of them.

## Connect the power cable and close the power circuit

Connect a cable from the battery (+) to the "VDC" ("VDC" is sometimes labelled "VCC") labelled pin.

![Shows same picture as in last section but with battery connected with a red cable from the batteries positive terminal (shorter flap) to the VDC (sometimes VCC) pin of the NeoPixel.](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/connections-battery-plus.png)

~hint Battery terminals

The shorter flap of the battery is usually the positive terminal of the battery. Look for the plus sign (+) to make sure.

hint~

~hint Cable colors

We use red cables from the power source to the device.

hint~

## Connect signal cable and close the signal circuit
Connect a cable from the micro:bit Pin 0 to the "DIN" ("DIN" is sometimes labelled "DI") labelled pin on the NeoPixel. This is our signal that we will use to control the NeoPixels with our micro:bit.

Check that all cables are securely connected.

![Shows same picture as in last section but additionaly with micro:bit connected with a yellow cable from the Neopixels signal "DI" (sometimes "DIN") to the signal pin "0" of the micro:bit (large pin on the left)](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/connections-microbit-signal.png)
![Shows close-up of a flipped NeoPixel pins with connected cables from top to botton: black, red, yellow, black. The cables leave the image on the right side.](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/neopixel-cables-closeup.png)

~hint Cable colors

We use red cables from the power source to the device and yellow cables for the signal.

hint~

## What you achieved @showdialog

You have now closed both circuits. The power supply circuit with the red and black cable and the signal cicuit with the yellow and black cable.

## Connect your micro:bit to your computer

Connect your micro:mit with your computer, press |Download| and see your NeoPixels glow.

~hint Your NeoPixels do not glow?

There can be multiple reasons why your NeoPixels are not glowing.

Check the following:
* Your code, especially that you have added **``||neopixelExtended:show||``** as the last block.
* All the cables are connected correctly and securely. Trace each connection and compare with the image. Use different cable colors to distinguish power, signal and ground cables.
* The signal to the NeoPixel to glow is only sent at the start. Resend the command by pressing |Download| again.
* Your battery has enough power: If unsure, use another battery.
* Your NeoPixels are broken: Replace them, if you are unsure.

![Shows a fully connected NeoPixel. There are four cables: red wire connects the shorter flap of the battery with the VDC pin of the NeoPixel. A black cable connects the longer flap of the battery with the GND pin on the NeoPixel right below the VDC pin. A yellow cable connects the NeoPixel pin "DI" to the pin 0 of the micro:bit. And last a black cable connects the GND pin of the NeoPixel above the DI pin to the large GND pin on the right side of the NeoPixel.](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/img/connections-microbit-signal.png)

Still not working? Ask somebody for support (e.g. your teacher).

hint~

#### ~ tutorialhint
```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 8, neopixelExtended.Format.RGB)
strip.setColor(0xff0000)
strip.show()
```

## What you achieved @showdialog

Congratulations! You finished your first small project with NeoPixels by making them glow in one color.

