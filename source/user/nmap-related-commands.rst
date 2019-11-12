Nmap Related Commands
=====================

Nmap (https://nmap.org) is the most known hacking tool, so:

1. You must know how to use Nmap
2. You must use Nmap

Please, if you don't know Nmap, read the documentation, it's awesome: https://nmap.org/book/man.html

Habu comes with some tools that provides integrations with Nmap and has some 
helpful functions.


Scan Result Parsing
-------------------

If you have an Nmap scan result (in XML, gnmap or nmap format), you can use some habu.nmap.* tools
to parse these files and obtain information about them.


Scanned Ports
.............

The command habu.nmap.ports gives you the list of ports that was scanned:

::

   $ habu.nmap.ports /tmp/scan.nmap 
   21,22,23,25,80,110,143,443,445,3389

This can be helpful if you want to run a new scan, but with different options.


Open Ports
..........

The command habu.nmap.open shows the ports that has been result open for the nmap scan.


::

   $ habu.nmap.open /tmp/scan.nmap 
   80,443

This can be helpful to the same reasons has the habu.nmap.ports.


Ports Outside Nmap
------------------

Sometimes, you need to expose a port to the whole internet on your server or another device.

They're a lot of security recommendations about that, but one quick thing you can do is open a port
that is not easy detected by the hundred scanners that are constantly probed to open ports.

Because most of the scanners are based on Nmap (or are Nmap), it's a good idea to use a port that
is not scanned by Nmap in the default configurations.

Obviously, Nmap can scan the 65535 possible ports, but that is not the case in the grand part of
the scans launched on internet.

You can use the following command to obtain a port that is not listed on the file '/usr/share/nmap/nmap-services',
which is the file used to define what ports are scanned if not specific ports are passed with the '-p' option.

::

   $ habu.nmap.excluded 
   10482


