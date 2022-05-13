# King of Fighters XIII Steam Edition Hitbox Viewer

## Readme
Source repository: https://github.com/odabugs/kof13-hitboxes
Developer contact: pdk.odabugs@gmail.com
This document was last edited on July 2, 2014

THIS VIEWER IS STILL IN VERY EARLY DEVELOPMENT.
Many thing may still be broken, and there may still be mistakes. We're hard
at work to make the viewer more user-friendly, but working correctly is our
highest priority.

This readme document is currently "to be written" in a future commit to this
project.  For now, please refer instead to INSTALL.txt for installation and
startup instructions.

Special thanks to Phoenix for testing, feature suggestions, compiling data
essential for proper discerning of hitbox types, and for fielding user
support.

## Installation guide
Source repository: https://github.com/odabugs/kof13-hitboxes
Developer contact: pdk.odabugs@gmail.com
This document was last edited on July 1, 2014

----

[TOC] TABLE OF CONTENTS

[INTR] Introduction & Compatibility Notes
[REQS] What You'll Need to Install
[ISTL] Installation Step-by-Step
[STRT] Getting Up and Running

To navigate this document, search for the tag to the left of each section of
the document with case sensitive search enabled.  For example, to jump to
"Installation Step-by-Step", enable matching case and search for "[ISTL]".

Viewing notes: This document is formatted to 78 character wide monospace.

-----

[INTR] Introduction & Compatibility Notes

The current development version of the KOF XIII SE Hitbox Viewer is a Python-
based application that attaches to a running instance of The King of Fighters
XIII Steam Edition.  As such, system requirements for the hitbox viewer are
the same as for the original game, which can be viewed at the game's Steam
store page: http://store.steampowered.com/app/222940/.  There is currently one
exception, however; this version of the hitbox viewer requires support for
Windows Aero, available only on Windows Vista and later editions of Microsoft
Windows.  Aero must also be enabled while running the game in order for the
hitbox viewer to function.  To prevent the game from automatically disabling
Aero on startup, pass the -a command line switch when starting kofxiii.exe.

This hitbox viewer is currently tested and developed with 32-bit builds of
Python 2.7 on Windows.  For reasons of third-party library compatibility,
there are no current plans to extend support to Python 3 or 64-bit Python.
All required components should work the same regardless of whether you're
installing on a 32- or 64-bit version of Windows.  Despite requiring nothing
that isn't available on Windows Vista and above, this tool has so far only
been developed and tested on 64-bit Windows 7 Professional; please report if
you experience compatibility issues with other combinations of hardware or
software.  In terms of video card compatibility, any card supporting DirectX
9.0c and also capable of running the original game should work; the current
development machine uses an AMD Radeon 5670 with 512MB video RAM.  Again,
please report any compatibility problems that you may experience with your
own setup.

-----

[REQS] What You'll Need to Install

The KOF XIII SE Hitbox Viewer requires the following software to be installed:
- Python 2.7 x86: https://www.python.org/ftp/python/2.7.7/python-2.7.7.msi
- setuptools: https://pypi.python.org/pypi/setuptools/5.3
- comtypes: https://pypi.python.org/pypi/comtypes/1.1.0
- pydbg: http://www.lfd.uci.edu/~gohlke/pythonlibs/#pydbg

If you do not already have the KOF XIII SE Hitbox Viewer downloaded on your
system, you may download it by either of the following means:

Direct download: https://github.com/odabugs/kof13-hitboxes/archive/master.zip
Using Git: git clone https://github.com/odabugs/kof13-hitboxes.git

The Git-based option will allow you to stay up-to-date on the development of
this program at any time with a simple "git pull" on the command line.  If you
are not familiar with Git, you may opt to use the direct download instead, or
you can find more information on Git at: http://git-scm.com/

-----

[ISTL] Installation Step-by-Step

This installation guide assumes that all of the above software packages, as
well as the KOF XIII SE Hitbox Viewer itself, have already been downloaded to
a central folder, which we will refer to as C:\Downloads\.  Replace this with
the actual location where you have saved these packages on your system.
In the same vein, we will refer to your Python installation directory (the
directory where your python.exe resides) as C:\Python27\.
It is advised to install these software packages in the order presented.
Naturally, you will need to have a copy of KOF XIII SE purchased via Steam and
installed on your machine.
NOTE: Administrator privileges may be required at some points in this install.


1. Python
Python 2.7 is provided as an MSI installer package for Windows at the link
given in the REQS section of this document.  You can simply follow the steps
that the installer walks you through, but ensure that you add Python to your
system's PATH environment variable.  During installation, this can be done on
the "Custome Python" screen: simply enable the option that says "Add
python.exe to Path".

If you did NOT add Python to your system's PATH during installation, you can
follow these steps to add it to your PATH after installation:
- Open the Control Panel and open System Properties.
- Click on Advanced System Settings, then the Advanced tab.
- Click on Environment Variables... at the bottom-right corner.
- In the System Variables listing on the bottom half of the screen,
  select PATH (may be rendered as "Path") and click Edit...
