# ns2nam-mac-silicon

Thanks to Tom Henderson (see this document [(https://www.nsnam.org/~tomh/ns-2-mac-m1-instructions.pdf)]) I managed to get ns2 running on the M2 Pro.
The guide is great. But, given it forgets to fix some Makefiles after the renaming that happens at Step 4. The renaming is done, in Step 5., as a part of the patch, only to the `Makefile.in` that is in the `ns-2.36` directory. This allows building ns-2.36, but needs to be fixed in the other `Makefile.in`s as well, especially if we want to get `nam` running. 

First you will need to get `XQuartz` [(https://www.xquartz.org)] to run `nam`.
Then to install: './install'.
Add don't forget to add `ns` and `nam` to your `$PATH`.

This repository has the changes indicated by Tom Henderson.
Instead of running `./configure LIBS="-framework CoreFoundation"` inside the `ns-2.36` directory, I modified the `install` file. This way, running `./install` builds and installs everything.

So the only things that change (on top of the other steps): finish renaming VERSION to VERSION.txt in the other `Makefile.in`s + add `LIBS="-framework CoreFoundation"` to the `install` file.

If you want to do everything by yourself, here is the initial source code: [(https://www.nsnam.org/release/ns-2/ns-allinone-2.36.rc2.tar.gz)].
