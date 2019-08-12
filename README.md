# XinaBox OD01 MakeCode extension

The OD01 is 64x128 dot matrix monochrome OLED screen which has an SSD1306 mounted on to it. Use it with a micro:bit to expand your output options:
 
![](od01.jpg)

This library provides functions to print and draw to the OD01 OLED display. 

The following functions are provided (with examples later):
* initialise OLED. This is triggered by default and you don't need to use this normally.
* display ON / OFF.  It is ON by default

NB: you do NOT not to initialise or turn on the OLED before using it - both are done for us.
* print String. Write anything to screen, and specify whether the start the NEXT print on a new line.
* print number. Write a number to screen, and specify whether the start the NEXT print on a new line.
* clear screen. 
* invert screen TRUE / FALSE. Setting this to TRUE causes all pixels to change from on to off, or off to on.

These are your main printing tools. They are easy to use and are more than adequate to output data to screen.
But there is a lot more you can do - the following functions are for drawing. In each case you specify a Color (soz UK for spelling). Color = 1 means the image is drawn and Color = 0 means the image is erased. 

Use the functions below to draw the items named on the OLED in a location you specify:
* show string
* show number
* set pixel
* draw horizontal line
* draw vertical line
* draw rectangle

This extension is based on [the OLED Package from microbit/micropython Chinese community](https://github.com/makecode-extensions/OLED12864_I2C). Great thanks to Shaoziyang for all the heavy lifting.
 

## How-to guides

A comprehensive set of How-to guides that show you how to use the blocks is available online:
* Search for OD01 on the [XinaBox website](https://xinabox.cc/)


## Basic Printing: Print string / number on same line / new line:

```blocks
// Print "Number = " then "42" on the NEXT line:
OD01.printString("Number = ", true)
OD01.printNumber(42, true)

// Print "Number = " then "42" on the SAME line:
OD01.printString("Number = ", false)
OD01.printNumber(42, true)

// And of course, when you want to start again just use clear screen:
OD01.clear()

// Or even go for a strobe effect with the screen invert function (but don't try this if that sort of thing bothers you):
basic.forever(function () {
    OD01.invert(true)
    basic.pause(200)
    OD01.invert(false)
    basic.pause(200)
})

```

## Basic Drawing: Flashing a string / number:

```blocks
// Print "Number = " then "42" in the location specified (column = 42, row = 4, color = 1):
OD01.String("Calling", 42, 4, 1)
OD01.Number(446, 88, 4, 1)

// Print "Calling " then "446" in the same place but inverted (use for emphasis like bold):
OD01.String("Calling", 42, 4, 0)
OD01.Number(446, 88, 4, 0)

// Now put these together to create a cool flashing effect:
basic.forever(function () {
    OD01.String("Calling", 42, 4, 1)
    OD01.Number(446, 88, 4, 1)
    basic.pause(500)
    OD01.String("Calling", 42, 4, 0)
    OD01.Number(446, 88, 4, 0)
    basic.pause(500)
})

```

There are loads of other drawing functions. Check out our How-to Guides online to learn how to use them all, and in the process learn how to make a pixel bounce around the screen and how to control a rectangle with the A and B buttons.


## License

MIT

Copyright (c) 2019, XinaBox  

## Supported targets

* for PXT/microbit

