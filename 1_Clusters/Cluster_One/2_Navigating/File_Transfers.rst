File Transfers
===========================

Copy Files with SCP
********************

Use the ``scp`` command to copy files or directories to Cluster One:

.. code-block:: console

  scp -r <DIR> <userid>@TODO: data transfer host:/path/to/destination/

Synchronize with Rsync
************************

Use ``rsync`` for efficient file syncing:

.. code-block:: console

  rsync -rav ~/data <userid>@TODO: data transfer host:~/data/
  rsync -rav --delete --exclude-from=~/exclude.txt ~/data <userid>@TODO: data transfer host:~/data/

.. note::
   - ``--delete`` removes files not present in the source
   - ``--exclude-from`` uses a file to skip listed files

Data Transfer with Globus
*************************

The recommended method for transferring large data files to and from Cluster One is to use `Globus <https://www.globus.org>`_. Globus manages transfers reliably in the background, handling restarts if interruptions occur.

.. note::
   The step-by-step screenshots for connecting via Globus are currently being updated. The general workflow remains the same: log into Globus with your JHED ID, search for the Cluster One collection, authenticate, and begin transferring files to and from your projects.

TODO: Add updated Globus screenshots once available.
