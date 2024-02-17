# homepage2ctrlq

Remap Homepage to Control Q to close apps.

This is an [Interception Tools](https://gitlab.com/interception/linux/tools)
plugin that sucks up all Homepage key presses and remaps them to a combination
of Control Q. Works globally, no requirement of X11 or any
graphics.

## Install

Binaries are not currently provided. Compile and place within `$PATH`.

``` shell
$ cmake -B build -DCMAKE_BUILD_TYPE=Release
-- The C compiler identification is GNU 10.2.0
-- The CXX compiler identification is GNU 10.2.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done
-- Generating done
-- Build files have been written to: /home/user/proj/homepage2ctrlq/build
$ make -C build
make: Entering directory '/home/user/proj/homepage2ctrlq/build'
make[1]: Entering directory '/home/user/proj/homepage2ctrlq/build'
make[2]: Entering directory '/home/user/proj/homepage2ctrlq/build'
Scanning dependencies of target homepage2ctrlq
make[2]: Leaving directory '/home/user/proj/homepage2ctrlq/build'
make[2]: Entering directory '/home/user/proj/homepage2ctrlq/build'
[ 50%] Building C object CMakeFiles/homepage2ctrlq.dir/homepage2ctrlq.c.o
[100%] Linking C executable homepage2ctrlq
make[2]: Leaving directory '/home/user/proj/homepage2ctrlq/build'
[100%] Built target homepage2ctrlq
make[1]: Leaving directory '/home/user/proj/homepage2ctrlq/build'
make: Leaving directory '/home/user/proj/homepage2ctrlq/build'
```

## Usage

`homepage2ctrlq` is an [Interception Tools](https://gitlab.com/interception/linux/tools)
plugin. Refer to that project's README for information on installation and
usage. An example `udevmon` configuration:

``` yaml
- JOB: "intercept -g $DEVNODE | homepage2ctrlq | uinput -d $DEVNODE"
  DEVICE:
    EVENTS:
      EV_KEY: [KEY_HOMEPAGE]
```
