# [Component Selection](https://docs.google.com/document/d/1LcmL5Pp_lv0PSCJ3DXv-DvtYZl9i9sau2eAefg3Dcjk/edit?usp=sharing)   

## Voltage Regulator - [LM2575D2T-3.3R4G](https://www.digikey.com/en/products/detail/onsemi/LM2575D2T-3.3R4G/5801702?utm_adgroup=&utm_source=google&utm_medium=cpc&utm_campaign=PMax%20Shopping_Product_Medium%20ROAS%20Categories&utm_term=&utm_content=&utm_id=go_cmp-20223376311_adg-_ad-__dev-c_ext-_prd-5801702_sig-CjwKCAiAibeuBhAAEiwAiXBoJHnZP0vQYhg2BseQ3jPSFarn2P5zuhtLkV188zWd8XpeyW5NurhlyRoC53MQAvD_BwE&gad_source=1&gclid=CjwKCAiAibeuBhAAEiwAiXBoJHnZP0vQYhg2BseQ3jPSFarn2P5zuhtLkV188zWd8XpeyW5NurhlyRoC53MQAvD_BwE)  
![Voltage Regulator](https://github.com/Team-310/Team-310.github.io/assets/157059404/b8292bf4-7cca-41b0-9c0f-20a72e7351fd)  
Our team ultimately chose the LM2575D2T-3 as our 3.3V switching voltage regulator for the weather station project, prioritizing its perfect alignment with our voltage requirements and its high efficiency for power conservation. Despite being slightly pricier at 10/$1.49, the regulator's low dropout and compact design justified the extra cost by ensuring reliable performance and fitting within our design constraints. The LM2575D2T-3 direct 3.3V output simplifies our system, avoiding the need for additional regulation and making it an ideal choice for our battery-powered, outdoor application.  

## Motor Driver - [IFX9201SGAUMA1](https://www.digikey.com/en/products/detail/infineon-technologies/IFX9201SGAUMA1/5415542)  
![Motor Driver](https://github.com/Team-310/Team-310.github.io/assets/157059404/cb1a1a7b-cff0-4249-b2a7-967dc4a40287)  
Our team chose this motor driver because of its features. This driver can be powered with 3.3V which is a requirement for our product. In addition, it has low standby current and chopper current limitations. This driver also communicates with the microcontroller using SPI or PWM which is ideal. Although this driver isn't the cheapest of the motor drivers available our team finds that the pros outweigh the price and are willing to make space in the budget for this motor driver.

## Temperature Sensor - [TC74A4](https://www.digikey.com/en/products/detail/microchip-technology/TC74A4-3-3VCTTR/443268)  
![TC74](https://github.com/Team-310/Team-310.github.io/assets/157059404/12b20c2e-b266-4cdb-aebd-e14246c67a48)
  
Our team chose the TC74A4 temperature sensor because of its solderability and reliability. This sensor comes in at $1.15 which is very affordable which aligns with our budget. The sensors' supply voltage is 2.7V to 5.5V which also works for our design since we will be supplying our circuit with 3.3V as required. This sensor's margin of error is 2 degrees Celcius between 25 degrees Celcius and 85 degrees Celcius. With all of these features in mind, this makes the TC74A4 the right sensor for our project.

## Barometric Pressure Sensor - [BME280](https://www.digikey.com/en/products/detail/bosch-sensortec/BME280/6136306)  
![Pressure](https://github.com/Team-310/Team-310.github.io/assets/157059404/97e0b5b0-e32a-4cbd-b10e-c8bf5a444dda)  
Our team chose the BME 280 Combined humidity and pressure sensor because it acts as a humidity and pressure sensor in one. Despite being the most expensive one, it comes with a very detailed datasheet that makes it easy to set up. While it may be more difficult to solder, the team has come up with a plan to successfully solder this part onto a PCB. The main supply voltage ranges from 1.71 V to 3.6 V, which is perfect for this project's power  requirements. It is also the most accurate from 32 degrees to 150 degrees Fahrenheit, making it ideal for the Arizona weather that can reach up to 121 degrees.

## Component Summary  
In selecting components for our weather station, we prioritized efficiency, compatibility, and cost-effectiveness. For voltage regulation, we chose the LM2575D2T-3 for its precise 3.3V output and high efficiency, despite a slightly higher cost. Our motor driver selection prioritized 3.3V compatibility, low standby current, and flexible communication options. The TC74A4 temperature sensor met our needs for reliability, affordability, and voltage compatibility. For humidity and pressure sensing, the BME280 Combined sensor stood out for its detailed datasheet, accuracy across extreme temperatures, and suitability for our power requirements. Each component was chosen to ensure seamless integration, reliability, and adherence to project specifications while staying within budget constraints.

# [Power Budget](https://docs.google.com/spreadsheets/d/1HANT8wJLup0bfyjqzk9ScGWXk3m4afTw/edit?usp=sharing&ouid=106828450620415480012&rtpof=true&sd=true)
![pwB2](https://github.com/Team-310/Team-310.github.io/assets/157059404/e7b2cdd0-066c-4160-93b0-c0a0ce020b74)  
![PWB2-2](https://github.com/Team-310/Team-310.github.io/assets/157059404/65f1692a-b007-4376-8fc9-98f33cd8cfb3)  


- Our power budget analysis indicates that, when operating at full capacity continuously, the product provides approximately 2 hours of runtime. However, we expect users to enjoy longer periods of use, as it's unlikely the device will be consistently running at maximum. We've also made battery replacement straightforward, and for those interested in sustainability, the product is compatible with rechargeable batteries, enhancing its eco-friendly appeal.
