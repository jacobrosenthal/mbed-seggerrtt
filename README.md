Segger-RTT
----------
[Segger's RTT serial debugger files](https://www.segger.com/jlink-rtt.html)

See their documentation for details, but generally speaking include 
```
#include "seggerrtt/SEGGER_RTT.h"
```
then use
```
    SEGGER_RTT_printf(0, "pumpkins: %d\r\n", somevariable);
```
Probably a way to fix printf upstream somewhere, but can map it locally like:
```
#define printf(...)                      SEGGER_RTT_printf(0, __VA_ARGS__)
```

Then start your gdbserver and `telnet localhost 19021` to see the output