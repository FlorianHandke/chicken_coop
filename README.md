# chicken_coop
Blueprint for a simple automated chicken coop

# Summary

Construction plan for a simple battery-powered control of a chicken coop door.

The basis of the construction is an ESP32 microcontroller that controls a motor. The motor used is a DC gear motor that opens the door via a cable pull.

Since comparable models often cost over 100€, I want to show a low-cost alternative that can be implemented without much prior knowledge. The ESP32 is the optimal basis for this, because it is available for less than 10€ and is easy to program with Arduino.

# Bill of Materials

| Part      | Costs       | Source                          |
| :---:     | :-:         | :-:                             |
| ESP32     | 7,00         | [berrybase](https://www.berrybase.de/dev.-boards/esp8266-esp32-d1-mini/boards/dfrobot-firebeetle-esp32-e-iot-microcontroller-40-wlan-bluetooth-41?sPartner=g_shopping&gclid=Cj0KCQiAieWOBhCYARIsANcOw0xQ2V2XK0BZ4D0wuKFr1zgEPUG9Gw_NbxFlbUV5AfoqsegRdoo04fMaAsdVEALw_wcB) |
| L298N Motor Driver | 5,99 | [amazon](https://www.amazon.de/DollaTek-Controller-Board-Modul-verdoppeln-Smart-Auto-Roboter/dp/B07DK6Q8F9/ref=asc_df_B07DK6Q8F9/?tag=googshopde-21&linkCode=df0&hvadid=407376180407&hvpos=&hvnetw=g&hvrand=3184291338626227148&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9041896&hvtargid=pla-717167482690&psc=1&th=1&psc=1&tag=&ref=&adgrpid=87437852872&hvpone=&hvptwo=&hvadid=407376180407&hvpos=&hvnetw=g&hvrand=3184291338626227148&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9041896&hvtargid=pla-717167482690) |
|DC gear motor |15,39| [amazon](https://www.amazon.de/FTVOGUE-Drehmomentstarker-Langsamer-Elektromotor-Wellendurchmesser/dp/B07NY7GJ8F/ref=sr_1_19__mk_de_DE=ÅMÅŽÕÑ&crid=7HDI2RGU49YB&keywords=DC+Motor+12V+getriebe&qid=1641639284&sprefix=dc+motor+12v+getriebe%2Caps%2C72&sr=8-19)|
|4 x AA Batteries |7,15| [amazon](https://www.amazon.de/AmazonBasics-AA-Batterien-Kapazität-wiederaufladbar-vorgeladen-Schwarz/dp/B07NWT6YLD/ref=sr_1_3__mk_de_DE=ÅMÅŽÕÑ&crid=2L9RGNPBIFRLF&keywords=aa%2Bakku&qid=1641639500&s=ce-de&sprefix=aa%2Bakku%2Celectronics%2C81&sr=1-3&th=1)|
|100nF ceramic condensator|| [amazon](https://www.amazon.de/Generic-Stück-100nF-0-1uF-Keramikkondensator/dp/B01LWWKAIB/ref=sr_1_5?crid=20BK1WO5QNVKL&keywords=100nf+keramikkondensator&qid=1641639603&sprefix=100nF%2Caps%2C87&sr=8-5)|
|SPDT slide switch||[amazon](https://www.amazon.de/Sourcingmap-Schiebeschalter-Positionen-einpoliger-Umschalter/dp/B007Q854MS/ref=sr_1_13__mk_de_DE=ÅMÅŽÕÑ&crid=175HBGJSCFUBC&keywords=SPDT+slide+switch&qid=1641639692&sprefix=spdt+slide+switch%2Caps%2C73&sr=8-13)|
|Jumper wires||[amazon](https://www.amazon.de/Female-Female-Male-Female-Male-Male-Steckbrücken-Drahtbrücken-bunt/dp/B01EV70C78/ref=sr_1_1_sspa__mk_de_DE=ÅMÅŽÕÑ&crid=1D3XLIKPKA47I&keywords=jumper+wires&qid=1641639850&sprefix=jumper+wires%2Caps%2C87&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUExNkJXOTVKMjQzUUU3JmVuY3J5cHRlZElkPUEwNDI2MTE3MjVLMk9BSzZOV1YzUCZlbmNyeXB0ZWRBZElkPUExMDAwNjg1MUFSNzFTUlhGM0hSOSZ3aWRnZXROYW1lPXNwX2F0ZiZhY3Rpb249Y2xpY2tSZWRpcmVjdCZkb05vdExvZ0NsaWNrPXRydWU=)|

# Used Parts

## ESP32

Why did I choose the ESP32 as the basis for the project:

 * According to the manufacturer it can be operated from -40 to +125°C and is therefore suitable for all seasons
 * The energy consumption of the ESP32 is very low. This is especially important because I want to run my setup with batteries.
 * It has Wifi and Bluetooth. This can be used in later extensions, for example, to transfer sensor data (eg via MQTT) from the chicken coop.
 * The price for an ESP32 is about 7€.

## L298N Motor Driver

https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.pollin.de%2Fp%2Fjoy-it-motormodul-2-4phasen-l298n-810877&psig=AOvVaw3XxTVklSz12K8HTlJzCb6A&ust=1641726792549000&source=images&cd=vfe&ved=0CAsQjRxqFwoTCPi7r4SDovUCFQAAAAAdAAAAABAF![image](https://user-images.githubusercontent.com/34957612/148641970-c33ab5f8-ea55-4588-92c3-2547fe84ee98.png)

