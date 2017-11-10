# SSD1306
SSD1306 is a single-chip CMOS OLED/PLED driver with controller for organic / polymer light emitting diode dot-matrix graphic display system.
It consists of 128 segments and 64 commons.
This IC is designed for Common Cathode type OLED panel.
The SSD1306 embeds with contrast control, display RAM and oscillator, which reduces the number of external components and power consumption.
It has 256-step brightness control.
Data/Commands are sent from general MCU through the hardware selectable 6800/8000 series compatible Parallel Interface, I2C interface or Serial Peripheral Interface.
It is suitable for many compact portable applications, such as mobile phone sub-display, MP3 player and calculator, etc.

## DFRobot_SSD1306 Library for Arduino
---------------------------------------------------------
Provide a library faciltates operations in the screen that drived by SSD1306.

## Table of Contents

* [Summary](#summary)
* [Feature](#feature)
* [Installation](#installation)
* [Result](#result)
* [Methods](#methods)

* [History](#history)
* [Depends](#depends)
* [Compatibility](#compatibility)
* [Credits](#credits)
<snippet>
<content>

## Summary

Input commands and draw different figures in the screen

## Feature

Support different drawings in the screen, including point, line, circle, rectangle, triangle,rounded rectangle and some commands.<br>
Support English characters and character library chips of DFRobot modules.<br>
IIC: the redraw rate is more than 30 frames per second when redrawed by ESP series controllers<br>

## Installation

Download the library ZIP file and unzip it to the Arduino folder of the library.<br>
(If you haven't download DFRobot display library before,you need to download it first to drive (https://github.com/DFRobot/DFRobot_Display))


## Result

Functions supports. <0 means error;>0 means warning, 0 means OK .

begin type

value              |             result            
------------------ | -------------------------------------------
-1                 |             error             
1                  |      no feedback test         

function type

Value              |            result              
------------------ | -------------------------------------------
-4                 |          mem overflow
-3                 |          not support
-2                 |          param
-1                 |          error
1                  |          out range

## Methods

```C++

#include "DFRobot_SSD1306_I2C.h"

Except special instructions, all axis as below are relative to the source node , draw point in the screen when color>0，clear point in the screen when color=0.

/*
 * @brief ssd1306 objective
 *
 * @param I2C_addr        ssd1306 I2C address
 */
DFRobot_SSD1306_I2C(uint8_t I2C_addr);

/*
 * @brief lib begin
 *
 * @return begin result
 */
int16_t begin(void);

/*
 * @brief fill screen
 */
void fillScreen(uint16_t color);

/*
 * @brief draw a pixel
 *
 * @param x       x-axis coordinates
 *        y       y-axis coordinates
 */
void drawPixel(int16_t x, int16_t y, uint16_t color);

/*
 * @brief draw a line
 *
 * @param x0        The x-axis of the starting point
 *        y0        The y-axis of the starting point
 *        x1        The x-axis of the terminal point
 *        y1        The y-axis of the terminal point
 */
void drawLine(int16_t x0, int16_t y0, int16_t x1, int16_t y1, 
              uint16_t color);

/*
 * @brief draw a horizontal line
 *
 * @param x         The x-axis of the starting point
 *        y         The y-axis of the starting point
 *        width     The line lenth
 */
void drawHLine(int16_t x, int16_t y, int16_t width, uint16_t color);

/*
 * @brief draw a vertical line
 *
 * @param x         The x-axis of the starting point
 *        y         The y-axis of the starting point
 *        height    The line lenth
 */
void drawVLine(int16_t x, int16_t y, int16_t height, uint16_t color);

/*
 * @brief draw a rectangle
 *
 * @param x         The x-axis of the starting point
 *        y         The y-axis of the starting point
 *        width     The rectangle width
 *        height    The rectangle height
 */
void drawRect(int16_t x, int16_t y, int16_t width, int16_t height, 
              uint16_t color);

/*
 * @brief draw a fill rectangle
 *
 * @param x         The x-axis of the starting point
 *        y         The y-axis of the starting point
 *        width     The rectangle width
 *        height    The rectangle height
 */
void fillRect(int16_t x, int16_t y, int16_t width, int16_t height, 
              uint16_t color);

/*
 * @brief draw a circle
 *
 * @param x         The x-axis of the center
 *        y         The y-axis of the center
 *        r         The circle radius 
 */
void drawCircle(int16_t x, int16_t y, int16_t r, uint16_t color);

/*
 * @brief draw a fill circle
 *
 * @param x         The x-axis of the center
 *        y         The y-axis of the center
 *        r         The circle radius
 */
void fillCircle(int16_t x, int16_t y, int16_t r, uint16_t color);

/*
 * @brief draw a triangle
 *
 * @param x0        The x-axis of the first point
 *        y0        The y-axis of the first point
 *        x0        The x-axis of the second point
 *        y0        The y-axis of the second point
 *        x0        The x-axis of the third point
 *        y0        The y-axis of the third point
 */
void drawTriangle(int16_t x0, int16_t y0, int16_t x1, int16_t y1, 
                  int16_t x2, int16_t y2, uint16_t color);
                  
/*
 * @brief draw a fill triangle
 *
 * @param x0        The x-axis of the first point
 *        y0        The y-axis of the first point
 *        x0        The x-axis of the second point
 *        y0        The y-axis of the second point
 *        x0        The x-axis of the third point
 *        y0        The y-axis of the third point
 */
void fillTriangle(int16_t x0, int16_t y0, int16_t x1, int16_t y1, 
                  int16_t x2, int16_t y2, uint16_t color);

/*
 * @brief draw a rounded rectangle
 *
 * @param x         The x-axis of the starting point
 *        y         The y-axis of the starting point
 *        width     The rectangle width
 *        height    The rectangle height
 *        r         The rounded corner radius
 */
void drawRoundRect(int16_t x, int16_t y, int16_t, width, int16_t height, 
                   int16_t r, uint16_t color);
                   
/*
 * @brief draw a fill rounded rectangle
 *
 * @param x         The x-axis of the starting point
 *        y         The y-axis of the starting point
 *        width     The rectangle width
 *        height    The rectangle height
 *        r         The rounded corner radius
 */
void fillRoundRect(int16_t x, int16_t y, int16_t, width, int16_t height, 
                   int16_t r, uint16_t color);
                   
/*
 * @brief Set axis of the source node(relative to the top left corner)
 *
 * @param x         The x-axis of the source node
 *        y         The y-axis of the source node
 */
void setOrign(int16_t x, int16_t y);

/*
 * @brief Get axis of the source node(relative to the top left corner)
 *
 * @param x         Address to store varialbles of the source node x-axis
 *        y         Address to store varialbles of the source node y-axis
 */
void getOrign(int16_t* pX, int16_t* pY);

/*
 * @brief Set printing point axis (relative to the top left corner)
 *
 * @param x         x-axis of the printed point
 *        y         y-axis of the printed point
 */
void setCursor(int16_t x, int16_t y);

/*
 * @brief Get axis of the printed point(relative to the top left corner)
 *
 * @param x         Address to store varialbles of the printed point x-axis
 *        y         Address to store varialbles of the printed point y-axis
 */
void getCursor(int16_t* pX, int16_t* pY);

/*
 * @brief Set text color
 */
void setTextColor(uint16_t color);

/*
 * @brief Get text color
 *
 * @return 16 bits color data
 */
uint16_t getTextColor(void);

/*
 * @brief Set text size
 *
 * @param size        text size
 */
void setTextSize(uint8_t size);

/*
 * @brief Get text size
 *
 * @return text size
 */
uint8_t getTextSize(void);

/*
 * @brief Print text in the print point, the usage method is as same as the serial port
 */
size_t print(...);
size_t println(...);

size_t printf(...);  //Only ESP series cpntrollers are supportive

enum eROTATION {
  eROTATION_0,
  eROTATION_90,
  eROTATION_180,
  eROTATION_270
};

/*
 * @brief Set the screen to rotate
 *
 * @param eRotation       The rotation angle
 */
void setRotation(eROTATION eRotation);  //Need the hardware support

/*
 * @brief Get the screen rotation
 *
 * @return The rotation angle
 */
eROTATION getRotation(void);

/*
 * @brief Get screen width
 *
 * @return The screen width
 */
int16_t getWidth(void);

/*
 * @brief Get screen hight
 *
 * @return The  screen hight
 */
int16_t getHeight(void);

/*
 * @brief Display bmp file
 *
 * @param s       file objectiv
 *        x       The x-axis of the starting point
 *        y       The y-axis of the starting point
 *
 * @return Error message
 */
int16_t drawBmp(Stream *s, int16_t x, int16_t y);

/*
 * @brief invertDisplay
 *
 * @param eInvert       
 */
int16_t getWidth(void);

/*
 * @brief Get screen hight
 *
 * @return The  screen hight
 */
int16_t getHeight(void);

/*
 * @brief Show image array
 *
 * @param x       The x-axis of the starting point
 *        y       The y-axis of the starting point
 *        w       The image width
 *        h       The image hight
 *        pBuf    The array address
 */
int16_t drawBuffer(int16_t x, int16_t y, uint16_t w, uint16_t h, 
                   uint8_t* pBuf);

/*
 * @brief display ON
 */
void displayON(void);

/*
 * @brief display OFF
 */
void displayOFF(void);

```

## Depends

Projects           |                     URL                       | Remarks
------------------ | :-------------------------------------------: | -----------
DFRobot_Display    |  https://github.com/DFRobot/DFRobot_Display   | must

## Compatibility

MCU                | Work Well | Work Wrong | Untested  | Remarks
------------------ | :----------: | :----------: | :---------: | -----
FireBeetle-ESP32  |      √       |             |            | 
FireBeetle-ESP8266  |      √       |             |            | 
FireBeetle-BLE4.1 |       √      |             |            | 
Arduino uno |       √      |             |            | 
Arduino leonardo |      √       |             |            | 

## History



## Credits

Written by DFRobot_xiaowo, 2017. (Welcome to our [website](https://www.dfrobot.com/))
