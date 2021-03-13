# Blackbox firmware for the OpenLog

This modified version of [OpenLog 3 Light][] modifies the "CONFIG.TXT" system that is normally used to configure the
OpenLog in order to simplify the available settings and ensure it is compatible with the Blackbox. The only available
setting in CONFIG.TXT is the baud rate, which defaults to 115200.

This is a Fork of the [original OpenLog BlackBox firmware][] adapted to use the libraries SerialPort and SdFat (Version 2) available in 2021 to improve the performance of the OpenLog device used as a BlackBox.

You will find a zip file containing the required libraries, the source-code and the compiled hex file on the "releases" page above.

You'll need to copy the required libraries to your Arduino IDE's library path in order to build this from
source. Copy the inner `libs/SdFat` and `libs/SerialPort` folders to your libraries folder directly.

To flash the firmware to the OpenLog, you can use an FTDI programmer like the [FTDI Basic Breakout][] along with some
way of switching the Tx and Rx pins over (since the OpenLog has them switched) like the [FTDI crossover][] .

If you are using the FTDI USB to TTL cable you must also connect the DTR/RTS pin (green wire in my cable) to the hole labeled "GRN" on the OpenLog.  This is what Arduino uses to cause a reset on the processor so programming can begin.

In the Arduino IDE, choose the "Arduino Uno" as your board and select your serial port (if you use an FTDI cable) or 
your programmer if you're using one. Then click Sketch -> Verify/Compile and File -> Upload (if using FTDI do not choose upload using programmer) to send it to the OpenLog.

Some generic OpenLog boards might not flash if using "Arduino Uno" as your board. Choosing "Arduino Pro or Pro Mini" as your board might solve this problem if you run into it.

[OpenLog 3 Light]: https://github.com/sparkfun/OpenLog/tree/master/firmware/OpenLog_v3_Light
[FTDI Basic Breakout]: https://www.sparkfun.com/products/9716
[FTDI crossover]: https://www.sparkfun.com/products/10660
[1.0.6]: http://arduino.cc/en/Main/Software#toc2
[original OpenLog BlackBox firmware]: https://github.com/cleanflight/blackbox-firmware