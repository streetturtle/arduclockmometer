# arduclockmometer

Clock and thermometer based on arduino and max7219 led panel

## Dependencies / Libraries

 - [MD_Parola](https://github.com/MajicDesigns/MD_Parola)
 - [MD_MAX72XX](https://github.com/MajicDesigns/MD_MAX72XX)
 - [DS3231](https://github.com/NorthernWidget/DS3231)
 - [Adafruit Sensor](https://github.com/adafruit/Adafruit_Sensor)
 - [DHT](https://github.com/adafruit/DHT-sensor-library)

Could be installed by **Tools** -> **Manage Libraries** and then search by name, or by downloading .zip from github and unzipping inside arduino's libraries folder.

## More sprites

Space invader:

```cpp
const uint8_t F_INVADER = 2;
const uint8_t W_INVADER = 12;
static const uint8_t PROGMEM invader[F_INVADER * W_INVADER] =
{
  0x00, 0x70, 0x10, 0x7d, 0xb6, 0x3c, 0x3c, 0xb6, 0x7d, 0x10, 0x70, 0x00,
  0x00, 0x1c, 0x28, 0x7d, 0x36, 0x3c, 0x3c, 0x36, 0x7d, 0x28, 0x1c, 0x00
};
```

Mushroom:

```cpp
const uint8_t F_MUSHROOM = 2;
const uint8_t W_MUSHROOM = 11;
static const uint8_t PROGMEM mushroom[F_MUSHROOM * W_MUSHROOM] =
{
  0x00, 0x1c, 0x62, 0x91, 0xb1, 0x91, 0xb1, 0x91, 0x62, 0x1c, 0x00,
  0x00, 0x1c, 0x62, 0x91, 0x91, 0x91, 0x91, 0x91, 0x62, 0x1c, 0x00
};
```

## Troubleshooting

 - Text seems to be reversed and blocks independent.
 Change `HARDWARE_TYPE` variable to `FC16_HW` as MAX7219 is of this type:

```cpp
#define HARDWARE_TYPE MD_MAX72XX::FC16_HW
```

 - Permission denied when uploading sketch:

```bash
avrdude: ser_open(): can't open device "/dev/ttyUSB0": Permission denied
Problem uploading to board.  See http://www.arduino.cc/en/Guide/Troubleshooting#upload for suggestions.
```

Solution: `sudo chmod a+rw /dev/ttyUSB0`
