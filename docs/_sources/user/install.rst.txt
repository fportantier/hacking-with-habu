.. _install:

Installation of Habu
========================

This part of the documentation covers the installation of Habu.
The first step to using any software package is getting it properly installed.

$ pip3 install habu
-------------------

To install Habu, run this simple command in your terminal of choice::

    $ pip3 install habu

**Note:** The "pip3" command can be named "pip" depending on your distribution.

Get the Source Code
-------------------

Habu is actively developed on GitHub, where the code is
`always available <https://github.com/fportantier/habu>`_.

You can either clone the public repository::

    $ git clone git://github.com/fportantier/habu

Or, download the `tarball <https://github.com/fportantier/habu/tarball/master>`_::

    $ curl -OL https://github.com/fportantier/habu/tarball/master
    # optionally, zipball is also available (for Windows users).

Once you have a copy of the source, you can install it with::

    $ cd habu
    $ pip3 install .
