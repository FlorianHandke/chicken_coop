# chicken_coop
Blueprint for a simple automated chicken coop

# Summary

Construction plan for a simple battery-powered control of a chicken coop door.

The basis of the construction is an ESP32 microcontroller that controls a motor. The motor used is a DC gear motor that opens the door via a cable pull.

Since comparable models often cost over 100€, I want to show a low-cost alternative that can be implemented without much prior knowledge. The ESP32 is the optimal basis for this, because it is available for less than 10€ and is easy to program with Arduino.

# ESP32

Why did I choose the ESP32 as the basis for the project:

 * According to the manufacturer it can be operated from -40 to +125°C and is therefore suitable for all seasons
 * The energy consumption of the ESP32 is very low. This is especially important because I want to run my setup with batteries.
 * It has Wifi and Bluetooth. This can be used in later extensions, for example, to transfer sensor data (eg via MQTT) from the chicken coop.
 * The price for an ESP32 is about 7€.

# Bill of Materials

| Part      | Costs       | Source                          |
| :---:     | :-:         | :-:                             |
| ESP32     | 7,00         | https://www.berrybase.de/dev.-boards/esp8266-esp32-d1-mini/boards/dfrobot-firebeetle-esp32-e-iot-microcontroller-40-wlan-bluetooth-41?sPartner=g_shopping&gclid=Cj0KCQiAieWOBhCYARIsANcOw0xQ2V2XK0BZ4D0wuKFr1zgEPUG9Gw_NbxFlbUV5AfoqsegRdoo04fMaAsdVEALw_wcB |
| L298N Motor Drive Controller | 5,99 | https://www.amazon.de/DollaTek-Controller-Board-Modul-verdoppeln-Smart-Auto-Roboter/dp/B07DK6Q8F9/ref=asc_df_B07DK6Q8F9/?tag=googshopde-21&linkCode=df0&hvadid=407376180407&hvpos=&hvnetw=g&hvrand=3184291338626227148&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9041896&hvtargid=pla-717167482690&psc=1&th=1&psc=1&tag=&ref=&adgrpid=87437852872&hvpone=&hvptwo=&hvadid=407376180407&hvpos=&hvnetw=g&hvrand=3184291338626227148&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9041896&hvtargid=pla-717167482690 |
|DC gear motor |15,39|https://www.amazon.de/FTVOGUE-Drehmomentstarker-Langsamer-Elektromotor-Wellendurchmesser/dp/B07NY7GJ8F/ref=sr_1_19?__mk_de_DE=ÅMÅŽÕÑ&crid=7HDI2RGU49YB&keywords=DC+Motor+12V+getriebe&qid=1641639284&sprefix=dc+motor+12v+getriebe%2Caps%2C72&sr=8-19|
