CLASSIC_STICK2BTN
=================

Copyright (C) 2013 Louis Marchand <prog@tioui.com>

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301  USA
This plugin permit to use the remote IR pointer as a relative axes.

This cwiid plugin is base on the nunchuk_stick2btn plugins from L. Donnie Smith <donnie.smith@gatech.edu>

COMPILATION INSTRUCTION
___________

* Download and extract the cwiid source code (http://abstrakraft.org/cwiid/downloads/cwiid-0.6.00.tgz).
* Execute the configure script in the root directory of the cwiid source code. For more information, see the cwiid README file.
* After the configure has successfully execute, copy the current directory (classic_stick2btn) in the <CWIID_source_code>/wminput/plugins/ directory.
* In the <CWIID_source_code>/wminput/plugins/classic_stick2btn/ directory, execute those command lines:

***

      gcc -g -Wall -W -DHAVE_CONFIG_H -I../../../common/include -I../../../wminput -I../../../libcwiid -fpic   -c -o classic_stick2btn.o classic_stick2btn.c
      gcc -shared   -o classic_stick2btn.so classic_stick2btn.o

***

* To install the plugin for one user execute those command lines:

***

    mkdir -p ~/.cwiid/plugins
    cp -p classic_stick2btn.so ~/.cwiid/plugins/

***

* To install the plugin in the plugin system wide, execute this command line with root privilege (on some system, you will have to use sudo):

***

    cp -p classic_stick2btn.so /usr/local/lib/cwiid/plugins

***

* On some system, the plugins directory is in /usr/lib/cwiid/plugins/. So, if the precedent command give you a "Directory not exist" kind of error, use this command:

***

      cp -p classic_stick2btn.so /usr/lib/cwiid/plugins

***

UTILISATION
___________

In a wminput config file, use those lines (adjust the KEY_XX to what you need):

***

	Plugin.classic_stick2btn.LStickUp       = KEY_UP
	Plugin.classic_stick2btn.LStickDown     = KEY_DOWN
	Plugin.classic_stick2btn.LStickLeft     = KEY_LEFT
	Plugin.classic_stick2btn.LStickRight    = KEY_RIGHT

	Plugin.classic_stick2btn.RStickUp       = KEY_KP8
	Plugin.classic_stick2btn.RStickDown     = KEY_KP2
	Plugin.classic_stick2btn.RStickLeft     = KEY_KP4
	Plugin.classic_stick2btn.RStickRight    = KEY_KP6

***
