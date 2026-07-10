# Refurbishing Lenovo Yoga 11e Gen 1
Recently recieved an untested lenovo laptop and I'm going to Refurbish it.

## Goal
I intended to make this Lenovo Thinkpad yoga 11e Gen1 my daily driver for school and other projects.

Linux mint will be installed on this device and stress tested for performance 

Laptop will be cleaned and be given applicable upgrades / working parts

## SPECS
- Intel N2930 celeron 1.82ghz
- 4G 1333mhz ddr3 ram
- 128G Samsung ssd
- 1368 x 768 screen
  
## Parts & Cost
- Laptop — Free
- Lenovo 65 watt Charger  — 16 aud
- Total cost: $16.00 aud

## Time
- 26/6/26 Laptop Received.
- 26/6/26 Charger ordered & Breakdown performed.
- 02/7/26 Charger arrives and first power on test.
- 02/7/26 Installed Linux mint OS.
- 02/7/26 Battery is test for condition.
- 05/7/26 Changed OS to antiX OS, Debian based. 

## Before / After

#### Front view.

<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/425163039e0cb88c6c4b1899a39115403d2916ef/images/yoga%2011e%20front%20before.jpg" width="1200">

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

Notes: After inspecting voltage requirements I have order a relvant charger for this laptop, it's manufacture charger is a recommended 20V == 2.25A the equivalent of 45 watts. I have ordered a Lenovo 65 watt 20V 3.25A charger for additional overhead so the charger won't get as warm ensuring longer life and for future projects.

## Steps I followed (high-level)
1. Initial inspection & photos
Laptop looks fine with no obivous problems. first inspection there are no broken ports or damaged parts, case has scuff marks here and there. Back cover was removed and components look fine with no apparent damge
2. Power-on diagnostics
Powered on Laptop with charger, fn key lights flash on and off, then thinkpad logo follows. Screen back light turns on then lenovo symbols shows. 2 beeps are heard
- screen prompts 0261: real time clock error displayed.
<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/c334cc77296264a66c5ac8a766ab2a2039fa21bf/images/yoga%2011e%20start%20up%20error.jpg" width="1200">
 Diagnostics are cmos cr2025 battery is flat and needs replacing, continuing into the bios to indentify parts which are
- BIOS version 1.10.
- CPU Celeron N2930.
- 4096mb Memory.
<img src="https://github.com/finncameron2002-eng/Refurbing-Yoga-11e/blob/c334cc77296264a66c5ac8a766ab2a2039fa21bf/images/yoga%2011e%20bios%20before.jpg">
save & quit.   laptop boots into windows then immedately crashes and prompts windows automatic repair
3. Test SSD, reseat RAM / upgrade
- Removed previous Samsung 128GB sata SSD and installed the Patriot p210 256GB sata SSD.
- Memory only has 1 so-dimm slot, 8gb 1600mhz ram was installed.
- New Cmos battery installed to fix the 0261: real time clock error   
4. Installed OS and drivers
Installed Linux Mint Xfce 4.18 because it is a light weight OS for the aged parts.
After testing and stress testing Mint is too heavy for the laptop and have changed over to a lighter OS, antiX
5. Final tests (battery, memtest, final stress test)
Peformed memtest, battery test and stress test. Results are below

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
- idle 36-38°C
- 1 min stress test 40-42°C.
- 5 min stress test 57-58°C.
- 10 min stress test 58-60°C.
After 10 minutes temperatures no longer increased.

## What I learned
- I learnt how to replace the cmos, ram and storage of a yoga 11e gen 1.
- How to perform a battery life test.
- How to stress test and monitor the cpu.
- How to replace the cmos battery replacement.
- Using antiX OS for the first test.
- Falkon browser is a good lightweight alternative to firerfox.
  
## Future improvements
- Be prepared with a charger as it delayed my plans until arrival.
- Document more thorougly, notes and photos.
- Better formatting of the github page.

## Conclusion
This laptop is functional touch screen included, but does not meet to par for todays standards. It could barely run linux mint OS with a Ram and SSD uprade, after installing antiX it is barely fuctional. Lagging to type in the terminal or having more than 3 applications open. It can run vscode with some delay and youtube as well but at 85% cpu usage at 720p. At best this laptop will be used to improve my skills on Linux and a note taker, that is all. 
