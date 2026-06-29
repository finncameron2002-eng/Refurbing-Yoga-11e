# Refurbishing Lenovo yoga 11e gen 1
Recently recieved an untested lenovo laptop and I am going to Refurbish it.

## Goal
I intended to make this Lenovo Thinkpad yoga 11e my daily driver for school and other projects.

Linux mint will be installed on this device and stress tested for performance 

Laptop will be cleaned and if needed parts will be upgraded / restored to it's full potential

## Parts & Cost
- Laptop — Free
- Lenovo 65 watt Charger  — 16 aud
- Total cost: $16.00 aud

## Time
- Laptop Received 26/6/26.
- Charger ordered & Breakdown performed 26/6/26.

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
2. Power-on diagnostics < - waiting 
3. test SSD, reseat RAM / upgrade
4. Cleaned fan, replaced thermal paste, stress test
5. Installed OS and drivers
6. Final tests (battery, memtest, final stress test)

## Commands & scripts
Include command snippets you ran, e.g.:
- Disk cloning: `sudo dd if=/dev/sda of=/dev/sdb bs=4M status=progress`
- Linux install steps or server start commands

## Tests & Results
- Battery: 3.5 hours
- CPU temps under load: max 75°C
- Memtest: no errors (link to memtest log in notes/)

## What I learned
Short bullet points about troubleshooting, gotchas, recommended parts.

## Future improvements
Ideas for next steps.

## License
Specify documentation license (e.g., CC-BY-4.0) and code license (MIT) if relevant.
