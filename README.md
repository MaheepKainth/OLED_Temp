ESP32 OLED Temperature & Humidity Monitor
A standalone sensor display using an ESP32, DHT11, and SSD1306 OLED. Shows live temperature and humidity with a thermometer bitmap icon.

inilib_deps =
  adafruit/Adafruit SSD1306
  adafruit/Adafruit GFX Library
  adafruit/DHT sensor library
  
How It Works 

Reads DHT11 every 2 seconds using non-blocking millis() timing
Renders temperature (°C) and humidity (%) on the OLED alongside a custom thermometer bitmap
Bitmap is stored in flash via PROGMEM to avoid eating into RAM

Setup

Add dependencies to platformio.ini
Flash with PlatformIO

Notes

DHT11 has ~1°C / ~5% RH accuracy — fine for room monitoring
I2C address is 0x3C (standard for most SSD1306 breakouts; change if yours is 0x3D)
Bitmap drawn at offset (-22, -10) to position it partially off-screen on the left
