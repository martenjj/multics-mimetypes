Multics MIME Types
==================

This small package installs MIME types and file icons for Multics
source code and archive files.  When browsing local directories or FTP
archives, applicable files will be shown with a distinctive icon and
can be configured to open appropriately.

It has been developed and tested using KDE, but the installed MIME
type data and icons follow the freedesktop.org standard and so in
theory should be usable under GNOME or any other desktop or file
manager that supports that standard.

What to do when the files are opened is determined by the file manager
or desktop environment configuration, and is not set by this package.
By default, source files should be opened in a text editor or viewer
(because of the freedesktop rule for text/*).  Archive files require
an file manager or archive reader that understands the Multics format,
see http://github.com/martenjj/multics-archive-kio for a plugin that
allows them to be browsed using Konqueror or Dolphin.

The package and all the files contained in it is licensed under the
GNU GPL V3+; see the file LICENSE for more information.


Building and installing
-----------------------

This package does not require a full KDE installation, but only the
extra-cmake-modules component of that.  CMake is required for
building; Qt is not required either for building or at runtime.

Assuming that you have these installed or already provided by your
distro, go to a suitable build location (e.g. your home directory) and
do:

     git clone https://github.com/martenjj/multics-mimetypes.git
     cd multics-mimetypes
     mkdir build
     cd build
     cmake ..
     make
     sudo make install


Running
-------

No configuration or setup is required.  Simply use whatever file
manager you prefer, and the icons should appear for appropriate
Multics file types.


Problems?
---------

Please raise an issue on GitHub (at
http://github.com/martenjj/multics-mimetypes) if there are any
problems with installing or using this package, in particular if there
are any incompatibilities with other desktop environments or file
managers apart from KDE.

I'm not a talented icon artist, so any design improvements or new
icons to match other themes would also be most appreciated!


Thanks for your interest!
-------------------------

Jonathan Marten, http://github.com/martenjj
