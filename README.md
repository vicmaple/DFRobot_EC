## DFRobot_EC Library (No EEPROM)
---------------------------------------------------------

========== THIS IS STILL A WIP ==========

This fork adds a second library that uses the same class and methods of the original DFRobot_EC library, but without using EEPROM.

I made this because the library is perfect for what I want to do, but my microcontroller has no EEPROM chip at all. (See MKR Arduino series)

The calibration data will be held by the object until the microcontroller power off.

It MAY be possible to use FlashStorage ( https://github.com/cmaglie/FlashStorage ) to emulate EEPROM by "burning" data onto the flash. (For the moment, I don't want to delve into this witchcraft.)

Usage is the same. You don't need to call begin() anymore. begin() would only fetch data from memory which... well, we aren't using.

## Main Changes 

 - New library added : DFRobot_EC_NO_EEPROM
 
 - Inside DFRobot_EC_NO_EEPROM:
    - begin() has been removed
    - Parts of ecCalibration dealing with memory has been removed

Original README.md Ahead : 

This is the sample code for Gravity: Analog Electrical Conductivity Sensor / Meter Kit V2 (K=1.0), SKU: DFR0300.
## Table of Contents

* [Methods](#methods)
* [History](#history)
* [Credits](#credits)
<snippet>
<content>

## Methods

```C++

/*
 * @brief Init The Analog Electrical Conductivity Sensor
 */
void begin();

/*
 * @brief Convert voltage to EC with temperature compensation
 *
 * @param voltage     : Voltage value
 *        temperature : Ambient temperature
 *
 * @return The EC value
 */
float readEC(float voltage, float temperature);

/*
 * @brief Calibrate the calibration data
 *
 * @param voltage     : Voltage value
 *        temperature : Ambient temperature
 *        cmd         : enterec -> enter the EC calibration mode
 *                      calec   -> calibrate with the standard buffer solution, two buffer solutions(1413us/cm and 12.88ms/cm) will be automaticlly recognized
 *                      exitec  -> save the calibrated parameters and exit from EC calibration mode
 */
void calibration(float voltage, float temperature, char* cmd);

```

## History

- date 2018-11-6
- version V1.0

## Credits

Written by Jiawei Zhang(Welcome to our [website](https://www.dfrobot.com/))
