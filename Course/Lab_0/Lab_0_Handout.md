# Lab 0 Kit and board setup

ECE 116 • Fall 2026 • September 24

Collect your kit, solder the XIAO headers with staff supervision, and upload the course starter to check USB communication. Bring your laptop and a USB-C data cable that fits your laptop. Lab 0 is ungraded and has no separate code submission.

## 1  Check your kit

Pick up one Seeed Studio XIAO ESP32-S3 Sense and one ELEGOO Electronic Fun Kit. Label the kit box with your name. Check these items before leaving the pickup area.

☐  XIAO board, Sense expansion with camera and microphone, and antenna. Keep the camera and its cable protected.

☐  Two 7-pin male header rows for the XIAO. If using longer strips, cut two rows of seven pins with flush cutters while wearing eye protection.

☐  Breadboard and jumper wires, including male-to-male wires.

☐  Red, yellow, and green LEDs; pushbuttons; and the light-sensitive resistor (photoresistor).

☐  Resistor packs labeled 220 Ω, 330 Ω, and 10 kΩ. Keep the labels with the parts.

Compare the remaining parts with the packing list supplied with your kit. Report missing or damaged parts and save the extra parts for later use.

For this lab, power the XIAO only through USB. Leave the kit’s breadboard power module and other loose components disconnected.

## 2  Solder and inspect the headers

1. Go to a staff-supervised soldering station. Wear eye protection, use the station’s fume extraction, and keep the hot iron in its stand. Disconnect USB before assembly.

2. Position the headers with the long pins pointing down into the breadboard and the short ends passing through the XIAO pads. Check that both rows are parallel and the board rests flat on the header spacers.

3. Secure both rows straight in the station’s holder. Tack one pin on each row, check alignment, then solder the remaining pins. Heat the pad and pin together and add only enough solder to join them.

4. Let the board cool, then inspect all 14 joints. Each joint must join the pin to its pad, with no gaps or loose pins. Check for solder bridges between adjacent pins or to the metal shield. Correct any defects before connecting USB. If the headers are already soldered, inspect them and skip soldering.

## 3  Set up Arduino and upload the starter

1. Install Arduino IDE 2 on your laptop. Download and extract the A1 student package from the course materials. Keep its folders and files together.

2. Open Arduino IDE settings (File > Preferences on Windows/Linux; Arduino IDE > Settings on macOS). Add this address to Additional Boards Manager URLs:

https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json

3. Open Boards Manager and install esp32 by Espressif Systems, version 3.3.10. Select Tools > Board > esp32 > XIAO_ESP32S3. Set USB CDC On Boot to Enabled if that option is shown.

4. Connect the XIAO directly to your laptop with a USB data cable. Keep it on a nonconductive surface with no external circuit attached. Select its port in Tools > Port. To identify it, unplug the board: that port disappears. Reconnect it: the port reappears.

5. Open Arduino/Lab_1/Lab_1.ino in the extracted A1 package. Keep a1_lab_logic.h and a1_lab_logic.cpp in the same folder. Leave all files unchanged. Click Verify and confirm compilation finishes without errors. Click Upload and confirm the IDE reports a completed upload without errors.

6. Open Serial Monitor at 115200 baud. Confirm this exact banner:

A1 Lab: responsive night-light controller

The starter is intentionally unfinished. No external LED behavior or light-sensor response is required yet. The banner confirms that your uploaded program runs and communicates over USB; it does not test every header pin, the camera, or the microphone.

## If the board does not respond

No port: Try a known-good data cable and a direct laptop connection. A charging-only cable can supply power without allowing uploads.

Upload fails: Close Serial Monitor. Disconnect USB, hold BOOT, reconnect USB, then release BOOT. Select the newly appearing port and upload again. Press RESET afterward and reselect the port if it changes.

No banner: Confirm the board, port, USB CDC setting, and 115200 baud. Reopen Serial Monitor or press RESET. If the board becomes unusually hot or smells burnt, disconnect USB immediately and get help before reconnecting it.

## 4  Check your results before you leave

☐  Required kit parts are present; any missing or damaged parts are reported.

☐  Both header rows are straight; all 14 joints join pin to pad, with no loose pins or solder bridges.

☐  Verify and Upload finish without errors, and Serial Monitor displays the exact banner.

Keep this checklist and a screenshot of the banner for your own setup record. No staff signoff is required. If a check fails, use the troubleshooting steps or ask for help before the A1 structured lab on October 1. Bring your kit, laptop, and data cable to that lab.

[Arduino IDE installation guide](https://docs.arduino.cc/software/ide-v2/tutorials/getting-started/ide-v2-downloading-and-installing)

[Seeed XIAO ESP32-S3 setup and hardware reference](https://wiki.seeedstudio.com/xiao_esp32s3_getting_started/)
