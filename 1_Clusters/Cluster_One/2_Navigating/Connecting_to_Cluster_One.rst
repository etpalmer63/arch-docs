Logging in to Cluster One
===========================

This section covers how to log into Cluster One and transfer files to and from the system.

Use Secure Shell (SSH) to connect:

.. code-block:: console

  ssh -XY <userid>@TODO: login hostname

You can also use:

.. code-block:: console

  ssh -XY TODO: login hostname -l <userid>

**Gateway:** ``TODO: login hostname``

Access to Login Node
********************

Once you establish a connection, SSH will prompt for your password. Once you have signed into the login node, you should see the Message of the Day "MOTD".

Quota information will be provided to users automatically on login, but users can use the ``quotas.py`` command at anytime to view quota and usage information.

.. note::
   The exact MOTD output may differ from the example below.

Multiplexing SSH Connections
****************************

To avoid re-entering your password and two-factor code with each connection, you can enable SSH multiplexing:

1. Edit (or create) ``~/.ssh/config`` on your local Unix-based machine:

   .. code-block:: text

     Host TODO: login hostname
         ControlMaster auto
         ControlPath ~/.ssh/control:%h:%p:%r

2. Start the master connection:

   .. code-block:: console

     ssh -fNM -X TODO: login hostname -l <userid>

3. To stop the connection:

   .. code-block:: console

      ssh -O stop TODO: login hostname

.. note::
   Large file transfers and terminal sessions may experience lag when using the same multiplexed connection.

**Windows users:** Use `PuTTY`_ or `MobaXterm` (Home Edition -> Installer edition) to connect. MobaXterm includes an X11 server for GUI apps and supports SFTP file transfers.

**Mac users:** Use the built-in Terminal. For GUI support, install `XQuartz`_.

.. _PuTTY: https://www.putty.org
.. _XQuartz: https://www.xquartz.org
.. _MobaXterm: https://mobaxterm.mobatek.net
