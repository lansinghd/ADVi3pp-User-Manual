# ADVi3++ User Manual
Version 2.0 - October 17, 2017

![](assets/boot.gif)

## Table of content

* Introduction
* [How to Flash](How-to-Flash.md)
* [LCD Touch Screen Manual](LCD-Touch-Screen-Manual.md)
* [Default Configuration](Default-Configuration.md)
* [Resources](Resources.md)

# Introduction

**ADVi3++** is a custom firmware for **Wanaho** Duplicator i3+ printers (and their clones like the Monoprice Select Plus). It is based on the latest stable release of Marlin (1.1.6) and adds some new specific features. It has the following features when compared to the stock Wanhao firmwares:

* Based on Marlin 1.1.6 (Wanhao firmware is based on a fork of Marlin created in 2014)
* New LCD screens in color (yes, your LCD display is able to show colors)
* Access on the LCD display to more printer parameters like Feedrate, Acceleration and Jerk settings
* Calibration of the X, Y, and Z motors and of the extruder
* Temperature graphs
* 3 preheat presets
* 5 points manual bed leveling
* Display of messages (M117 code) from external software such as OctoPrint (Detailed progress plugin for example)
* An up to date User Manual

## Source Code

The full source code of ADVi3++ is available in the following GitHub repositories:

* [ADVi3pp-Marlin](https://github.com/andrivet/ADVi3pp-Marlin)
* [ADVi3pp-LCD](https://github.com/andrivet/ADVi3pp-LCD)
* [ADVi3pp-User-Manual](https://github.com/andrivet/ADVi3pp-User-Manual)

## Disclaimers

I am not affiliated, associated, authorized, endorsed by, or in any way officially connected with **Wanaho**, or any of its subsidiaries or its affiliates.

**USE THIS CUSTOM FIRMWARE AT YOUR OWN RISK. I am not responsible for any damage done to your printer or LCD when using this firmware.**

## Copyrights

**ADVi3++**

* Copyright &copy; 2017 Sebastien Andrivet [GitHub advi3pp-Marlin project](https://github.com/andrivet/advi3pp-Marlin])
* Copyright &copy; 2016 [MarlinFirmware](https://github.com/MarlinFirmware/Marlin)
* Based on Sprinter and grbl.
* Copyright &copy; 2011 Camiel Gubbels / Erik van der Zalm

**ADVi3++ User Manual**

* Copyright &copy; 2017 Sebastien Andrivet

## Licenses

**ADVi3++**

> This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

> This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details.

> You should have received a copy of the GNU General Public License along with this program. If not, see <http://www.gnu.org/licenses/>.

**ADVi3++ User Manual**

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This manual is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.


