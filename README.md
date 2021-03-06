Raspi.js
==========

[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/nebrius/raspi-io?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Raspi.js provides initialization and base support for the Raspberry Pi. This module, along with [Raspi Board](https://github.com/nebrius/raspi-board) and [Raspi Peripheral](https://github.com/nebrius/raspi-peripheral), provide support for various peripherals on the Raspberry Pi. These libraries form the basis for [Raspi IO](https://github.com/nebrius/raspi-io), an IO plugin that adds support for the Raspberry Pi to [Johnny-Five](https://github.com/rwaldron/johnny-five).

Check out the following peripheral API modules:

* [Raspi GPIO](https://github.com/nebrius/raspi-gpio)
* [Raspi PWM](https://github.com/nebrius/raspi-pwm)
* [Raspi Software PWM](https://github.com/tralves/raspi-soft-pwm)
* [Raspi I2C](https://github.com/nebrius/raspi-i2c)
* [Raspi LED](https://github.com/nebrius/raspi-led)
* [Raspi Serial](https://github.com/nebrius/raspi-serial)

Note: when using this module, the script MUST be called with root permissions.

## Installation

Install with NPM:

```Shell
npm install raspi
```

_Note:_ this module requires [Wiring Pi](http://wiringpi.com/) be installed before installation of this module. Wiring Pi is included by default in the Raspbian OS, but if you want to verify that it is installed, run `gpio` from the command line and make sure the command exists.

**Warning**: this module requires GCC 4.8 or newer. This means that you should be running Raspbian Jessie or newer, released in September of 2015.

Detailed instructions for getting a Raspberry Pi ready for NodeBots, including how to install Node.js, can be found in the [Raspi IO wiki](https://github.com/nebrius/raspi-io/wiki/Getting-a-Raspberry-Pi-ready-for-NodeBots)

## Example Usage

```JavaScript
var raspi = require('raspi');
var gpio = require('raspi-gpio');

raspi.init(function() {
  var input = new gpio.DigitalInput('P1-3');
  var output = new gpio.DigitalOutput('P1-5');
  output.write(input.read());
});
```

## API

### init(cb)

The ```init``` method initializes the library suite. This method MUST be called before using any peripherals.

_Arguments_:

<table>
  <thead>
    <tr>
      <th>Argument</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tr>
    <td>cb</td>
    <td>Function</td>
    <td>Callback to be called once the board has been initialized. Takes no arguments</td>
  </tr>
  <tr>
    <td></td>
    <td colspan="2">
      <table>
        <tr><td>Takes no arguments</td></tr>
      </table>
    </td>
  </tr>
</table>

_Returns_: None

License
=======

The MIT License (MIT)

Copyright (c) 2014 Bryan Hughes <bryan@nebri.us>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
