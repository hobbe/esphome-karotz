# ESPHome - Karotz

> Replace the motherboard of your Karotz/Nabaztag with an ESP and play with the hardware.

Just play with old Nabaztag. Ears, head button, speaker, wheel and probably the input power can be reused easily.
The microphone is an electret microphone, it's way easier to replace it by an i2s one.

Original idea by [bemble (esphome-nabaztag)](https://github.com/bemble/esphome-nabaztag)

## Hardware

### Components

- Nabaztag v1/v2 or Karotz but the connectors are different (smaller on the Karotz)
- ESP32 ([ESP32 Dev Kit C](https://www.amazon.fr/gp/product/B074RG86SR?&_encoding=UTF8&tag=bemble-21&linkCode=ur2&linkId=e3e6b2688822db2bd779a096dffda58b&camp=1642&creative=6746))
- [INMP441 microphone](https://www.amazon.fr/dp/B07YXF6ZV2?&_encoding=UTF8&tag=bemble-21&linkCode=ur2&linkId=980b291099807d8eb12a9ffb818c0274&camp=1642&creative=6746)
- [MAX98357 DAC](https://www.amazon.fr/dp/B08BCHHZPN?&_encoding=UTF8&tag=bemble-21&linkCode=ur2&linkId=65fe38accd229f9937d377b7f792373c&camp=1642&creative=6746)
- RGB LED

### Pinout

| ESP32 | Component |
|---|---|
| GPIO4 | RGB - R |
| GPIO14 | INMP441 SCK |
| GPIO18 | MAX98357 LRC |
| GPIO19 | MAX98357 BCLK |
| GPIO21 | MAX98357 DIN |
| GPIO22 | Left ear (+) |
| GPIO23 | Right ear (+) |
| GPIO25 | Head button (+) |
| GPIO26 | INMP441 SD |
| GPIO27 | INMP441 WS |
| GPIO32 | RGB - G |
| GPIO33 | RGB - B |
| GND | INMP441 GND |
| GND | INMP441 L/R |
| GND | MAX98357 GND |
| GND | Head button (-) |
| GND | Left ear (-) |
| GND | Right ear (-) |
| GND | RGB - GND |
| 3v3 | INMP441 VDD |
| 3v3 | MAX98357 VDD |

## Configuration

```yaml
substitutions:
  name: "espkarotz"
  friendly_name: "Karotz"
  wifi_ap_password: ap_password

packages:
  Violet.Karotz: github://hobbe/esphome-karotz/violet-nabaztag-tag.yaml@karotz

esphome:
```

## TODO

- [ ] add photos, schema etc
- [ ] use ears encoder instead of basic time based rotation
- [ ] use a led ring
- [ ] add an optional OLED screen
- [ ] use the wheel to manager leds max brightness (or something else, to be defined)
- [ ] make a PCB (⚠️ Nabaztag and Karotz have different connectors)

## Resources

- [Hack the Nabaztag](https://www.instructables.com/Hack-the-Nabaztag/)
- [Tagtagtag ears encoder](https://github.com/pguyot/tagtagtag-ears)
- [TEARDOWN: NABAZTAG](https://hackaday.com/2020/05/26/teardown-nabaztag/)
