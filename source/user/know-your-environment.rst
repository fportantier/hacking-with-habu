Know Your Environment
=====================

The first step that you must execute to learn about Habu is start to know your environment
(operating system, network connection, etc.)

This can be acomplished with the following tasks.

Public IP
---------

It's easy to use operating system commands to know your network interface address, but
your public IP is almost never the same that your network interface IP, so, you can use
the following command:

::

   $ habu.ip
   80.219.53.185


How it works?
.............

It uses the https://www.ipify.org/ service to know what is the IP address that the service
sees as your public IP address.

Basically, makes a request to https://api.ipify.org


Connection Capabilities
-----------------------

If you're using your work or home internet connection, probably you have unrestricted
access to any IP or service that is available on internet.

But, if you're using any network that you don't know well, maybe your internet access can
be limited by filtering policies.

To know what services you can access, you can use the following command:

::

   $ habu.contest
   IP:    True
   DNS:   True
   FTP:   True
   HTTP:  True
   HTTPS: True


How it works?
.............

Tries to make connections to popular services to test if the service it's allowed.

The current version uses the following services:

================= ===========================================================
Protocol          Service
================= ===========================================================
DNS               Google (8.8.8.8, 8.8.4,4)
FTP               Debian (ftp.debian.org), RedHat (ftp.redhat.com)
HTTP              Google (http://www.google.com), IBM (http://www.ibm.com)
HTTPS             Google (https://www.google.com), IBM (https://www.ibm.com)
================= ===========================================================

Please, consider that habu.contest only checks if the services is not completly
blocked. But, maybe, you can access to Debian and RedHat FTP servers, but some
other FTP servers are restricted. 


Network Interfaces
------------------

If you want to list your network cards and their addresses (IPv4, IPv6, MAC), you
can execute the following command:

::

   $ habu.ip.internal
   {
       "lo": {
           "ipv4": [
               {
                   "addr": "127.0.0.1",
                   "netmask": "255.0.0.0",
                   "peer": "127.0.0.1"
               }
           ],
           "link_layer": [
               {
                   "addr": "00:00:00:00:00:00",
                   "peer": "00:00:00:00:00:00"
               }
           ],
           "ipv6": [
               {
                   "addr": "::1",
                   "netmask": "ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff/128"
               }
           ]
       },
       // The other network interfaces... //


This can be used not only to list your NICs, but also to know if Habu is
detecting correctly all your network interfaces.


Host Information
----------------

To know some characteristics of your host, you can use the following command:

::

   $ habu.host
   {
       "kernel": [
           "Linux",
           "p",
           "5.2.0-kali3-amd64",
           "#1 SMP Debian 5.2.17-1kali1 (2019-09-27)",
           "x86_64",
           ""
       ],
       "distribution": [
           "Kali",
           "kali-rolling",
           "kali-rolling"
       ],
       "libc": [
           "glibc",
           "2.29"
       ],
       "arch": "x86_64",
       "python_version": "3.7.5rc1",
       "os_name": "Linux",
       "static_hostname": "p",
       "cpu": "",
       "fqdn": "p"
   }


This is basic info is really useful when you need to do some troubleshooting, or
submit software issues.

