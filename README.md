Overview
This project utilizes an Adafruit OLED display, an Adafruit LSM6DS3TRC IMU sensor, a SIM800L GSM module, and a WiFi module to create a versatile IoT device. The project includes a bitmap display of the Crowley logo and connects to the internet using both WiFi and cellular networks.

Hardware Components
Xiao Sense
Xiao Expansion Board with OLED
Adafruit SSD1306 OLED display
Adafruit LSM6DS3TRC IMU sensor
UART WiFi module
UART SIM800L cellular module
Float switch (normally open)
Various connecting wires


Libraries Required
#include <Wire.h>
#include <Adafruit_SSD1306.h>
#include <Adafruit_GFX.h>
#include <Adafruit_Sensor.h>
#include <Adafruit_LSM6DS3TRC.h>
#include <SoftwareSerial.h>
#include <SIM800L.h>
#include <TinyGsmClient.h>

OLED Display Settings
#define SCREEN_WIDTH 128
#define SCREEN_HEIGHT 64
#define OLED_RESET -1
Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, OLED_RESET);

IMU Sensor Setup
Adafruit_LSM6DS3TRC lsm6ds3trc;

WiFi and SIM800L Modules
SoftwareSerial wifiSerial(2, 3); // RX, TX for WiFi module
SoftwareSerial sim800lSerial(4, 5); // RX, TX for SIM800L module

SIM800L sim800l(&sim800lSerial, 7, 200, 512); // SIM800L instance
#define SIM800_RX_PIN 10
#define SIM800_TX_PIN 11
#define SIM800_RST_PIN 6
#define APN "altanwifi"



Setup Instructions
Install the necessary libraries:

Wire
Adafruit_SSD1306
Adafruit_GFX
Adafruit_Sensor
Adafruit_LSM6DS3TRC
SoftwareSerial
SIM800L
TinyGsmClient
Connect the hardware components according to the pin configuration in the code.

Upload the code to the Xiao Sense using the Arduino IDE.

Verify the connections and ensure that all modules are functioning correctly.

Run the program and observe the output on the OLED display. The device should connect to the internet using either the WiFi or SIM800L module.

Usage
The OLED display will show the Crowley logo and sensor data.
The IMU sensor will provide motion and orientation data.
The WiFi and SIM800L modules will enable internet connectivity.
The float switch can be used to trigger specific actions or alerts.
Troubleshooting
OLED display issues: Ensure that the display connections are secure and the correct library is installed.
Sensor not responding: Check the I2C connections and ensure the sensor library is correctly installed.
WiFi/SIM800L connectivity problems: Verify the serial connections and APN settings for the SIM800L module.
License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgements
Special thanks to the developers of the libraries and the open-source community for their contributions.

Contact
For any inquiries or support, please contact [your email address].
