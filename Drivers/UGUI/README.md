# Introduction

## Fork Info
This repo has several changes from the original version. I added some commits from other forks, also I added some modifications I believe are valuable. A list can be found bellow.

## What is µGUI?
µGUI is a free and open source graphic library for embedded systems. It is platform-independent
and can be easily ported to almost any microcontroller system. As long as the display is capable
of showing graphics, µGUI is not restricted to a certain display technology. Therefore, display
technologies such as LCD, TFT, E-Paper, LED or OLED are supported. The whole module
consists of three files: **ugui.c**, **ugui.h** and **ugui_config.h**.

## µGUI Features
* µGUI supports any color, grayscale or monochrome display
* µGUI supports any display resolution
* µGUI supports multiple different displays
* µGUI supports any touch screen technology (e.g. AR, PCAP)
* µGUI supports windows and objects (e.g. button, textbox, checkbox)
* µGUI supports platform-specific hardware acceleration
* 16 different fonts available
* cyrillic fonts supported
* TrueType font converter available ([https://github.com/AriZuu](https://github.com/AriZuu))
* integrated and free scalable system console
* basic geometric functions (e.g. line, circle, frame etc.)
* can be easily ported to almost any microcontroller system
* no risky dynamic memory allocation required

## µGUI 0x3333 Fork Features
* Fonts, Components, Colors have been externalized to a separated file
* Pseudo Theme created(See `ugui_theme.h`)
* Added `flush` function. In case the display driver uses Framebuffer, this function will be called after `UG_Update` is called
* Prefixed all defines with `UGUI_`
* Touch support is optional using `UGUI_USE_TOUCH` define
* Added `UGUI_USE_COLOR_BW` for monochromatic displays, also added theme support
* Added X11 Simulator. Based on the fork https://github.com/MarioIvancic/UGUI. Tested only on MacOS 10.14.
* Added Simulation config
* Added Simulation example
* Added Function to convert from RGB565 to RGB888
* Added a check to UG_DrawRoundFrame, draw a rect frame in case radius 0
* Added ProgressBar object
* Console support is optional using `UGUI_USE_CONSOLE` define.
* Created a UG_DEVICE struct to hold device information.

## To Do List
A [To Do List](TODO.md) has been added.

# Commits added from other forks

* https://github.com/stone-payments/UGUI/commit/a8e3da4e0ff2eb1c3c78e0d88a36ae825227726d
    * Add const specifier for not changed variables
* https://github.com/goat91/UGUI/commit/16f4d171cd16ae2ee4215de48b4638cce3124e7c
    * Update checked style for checkbox
        * Note: I didn't added the new style for the checked box, as it doesn't scale to all sizes and displays

## µGUI Requirements
µGUI is platform-independent, so there is no need to use a certain embedded system. In order to
use µGUI, only 3 requirements are necessary:
* a C-function which is able to control pixels of the target display.
* a C-function which is able to flush the framebuffer to the target display(See µGUI 0x3333 Fork Features above).
* integer types for the target platform have to be adjusted in ugui_config.h.

## Simulator Screenshots
Simulator running with 4X multiplier with progress bars.

![Alt text](/.github/simulator-rgb888-x2.jpg?raw=true "Multiplier 4X with Progress Bar")

Simulator running with 4X multiplier.

![Alt text](/.github/simulator-rgb888-x4.jpg?raw=true "Multiplier 4X")

Simulator running with 4X multiplier and Black/White color scheme.

![Alt text](/.github/simulator-bw-x4.jpg?raw=true "Multiplier 4X B/W")
