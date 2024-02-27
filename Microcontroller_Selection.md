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
| link (URL) to Product Page |[Link]([http://www.google.fr/](https://www.microchip.com/en-us/product/avr32da32) "Named_Link")           | 11           | 24           |
| Built-in Hardware PWM? How many?                | 8            | 2            | 2            |
| Built-in I2C? SPI? How many?                    | 2 SPI and 2 I2C | 2 SPI and 2 I2C | 2 SPI and 2 I2C |
| Built-in UART? How many?                        | 3            | 1            | 1            |
| Other Required Built-In Features? (optional)    | -            | -            | -            |
| Additional considerations specific to your project specifications (optional) | -            | -            | -            |
