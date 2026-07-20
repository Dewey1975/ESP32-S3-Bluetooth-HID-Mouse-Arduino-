Overview

This project turns an ESP32-S3 DevKitC-1 (N8R8) into a Bluetooth HID mouse using the Arduino IDE. It provides:

Analog joystick cursor control
Left mouse button
Right mouse button
Scroll Up
Scroll Down
Automatic Bluetooth reconnection after pairing
No CircuitPython required

The project was developed and tested using an ESP32-S3 DevKitC-1 with 8 MB Flash and 8 MB PSRAM.

Hardware
Board
ESP32-S3 DevKitC-1 (N8R8)
Arduino IDE
Arduino IDE 2.3.x
ESP32 Arduino Core
Bluetooth Library

HIJEL HID BLE Mouse

Version tested:

0.1.0

Wiring
Function	GPIO
Joystick X	GPIO 4
Joystick Y	GPIO 5
Left Click	GPIO 6
Right Click	GPIO 7
Scroll Up	GPIO 15
Scroll Down	GPIO 16

Button wiring:

One side of each button connects to the GPIO pin.

The opposite side connects to GND.

The sketch uses the ESP32's internal pull-up resistors, so no external resistors are required.

Joystick power:

3.3V
GND
Arduino Settings

Board:

ESP32S3 Dev Module

Flash Size:

8MB (64Mb)

PSRAM:

OPI PSRAM

USB CDC On Boot:

Enabled

Port:

Select the COM port assigned to the board.

Installing
Install the ESP32 Arduino board package.
Install the HIJEL HID BLE Mouse library (version 0.1.0).
Open the sketch.
Select the correct board and COM port.
Upload.
Pairing

After uploading:

Enable Bluetooth on the host device.
Search for Bluetooth devices.
Pair with:

My ESP32 Mouse

After the initial pairing, the mouse reconnects automatically when powered on.

Features
Smooth analog cursor movement
Adjustable dead zone
Adjustable cursor sensitivity
Left click
Right click
Vertical scrolling
Automatic center calibration during startup
Automatic Bluetooth reconnect
Customization

The sketch exposes a few values that are easy to adjust.

Dead zone:

const int dead_zone = 250;

Increase to reduce small joystick movement.

Decrease for higher sensitivity.

Cursor speed:

const int movement_divider = 180;

Lower values make the cursor move faster.

Higher values slow it down.

Notes

This project intentionally uses Arduino instead of CircuitPython.

Once the Arduino sketch is uploaded, it replaces the previously installed CircuitPython application.

The project has been tested with:

Successful firmware upload
Bluetooth pairing
Automatic reconnection
Cursor movement
Left click
Right click
Scroll Up
Scroll Down
Future Ideas

Possible additions include:

Middle mouse button
DPI switching
Media controls
Volume control
Keyboard hotkeys
Battery level reporting
Sleep mode
USB/Bluetooth dual mode
Macro buttons
License

Choose any license that fits your project, such as MIT, BSD-3-Clause, or GPL, depending on how you want others to use and distribute the code.

Acknowledgments

Thanks to the ESP32 Arduino project and the HIJEL HID BLE Mouse library developers for providing the foundation that made this project possible.
