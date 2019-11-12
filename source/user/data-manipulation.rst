Data Manipulation
=================

One key aspect of Habu is that it's inspired on the following Unix phisolophy concept:

*"Write programs to handle text streams, because that is a universal interface."*

You can manipulate text data with a lot of Unix well known tools, like sed, awk and grep,
but Habu has some tools that can do other specific things.


Data Extraction
---------------

One thing that you will need to do a lot of times it's extract information from text streams,
like IP addresses, domain names, etc.

You can use the awesome "grep" tool (http://man7.org/linux/man-pages/man1/grep.1.html) for that,
but you need to know exactly wich regular expression (https://en.wikipedia.org/wiki/Regular_expression)
do you need for each case.

Also, some data extraction tasks can't be only done with regular expresions (like validate if a
domain exists).

For the data extraction process, you can use the habu.data.extract.* tools, that are the following:

- habu.data.extract.ipv4
- habu.data.extract.ipv6
- habu.data.extract.domain
- habu.data.extract.fqdn
- habu.data.extract.email

A simple example:


::

   $ cat logfile.txt | habu.data.extract.ipv4
   181.143.135.154
   192.168.0.128
   152.118.223.187
   181.12.112.78
   181.22.122.130
   181.22.122.130
   172.16.5.14
   200.125.122.20


Probably, you will see a lot of repeated results (like in the example above). To show each record only
one time, you can use the awesome "sort" tool, with the "-u" (unique) parameter, like this:


::

   $ cat logfile.txt | habu.data.extract.ipv4 | sort -u
   152.118.223.187
   172.16.5.14
   181.12.112.78
   181.143.135.154
   181.22.122.130
   192.168.0.128
   200.125.122.20


For convenience, the habu.data.extract.* commands support the '-u' option, that does the same:

::

   $ cat logfile.txt | habu.data.extract.ipv4 -u
   152.118.223.187
   172.16.5.14
   181.12.112.78
   181.143.135.154
   181.22.122.130
   192.168.0.128
   200.125.122.20


Data Enrichment
---------------

Now, you have a list of IP addresses that appears in the file 'logfile.txt'. But, possibly, you need
to get more information about each item, so, you can use the command habu.data.enrich, like this:

::

   $ cat logfile.txt | habu.data.extract.ipv4 -u | habu.data.enrich
   [
    // LINES ABOVE REMOVED FOR CLARITY //
    {
        "item": "181.22.122.130",
        "family": "ipv4_address",
        "is_multicast": false,
        "is_global": true,
        "is_unspecified": false,
        "is_reserved": false,
        "is_loopback": false,
        "is_link_local": false
    },
    {
        "item": "192.168.0.128",
        "family": "ipv4_address",
        "is_multicast": false,
        "is_global": false,
        "is_unspecified": false,
        "is_reserved": false,
        "is_loopback": false,
        "is_link_local": false
    },
    {
        "item": "200.125.122.20",
        "family": "ipv4_address",
        "is_multicast": false,
        "is_global": true,
        "is_unspecified": false,
        "is_reserved": false,
        "is_loopback": false,
        "is_link_local": false
    }
   ]


Now, you have a JSON formated list of items, each one with additional information.

On the current version, Habu supports the following item families:

- ipv4_address
- ipv4_network
- ipv6_address
- ipv6_network

More families can be added on next versions.


Data Filtering
--------------

With the enrichment done in the later step, we can use the command habu.data.filter to
take only the items in which we are interested.

Supose that you only want to get the private IP addresses, you can use the following:

::

   $ cat logfile.txt | habu.data.extract.ipv4 -u | habu.data.enrich | habu.data.filter is_global false
   [
       {
           "item": "172.16.5.14",
           "family": "ipv4_address",
           "is_multicast": false,
           "is_global": false,
           "is_unspecified": false,
           "is_reserved": false,
           "is_loopback": false,
           "is_link_local": false
       },
       {
           "item": "192.168.0.128",
           "family": "ipv4_address",
           "is_multicast": false,
           "is_global": false,
           "is_unspecified": false,
           "is_reserved": false,
           "is_loopback": false,
           "is_link_local": false
       }
   ]


You can pipe the commands much times has you need, to make more filterings.

**Note:** The command habu.data.filter can be used to filter any JSON formated text, not only the
outputs that have been produced by another Habu command.


Data Selection
--------------

To finish, maybe you need to select only the value of one field of each item, like this:


::

   $ cat logfile.txt | habu.data.extract.ipv4 -u | habu.data.enrich | habu.data.filter is_global false | habu.data.select item
   172.16.5.14
   192.168.0.128


Summary
-------

And thats all, with some simple commands, you've made the following steps:

1. Extract the IPv4 addresses from a text file
2. Enriched each IPv4 address to know things like if they're public or private addresses
3. Filtered only the private addresses, discarding the public ones
4. Select only the address part of each item, discaring the other information


