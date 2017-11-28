# Welcome!

You've reached Albert Gräf's presence on Github. I'm a computer scientist and
mathematician working at the [Johannes Gutenberg University][0] (JGU) at Mainz,
Germany. Here you can find pointers to the source code and documentation of my
functional programming language [Pure][1] (now on Github) and related projects
still mostly hosted on Bitbucket. In particular, there's also some software
for [Faust][5], Grame's functional dsp programming language, [Pd][7], Miller
Puckette's graphical computer music and multimedia environment, and Dave
Robillard's [LV2][11], the new audio and MIDI plugin standard for Linux and
other Unix systems.

Please note that this site is in a perpetual state of construction, and also
serves as a grab bag for various other side projects. I will hopefully turn it
into a full website some time, but for the time being, here's a brief overview
of the available projects.

## The Pure programming language

* The [pure-lang][2] source code repository has the source code of the Pure
  programming language interpreter and various addon modules. In particular,
  there are the [pd-pure](https://agraef.github.io/pure-docs/pd-pure.html) and
  [pd-faust](https://agraef.github.io/pure-docs/pd-faust.html) modules which let
  you run Pure and Faust programs as Pd externals.

* The Pure Language and Library Documentation is available in [html][3] and
  [pdf][4] format.

* [sublime-pure](https://bitbucket.org/agraef/sublime-pure) provides Pure
  language support for the [Sublime Text](http://www.sublimetext.com/) editor.

## The computer music and multimedia corner

* **NEW!** [apcmini-ardour](https://github.com/agraef/apcmini-ardour): These are my Ardour bindings for the [AKAI APCmini](http://www.akaipro.com/products/pad-controllers/apc-mini) controller which turn the APCmini into a useful DAW controller. There's a little [pdf](https://github.com/agraef/apcmini-ardour/blob/master/APCmini-Ardour.pdf) manual available.

* [faust-lv2](https://bitbucket.org/agraef/faust-lv2) is my latest and
  greatest version of the LV2 plugin architecture for the Faust programming
  language. This gives you a convenient way to create LV2 effect and
  instrument plugins from Faust programs.

* [faust-vst](https://bitbucket.org/agraef/faust-vst) is a port of
  faust-lv2 to Steinberg's [VST][19] plugin standard. I recommend using LV2 if
  possible, since it's an open standard. However, none of the commercial DAWs
  seem to implement LV2 (yet), so this architecture gives you a way to run
  your Faust plugins with those programs. Note that to compile the generated
  plugins, you'll also need Steinberg's VST SDK which isn't redistributable,
  so you need to download it yourself; please check the included README file
  for details.

* [osc2midi-utils](https://bitbucket.org/agraef/osc2midi-utils) is a
  collection of utilities to deal with [TouchOSC][12] layouts and
  [osc2midi][20] map files. Currently it offers a converter from TouchOSC
  layouts to osc2midi map files and a graphical frontend to the osc2midi
  program, Spencer Jackson's configurable OSC-(Jack)MIDI bridge written in C.
  Requires Pure, as well as Tcl/Tk and Gnocl.

* The [Pd-L2Ork Arch Package Repository](https://l2orkaur.bitbucket.io/)
  has binary packages for pd-l2ork, purr-data (Jonathan Wilkes' new
  cross-platform variant of pd-l2ork),
  as well as builds of pd-pure and pd-faust for pd-l2ork/purr-data and all
  required dependencies not readily available in the standard Arch
  repositories. There's also an extensive README there with setup
  instructions, list of related AUR packages, etc. Essentially the same set of
  packages is also available for Ubuntu, please check the
  [Pd-L2Ork Ubuntu PPAs](https://l2orkubuntu.bitbucket.io/) page for details.

* **NEW!** [pd-jacktime](https://github.com/agraef/pd-jacktime) is a Pd external written in Lua which provides a basic interface to the Jack transport client API. This lets you sync your Pd patches to Jack time masters such as [Ardour](https://ardour.org/) and [Hydrogen](http://hydrogen-music.org). Requires [pd-lua](https://github.com/agraef/pd-lua) (and [Jack](http://jackaudio.org/), of course).

* [pd-lv2plugin](https://bitbucket.org/agraef/pd-lv2plugin) is an LV2 plugin
  host for Pd, written in Pure. It provides a Pd external `lv2plugin~`
  which lets you run LV2 audio and MIDI plugins in Pd.

* [pd-mdnsbrowser](https://bitbucket.org/agraef/pd-mdnsbrowser) is a
  [Zeroconf](http://en.wikipedia.org/wiki/Zero-configuration_networking)
  external for Pd written in Pure, which lets you discover and publish
  services in the local network, so that your Pd patches can establish network
  connections in an automatic fashion. This is a standalone version of the
  `oscbrowser` object in pd-touchosc (see below), but it isn't limited to OSC
  services, so it can be used for any kind of TCP- or UDP-based service
  running in the local Zeroconf domain.

* [pd-smmf](https://bitbucket.org/agraef/pd-smmf): Documentation and
  examples for the Pd "Simple MIDI Message Format", a symbolic MIDI
  representation in Pd message format. This is used by most of my Pd externals
  using MIDI in some way, but is useful in its own right if you need to pass
  around MIDI data in Pd. Two abstractions midi-input.pd and midi-output.pd
  are included to translate between Pd's built-in MIDI I/O and SMMF. (These
  abstractions are just plain Pd patches which require no additional software
  to work, but the other examples included in the package require pd-pure.)

* [pd-touchosc](https://bitbucket.org/agraef/pd-touchosc) is a TouchOSC MIDI
  bridge written in Pure. This is a collection of Pd externals and patches
  which make it easy to interface Pd to [TouchOSC][12], an OSC and MIDI
  control surface for Android and iOS devices. Please note that this has
  mostly been superseded by Spencer Jackson's osc2midi and my osc2midi-utils
  package (see above).

* [pizmidi](https://bitbucket.org/agraef/pizmidi/) is a comprehensive
  suite of VST MIDI plugins for Linux, Mac OS X and Windows. This is a fork of
  the original source code by Reuben Vinal at [Google Code](https://code.google.com/archive/p/pizmidi/)
  with some minor touches for Linux compatibility. An Arch PKGBUILD is available
  in the [AUR](https://aur.archlinux.org/packages/pizmidi-git/).

* The [Pure LAC09 examples](https://github.com/agraef/pure-lac09) are back! You can also download them as a [tarball](https://github.com/agraef/pure-lac09/archive/1.0.tar.gz) or a [zip archive](https://github.com/agraef/pure-lac09/archive/1.0.zip) again. These are the accompanying materials for my presentation "Signal Processing in the Pure Programming Language" at the Linux Audio Conference 2009 at Parma, with some minor touches for compatibility with present-day Pure. They were originally on Pure's GoogleCode page, but got lost when GC closed its doors. Since the paper and the accompanying materials are still valid and may still be useful for Pure users, they have found a new home on Github now.

* **NEW!** The Purr Data [Github mirror][21] provides a one-stop shop for
  Jonathan Wilkes' new cross-platform variant of Pd-l2ork (a Pd version with a
  much improved GUI and lots of bundled externals).

* [rigkontrol](https://bitbucket.org/agraef/rigkontrol) is a Pd patch
  which translates control signals from Native Instrument's [Guitar Rig Kontrol](http://www.soundonsound.com/sos/sep04/articles/niguitar.htm#2)
  foot switch to MIDI CC. You'll find this patch useful if you have a Rig Kontrol
  device lying around which you want to put to good use by hooking it up to your
  DAW or other MIDI-capable hard- and software. No special externals or addons
  are required, so the patch should work with any Pd flavor out there. Only the
  Rig Kontrol 1 (the original blue one) is supported right now, but adjusting the
  patch to later GR Kontrol versions should be a piece of cake. :)

* [sclsyx](https://bitbucket.org/agraef/sclsyx) is a little Pure script which
  helps you create MIDI Tuning Standard (MTS) sysex or MIDI files from musical
  tunings in Manuel Op de Coul's [Scala](http://www.huygens-fokker.org/scala/)
  format. It can also print the sysex messages in a human-readable format on the
  terminal, from where you can copy and paste the data into DAWs which support
  manual entry of sysex messages. **NEW!** This program is also available as a
  Pd external in the [pd-smmf](https://bitbucket.org/agraef/pd-smmf) package,
  see above.

## Notes

The Faust-related software has been tested and is known to work with both the
stable Faust and the experimental [Faust2][6] version available in the Faust
git repository. The Pd externals have been tested and work with
both [vanilla Pd][8] and with the [pd-extended][9], [pd-l2ork][10]
and [purr-data][21] distributions.

Source tarballs and binary packages for Pure and related projects can be found
on the [Download](https://github.com/agraef/pure-lang/releases) page of
the Pure project.

Users of Arch Linux may want to check out the [Arch User Repositories][13] for
ready-made packages (in particular, you can find the Pure packages
[here](https://aur.archlinux.org/packages/?SeB=m&K=pure-aur&PP=100) and the other
AUR packages that I maintain [here](https://aur.archlinux.org/packages/?SeB=m&K=aggraef&PP=100)).
More details, including pointers to binary package repositories, can be found on
the [Pure on Arch Linux][14] wiki page. Moreover, Arch packages for pd-l2ork et
al can be found in my [Pd-L2Ork Arch Package Repository](https://l2orkaur.bitbucket.io/).

I also maintain a reasonably complete and up-to-date collection of packages
for recent Ubuntu releases on my [Launchpad page][15]. This also offers packages
for Faust, [Pd-L2Ork](https://l2orkubuntu.bitbucket.io/)
and some other dependencies which aren't packaged elsewhere.

Mac OS X users can find Pure on [MacPorts][16]; please check the [Pure on Mac
OS X][17] wiki page for details. We also have binary packages for most of the
other projects available; please check the Download pages of the corresponding
projects for those.

Windows users can find pointers to binary packages for Pure and some of the
addon modules on the [Addons][18] wiki page.

[0]: https://www.uni-mainz.de/eng/index.php
[1]: https://agraef.github.io/pure-lang/
[2]: https://github.com/agraef/pure-lang
[3]: https://agraef.github.io/pure-docs/
[4]: https://agraef.github.io/pure-docs/puredoc.pdf
[5]: http://faust.grame.fr/
[6]: https://github.com/agraef/pure-lang/wiki/Faust2
[7]: http://puredata.info/
[8]: http://puredata.info/downloads/pure-data
[9]: http://puredata.info/downloads/pd-extended
[10]: http://puredata.info/downloads/Pd-L2Ork
[11]: http://lv2plug.in/
[12]: http://hexler.net/software/touchosc
[13]: https://aur.archlinux.org/
[14]: https://github.com/agraef/pure-lang/wiki/ArchPackaging
[15]: https://launchpad.net/~dr-graef
[16]: http://www.macports.org/
[17]: https://github.com/agraef/pure-lang/wiki/PureOnMacOSX
[18]: https://github.com/agraef/pure-lang/wiki/Addons
[19]: http://www.steinberg.net/en/company/developers.html
[20]: https://github.com/ssj71/OSC2MIDI
[21]: https://agraef.github.io/purr-data/
