# Deep sleep

## BMA400

[BMA400](https://www.bosch-sensortec.com/products/motion-sensors/accelerometers/bma400/) is a feature ritch 3-axis accelerometer developed by Bosch. All movement based use cases such as auto deep sleep, step counting, tap-to-wake are based on the features of this IC. It has two interrupt outputs for easy reporting of states to the main IC.

## How to activate

The main way to activate deep sleep is via the BMA 400 accelerometer. After a few seconds of non movement the accelerometer generates an interrupt read by the ESP32 which in turn goes to sleep after setting the [CAM M8C GNSS receiver](https://www.u-blox.com/en/product/cam-m8-series) to sleep and disabling all peripherals.

## How to wake up

The default way the device wakes up is similar to the way it goes to sleep just in reverse. After the BMA400 detects movement it sends another interrupt on a second output. The ESP32 receives it on one of the pins available while in deep sleep.

Another way is to double tap the device.

```{note} Double tapping requires one of the interrupt pins from the BMA400. Therefore it can't be used together with the auto wakeup feature. 

```

## Power Consumption

unsurv offline consumes about 3 mA when in deep sleep while the USB to Serial adapter is switched off via the installed dipswitch. With an installed battery capacity of 250 - 300 mAh we are able to get multiple days of standby time.

```{figure} ./assets/deep_sleep_power.png
:width: 80%
:alt: graph of power measurement

PPK2 measurement over 7 seconds
```

These measurements were taken with the [nrf PPK2](https://www.nordicsemi.com/Products/Development-hardware/Power-Profiler-Kit-2)