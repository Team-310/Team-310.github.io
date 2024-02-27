## Microcontroller Selection 
*Table 1. Microcontroller Design Conciderations*


| Design Considerations | Team Project-Specific Requirements from Problem Definition and Block Diagram | PIC Option 1 | PIC Option 2 | PIC Option 3 |
| ---------------------- | --------------------------------------------------------------------------- | ------------ | ------------ | ------------ |
| How many GPIO Pins?    | Need at least 10 GPIO Pins                                                  | 23           | 14           | 28           |
| Built-in Analog to Digital Converter? How many? | Least 2 Analog to Digital Converter JUST INCASE | 14           | 11           | 24           |
| Built-in Hardware PWM? How many?                | 1 Built in PWM for the motor                    | 8            | 2            | 2            |
| Built-in I2C? SPI? How many?                    | 1 built in I2C for the temperature sensor and the pressure sensors | 2 SPI and 2 I2C | 2 SPI and 2 I2C | 2 SPI and 2 I2C |
| Built-in UART? How many?                        | None                                            | 3            | 1            | 1            |
| Other Required Built-In Features? (optional)    | None                                            | -            | -            | -            |
| Additional considerations specific to your project specifications (optional) | Needs to be easy to solder and not super small | -            | -            | -            |


*Table 2. Microcontroller Considerations*


| Microcontroller Considerations | PIC Option 1 | PIC Option 2 | PIC Option 3 |
| ---------------------- | ------------ | ------------ | ------------ |
| Part Number    | AVR32DA32 | PIC16F18425          | PIC18F27Q10          |
| Link(URL) to Product Page |[Link](https://www.microchip.com/en-us/product/avr32da32)| [Link](https://www.microchip.com/en-us/product/pic16f18425)  | [Link](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27_47Q10-data-sheet-40002043C.pdf)         | 
| Links (URL) to Data Sheets                | [Datasheet Link](https://ww1.microchip.com/downloads/aemDocuments/documents/MCU08/ProductDocuments/DataSheets/AVR32DA28-32-48-Data-Sheet-40002228B.pdf) |[Datasheet Link](https://ww1.microchip.com/downloads/aemDocuments/documents/MCU08/ProductDocuments/DataSheets/PIC16-L-F18425-45-Microcontroller-Data-Sheet-DS40002002.pdf)            |[Datasheet Link](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27_47Q10-data-sheet-40002043C.pdf)           |
| Links (URL) to Application Notes          | [TouchPad Link](https://www.microchip.com/en-us/application-notes/an3433), [CCL Link](https://www.microchip.com/en-us/application-notes/tb3245), [Bootloader](https://www.microchip.com/en-us/application-notes/an3341) |[Layout Link](https://www.microchip.com/content/dam/mchp/content-fragments/external-links/application-notes/an688-layout-tips-for-12-bit-a-d-converter-application), [5-Bit ADC Link](https://www.microchip.com/en-us/application-notes/tb3238.html), [C-Code](https://onlinedocs.microchip.com/g/GUID-2AB01789-9FC2-4D02-AE67-727C4F9D3E47) |[HLVD Link](https://www.microchip.com/en-us/application-notes/tb3237.html), [5-Bit Link](https://www.microchip.com/en-us/application-notes/tb3238.html), [Getting Started Link](https://www.microchip.com/en-us/application-notes/tb3263) |
| Links (URL) to External Resources    |[UPDI Programer](https://forum.arduino.cc/t/looking-for-updi-programmer/686029), [Number Maze](http://www.technoblogy.com/show?45JT)            |[Embedded Lab](https://embedded-lab.com/blog/embedded-lab-projects/), [DEV-Kit Link](https://www.ccsinfo.com/product_info.php?products_id=1825-kit)            |[Help Fourm](https://forum.microchip.com/s/topic/a5C3l000000Bs9rEAC/t393021), [Arduino Uni](https://www.pcbway.com/project/sponsor/Arduino_UNO_used_to_program_pic_microcontroller.html)          |
| Production Unit Cost    | $ 1.65           | $ 1.58            | $ 1.76            |
| Supply Voltage Range    | 1.8 - 5.5 V      | 1.8 - 5.5 V       | 1.8 - 5.5 V       |
| Absolute Maximum Current for entire IC     | 350 mA            | 250 mA            | 250 mA            |
| Maximum GPIO Pin Current (Source/Sink)     | ±50 mA            | ±50 mA            | ±50 mA            |
| 8-bit or 16-bit Architecture    | 32 Bit            | 16 Bit           | 8 Bit            |
| Available IC Packages / Footprints    | * VQFN48 
* VQFN32
* TQFP
* SSOP
* SOIC
* SPDIP |
* PDIP
* SOIC (3.9 mm)
* TSSOP * UQFN (4x4) |
* SPDIP
* SOIC
* SSOP
* VQFN
* QFN |
| Supports External Interrupts?    | Yes            | Yes            | Yes           |
| In-System Programming Capability and Type    | Yes, In-System Programmable    | Yes, In-System Programmable   | Yes, In-Circuit Serial Programming     |
| Works with MPLAB® X Integrated Development Environment (IDE)?    | Yes            | Yes            | Yes            |
| Works with Microchip Code Configurator?    | Yes            | Yes            | Yes  |


*Table 3. Reason for Choosing Microcontrollers*


| Write overall pros, cons, and rankings for the chosen microcontrollers | AVR32DA32 | PIC16F18425          | PIC18F27Q10          |
| ---------------------------------------------------------------------- | --------- | -------------------- | -------------------- |
| Overall Pro's    | * Features a 32-bit architecture, offering higher computational power and efficiency for complex applications. * Wide supply voltage range (1.8-5.5V), providing flexibility in power supply design | * Lower cost compared to the other options, making it a budget-friendly choice for cost-sensitive projects. * Available in a DIP package, facilitating easy soldering and prototyping for beginners or projects with manual assembly needs. | * Highest number of GPIO pins (28) and ADC inputs (24), ensuring ample connectivity for sensors and actuators. * Supports a wide range of communication protocols including 2 SPI and 2 I2C, offering versatile peripheral connectivity. |
| Overall Con's    | * Limited number of ADC inputs (14) compared to project requirements, potentially restricting the number of analog sensors that can be directly connected. * Lacks a DIP package option, making it less ideal for projects requiring manual soldering or prototyping on breadboards. | * Fewer GPIO pins (14) than required for projects needing extensive external connections. * Limited ADC inputs (11), restricting the direct interfacing with multiple analog sensors.  |  * Higher cost relative to other options, which may affect budget considerations for the project.  * While it offers a broad feature set, the complexity and capabilities might necessitate a steeper learning curve.  | 
|Ranking's        | 2   |    3    | 1   |
