# logitech_pairing_tool
Linux shell pairing tool for Logitech Unifying Receiver

Compile it with with gcc -o pairing_tool pairing_tool.c

To find the device that the receiver has, therefore take a look at the outputs of

  $ ls -l /sys/class/hidraw/hidraw*/device/driver | awk -F/ '/receiver/{print $5}'

This will show the names of your receiver, for example hidraw0.

Now switch off the device that you want to pair (if it was on) and execute your compiled program with the appropriate device as argument:

  $ sudo pairing_tool /dev/hidraw0
  The receiver is ready to pair a new device.
  Switch your device on to pair it (you have thirty seconds to do so).

Now switch on the device you want to pair. After a few seconds your new device should work properly. 