- At the end of the line to be edited, type ";C:\Python27\" (without quotes).
- Click OK at all steps to return to the Control Panel.
- Select Run... from the Start Menu and type "python" to test your changes.
  If you were successful, then Python will start up and print a startup line.


2. setuptools
setuptools is used as a means to make the process of installing comtypes in
the next step simpler.  Download ez_setup.py, then double-click on it to "run"
it.  This will automatically "bootstrap" a working setuptools installation.


3. comtypes
Extract comtypes-1.1.0.zip to C:\Downloads\.  Open a command line at
C:\Downloads\comtypes-1.1.0\, and type "python setup.py install".

If you do not know how to navigate in a command line, follow these steps:

- Click "Run" on the Start Menu (or press Windows Key+R).
- Type "cmd", then press Enter.
- Type "cd C:\Downloads\comtypes-1.1.0\", then press Enter.
  (Note: If your actual download folder has a space anywhere in the pathname,
   then put double quote marks around the full path that you type in).
- Type "python setup.py install".  You can close the command line when it
  allows you to type on the prompt again, if installation was successful.


4. pydbg
Download "pydbg-1.2.win32-py2.7.exe" from the link given for pydbg in the
REQS section of this document.  Run the installer and follow its steps.
If you have multiple versions of Python installed on your system concurrently,
make sure that you choose the instance of Python that you just installed in
step 1 (in C:\Python27\) when the pydbg installer asks which Python version
it should install itself on top of.


-----

[STRT] Getting Up and Running

After installing all of the above software packages, you may set up and run
the KOF XIII SE Hitbox Viewer.  If you downloaded it via the Git-based
approach, simply navigate to the directory where you performed the "git
clone".  If you downloaded the zip file, extract it to any location, then
open the "kof13-hitboxes-master" folder that it creates upon extraction.

Start the game with Aero enabled before starting the hitbox viewer.  In order
to prevent the game from automatically turning Aero off, pass the -a command
line switch to it on startup.  This can be done on Steam with these steps:

- Open the Steam client and log into your Steam account if necessary.
- Go to Library, then Installed.
- Right-click on King of Fighters XIII in your installed games list.
- Select Properties, then go to the General tab.
- Click Set Launch Options...
- Type "-a" (without quotes) in the Launch Options dialog box.
- Press OK at all steps to return to the Steam client.

Once the game is up and running, start a match in any game mode and double-
click on start.bat in the folder where you installed the hitbox viewer.
It is advised to start the hitbox viewer either during gameplay or shortly
beforehand (e.g., during stage select or character select), since it can
"hang" if left on menu screens for a long enough time.  For this reason,
users may also experience crashes inbetween matches; "your mileage may vary"
regarding stability of the hitbox viewer in its current state, though it
should be stable enough to play a 3v3 match from start to finish.

NOTE: We haven't tried taking this tool online yet, and though it probably won't
result in a ban, we don't advise it (at least for now).  Since this tool works
by setting a software breakpoint on the game's running process, this modifies
the game's memory while it's running, which can be detected by certain anti-
cheat mechanisms.  We currently have no idea how the game's anti-cheat works,
and we don't intend for this to be a tool to aid cheating in online games.
We especially do not intend for this tool to aid users trying to pirate a copy
of KOF XIII; we make no attempt to circumvent the game's built-in copy
protection, and we have no plans to do so.



## TODO list and prospective feature ideas (last update June 7, 2014):

