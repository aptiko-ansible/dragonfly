====================
DragonFly Mail Agent
====================

Description
===========

This is an Ansible role for installing the DragonFly Mail Agent, or dma,
on a Debianserver.  It also sets a catch-all alias in ``/etc/aliases``.
It can be set to only send emails (useful for enabling a machine to send
administrative email, such as cron error messages, to the admins).

Examples
========

Configuration example::

   admins: myemail@somewhere.com
   dma_smarthost: mail.itia.ntua.gr
   dma_smarthost_port: 587
   dma_smarthost_username: myuser
   dma_smarthost_password: topsecret
   dma_masquerade: sender@somewhere.com
   dma_defer: True
   dma_securetransfer: True
   dma_starttls: True

Reference
=========

The following variables are used:

- ``admins``: A comma-separated list of emails, to which all received
  emails without a domain will be sent.
- ``dma_smarthost``: The smarthost.
- ``dma_smarthost_port``: The port for the smarthost; usually 25, 465,
  or 587.
- ``dma_smarthost_username``, ``dma_smarthost_password``: Necessary when
  the smarthost requires authentication.
- ``dma_masquerade``: Optional. The email address DMA will use for the
  envelope-from. Some smarthosts require the envelope-from to belong to
  the connected user.
- ``dma_defer``, ``dma_securetransfer``, ``dma_starttls``,
  ``dma_opportunistic_tls``, ``dma_insecure``: By default these are
  False. If True, then they are set in the configuration file; e.g. if
  dma_starttls is true, STARTTLS is set in ``/etc/dma.conf``.

Meta
====

Written by Antonis Christofides

| Copyright (C) 2014 TEI of Epirus
| Copyright (C) 2014-2019 Antonis Christofides
| Copyright (C) 2014-2019 National Technical University of Athens

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see http://www.gnu.org/licenses/.
