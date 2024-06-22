FDLog = Field Day Logging Program                Copyright 1984-2023 Alan W6AKB
www.FDLog.us                www.AntennaLaunchers.com              www.HSFDG.org

FDLOG is distributed under the GNU V2 1991 Public License

Revision: 1.27 3/28/2023

  This program is designed to support Amateur Radio Field Day Operations by 
providing a robust multiplatform networked distributed logging database and
information service. It also has features for VHF contest logging.


Introduction

  This is a complete rewrite of W6AKB/WB6ZQZ's Field Day Logging program.
It is nearly 20 years old (as of this rewrite in 2002), but the new Python
version has many new features, primary of which is the ability to synchronize 
the logfile database across a network in a peer to peer fashion, avoiding 
single points of failure. The expectation is that a wireless network is used.

  To run this program (in 2023) you will need to install Python 3. This version 
has been developed with Python 3.10 but should run on somewhat earlier (and later) 
versions of Python 3, and it also runs on Linux (including Raspberry Pi) and 
the Mac. Python is available from www.python.org. Either 32 or 64 bit versions
should be adequate.

  If you want the audio output (beeps) you will need to load the optional pyaudio
library. This is generally done with "pip install pyaudio" from a command line.
Get a command window with Windows-R / cmd <return>. Navigate to the Scripts 
directory for the version of Python you have installed and run pip from there. 
The directory on windoze is something like:
c:/users/<user>/appdata/local/programs/python/pythonVER/scripts.
You can use cd <dir> to move through the directories one at a time and dir
to find your way.

  Networking is required to use the data sync features of the program. A
UDP broadcast is used, so stations on the same subnet running the program will
sync databases.  An authentication code is used, so only stations with the
same auth code will be able to share data. There is a remote TCP capability
as well which is useful for testing, training, or remote operation.

  Setting up ad-hoc or peer-to-peer 802.11 networking is beyond the scope of this 
note. This should be done prior to running the logging software. Note that each
station does need a distinct hostname for proper database synchronization. See
the separate note on wireless networking.

  The computer's clock accuracy is important, so set it before starting the log 
program. This will reduce the amount of correction the internal time sync has
to compensate for. Designate one accurate and stable computer as the master 
timekeeper (and set this in FDLog). Then all program time clocks will track 
that one. Using NTP across the site to synchronize computers is an excellent 
plan especially with digital modes that rely on the time sync. We use Meinberg
NTP client on Windows boxes, and other programs are available to set the system
time. We use several GPS based NTP servers to provide reliable time at our 
off-network remote Field Day site.

  Getting the latest version of the program on Field Day at our site is 
handled by a small web server on one of the NTP servers, or by passing
a USB flash drive around (but it is even better to pre-load it ahead of time). 
Other files like Python and FD rules can be handled in similar fashion.

  Installing the FDLog program is straightforward - all that is needed is a
directory with the files in it. The program will create database and log files
in this directory. Unpack the zipfile in the directory you have chosen.

Viewing pdf files requires some type of pdf reader to be installed in the system.

  The FDLOG program is launched by double-clicking on the fdlog3.py icon in the 
directory. For convenience you may want to create a shortcut on the desktop.

  When FDLog comes up it presents a text window and a small dialog box. The text
window is used for diagnostic and status information. I usually situate it so I 
can see the bottom 5-10 lines or so and cover it with the main FDLog window to 
save screen space.

  The initial dialog box shows the FDLog version and allows selection of contest
either FD or VHF. It shows the Host name and allows the user to set the Node ID.
Each node must have a unique ID which defaults to part of the host name. Something
that others can recognize is best, perhaps your callsign or initials. Next is the
Network Selection. This is usually fine at default, but if a machine has more
than one network, such as a VPN this can be used to select the one FDLog should
use. Once these settings are made click the Run FDLog button to continue into the 
main program.

  Visit the FDLog help menu 'Help/Getting Started' for further instructions.

  More complete information is in the manual contained in file fdlogman.txt, and
this and other documentation and help files are available in FDLog under the Help 
and Docs menus.

Alan Biocca, W6AKB at ARRL.net

eof