- Prioritize and sort the following items!
- Centralized program configuration; one class to load and parse configs/argv
- Global.py belongs on the chopping block after this class is implemented
- Support at least the following config options:
  - Set box colors for each box type we're currently anticipated to need:
    - Player vulnerability boxes
	- Player attack boxes
	- Projectile attack boxes
	- Projectile vulnerability boxes (these last 3 items are currently the same)
	- Throw boxes (regular and special/super throws; same color for both is OK)
	- Block/armor boxes (both are currently the same)
	- Collision boxes
	- Proximity detection boxes (e.g., Kyo hcb+K)
	- Any other new box types found later on?
  - Let users enter colors as #RRGGBB hex or rgb(RR,GG,BB) decimal
  - Maybe support preset color names? (WHITE=rgb(255,255,255) etc.)
  - Set the drawing order of boxes by type (also on a per-player basis?)
  - Set transparency amounts of box fill and box borders (maybe pivots too?)
  - Let users enter transparency amounts as hex or decimal (range is 0-255)
  - Set size and color of pivot crosses (and alternate styles like X marks?)
  - Selectively disable rendering of box fill, box borders and pivot crosses
  - Selectively disable viewing certain box types (also on a per-player basis?)
  - Disable player 1 or player 2 boxes/pivots entirely
  - Support loading configs from files; add an appropriate default config file
  - Support specifying to load a certain config file on command line
  - Support setting config options via command line (and exporting to a file?)
  - Warn users when enabling -nosync flag (it's NOT intended for normal usage)
    - Probably shouldn't support setting this in config files as insurance
  - Command line settings override config file settings
  - Fine-grained (e.g. set per player) settings override more general settings
- Renderer.py has too many hardcoded details about box types and colors
- Support drawing boxes in "layers" based on box type to handle box overlap
  - Interleave drawing of each box "layer" between player 1 and 2
- Support ability to pause and unpause the game safely
- Support frame advance
- Frame-by-frame input control
- Save and load replayable input sequences
- Input sequence editor/viewer (for making TAS combos)
- Add a separate GUI window? (to provide controls and UI for things like TASing)
- Look into alternative implementation choices; e.g. DLL injection, EndScene()
  - Might need to switch to another language (Visual C++?) for DLL injection
  - If we need to switch, do the desired tools exist outside of Visual Studio?
- Support translations for program strings; move strings to localized files
- Write installation guide (preferably with illustrations; this process is dumb)
- Write general documentation and usage guide
- Fix box movement not lining up perfectly with camera shaking (Takuma's taunt)
- Fix boxes touching the ceiling when the camera scrolls upward; e.g. Billy dp+K
- Fix boxes not scaling when camera zooms in (e.g. during neomax animations)
- Auto-calculate placement of hitbox Y = 0 onscreen; remove hardcoded 720p value
  - Might be better to place boxes relative to the Y box coordinate value that
    correlates to the vertical center of the screen?
- Test fullscreen and "windowed fullscreen" modes (they probably won't work)
- What moves other than Yuri's taunt are affected by randomness?
- Do any taunts other than Benimaru's have hitboxes or other special properties?
- What does the wide box surrounding Daimon qcb+K represent?  Throwable box?
- Test different solutions for floating-point roundoff affecting box alignment
  relative to player sprites onscreen (boxes "shifting" by a pixel or two)
- Reverse engineer how the game knows a box's "type"; hurtbox, throwbox, etc.
- Test at least all the basic normals/specials for all characters
  - Are there any moves that require special attention to support properly?
- What tools can record lossless 60hz video for hitbox capture purposes?
  - How easy is it to split the output of those tools into individual frames
    while remaining lossless?
- What features could help make capturing box shots easier for wiki authors?
- Test Python 2.7.7 and 64-bit Python builds (currently using 2.7.6, 32-bit)
  - 64-bit probably too much of a pain due to library incompatibility
- Python 3 transition will probably never happen without all dependencies
  - Is there any functional benefit that Python 3 could offer us?  Libraries?
  - Might be best to move away from Python wholesale in the future?
    (see earlier points about DLL injection/EndScene())
- HitboxViewer.py's file and class name is misleading given its current role?
  - Renaming it e.g. Process.py and giving the class a narrower scope may be
    better for code clarity and reducing the current amount of code coupling
- HitboxViewer and Renderer classes are getting a bit too tightly coupled?
- Move all info about the game state to "game info" and "player info" classes?
- More code refactoring? (a lot of this BS is probably not even called anymore)
- Any way to replace the stage background with a solid color?
- Any way to to render the player sprites without any smoothing/filtering?
- Any way to completely disable or conceal onscreen HUD (bars, timer, etc.)?
- Add pivot crosses to projectiles?  (Requires more reverse engineering work)

## LICENSE

KoF XIII Hitbox Viewer Copyright (C) 2014 E. Fuller (pdk.odabugs@gmail.com)

Permission to use, copy, modify, and distribute this software and its
documentation for any purpose and without fee is hereby granted,
provided that the above copyright notice appear in all copies and that
both the copyright notice and this permission notice and warranty
disclaimer appear in supporting documentation, and that the name of
the above copyright holders, or their entities, not be used in
advertising or publicity pertaining to distribution of the software
without specific, written prior permission.

The above copyright holders disclaim all warranties with regard to
this software, including all implied warranties of merchantability and
fitness. In no event shall the above copyright holders be liable for
any special, indirect or consequential damages or any damages
whatsoever resulting from loss of use, data or profits, whether in an
action of contract, negligence or other tortious action, arising out
of or in connection with the use or performance of this software.

Additional notices and disclaimers:
The King of Fighters XIII Copyright (C) 2010-2013 SNK Playmore Corporation
Steam Copyright (C) 2003-2014 Valve Corporation
All rights reserved by their respective copyright holders.

This software, and all components or derivatives thereof, are not officially
endorsed, supported, or sponsored by SNK Playmore Corporation nor by Valve
Corporation.  Any use of this software is at the user's own risk, including the
risk that the user's account may be banned from the Steam service or from
online play due to the use of this software.

DirectPython (C) 2007-2013 Heikki Salo (http://directpython.sourceforge.net/)
pydbg, PaiMei (C) Pedram Amini (http://pedram.openrce.org/PaiMei/docs/)
comtypes (C) Thomas Heller (http://starship.python.net/crew/theller/comtypes)
setuptools (C) Jason R. Coombs et al.
(https://pypi.python.org/pypi/setuptools#credits)
These software packages are copyright their respective owners, and are subject
to the license agreements laid out by them.  This software, and all components
or derivatives thereof, are not officially endorsed, supported, or sponsored by
any of the above individuals nor by any contributors to their respective
software projects.