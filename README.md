# hxserial

**hxserial** is a library for serial communication in [Haxe](http://haxe.org) (C++/Neko target). It is based on ofSerial in [OpenFrameworks](http://www.openframeworks.cc/).
## this fork changes the library to an all lowercase name to fix the library not loading on haxe 4 and recent haxelib

## Download and Install

You can download/checkout the source from [the github repo](http://github.com/werkplaatsenpabobreda/hxserial).  

Rebuild the library with 
``` 
lime rebuild ./ platform
```
(substitute `platform` with the name of your platform)



The original library by Andy Li can be found at [http://github.com/andyli/hxSerial](http://github.com/andyli/hxSerial).
## How to use

Create a `Serial` object, given its device name and speed (in bits per second, ie.baud):

```haxe
var serialObj = new hxSerial.Serial("/dev/tty.usbserial-A4001tkb",9600);
```

The device name above is something you will get in Mac. For Windows, it should be something like "COM7". For Linux (e.g. Ubuntu), it should be similar to "/dev/ttyUSB0".

You can check the device names by `trace(hxSerial.Serial.getDeviceList())`.

You can then read/write to the device using the `readByte`/`writeByte` method.

*Note that you must read from the serial after setup. If the serial input is accumulated for too long, it will slow down the whole system.*

### Writing

For writing, `writeByte()` returns `true` if the operation is successful. `writeBytes()` returns the number of bytes it writes.

### Reading

For reading, you first check the number of bytes arrived by calling `available()`. If the amount of bytes you needed is enough, call `readByte()` to get a single byte as `Int` or call `readBytes()` to get multiple bytes as `String`.

## change log


### version 0.1.3

Changes libraryname to an all lowercase to fix library not loading.

### version 0.1.2

Fixes for haxe 3.1.3 and hxcpp 3.1.39.

### version 0.1.1

Fixed memory leak and added Neko support.

### version 0.1.0

First release. Supports Windows/Mac/Linux.
