# UNO R4 Library Compatibility

The Arduino UNO R3 is a development board based on the **8-bit ATMega328P** microcontroller. It is one of the most iconic boards ever designed, and it is known and loved by millions of makers worldwide.

In June 2023, the **Arduino Uno R4 series** was released, the first UNO to feature a 32-bit microcontroller, the [RA4M1](https://www.renesas.com/us/en/document/dst/renesas-ra4m1-group-datasheet?r=1054146) from Renesas.  While 32-bit microcontrollers are no new thing, it is the first official UNO board to feature one. The R4 series has two versions:
- **Arduino UNO R4 Minima** ([store](http://store.arduino.cc/uno-r4-minima) / [docs](https://docs.arduino.cc/hardware/uno-r4-minima)) - base version.
- **Arduino UNO R4 WiFi** ([store](http://store.arduino.cc/uno-r4-wifi) / [docs](https://docs.arduino.cc/hardware/uno-r4-wifi)) - version with a Wi-Fi/Bluetooth module (ESP32) and a 12x8 LED matrix.

This major change will introduce many challenges, mainly for the amazing libraries developed over the years, particularly around the **ATMega328P**.

This repository is a gathering point for you all who want to participate in the testing & porting of libraries to the new 32-bit platform. Here you will see the status, and we welcome you to submit your testing data directly to this repository! 

See the [tested and confirmed library list](#tested-and-confirmed-libraries) further down this page.

## Donations

Please consider donating to your favorite library's developers. They are a fundamental part of the Arduino platform.

If your library is not yet supported on the UNO R4, donations may also ensure that your library can be ported to this new architecture.

## Guidelines

There are many ways to contribute to this project, including:
- **As a library developer:** can port your library to this new architecture, and document possible caveats.
- **As a tester:** test out libraries and report the status in this repository.

### Library Developers

As a library developer, you can support this project by making your existing library compatible with the 32-bit architecture, which the UNO R4 boards are based on.

This means making any changes needed for your library to compile and run on a UNO R4 board, i.e. *porting* your library.

For many libraries, there might be no changes at all, but for some that are focused on **ATMega328P** (e.g. accessing specific registers, memory management and so on), the challenge may be much bigger.

Essentially, the porting of a library should follow three crucial steps:

- Migration to the 32-bit Renesas architecture.
- Updating of library metadata (stating the compatibility).
- Report the status of the migration in the [issues]() section of this repository.

### Testers

If you are not a library developer, you can support this project by testing out various libraries not yet stated as compatible.

The [list](#tested-and-confirmed-libraries) that is found further below in this repository will show the progress of all tested libraries, regardless of a PASS / FAIL outcome.

We encourage you to test out the examples of a library with the UNO R4 and report the results both in this repository and in the library repository.

Some things to keep in mind are:
- If the library is on the [list](#tested-and-confirmed-libraries), there is no need to test it again.
- Follow the same structure as the [list](#tested-and-confirmed-libraries).

## How to Contribute

Tested and ported libraries should be reported in the [issues]() section of this repository, following the guidelines below:
- The title of your issue should *only* contain **Library Name** + **(Status)**. An ideal title: **Servo (PASS)**.
- If reporting a library that does not work, please report this in as much detail as possible, including:
  - Include link to tested example(s)
  - If it fails to compile, please attach the verbose log
  - If it compiles and uploads, but does not work as intended, please describe the issues you are having.

Issues reported in this repository will be continuously reviewed and added to the list of tested libraries, regardless of PASS/FAIL status.

## Tested and Confirmed Libraries

This list contains the status of tested Arduino libraries with the UNO R4 board. To change the list, submit a pull request to this repository.

### Robotics

| No. | Library                                                    | Compilation   | Hardware Test | Notes |
| --- | ---------------------------------------------------------- | ------------- | ------------- | ----- |
| 1.  | [Servo](https://github.com/arduino-libraries/Servo)        | PASS ✅      | PASS ✅        |       |
| 2.  | [Stepper](https://github.com/arduino-libraries/Stepper)    | PASS ✅      | PASS ✅        |       |
| 3.  | [AccelStepper](https://github.com/waspinator/AccelStepper) | PASS ✅      | FAIL ❌        |       |
| 4.  | [MobaTools](https://github.com/MicroBahner/MobaTools)      | PASS ✅      | PASS ✅        |       |


### Sensors

| No. | Library                                                                                                        | Compilation   | Hardware Test  | Notes                                      |
| --- | -------------------------------------------------------------------------------------------------------------- | ------------- | -------------- | ------------------------------------------ |
| 1.  | [Adafruit Neopixel](https://github.com/adafruit/Adafruit_NeoPixel)                                             | PASS ✅      | FAIL ❌        |                                            |
| 2.  | [Adafruit DHTSensor](https://github.com/adafruit/DHT-sensor-library)                                           | PASS ✅      | PASS ✅        |                                            |
| 3.  | [IRremote](https://github.com/Arduino-IRremote/Arduino-IRremote)                                               | FAIL ❌      | FAIL ❌        |                                            |
| 4.  | [Grove_BMP280](https://github.com/Seeed-Studio/Grove_BMP280)                                                   | PASS  ✅     | PASS  ✅       |                                            |
| 5.  | [Seeed_Arduino_LIS3DHTR](https://github.com/Seeed-Studio/Seeed_Arduino_LIS3DHTR)                               | PASS  ✅     | PASS  ✅       |                                            |
| 6.  | [DHT_sensor_library](https://github.com/adafruit/DHT-sensor-library)                                           | PASS  ✅     | PASS  ✅       |                                            |
| 7.  | [Grove_Temperature_And_Humidity_Sensor](https://github.com/Seeed-Studio/Grove_Temperature_And_Humidity_Sensor) | PASS  ✅     | PASS  ✅       |                                            |
| 8.  | [Keypad](https://github.com/Chris--A/Keypad)                                                                   | FAIL ❌      | FAIL ❌        |                                            |
| 9.  | [Adafruit_BMP280_Library](https://github.com/adafruit/Adafruit_BMP280_Library)                                 | PASS  ✅     | PASS  ✅       |                                            |
| 10. | [Adafruit_Keypad](https://github.com/adafruit/Adafruit_Keypad)                                                 | PASS  ✅     | PASS  ✅       |                                            |
| 11. | [Bounce2](https://github.com/thomasfredericks/Bounce2)                                                         | PASS  ✅     | PASS  ✅       |                                            |
| 12. | [Adafruit_BusIO](https://github.com/adafruit/Adafruit_BusIO)                                                   | PASS  ✅     | PASS  ✅       |                                            |
| 13. | [Adafruit_SGP30_Sensor](https://github.com/adafruit/Adafruit_SGP30)                                            | PASS  ✅     | PASS  ✅       |                                            |
| 14. | [Adafruit_SHT31_Library](Adafruit_SHT31_Library)                                                               | PASS  ✅     | PASS  ✅       |                                            |
| 15. | [Adafruit_LIS3DH](https://github.com/adafruit/Adafruit_LIS3DH)                                                 | PASS  ✅     | PASS  ✅       |                                            |
| 16. | [Adafruit_LSM6DSOX](https://github.com/adafruit/Adafruit_LSM6DS)                                               | PASS  ✅     | PASS  ✅       |                                            |
| 17. | [Adafruit_LSM6DSO32](https://github.com/adafruit/Adafruit_LSM6DS)                                              | PASS  ✅     | PASS  ✅       |                                            |
| 18. | [Adafruit_ADXL343](https://github.com/adafruit/Adafruit_ADXL343)                                               | PASS  ✅     | PASS  ✅       |                                            |
| 19. | [Adafruit-MLX90614-Library](https://github.com/adafruit/Adafruit-MLX90614-Library)                             | PASS  ✅     | PASS  ✅       |                                            |
| 20. | [SparkFunMLX90614](https://github.com/sparkfun/SparkFun_MLX90614_Arduino_Library)                              | FAIL ❌      | FAIL ❌        |                                            |
| 21. | [Adafruit_TCS34725](https://github.com/adafruit/Adafruit_TCS34725)                                             | PASS  ✅     | PASS  ✅       |                                            |
| 22. | [DFRobot_TCS34725](https://github.com/DFRobot/DFRobot_TCS34725)                                                | FAIL ❌      | FAIL ❌        |                                            |
| 23. | [DHTstable](https://github.com/RobTillaart/DHTstable)                                                          | PASS  ✅     | PASS  ✅       |                                            |
| 24. | [DHTNew](https://github.com/DFRobot/DFRobot_TCS34725)                                                          | PASS  ✅     | FAIL ❌        | Returns incorrect temperature and humidity |
| 25. | [Ultrasonic](https://github.com/ErickSimoes/Ultrasonic)                                                        | PASS  ✅     | PASS  ✅       |                                            |
| 26. | [Adafruit_BME280_Library](https://github.com/adafruit/Adafruit_BME280_Library)                                 | PASS  ✅     | PASS  ✅       |                                            |
| 27. | [arduino-bme280](https://github.com/malokhvii-eduard/arduino-bme280)                                           | PASS  ✅     | PASS  ✅       |                                            |
| 28. | [bme280](https://github.com/bolderflight/bme280)                                                               | PASS  ✅     | PASS  ✅       |                                            |
| 29. | [ER_OLEDM1_CH1115](https://github.com/gavinlyonsrepo/ER_OLEDM1_CH1115)                                         | PASS  ✅     | PASS  ✅       |                                            |
| 30. | [ERM19264_UC1609](https://github.com/gavinlyonsrepo/ERM19264_UC1609)                                           | PASS  ✅     | PASS  ✅       |                                            |
| 31. | [ADXL345](https://github.com/sparkfun/SparkFun_ADXL345_Arduino_Library)                                        | FAIL ❌      | FAIL ❌        |                                            |
| 32. | [SHT21-Arduino-Library](https://github.com/SolderedElectronics/SHT21-Arduino-Library)                          | PASS  ✅     | PASS  ✅       |                                            |
| 33. | [ArduinoJoystickLibrary](https://github.com/MHeironimus/ArduinoJoystickLibrary/tree/master)                    | FAIL ❌      | FAIL ❌        |                                            |
| 34. | [SHT21-Arduino-Library](https://github.com/SolderedElectronics/SHT21-Arduino-Library)                          | PASS  ✅     | PASS  ✅       |                                            |
| 35. | [DFRobot_SGP40](https://github.com/DFRobot/DFRobot_SGP40)                                                      | FAIL ❌      |                | Compiles on Wifi fails on Minima           |   
| 36. | [JoystickWin](https://github.com/controllercustom/JoystickWin)                                                 | PASS  ✅     | PASS  ✅       |                                            |
| 37. | [LoveButton](https://github.com/delta-G/LoveButton)                                                            | PASS  ✅     | PASS  ✅       |   made for Minima                          |
| 34. | [DIYables Keypad](https://github.com/DIYables/DIYables_Keypad)                                                 | PASS  ✅     | PASS  ✅       |                                            |

### Displays

| No. | Library                                                                                       | Compilation   | Hardware Test | Notes                                                                                                |
| --- | --------------------------------------------------------------------------------------------- | ------------  | ------------- | ---------------------------------------------------------------------------------------------------- |
| 1.  | [u8g2](https://github.com/olikraus/u8g2)                                                      | PASS ✅      | PASS ✅       |                                                                                                      |
| 2.  | [Adafruit SSD1306](https://github.com/adafruit/Adafruit_SSD1306)                              | PASS ✅      | FAIL ❌       | Scattered pixels all over the display.                                                               |
| 3.  | [LiquidCrystal](https://github.com/arduino-libraries/LiquidCrystal)                           | PASS ✅      | PASS ✅       |                                                                                                      |
| 4.  | [LiquidCrystal_I2C](https://github.com/johnrickman/LiquidCrystal_I2C)                         | PASS ✅      | PASS ✅       |                                                                                                      |
| 5.  | [SevSeg](https://github.com/DeanIsMe/SevSeg)                                                  | PASS ✅      | PASS ✅       |                                                                                                      |
| 6.  | [Adafruit_ST7735](https://github.com/adafruit/Adafruit-ST7735-Library)                        | PASS ✅      | PASS ✅       |                                                                                                      |
| 7.  | [Adafruit_ILI9341](https://github.com/adafruit/Adafruit_ILI9341)                              | FAIL ❌      | FAIL ❌       |                                                                                                      |
| 8.  | [FastLED](https://github.com/FastLED/FastLED)                                                 | PASS ✅      | PASS ✅       | Use fork by @facchinm                                                                                |
| 9.  | [ArduinoGraphics](https://github.com/arduino-libraries/ArduinoGraphics)                       | PASS ✅      | -             |                                                                                                      |
| 10. | [TFTLCD-Library](https://github.com/adafruit/TFTLCD-Library)                                  | FAIL ❌      | FAIL ❌       | #include "wiring_private.h                                                                           |
| 11. | [TM1638plus](https://github.com/gavinlyonsrepo/TM1638plus)                                    | PASS ✅      | PASS ✅       |                                                                                                      |
| 12. | [NOKIA5110_TEXT](https://github.com/gavinlyonsrepo/NOKIA5110_TEXT/)                           | PASS ✅      | PASS ✅       |                                                                                                      |
| 13. | [HD44780_LCD_PCF8574](https://github.com/gavinlyonsrepo/HD44780_LCD_PCF8574/)                 | PASS ✅      | PASS ✅       |                                                                                                      |
| 14. | [Arduino_GFX](https://github.com/moononournation/Arduino_GFX)                                 | PASS ✅      | PASS ✅       | Supports many data buses, also<br />TFT UNO-format shields (e.g., MCUFriend shields)                 |
| 15. | [DIYables_4Digit7Segment_74HC595](https://github.com/DIYables/DIYables_4Digit7Segment_74HC595)| PASS ✅      | PASS ✅       |                                                                                                      | 
| 16. | [MD_Parola](https://github.com/MajicDesigns/MD_Parola )                                       | PASS ✅      | PASS ✅       |                                                                                                      | 
| 17. | [MD_MAX72XX](https://github.com/MajicDesigns/MD_MAX72XX)                                      | PASS ✅      | PASS ✅       |                                                                                                      |
| 18. | [DIYables TFT Shield](https://github.com/DIYables/DIYables_TFT_Shield)                        | PASS ✅      | PASS ✅       |                                                                                                      |
| 19. | [DIYables TFT Touch Shield](https://github.com/DIYables/DIYables_TFT_Touch_Shield)            | PASS ✅      | PASS ✅       |                                                                                                      |

### USB

| No. | Library                                                   | Compilation | Hardware Test | Notes |
| --- | --------------------------------------------------------- | ----------- | ------------- | ----- |
| 1.  | [Mouse](https://github.com/arduino-libraries/Mouse)       | PASS ✅      | PASS ✅        |       |
| 2.  | [Keyboard](https://github.com/arduino-libraries/Keyboard) | PASS ✅      | PASS ✅        |       |
| 3.  | [USB_Host_Shield_2.0](https://github.com/felis/USB_Host_Shield_2.0) | PASS ✅      | PASS ✅     |       |

### Analog

| No. | Library                                                          | Compilation | Hardware Test | Notes |
| --- | ---------------------------------------------------------------- | ----------- | ------------- | ----- |
| 1.  | [Adafruit_MCP4725](https://github.com/adafruit/Adafruit_MCP4725) | PASS  ✅     | PASS  ✅       |       |


### Communication / Network

| No. | Library                                                                     | Compilation  | Hardware Test | Notes                                |
| --- | --------------------------------------------------------------------------- | ------------ | ------------- | ------------------------------------ |
| 1.  | [Ethernet](https://github.com/arduino-libraries/Ethernet)                   | PASS ✅      | PASS ✅        | Some examples need to be revised   |
| 2.  | [WiFi101](https://github.com/arduino-libraries/WiFi101)                     | PASS ✅      | FAIL ❌        | No networks are found              |
| 3.  | [RTClib](https://github.com/arduino-libraries/WiFi101)                      | PASS ✅      | PASS ✅        |                                    |
| 4.  | [JSON](https://github.com/arduino-libraries/Arduino_JSON)                   | PASS ✅      |                 |                                    |
| 5.  | [Adafruit_GPS_Library](https://github.com/adafruit/Adafruit_GPS)            | PASS ✅      |                 | Not tested on hardware yet         |
| 6.  | [Firmata](https://github.com/firmata/arduino)                               | FAIL ❌      | FAIL ❌        |                                    |
| 7.  | [OneWire](https://github.com/PaulStoffregen/OneWire)                        | PASS ✅      | PASS ✅        |                                    |
| 8.  | [Telemetrix4Arduino](https://github.com/PaulStoffregen/OneWire)             | PASS ✅      | PASS ✅        |     The R4 Branch                  |
| 9.  | [mWebSockets](https://github.com/skaarj1989/mWebSockets)                    | PASS ✅      | PASS ✅        |                                    |
| 10. | [GPIO_NXP_Arduino](https://github.com/teddokano/GPIO_NXP_Arduino)           | PASS ✅      | PASS ✅        |                                    |
| 11. | [LCDDriver_NXP_Arduino](https://github.com/teddokano/LCDDriver_NXP_Arduino) | PASS ✅      | PASS ✅        |                                    |
| 12. | [LEDDriver_NXP_Arduino](https://github.com/teddokano/LEDDriver_NXP_Arduino) | PASS ✅      | PASS ✅        | Not working with PCA9957(SPI)      |
| 13. | [MUX_SW_NXP_Arduino](https://github.com/teddokano/MUX_SW_NXP_Arduino)       | PASS ✅      | PASS ✅        |                                    |
| 14. | [RTC_NXP_Arduino](https://github.com/teddokano/RTC_NXP_Arduino)             | PASS ✅      | PASS ✅        | Not working with PCA2131(SPI mode) |
| 15. | [WiFiEspAT](https://github.com/jandrassy/WiFiEspAT)                         | PASS ✅      | PASS ✅        |                                    |
| 16. | [EthernetENCT](https://github.com/JAndrassy/EthernetENC)                    | PASS ✅      | PASS ✅        |                                    |
| 17. | [ArduinoOTA](https://github.com/jandrassy/ArduinoOTA)                       | PASS ✅      | PASS ✅        |                                    |
| 18. | [TelnetStream](https://github.com/jandrassy/TelnetStream)                   | PASS ✅      | PASS ✅        |                                    |
| 19. | [StreamLib](https://github.com/jandrassy/StreamLib)                         | PASS ✅      | PASS ✅        |                                    |
| 20. | [pubsubclient](https://github.com/knolleary/pubsubclient)                   | PASS  ✅     | PASS  ✅       |                                    |
| 21. | [EtherSia](https://github.com/njh/EtherSia)                   | PASS  ✅     | PASS  ✅       |                                    |
| 22. | [DS3231](https://github.com/NorthernWidget/DS3231)                      | PASS ✅      | PASS ✅        | 

### Storage

| No. | Library                                       | Compilation | Hardware Test | Notes |
| --- | --------------------------------------------- | ----------- | ------------- | ----- |
| 1.  | [SD](https://github.com/arduino-libraries/SD) | PASS ✅     | PASS ✅      |       |

### Power

| No. | Library                                                              | Compilation | Hardware Test | Notes |
| --- | -------------------------------------------------------------------- | ----------- | ------------- | ----- |
| 1.  | [Adafruit SleepyDog](https://github.com/adafruit/Adafruit_SleepyDog) | FAIL ❌     | FAIL ❌      |       |

### Audio

| No. | Library                                                                                                                | Compilation | Hardware Test | Notes                   |
| --- | ---------------------------------------------------------------------------------------------------------------------- | ----------- | ------------- | ----------------------- |
| 1.  | [Talkie](https://github.com/ArminJo/Talkie)                                                                            | FAIL ❌     |               | Fail on Minima and Wifi |
| 2.  | [Sparkfun-MP3-Player-Shield-Arduino-Library](https://github.com/madsci1016/Sparkfun-MP3-Player-Shield-Arduino-Library) | FAIL ❌     |               |
