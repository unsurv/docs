# NFC_temp

NFC_temp developed out of studying the [RF430 NFC IC](https://www.ti.com/product/RF430CL330H) documents I found a passive thermometer example design based completely (of course) on TI components. I based my design on AVRs ATtiny series and after some tries with analog thermometers decided on the [TMP117](https://www.ti.com/product/TMP117) digital thermometer.

With the massive help of [SpenceKonde's ATTinyCore](https://github.com/SpenceKonde/ATTinyCore) library and its great documentation I managed to make the NFC_temp work within the Arduino IDE and the UPDI protocol for programming.

The device is powered by the NFC reader's RF field and provides just enough power to boot the ATTiny1626 in 1 MHz mode to read the temperature and write the result to the RF430's flash.

## General Info

### Main Parts

- ATTiny 1626
- RF430CL330H
- TMP117

## Tutorial

### Android

On some Android devices just holding the phone to the device presents the content in a notification. If not the case, check if your phone has a NFC enable setting and/or download [NFC Tools](https://play.google.com/store/apps/details?id=com.wakdev.wdnfc) from the playstore.

Here is a [Video](https://vimeo.com/928739952)

### iOS

I suspect Apple has tuned their NFC reader antenna to work best when angling the front downwards.
For iOS I recommend [GoToTags](https://apps.apple.com/us/app/gototags/id1271508009).

[Video demo](https://vimeo.com/928731813) to show the different angle needed.
