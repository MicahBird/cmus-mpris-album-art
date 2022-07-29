cmus — C\* Music Player - Fork with Album Art in MPRIS

## All credit goes to @mpostaire and @TorchedSammy for actually making the feature, this is just a tutorial to install it.

https://cmus.github.io/

Copyright © 2004-2008 Timo Hirvonen <tihirvon@gmail.com>

Copyright © 2008-2017 Various Authors


Installing 
----------

## Make sure to **uninstall** any installed versions of cmus to avoid issues!

### Ubuntu Dependencies

Clone the repo and install the following dependencies:
```
sudo apt update
sudo apt-get install -y \
            ffmpeg libao-dev libasound2-dev libavcodec-dev \
            libavformat-dev libswresample-dev libcddb2-dev libcdio-cdda-dev \
            libcue-dev libdiscid-dev libfaad-dev libflac-dev libjack-dev \
            libmad0-dev libmodplug-dev libmpcdec-dev libncursesw5-dev \
            libopusfile-dev libpulse-dev libroar-dev libsamplerate0-dev \
            libsndio-dev libvorbis-dev libwavpack-dev libsystemd-dev pkg-config
```

### Fedora Dependencies

NOTE: This is not all the dependencies, just for building with pulse, mp3, and opus support.

```
sudo dnf -y install ffmpeg libmad-devel ncurses-devel pulseaudio-libs-devel opusfile-devel libsamplerate-devel systemd-devel

```
### Building And Installing

Clone the repo or download the ZIP and run the `configure` script

`./configure`

Then to build run:
```
make -j `nproc`
```
Finally to install run:

`sudo make install`


# Uninstall

To uninstall run:
```
sudo make uninstall
```

_Old cmus README:_

Configuration
-------------

List available optional features

    $ ./configure --help

Auto-detect everything

    $ ./configure

To disable some feature, arts for example, and install to `$HOME` run

    $ ./configure prefix=$HOME CONFIG_ARTS=n

After running configure you can see from the generated `config.mk` file
what features have been configured in (see the `CONFIG_*` options).

*Note*: For some distributions you need to install development versions
of the dependencies.  For example if you want to use 'mad' input plugin
(mp3) you need to install `libmad0-dev` (Debian) or `libmad-devel` (RPM)
package. After installing dependencies you need to run `./configure`
again, of course.

If you want to use the Tremor library as alternative for decoding
Ogg/Vorbis files you have to pass `CONFIG_TREMOR=y` to the configure
script:

    $ ./configure CONFIG_VORBIS=y CONFIG_TREMOR=y

The Tremor library is supposed to be used on hardware that has no FPU.


Manuals
-------

    $ man cmus-tutorial

And

    $ man cmus


Mailing List
------------

To subscribe to cmus-devel@lists.sourceforge.net or view the archive visit
http://lists.sourceforge.net/lists/listinfo/cmus-devel.

The mailing list now serves as an archive for old releases and issues.
Please use the github [issues](https://github.com/cmus/cmus/issues)
page for any problems, suggestions, or bug reports.


Reporting Bugs
--------------

Bugs should be reported using the Github [issue tracker](https://github.com/cmus/cmus/issues).
When creating a new issue, a template will be shown containing instructions on how to collect
the necessary information.

Additional debug information can be found in `~/cmus-debug.txt` if you configured cmus with
maximum debug level (`./configure DEBUG=2`). In case of a crash the last lines may be helpful.


Git Repository
--------------

https://github.com/cmus/cmus

    $ git clone https://github.com/cmus/cmus.git


Hacking
-------

cmus uses the [Linux kernel coding style](https://www.kernel.org/doc/html/latest/process/coding-style.html).
Use hard tabs.  Tabs are _always_ 8 characters wide.  Keep the style consistent with rest of the
code.

Bug fixes and implementations of new features should be suggested as a
[pull request](https://github.com/cmus/cmus/pulls) directly on Github.

