# Kegberry: Complete Beer Tap Monitoring and Display for Raspberry Pi

You've got a Raspberry Pi and you love beer on tap.  Now what? *Make it a
Kegberry*.

I have made some changes and improvements to the services which includes:
 * No need for the old Android app - enhanced web UI for a real time web UI configured to run in Kiosk mode on the Pi.
 * My deployment expects you to have an Arduino with a Kegboard to hook up the flow and temp sensors, though you may be successful hooking flow sensors directly up to a Pi.
 * Hardware and parts I use:
   * Raspberry Pi 3 B+
   * 7" LCD touch screen with Pi mount to show the web UI in Kiosk mode
   * Arduino Uno with a Kegboard shield, and Kegboard Coaster
   * 2x Swissflow SF-800 flow sensors (I have 2 taps) and 4x John Guest 3/8" Stem OD x 1/4" Hose OD Tube to Hose Stem adapters
   * 1x DS18B20 temperature sensor
   * 3D printed case for the Arduino Uno with Kegboard header

Make sure to use the images from all these repos, as they have several UI changes and stability improvements:
 * [Kegboard](https://github.com/flangelo/kegboard): Firmware and schematics for the Kegbot controller board.
 * [Kegbot-Server](https://github.com/flangelo/kegbot-server): Kegbot main web application and web UI.
 * [Kegbot-Pycore](https://github.com/flangelo/kegbot-pycore): Kegbot core application which allows for communication with the Kegboard interface.

## What can it do?

* **Keg Volume Monitor.** Want to know what's left?  With a little extra
  hardware, your Kegberry becomes a powerful and battle-tested keg monitor.
* **Digital Tap List.**  Give your taps an internet presence.  Kegberry's
  server lets everyone know what's on tap.
* **Notification System.** Want to be alerted when the keg is running low,
  or when someone has started pouring?  No problem; Kegberry does it all.
* **Account System.** Give your friends and family access to your data, and
  enable privacy modes to keep others out.

... and much more.


## What does it cost?

**It's free!** You provide the Raspberry Pi and optional HDMI display,
we give you the software for free.


## Get Started

For a quick start, run our simple install script by pasting the following
command into your Raspbian system:


```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/kegbot/kegberry/master/install.sh)"
```

The installer will guide you through the next steps.


## Help & Next Steps

Have questions, need help, or want to show off your build? Visit the
[Kegbot Project Forum](https://forum.kegbot.org).


## Open Source: Powered by Kegbot

Kegberry is brought to you by the same team that
invented [Kegbot](https://kegbot.org/), the original intelligent Kegerator.

Under the hood, Kegberry is built around
[Kegbot Server](https://github.com/Kegbot/kegbot-server), a mature, heavily
tested keg monitoring and management server.


## License and Copyright

All code is offered under the **MIT** license, unless otherwise noted.  Please
see `LICENSE.txt` for the full license.
