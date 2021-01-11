# ralt2hyper

Remap Right Alt (commonly AltGr) to Hyper (i.e. Control, Alt and Super).

This is an [Interception Tools](https://gitlab.com/interception/linux/tools)
plugin that sucks up all Right Alt key presses and remaps them to a combination
of Control, Alt and Super. Works globally, no requirement of X11 or any
graphics.

## Background

I use a combination of Control, Alt and Super as my window manager's "mod key".
This means that manipulating windows requires these three keys to be held at the
same time - quite a difficult feat! Most of the time I'm using an external USB
keyboard that allows custom firmware so I have a single key which acts as all
three; no problems.

However, I like to be able to use my laptop's integrated keyboard sometimes and
on that I cannot load custom firmware. Thankfully, [Francisco Lopes](https://gitlab.com/oblitum)
has developed their [Interception Tools](https://gitlab.com/interception/linux/tools)
toolkit. This is a plugin for _Interception Tools_ to perform the task.

_Interception Tools_ works everywhere without relying on X11 or Wayland.

## Install

Binaries are currently published on the
[Package Registry](https://gitlab.com/oarmstrong/ralt2hyper/-/packages) for
this project. The binaries are compiled for 64-bit Linux and only require
`glibc`.

## Usage

`ralt2hyper` is an [Interception Tools](https://gitlab.com/interception/linux/tools)
plugin. Refer to that project's README for information on installation and
usage. An example `udevmon` configuration:

``` yaml
- JOB: "intercept -g $DEVNODE | caps2esc -m 1 | ralt2hyper | uinput -d $DEVNODE"
  DEVICE:
    LINK: /dev/input/by-path/platform-i8042-serio-0-event-kbd
```

## Maintainers

- [@oarmstrong](https://gitlab.com/oarmstrong)

## Thanks

This plugin wouldn't exist without [Francisco Lopes](https://gitlab.com/oblitum)
and their [Interception Tools](https://gitlab.com/interception/linux/tools)
project. I also heavily leaned on
[`caps2esc`](https://gitlab.com/interception/linux/plugins/caps2esc) as a sample
codebase. Thanks, Francisco!!

## Contributing

Please feel free to submit
[issues](https://gitlab.com/oarmstrong/ralt2hyper/-/issues/new) for any bugs or
feature requests. MRs with improvements are always welcome too!

Alternatively you may contact `ollie@armstrong.io` if you'd prefer.

Contributor guidelines are simply: don't be a dick. This project is welcoming
of contributions from anyone, quality of code is the only thing to be judged or
criticised. Personal comments of any kind are not relevant.

## License

MIT License.

```
Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
