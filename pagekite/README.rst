hass.io Pagekite integration
============================

This Home assistant add-on integrates a Pagekite client into hass.io, the base
system of Home Assitant. With this add-on, you can make your local home
automation available for remote access without having to manage any NAT port
forwarding, network addresses or dynamic DNS.

Usage
-----

Account setup
~~~~~~~~~~~~~

In order to use this module, you should have obtained a PageKite account. They
are available for a small fee on https://pagekite.net/. You can set up and
host your own frontend as well, but this guide assumes that you are using the
default provider.

When you have set up your account, you will have a "kite" (a host name of the
form \<your-name\>.pagekite.me) and a secret for it (which is typically the
account default secret as available in the "Your Details" section of `your
account page`_.

Add-on installation
~~~~~~~~~~~~~~~~~~~

This add-on is published in the author's `personal repository`_. You can
install it by going to your hass.io dashboard's add-on store page, adding the
URI https://gitlab.com/chrysn/hassio-addons as a new repository, clicking on
the PageKite add-on and pressing the install button.

Configuration
~~~~~~~~~~~~~

After you have enabled the add-on, its configuration needs to be updated. Fill
in your kite name and kiet secret from the account setup in the add-on's config
section under respective default entries.

When you have entered and saved those values, you can start the service and
access your home assistant installation on ``https://<your-name>.pagekite.me``
(no ``:8123``!).  Note that the HTTPS server is set up by pagekite.me; there is
no need to set up any Let's Encrypt or similar HTTPS certificate provider
locally, but that also means that the connection is only encrypted between the
user and pagekite.me and between pagekite.me and your Home Assistant
installation, not all the way through.

By default, both the default Home Assistant port (8123) and the SSH port (22)
are published under your kite name (the latter requires the SSH server add-on
to be actually usable); you can disable them individually.

If you need additional configuration, you can add a ``default-override`` record
to your configuration. This allows you to change the default flags which are
passed on to pagekite (``"--clean --defaults"``); use this to enable additional
services or to configure your own kite frontend.

.. _`your account page`: https://pagekite.net/home/
.. _`personal repository`: https://gitlab.com/chrysn/hassio-addons

License
-------

This hass.io module was written by chrysn <chrysn@fsfe.org> and is
published under the terms of the GNU AGPL version 3 or later, as described on
https://www.gnu.org/licenses/agpl-3.0.en.html.

The shipped pagekite software was written by the Beanstalks Project ehf. and
Bjarni Runar Einarsson, and is published under the same license (see
``src/pagekite.py`` for details).
