# ESP32 Pool Temperature Sensor

## Objective:
Collect pool water temperature data and report to the local Home Assistant server.

## Requirements:
  1. The sensor shall use an ESP32 microcontroller.
  2. The sensor shall be battery powered.
  3. The sensor shall be capable of being powered by and also recharge the battery using an external USB-C connector.
  4. The sensor shall connect to the local wifi network and be capable of accepting over-the-air (OTA) programming.
  5. The sensor shall communicate status via MQTT protocols.  
  6. The sensor shall be capable of operating in a power conservation mode.
  7. The sensor shall collect water temperature readings at least 6 inches below the water surface.
  8. The sensor shall be located close to the pool surface and be waterproof to at least the [IP67 standard](https://www.test-and-measurement-world.com/terminology/understanding-ip-ratings.html).
  9. The sensor shall report the internal enclosure temperature and humidity values to monitor the operating environment.

## Design Considerations:
  - The sensor enclosure must be waterproof, so any pass-through cabling (water temp probe, USB-C socket) must also be waterproof.
  - Running on battery power will require hardware battery management.
  - Since there will not be any external display to indicate battery status, include battery voltage monitoring and reporting to Home Assistant.
  - The sensor software shoud use ESPHome integration, but it can be written with the ESPHome integration or in C with the appropriate libraries.
  - If there are multiple modules inside the enclosure, they can/should be hard-wired (soldered), but any connections to external I/O should use some kind of mechanical connection such as JST connectors. A good example is the externally mounted USB-C connector. It would put undue mechanical strain on the ESP32 USB connector to directly expose it outside the case. So we'll use a case-mounted USB-C socket and cable it internally to the ESP32 board.
  
## Bill of Materials (BOM):

  |  Part         | Qty  |  Source       |
  | ------------- | :--: | ------------- |
  | IP67 Outdoor Waterproof Case     |   1  | [AliExpress](https://www.aliexpress.us/item/3256803233842364.html)    |
  | DS18B20 Temperature Sensor Module Kit |  1 | [AliExpress](https://www.aliexpress.us/item/3256801415671848.html) |
  | 3.7V Lipo Battery 3000Mah |  1  | [AliExpress](https://www.aliexpress.us/item/3256808535461122.html) |
  | DHT22 Temperature and Humidity Module |  1  |  [AliExpress](https://www.aliexpress.us/item/3256808286437674.html) |
  | ESP32 ProS3[D]  |  1  |  [Unexpected Maker](https://unexpectedmaker.com/shop.html#!/ProS3-D/p/759221737)  |
  | IP68 Cable Gland  |  1  |  [AliExpress](https://www.aliexpress.us/item/3256803660219611.html)  |
  | IP68 Type C USB Female Connector  |  1  |  [AliExpress](https://www.aliexpress.us/item/3256807296295711.html)  |
  | 10K Ohm Resistor  |  1  |  |
   
