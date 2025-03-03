# Eurorack Cards

Yet un-named informal standard for USB and microcontroller oriented cards, using the eurorack form factor (but not the same power supply).

## The "standard"

![connector](./assets/connector.jpg)

Most of the "standard" here is the connector used on the boards. It's a 0.1" pitch 2x6 IDC connector. The picture above is taken looking at the BACK of the board.

The pins are:

| Use           | Pin   | Pin | Use             |
| :--           | :--   | --: | --:             |
| +20v power    | 1     |   2 |          Ground |
| +20v power    | 3     |   4 |          Ground |
| +5v0 power    | 5     |   6 |          Ground |
| +5v0 power    | 7     |   8 |          Ground |
| USB FS/HS D+  | 9     |  10 |    USB FS/HS D- |
| Ground        | 11    |  12 |          Common |

### "+20v power"

This is intended to be supplied by USB-PD, so it should be expected this rail can be any voltage 5v0 to 20v0 max. This rail is expected to have more wattage available than the +5v0 power rail. You may need a variable input DC/DC that can handle this.

### "+5v0 power"

This is a 5-volt-ish rail. Probably something in the tolerance of regular USB 5v, so +/- 0.25v. You can use this exclusively, but current may be shared with many other boards. If you need to do something high current, do it from the +20v power rail.

### "USB FS/HS D+/D-"

This is the normal differential pair used by USB Full Speed or USB High Speed.

### "Common"

This isn't super well defined, but it is intended as a low frequency, open-drain, interface, usable for clock sync or trigger. TBD who provides the pullup, maybe all boards on the order of 10k-50k (i.e. internal MCU pullups).

## `boards/` folder

These are board designs that are compatible with this "standard".

Feel free to open a PR. KICAD designs preferred.

## License

idk something like cc-by-sa-nc?


