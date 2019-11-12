Configuration Management
========================

A lot of Habu commands can be used without any additional configuration, but some commands
need to know some data, like your Shodan (https://www.shodan.io) API key.

To configure Habu, you can use the habu.config.* command, like I will show on the following
examples.

Show
----

To show the current configuration, you can use the habu.config.show command, like this:


::

   $ habu.config.show
   {
    "SHODAN_APIKEY": "*************",
    "VIRUSTOTAL_APIKEY": "*************"
   }


By default, all the configuration values that has the work "key" are masked. If you need to
you these values too, use the '-k' parameter:

::

   $ habu.config.show -k
   {
    "SHODAN_APIKEY": "Some-key-that-is-not-my-key",
    "VIRUSTOTAL_APIKEY": "Another-invalid-key-for-this-example"
   }


Set
---

To set configuration values, you simply need to use the habu.config.set command, like this:

::

   $ habu.config.set SOME_OPTION some-value


Delete
------

To delete configuration values, you simply need to use the habu.config.del command, like this:

::

   $ habu.config.del SOME_OPTION


Storage
-------

The configuration is stored in the following file: '~/.habu.json', this path will be expanded according
your environment and operating system.

In Unix-like operating systems, will be like '/home/fportantier/.habu.json'.

And, yes, is a simple JSON file, so can also be edited with your prefered text editor.

