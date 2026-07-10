# Refurbishing Lenovo Yoga 11e Gen 1
A complete refurbishment of a Lenovo ThinkPad Yoga 11e Gen 1 that was received untested.

This project documents inspection, diagnosis, hardware upgrades, Linux installation, stress testing, battery testing and final performance evaluation.

## Goal
I intended to make this Lenovo Thinkpad yoga 11e Gen1 my daily driver for school and other projects.

Linux mint will be installed on this device and stress tested for performance 

Laptop will be cleaned and be given applicable upgrades / working parts

## SPECS
| Component | Specification                            |
| --------- | ---------------------------------------- |
| CPU       | Intel Celeron N2930                      |
| RAM       | 4 GB DDR3L (upgraded to 8 GB)            |
| Storage   | 128 GB Samsung SSD → Patriot P210 256 GB |
| Display   | 1366×768 Touchscreen                     |

## Hardware upgrades

- Replaced 128GB Samsung SSD with Patriot P210 256GB SSD
- Upgraded RAM from 4GB DDR3L to 8GB DDR3L
- Replaced CMOS battery
- Installed genuine Lenovo 65W charger
  
## Parts & Cost
| Item               |        Cost |
| ------------------ | ----------: |
| Laptop             |        Free |
| Lenovo 65W charger |     $16 AUD |
| **Total**          | **$16 AUD** |


## Time
- 26/6/26 Laptop Received.
- 26/6/26 Charger ordered & Breakdown performed.
- 02/7/26 Charger arrives and first power on test.
- 02/7/26 Installed Linux mint OS.
- 02/7/26 Battery is test for condition.
- 05/7/26 Changed OS to antiX OS, Debian based. 

## Before / After

#### Front view.

<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/425163039e0cb88c6c4b1899a39115403d2916ef/images/yoga%2011e%20front%20before.jpg" width="1000">

#### Left view 

<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/cb6470e838ad56e285060bb635e78bec333f0e70/images/yoga%2011e%20ports%20left.jpg" width="1200">

### Right view 

<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/cb6470e838ad56e285060bb635e78bec333f0e70/images/yoga%2011e%20ports%20right.jpg" width="1200">

Photo of first inspection, screen and keyboard are dirty and need a cleaning. Device has not been powered on yet so unable to test keys and screen but from a first glance everything looks fine, But I now have a checklist of components to test. 

##### To test.

keyboard, touchpad, speakers, usb ports, microphone, screen, display lights, volume button, hdmi port and ethernet port.  

#### Analysing components 
<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/425163039e0cb88c6c4b1899a39115403d2916ef/images/yoga%2011e%20back%20dismantled%20before.jpg" width="1200">

Photo of first inspection with back cover taken off. First glance no obivous fixes needed below are up close photos of components like ram, battery and voltage requirements.

<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/425163039e0cb88c6c4b1899a39115403d2916ef/images/yoga%2011e%20ssd%20before.jpg" width="1200"> 
<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/425163039e0cb88c6c4b1899a39115403d2916ef/images/yoga%2011e%20battery%20before.jpg" width="1200"> 
<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/425163039e0cb88c6c4b1899a39115403d2916ef/images/yoga%2011e%20wifi%20card%20before.jpg" width="1200">
<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/425163039e0cb88c6c4b1899a39115403d2916ef/images/yoga%2011e%20ram%20and%20cmos%20battery%20before.jpg" width="1200">
<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/425163039e0cb88c6c4b1899a39115403d2916ef/images/yoga%2011e%20power%20input.jpg" width="1200">

Notes: After inspecting voltage requirements I have order a relvant charger for this laptop, it's manufacture charger is a recommended 20V == 2.25A the equivalent of 45 watts. I deliberately bought a 65W charger because it provides additional headroom while still supplying the required 20V.
## Steps I followed (high-level)
- 1. Initial inspection & photos
Laptop looks fine with no obvious problems. first inspection there are no broken ports or damaged parts, case has scuff marks here and there. Back cover was removed and components look fine with no apparent damge
- 2. Power-on diagnostics
Powered on Laptop with charger, fn key lights flash on and off, then thinkpad logo follows. Screen back light turns on then Lenovo symbols shows. 2 beeps are heard
- screen prompts 0261: real time clock error displayed.
<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/c334cc77296264a66c5ac8a766ab2a2039fa21bf/images/yoga%2011e%20start%20up%20error.jpg" width="1200">
 Diagnostics are cmos cr2025 battery is flat and needs replacing, continuing into the bios to identify parts that are:
- BIOS version 1.10.
- CPU Celeron N2930.
- 4096mb Memory.
<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/c334cc77296264a66c5ac8a766ab2a2039fa21bf/images/yoga%2011e%20bios%20before.jpg">
save & quit.   laptop boots into windows then immediately crashes and prompts windows automatic repair

- 3. Test SSD, reseat RAM / upgrade
- Removed previous Samsung 128GB sata SSD and installed the Patriot p210 256GB sata SSD.
- Memory only has 1 so-dimm slot, 8gb 1600mhz ram was installed.
- New CMOS battery installed to fix the 0261: real time clock error   

- 4. Installed OS and drivers
Installed Linux Mint Xfce 4.18 because it is a light weight OS for the aged parts.
After testing and stress testing Mint is too heavy for the laptop and have changed over to a lighter OS, antiX

- 5. Final tests (battery, memtest, final stress test)
Performed memtest, battery test and stress test. Results are below

## Commands & scripts
###Battery Life Testing
First I used the command `upower -e` to identify power related devices
Then ran battery test command: `upower -i /org/freedesktop/UPower/devices/battery_BAT1`

###stress testing
First I installed `sudo apt install lm-sensors` for monitoring and `sudo apt install stress` for stress testing.
Then I ran the command `watch n 3 sensors` which updates the terminal every 3 seconds of the sensor application
& ran in a seperate terminal `stress --cpu $(nproc) --timeout 60s` which stress test all the cores for 60 seconds.

## Tests & Results
- Battery:
Energy-full 27.13Wh.    Energy-full-design 34.04Wh.    Capacity 79.7004%
Battery is at a worn to good condition but is more than usable. Estimates are the battery will last 6.7 hours.
<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/c334cc77296264a66c5ac8a766ab2a2039fa21bf/images/yoga%2011e%20battery%20test.jpg" width="1200">
CPU temps under load:
| Test       | Temperature |
| ---------- | ----------: |
| Idle       |     36–38°C |
| 1 minute   |     40–42°C |
| 5 minutes  |     57–58°C |
| 10 minutes |     58–60°C |


## What I learned
- I learnt how to replace the CMOS, RAM and storage of a yoga 11e gen 1.
- How to perform a battery life test.
- How to stress test and monitor the cpu.
- How to replace the cmos battery replacement.
- Using antiX OS for the first time as a substitute for Mint OS.
- Falkon browser is a good lightweight alternative to firefox.
  
## Future improvements
- Be prepared with a charger as it delayed my plans until arrival.
- Document more thoroughly, notes and photos.
- Better formatting of the github page.

## Conclusion

The laptop is now fully working after replacing the RAM, SSD and CMOS battery. Although it runs much better with antiX than Linux Mint, the Celeron N2930 is still a slow processor by today's standards. It is good for learning Linux, taking notes, basic programming and light web browsing, but it struggles with heavier tasks and running several programs at once.

## Final configuration

CPU
Intel Celeron N2930

RAM
8GB DDR3L

Storage
256GB Patriot P210 SSD

Operating System
antiX Linux

Battery health
79.7%

Touchscreen
Working

Wi-Fi
Working

Audio
Working

USB
Working

HDMI
Working

Ethernet
Working
