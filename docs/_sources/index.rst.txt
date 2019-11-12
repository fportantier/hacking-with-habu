.. Habu documentation master file, created by
   sphinx-quickstart on Sat Apr 27 22:04:26 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Hacking with Habu
=================

.. image:: https://img.shields.io/pypi/l/habu.svg
    :target: https://pypi.org/project/habu/

.. image:: https://img.shields.io/pypi/pyversions/habu.svg
    :target: https://pypi.org/project/habu/


.. _introduction:

*"An open sourced set of simple tools to learn about hacking"*

Some key aspects:

1. Command line applications
2. Developed in Python
3. Designed to be simple to use and understand


Development
-----------

If you want to collaborate with the project or simply learn how Habu is developed,
read the "Development Guide".


Operating System Compatibility and Issues
-----------------------------------------

Habu is developed with GNU/Linux systems in mind, but with a lot of efforts to make
it compatible with any Unix-like system and even with Microsoft Windows.

Please, if you find that some tool doesn't work with your OS, don't hesitate to
report the issue through Github (https://github.com/portantier/habu/issues).


Permissions
-----------

Some of the tools need elevated permissions to run correctly, so, it's recommended
to run these tools with the root user (or use sudo/doas) on Unix, or with elevated
permissions through UAC on Microsoft Windows.


Quick Installation or Upgrade
-----------------------------

::

   $ pip3 install --upgrade habu
   $ habu.version
   0.1.30


For detailed (or alternative) installation steps, read "Detailed Installation" section.


This Guide
----------

The purpouse of this guide is not only learn how to use Habu, but also learn a lot of
hacking concepts.

Feel free to jump to any section of your interest but, if you want to learn from the most
basic concepts, read this guide in an ordered way.


Usage Videos
------------

The following Youtube Playlist has videos that shows the installation
and usage and various Habu tools:

https://www.youtube.com/watch?v=rgp9seLLyqE&list=PL4HZnX8VnFXqSvNw7x-bXOn0dgxNdfnVD


Telegram Group
--------------

If you want to discuss some Habu features, possible improvements, etc,
you can use the Habu Telegram Group: https://t.me/python_habu


The User Guide
--------------

This part of the documentation, guides you through the usage of Habu tools and teachs
you a lot of concepts about hacking.

.. toctree::
   :maxdepth: 2

   user/first-steps
   user/know-your-environment
   user/data-manipulation
   user/configuration-management
   user/nmap-related-commands

TODO:

- Development Overview
- Installation (detailed)
- Nmap Scan Parsing
- Domain Information
- Subdomain Discovery
- Web Technologies Enumeration
- Integration With External Services
   - AsyDNS
   - Shodan
   - VirusTotal
- Address Resolution Protocol (ARP)
   - ping
   - sniff
   - poison
- Classic Network Attacks
   - land
   - synflood
- Enumeration
- Extracting Data From Logs
- Cryptography Functions
   - Hash functions
   - Hash identification
   - Fernet
   - XOR
   - Group Policy Preferences (GPP) Decryption
   - Broken Cryptography Decrypt
      - Cisco 7
- Other Hacking Techniques 
   - Crack SNMP
   - Crack Luhn
   - DHCP Starvation
   - DHCP Discover
   - TCP Flags
   - TCP Scan
   - ISN variation detection
   - Protocol Scan
   - Social Network Username Discovery
   - Virtual Hosting Discovery
   - Web Headers
   - Data about IP Addresses
   - Data about Domain Names
Protocol Servers
   - Fake FTP Server





The Development Guide
---------------------

This part of the documentation explains three things:

1. How Habu is developed
2. How Habu can be used to develop other tools
3. How you can contribute with the project


Command Reference
-----------------

This part of the documentation contains the complete help text of each tool and is the
recommended source of information if you want to know how to use a specific tool.


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
