# ns2nam-mac-silicon

Thanks to Tom Henderson (see this document [(https://www.nsnam.org/~tomh/ns-2-mac-m1-instructions.pdf)]) I managed to get ns2 running on the M2 Pro.
The guide is great. But, given it forgets to fix some Makefiles after the renaming that happens at Step 4. The renaming is done, in Step 5., as a part of the patch, only to the `Makefile.in` that is in the `ns-2.36` directory. This allows building ns-2.36, but needs to be fixed in the other `Makefile.in`s as well, especially if we want to get `nam` running. 

First you will need to get `XQuartz` [(https://www.xquartz.org)] to run `nam`.
Then to install run: `./install`.
Add don't forget to add `ns` and `nam` to your `$PATH`.

This repository has the changes indicated by Tom Henderson.
Instead of running `./configure LIBS="-framework CoreFoundation"` inside the `ns-2.36` directory, I modified the `install` file. This way, running `./install` builds and installs everything.

So the only things that change (on top of the other steps): finish renaming VERSION to VERSION.txt in the other `Makefile.in`s + add `LIBS="-framework CoreFoundation"` to the `install` file.

If you want to do everything by yourself, here is the initial source code: [(https://www.nsnam.org/release/ns-2/ns-allinone-2.36.rc2.tar.gz)].


## The original README

1. Introduction
----------------

Ns-allinone is a package which contains required components and some of
optional components used in running ns. The package contains an
"install" script to automatically configure, compile and install these
components. If you haven't installed ns before and want to quickly try
ns out, ns-allinone may be easier than getting all the pieces by hand.
 
Currently the package contains:
  
- Tcl       Tcl release 8.5.8    (required component)
- Tk        Tk release 8.5.8     (required component)
- Otcl      otcl release 1.14    (required component)
- TclCL     tclcl release 1.20  (required component)
- Ns        ns release 2.35    (required component)
- Nam       Nam release 1.14       (optional component)
- Xgraph    xgraph version 12     (optional component)
- GT-ITM    Georgia Tech Internetwork
            Topology Modeler      (optional component)
- SGB       Stanford GraphBase
            package               (optional component)
- CWEB      CWeb version 1.0 (?)  (optional component)
- ZLib      zlib version 1.2.3    (optional component) 

2. FEATURES IN ns-allinone-2.35
-------------------------------

Features in this version include:

- Update to Tcl/Tk 8.5 series (becoming the default Tcl/Tk version on
  many platforms)

- Update for Cygwin-1.7.1 release for Windows

- New features for ns-2.35 release (see the ns-2/CHANGES.html file)

3. Installing the package
--------------------------

All you need to do is type "./install" under this directory. The install
script will compile and install the whole package for you. The script also
will tell you the final installation result.


4. More information
--------------------

Ns-allinone is available from
<http://sourceforge.net/projects/nsnam>
or
<http://www.isi.edu/nsnam/ns/ns-build.html>

-----------------------------
The nsnam Project
http://www.nsnam.org

