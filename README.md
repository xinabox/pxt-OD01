# XinaBox OD01 MakeCode extension

The OD01 is 64x128 dot matrix monochrome OLED screen which has an SSD1306 mounted on to it. 

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
  
![](od01.jpg)

## How-to guides

A comprehensive set of How-to guides that show you how to use the blocks is available online:
* Search for OD01 on the [XinaBox website](https://xinabox.cc/)


## Core functions: Print string / number on same line / new line:

```blocks
// Print "Number = " then "42" on the NEXT line::
OD01.printString("Number = ", true)
OD01.printNumber(42, true)

// Print "Number = " then "42" on the SAME line::
OD01.printString("Number = ", false)
OD01.printNumber(42, true)


```

## License

MIT

Copyright (c) 2019, XinaBox  

## Supported targets

* for PXT/microbit

