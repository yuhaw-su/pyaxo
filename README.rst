Python implementation of the Axolotl ratchet protocol.
======================================================

Overview
--------
The Axolotl ratchet is a protocol (similar to OTR) that
provides for perfect forward secrecy in (a)synchronous
communications. It uses triple Diffie-Hellman for
authentication and ECDHE for perfect forward secrecy.
The protocol is lighter and more robust than the OTR
protocol - providing better forward and future secrecy,
as well as deniability.

The protocol was developed by Trevor Perrin and Moxie
Marlinspike. Its chief use currently is in the Whisper Systems
TextSecure SMS package.

A nice writeup of the protocol is on the `Whisper Systems Blog`_.
You can find the most recent specification of the protocol
`here <https://github.com/trevp/axolotl/wiki/newversion>`_.

Installation instructions
-------------------------
Make sure that you have the following::

    sudo apt-get install python-dev libffi-dev # If using Debian/Ubuntu
    sudo yum install python-devel redhat-rpm-config libffi-devel # If using Fedora

pyaxo also uses `pynacl`_ and `passlib`_,
but these packages will be downloaded and installed automatically by
`pip`_/`setuptools`_.

If you use *pip*, install pyaxo with::

    sudo pip install pyaxo

If you use *setuptools*, change to pyaxo's source folder and install
with::

    sudo python setup.py install

**pyaxo will be ready for use!**

If you do not use neither of those, you will have to manually install
each dependency before running the previous command.

Usage
-----
There are several examples showing usage. There are also
``encrypt_pipe()`` and ``decrypt_pipe()`` methods for use in
certain applications. I haven't put together an example using
them yet, but it should be straightforward.

Protocol Update
---------------
pyaxo 0.4 was updated according to the latest (Oct 1, 2014) version
of the protocol, which changed the order of the ratcheting. For that
reason, old conversations (created with pyaxo < 0.4) might not work
properly after the update. We suggest that users update pyaxo and
restart their conversations.

Bugs, etc. should be reported to the *pyaxo* github `issues page`_.

.. _`issues page`: https://github.com/rxcomm/pyaxo/issues
.. _`passlib`: https://pypi.python.org/pypi/passlib
.. _`pynacl`: https://pypi.python.org/pypi/PyNaCl/
.. _`pip`: https://pypi.python.org/pypi/pip
.. _`setuptools`: https://pypi.python.org/pypi/setuptools
.. _`Whisper Systems Blog`: https://whispersystems.org/blog/advanced-ratcheting/
