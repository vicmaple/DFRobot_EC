## DFRobot_EC Library (No EEPROM)
---------------------------------------------------------

========== THIS IS STILL A WIP ==========

The librairy has been edited so that it doesn't need EEPROM to save configurations.

It will use variables to hold data until the microcontroller power off.

It MAY be possible to use FlashStorage ( https://github.com/cmaglie/FlashStorage ) to emulate EEPROM by "burning" data onto the flash. (For the moment, I don't want to delve into this witchcraft.)

Original README.md : 

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
