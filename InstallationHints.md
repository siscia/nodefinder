# Introduction #

Do NOT attempt to build from a checkout from the source code repository: that is for wizards only. Instead, grab one of the released source tarballs from the [downloads](http://code.google.com/p/nodefinder/downloads/list) tab.

The released source tarballs build via ` ./configure; make; make install `.  The default prefix is `/usr` (not `/usr/local`) so if you don't like that use the `--prefix` option to configure.  You can test before installing with `make check`.

You should build and install `nodefinder` and `ec2nodefinder` before building `combonodefinder`, if you want `make check` to work for `combonodefinder`.