Cairo - Multi-platform 2D graphics library
https://cairographics.org

What is cairo
=============
Cairo is a 2D graphics library with support for multiple output
devices. Currently supported output targets include the X Window
System (via both Xlib and XCB), quartz, win32, and image buffers,
as well as PDF, PostScript, and SVG file output. Experimental backends
include OpenGL.

Cairo is designed to produce consistent output on all output media
while taking advantage of display hardware acceleration when available
(for example, through the X Render Extension).

The cairo API provides operations similar to the drawing operators of
PostScript and PDF. Operations in cairo include stroking and filling
cubic Bézier splines, transforming and compositing translucent images,
and antialiased text rendering. All drawing operations can be
transformed by any affine transformation (scale, rotation, shear,
etc.).

Cairo has been designed to let you draw anything you want in a modern
2D graphical user interface.  At the same time, the cairo API has been
designed to be as fun and easy to learn as possible. If you're not
having fun while programming with cairo, then we have failed
somewhere---let us know and we'll try to fix it next time around.

Cairo is free software and is available to be redistributed and/or
modified under the terms of either the GNU Lesser General Public
License (LGPL) version 2.1 or the Mozilla Public License (MPL) version
1.1.

Where to get more information about cairo
=========================================
The primary source of information about cairo is:

	https://cairographics.org/

The latest versions of cairo can always be found at:

	https://cairographics.org/download

Documentation on using cairo and frequently-asked questions:

	https://cairographics.org/documentation
	https://cairographics.org/FAQ

Mailing lists for contacting cairo users and developers:

	https://cairographics.org/lists

Roadmap and unscheduled things to do, (please feel free to help out):

	https://cairographics.org/roadmap
	https://cairographics.org/todo

Dependencies
============
The set of libraries needed to compile cairo depends on which backends
are enabled when cairo is configured. So look at the list below to
determine which dependencies are needed for the backends of interest.

For the surface backends, we have both "supported" and "experimental"
backends. Further, the supported backends can be divided into the
"standard" backends which can be easily built on any platform, and the
"platform" backends which depend on some underlying platform-specific
system, (such as the X Window System or some other window system).

As an example, for a standard Linux build similar to what's shipped by
your distro, (with image, png, pdf, PostScript, svg, and xlib surface
backends, and the freetype font backend), the following sample commands
will install necessary dependencies:

    Debian (and similar):

	apt-get build-dep cairo

    Fedora (and similar):

	yum install libpng-devel zlib-devel libXrender-devel fontconfig-devel

Technically you probably don't need pixman from the distribution since
if you're manually compiling Cairo you probably want an updated pixman
as well.  However, if you follow the default settings and install pixman
to /usr/local, your Cairo build should properly use it in preference to
the system pixman.


Supported, "standard" surface backends
------------------------------------
	image backend (required)
	------------------------
	pixman >= 0.30.0	https://cairographics.org/releases

	png support (can be left out if desired, but many
	-----------  applications expect it to be present)
	libpng			http://www.libpng.org/pub/png/libpng.html

	pdf backend
	-----------
	zlib			http://www.gzip.org/zlib

	postscript backend
	------------------
	zlib			http://www.gzip.org/zlib

	svg backend
	-----------
	[none]

Supported, "platform" surface backends
-----------------------------------
	xlib backend
	------------
	X11			https://freedesktop.org/Software/xlibs

	xlib-xrender backend
	--------------------
	Xrender >= 0.6		https://freedesktop.org/Software/xlibs

	quartz backend
	--------------
	MacOS X >= 10.4 with Xcode >= 2.5

	win32 backend
	-------------
	Microsoft Windows 2000 or newer[*].

	xcb backend
	-----------
	XCB			https://xcb.freedesktop.org

Font backends (required to have at least one)
---------------------------------------------
	freetype font backend
	---------------------
	freetype >= 2.1.9	http://freetype.org
	fontconfig		http://fontconfig.org

	quartz-font backend
	-------------------
	MacOS X >= 10.4 with Xcode >= 2.4

	win32 font backend
	------------------
	Microsoft Windows 2000 or newer[*].

	[*] The Win32 backend should work on Windows 2000 and newer
	    (excluding Windows Me.) Most testing has been done on
	    Windows XP. While some portions of the code have been
	    adapted to work on older versions of Windows, considerable
	    work still needs to be done to get cairo running in those
	    environments.

	    Cairo can be compiled on Windows with either the gcc
	    toolchain (see http://www.mingw.org) or with Microsoft
	    Visual C++.  If the gcc toolchain is used, the standard
	    build instructions using configure apply, (see INSTALL).
	    If Visual C++ is desired, GNU make is required and
	    Makefile.win32 can be used via 'make -f Makefile.win32'.
	    The compiler, include paths, and library paths must be set
	    up correctly in the environment.

	    MSVC versions earlier than 7.1 are known to miscompile
	    parts of cairo and pixman, and so should be avoided. MSVC
	    7.1 or later, including the free Microsoft Visual Studio
	    Express editions, produce correct code.


Compiling
=========
See the INSTALL document for build instructions.


History
=======
Cairo was originally developed by Carl Worth <cworth@cworth.org> and
Keith Packard <keithp@keithp.com>. Many thanks are due to Lyle Ramshaw
without whose patient help our ignorance would be much more apparent.

Since the original development, many more people have contributed to
cairo. See the AUTHORS files for as complete a list as we've been able
to compile so far.