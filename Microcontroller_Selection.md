## [Microcontroller Selection]([https://docs.google.com/document/d/1LWaWr0pPLa30dbQCew1ZHN3ukLjS1rly/edit](https://docs.google.com/document/d/1LWaWr0pPLa30dbQCew1ZHN3ukLjS1rly/edit?usp=sharing&ouid=106828450620415480012&rtpof=true&sd=true))  
_*Table 1. Microcontroller Design Conciderations*_


| Design Considerations | Team Project-Specific Requirements from Problem Definition and Block Diagram | PIC Option 1 | PIC Option 2 | PIC Option 3 |
| ---------------------- | --------------------------------------------------------------------------- | ------------ | ------------ | ------------ |
| How many GPIO Pins?    | Need at least 10 GPIO Pins                                                  | 23           | 14           | 28           |
| Built-in Analog to Digital Converter? How many? | Least 2 Analog to Digital Converter JUST INCASE | 14           | 11           | 24           |
| Built-in Hardware PWM? How many?                | 1 Built in PWM for the motor                    | 8            | 2            | 2            |
| Built-in I2C? SPI? How many?                    | 1 built in I2C for the temperature sensor and the pressure sensors | 2 SPI and 2 I2C | 2 SPI and 2 I2C | 2 SPI and 2 I2C |
| Built-in UART? How many?                        | None                                            | 3            | 1            | 1            |
| Other Required Built-In Features? (optional)    | None                                            | -            | -            | -            |
| Additional considerations specific to your project specifications (optional) | Needs to be easy to solder and not super small | -            | -            | -            |


_*Table 2. Microcontroller Considerations*_


| Microcontroller Considerations | PIC Option 1 | PIC Option 2 | PIC Option 3 |
| ---------------------- | ------------ | ------------ | ------------ |
| Part Number    | AVR32DA32 | PIC16F18425          | PIC18F27Q10          |
| Link(URL) to Product Page |[Link](https://www.microchip.com/en-us/product/avr32da32)| [Link](https://www.microchip.com/en-us/product/pic16f18425)  | [Link](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27_47Q10-data-sheet-40002043C.pdf)         | 
| Links (URL) to Data Sheets                | [Datasheet Link](https://ww1.microchip.com/downloads/aemDocuments/documents/MCU08/ProductDocuments/DataSheets/AVR32DA28-32-48-Data-Sheet-40002228B.pdf) |[Datasheet Link](https://ww1.microchip.com/downloads/aemDocuments/documents/MCU08/ProductDocuments/DataSheets/PIC16-L-F18425-45-Microcontroller-Data-Sheet-DS40002002.pdf)            |[Datasheet Link](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27_47Q10-data-sheet-40002043C.pdf)           |
| Links (URL) to Application Notes | * [TouchPad Link](https://www.microchip.com/en-us/application-notes/an3433)<br>* [CCL Link](https://www.microchip.com/en-us/application-notes/tb3245)<br>* [Bootloader](https://www.microchip.com/en-us/application-notes/an3341) | * [Layout Link](https://www.microchip.com/content/dam/mchp/content-fragments/external-links/application-notes/an688-layout-tips-for-12-bit-a-d-converter-application)<br>* [5-Bit ADC Link](https://www.microchip.com/en-us/application-notes/tb3238.html)<br>* [C-Code](https://onlinedocs.microchip.com/g/GUID-2AB01789-9FC2-4D02-AE67-727C4F9D3E47) | * [HLVD Link](https://www.microchip.com/en-us/application-notes/tb3237.html)<br>* [5-Bit Link](https://www.microchip.com/en-us/application-notes/tb3238.html)<br>* [Getting Started Link](https://www.microchip.com/en-us/application-notes/tb3263) |
| Links (URL) to External Resources | * [UPDI Programmer](https://forum.arduino.cc/t/looking-for-updi-programmer/686029)<br>* [Number Maze](http://www.technoblogy.com/show?45JT) | * [Embedded Lab](https://embedded-lab.com/blog/embedded-lab-projects/)<br>* [DEV-Kit Link](https://www.ccsinfo.com/product_info.php?products_id=1825-kit) | * [Help Forum](https://forum.microchip.com/s/topic/a5C3l000000Bs9rEAC/t393021)<br>* [Arduino Uni](https://www.pcbway.com/project/sponsor/Arduino_UNO_used_to_program_pic_microcontroller.html) |
| Production Unit Cost    | $ 1.65           | $ 1.58            | $ 1.76            |
| Supply Voltage Range    | 1.8 - 5.5 V      | 1.8 - 5.5 V       | 1.8 - 5.5 V       |
| Absolute Maximum Current for entire IC     | 350 mA            | 250 mA            | 250 mA            |
| Maximum GPIO Pin Current (Source/Sink)     | ±50 mA            | ±50 mA            | ±50 mA            |
| 8-bit or 16-bit Architecture    | 32 Bit            | 16 Bit           | 8 Bit            |
| Available IC Packages / Footprints | * VQFN48<br>* VQFN32<br>* TQFP<br>* SSOP<br>* SOIC<br>* SPDIP | * PDIP<br>* SOIC (3.9 mm)<br>* SSOP<br>* UQFN (4x4) | * SPDIP<br>* SOIC<br>* SSOP<br>* VQFN<br>* QFN |
| Supports External Interrupts?    | Yes            | Yes            | Yes           |
| In-System Programming Capability and Type    | Yes, In-System Programmable    | Yes, In-System Programmable   | Yes, In-Circuit Serial Programming     |
| Works with MPLAB® X Integrated Development Environment (IDE)?    | Yes            | Yes            | Yes            |
| Works with Microchip Code Configurator?    | Yes            | Yes            | Yes  |


_*Table 3. Reason for Choosing Microcontrollers*_


| Criteria | AVR32DA32 | PIC16F18425 | PIC18F27Q10 |
|----------|-----------|-------------|-------------|
| Overall Pro's | * Features a 32-bit architecture, offering higher computational power and efficiency for complex applications.<br>* Wide supply voltage range (1.8-5.5V), providing flexibility in power supply design. | * Lower cost compared to the other options, making it a budget-friendly choice for cost-sensitive projects.<br>* Available in a DIP package, facilitating easy soldering and prototyping for beginners or projects with manual assembly needs. | * Highest number of GPIO pins (28) and ADC inputs (24), ensuring ample connectivity for sensors and actuators.<br>* Supports a wide range of communication protocols including 2 SPI and 2 I2C, offering versatile peripheral connectivity. |
| Overall Con's | * Limited number of ADC inputs (14) compared to project requirements, potentially restricting the number of analog sensors that can be directly connected.<br>* Lacks a DIP package option, making it less ideal for projects requiring manual soldering or prototyping on breadboards. | * Fewer GPIO pins (14) than required for projects needing extensive external connections.<br>* Limited ADC inputs (11), restricting the direct interfacing with multiple analog sensors. | * Higher cost relative to other options, which may affect budget considerations for the project.<br>* While it offers a broad feature set, the complexity and capabilities might necessitate a steeper learning curve. |
| Rankings | 2 | 3 | 1 |


# **Final Microcontroller Choice** 
* PIC18F27Q10
## **Rationale** 
* Choosing the PIC18F27Q10 for our project was an easy decision. Its abundance of GPIO pins and ADCs makes connecting sensors and actuators easy, ensuring precise measurements. The support for essential communication protocols simplifies project integration, and despite its higher price, the microcontroller's adaptability and the comprehensive development tools available justify the investment. This choice guarantees a smoother development process and a more reliable final product, making the slight extra cost well worth it for the advantages it offers.
