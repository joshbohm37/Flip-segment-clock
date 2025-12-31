# Flip-Segment Clock

This is a custom-designed electromechanical flip segment clock. It uses a STM32-based controller in conjunction with a highly accurate RTC module and network time synchronization over Wi-Fi using [NTP](https://www.ntppool.org/en/).

## Project Goals

- Reasonable and clear documentation of design choices
- Reliable and safe operation of high power flip segment displays
- Extremely accurate timekeeping (overkill)
- Ultra low power consumption to allow for battery operation
- WIP ADD MORE

## Sytem Architecture
<div class="mermaid">
graph TD
power[Power Architecture]
mcu[STM32/Control]
rtc[RTC]
wifi[WiFi / Time Sync]
driver[Display Driver]
display[Flip-Segment Display]

power --> mcu
power --> driver
mcu --> driver
driver --> display
mcu <--> wifi
mcu <--> rtc

</div>

This system is comprised of several connected subsystems. The STM32 coordinates with the RTC module and WiFi / Time Synchronization module to keep as accurate time as possible. The STM32 then sends the current time to be displayed to the display driver which reduces the amount of GPIO required as well as handling the high current requirments of the Flip-Segment Display.

## Documentation Guide

- index --> you are here
- system-overview
    - More in depth explaination of the system architecture, how modules connect, project requirements, physical connection/modularity of actual PCB.
- changelog
    - Log file of revisions to the project.

- subsystems
    - In depth explainations of each module and how it functions.

- design-notes
    - Explainations of design choices and documentation of the thought process behind them.

## Current Status

- ~~Design breakout board for display driver~~ **complete**
- ~~Submit and pay for JLCPB manufacturing and assembly~~ **complete**
- Testing display driver for optimal high side voltage/pulse widths


## Revisions and Changes
[Changelog.md](changelog.md)