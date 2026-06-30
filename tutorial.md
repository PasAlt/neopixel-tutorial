# NeoPixel Beginner Tutorial

```package
neopixel=github:PasAlt/pxt-neopixel-matrix-extension
```

## Get the necessary equipment

You will need
* 4.5 V battery (e.g. LR12)
* NeoPixel strip with 8 NeoPixels
* 4 cables to connect battery and NeoPixel strip
* Micro:Bit with USB-Cable

![equipment](https://raw.githubusercontent.com/PasAlt/neopixel-tutorial/refs/heads/master/docs/static/tutorial-equipment.jpg)

### ~ avatar

You have now everything you need to start this tutorial

### ~

### ~ hint

Sometimes NeoPixel strips don't have connections that can easily be connected to.  You will have to solder that part on (or ask your teacher to do it).

### ~

## Initialize NeoPixel Object

Open the NeoPixel tab on the left side. Drag the top block called **``||neopixel:set strip to..||``** into the already existing **``||basics:on start||``** block. 

Your NeoPixel is 8 elements long. Therefore, change the number of leds to 8 Neopixels by clicking in it and pressing 8 on your keyboard.

You can leave the rest as it is.

### ~ avatar
You have now created an object (in our case a so called driver) called 'strip' that represents your NeoPixels.
### ~

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
```

## Set Colors for the NeoPixels

Drag the block **``||neopixel:setColor||``** from the tab NeoPixel below the **``||neopixel:set strip||``** block. Choose a color you like by clicking on the color element. 

This part will not let the NeoPixels glow immediately but store what color was set.

### ~ avatar
You have now stored the color of your NeoPixels in the buffer. See the next step to let the NeoPixels glow.
### ~

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
strip.setColor(0xff0000)
```

## Show 

Open the tab NeoPixel again and drag the element **``||neopixel:show||``**  below your current blocks.

Press start to watch your NeoPixels glow in the simulator.

### ~ avatar
You finished your code to let your NeoPixels glow. It is now time to connect your NeoPixels to the Micro:Bit.
### ~

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
strip.setColor(0xff0000)
strip.show()
```

## Connect NeoPixel strip with Micro:Bit

### Connect both of the ground cable.

The pin named GND besides the "VDC" label (sometimes "VCC") goes to the negative terminal of the battery.
The pin named GND right beside the "DIN" label (sometimes "DI") goes to the ground pin of the Micro:Bit called "GND".

### ~ hint

We use black cables for ground of the power supply and a white cable for the ground of the signal cable. 

The longer flap of the battery is usually the negative terminal of the battery.

### ~

### ~ avatar

You have now connected the two ground cables: One for the power supply cicuit and one for the signal circuit. In the next step we will have to close both of them.

### ~

### Connect power cable then the signal cable

Connect a cable from the battery (+) to the "VDC" (sometimes "VCC") labelled pin.

Connect a cable from the Micro:Bit to the "DIN" (sometimes "DI") labelled connection. This is our signal that we will use to control the NeoPixels with our Micro:Bit.

![Shows the connected Micro:Bit](/img/connected-micro-bit.png)

### ~ hint

We use red cables from the power source to the device and green cables for the signal.

The shorter flap of the battery is usually the positive terminal of the battery.

### ~

### ~ avatar

You have now closed both circuits. The power supply circuit with the red and black cable and the signal cicuit with the green and white cable.
d
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
```-