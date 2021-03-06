# DEPRECATED DEPRECATED DEPRECATED DEPRECATED #



# asterisk-gui-2.0

Introduction
======================
Asterisk-GUI is a framework for the creation of graphical interfaces for
configuring Asterisk.  Some sample graphical interfaces for specific vertical
markets are included for reference or for actual use and extension. 

Software License
================
Asterisk-GUI HTML and Javascript files
Copyright (C) 2006-2010 Digium, Inc.

This program is free software; you can redistribute it and/or
modify it under the terms of the GNU General Public License
as published by the Free Software Foundation, version 2 only.  This
software is also available under commercial terms from Digium, Inc.
Please contact us for details at:
____________________________________________________________

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA
02110-1301, USA.

Please contact Digium for information on alternative licensing 
arrangements for Asterisk-GUI.

Use of Graphics, Trademarks and Logos
=====================================
The images and logos included with Asterisk-GUI may only be distributed with
unmodified versions of the toolkit and may not be used in any derivative works
without special written permission from Digium.  

ASTERISK, ASTERISK-GUI and DIGIUM are all trademarks of Digium, Inc. and
their use is governed by our trademark policy available at:

http://www.digium.com/en/company/view-policy.php?id=Trademark-Policy

The GNU General Public License does not grant you any rights under
trademark law to use those trademarks or the images and logos included
with the Asterisk-GUI software.  Use of those trademarks is restricted
as described in our trademark policy to unmodified versions of the
toolkit, and may not be used in any other manner without prior written
permission from Digium.

Bugs
====
Bugs, patches, and feature requests may be submitted at http://bugs.digium.com
and should reference the GUI project.

Installation
============

./configure

make

make install

Configuration
=============
You may install sample configuration files by doing "make samples".  Also you 
will need to edit your Asterisk configuration files to enable the GUI properly,
specifically:

1) In http.conf:

	[general]
	enabled = yes
	enablestatic = yes
	
2) In manager.conf

	[general]
	enabled = yes
	webenabled = yes
	
3) Create an appropriate entry in manager.conf for the administrative user
(PLEASE READ THE security.txt FILE!)

    [admin]
    
    secret = thiswouldbeaninsecurepassword
    
    read = system,call,log,verbose,command,agent,config,read,write,originate
    
    write = system,call,log,verbose,command,agent,config,read,write,originate

Troubleshooting
===============
1) Check your config permissions:

$ chown asterisk:asterisk /etc/asterisk/*.conf

$ chmod 644 /etc/asterisk/*.conf
