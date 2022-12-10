## mpy-wpa_supplicant

MicroPython module to connect to the nearest known Wifi AP.


### Install

Install using `mip` e.g. in device REPL

```
>>> import mip
>>> mip.install("github:org/Carglglz/mpy-wpa_supplicant/wpa_supplicant.py")
```

Add a `wpa_supplicant.config` file with `SSID:PASSWORD` of known Wifi APs, e.g.

```
{
    "Wifi-FooAlice":"lH6AFqYWE8Ppwfg8cdeVug",

    "Wifi-BarBob":"I_EnivRDJ2h34CANnEI1Hw",

    "Wifi-GuestRoom":"TXyvzOdXae_nsufOLcJWyw",

}
```

### Usage

To connect add to `main.py`

```py
from wpa_supplicant import setup_network


if setup_network():
    # Now device is connected
    # Set time with ntptime

else:
    # Device is not connected
    # Start its own AP

```

Options for `setup_network(timeout=10, hostname=NAME, notify=True)`:

- `timeout`: In seconds to wait for connection [default: `10`]

- `hostname`: Hostname of the device, [default: `sys.platform-unique_id`, e.g. `esp32-7c9ebd3d9df4`]

- `notify`: To print connection status and ifconfig info [default: `True`] 
