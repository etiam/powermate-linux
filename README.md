# PowerMate Linux Driver

This is a small Linux input driver for the [Griffin PowerMate](https://store.griffintechnology.com/desktop/powermate). Tested only on Ubuntu 14.10.


# Disclaimer

PowerMate is a registered trademark of Griffin Technologies Inc. This software is not affiliated or endorsed by them.

This software is written by Stefan Sundin and is licensed under GPLv3.


# Installation

Create a udev rule by creating the file `/etc/udev/rules.d/60-powermate.rules`

```
ACTION=="add", ENV{ID_USB_DRIVER}=="powermate", SYMLINK+="input/powermate", MODE="0666"
```

After creating the file, unplug and plug the PowerMate back in.

Compile the executable with `make`, or download [here](https://github.com/stefansundin/powermate-linux/releases/latest).


# Run

Simply run the executable by running `./powermate`.

Make it run automatically on login somehow. The script should handle the device being disconnected and connected without problems.


# RSS

[![RSS](https://stefansundin.github.io/img/feed.png) Release feed](https://github.com/stefansundin/powermate-linux/releases.atom)


# TODO

- [ ] Change LED brightness depending on volume.
- [ ] Run program from udev rule (causes amixer connect error now).
- [ ] Create deb and ppa.