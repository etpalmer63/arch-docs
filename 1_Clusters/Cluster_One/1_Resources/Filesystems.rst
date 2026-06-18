Filesystems on Cluster One
##########################

Cluster One uses a combination of high-performance and research-tier file systems to support a wide range of workloads. Most storage is backed by IBM Spectrum Scale (GPFS), with additional WEKA-based storage for select partitions.

Storage on Cluster One is intended solely for research and educational purposes. Users are expected to manage their data responsibly, and storage quotas are enforced per group.

General Guidelines
******************

- **Data stored on ARCH-managed filesystems is not backed up by default.**
- Users are responsible for maintaining their own backups or purchasing backup services.
- Storage increases are granted on a case-by-case basis, based on need and system capacity.
- ARCH reserves the right to delete or move data as necessary to maintain system stability.
- Temporary storage for large projects is available -- please contact ARCH staff.

.. important::
  Data subject to restrictions -- including but not limited to, HIPAA, PHI, or CUI -- is **not permitted** on Cluster One.
  If your research involves an IRB and the data is de-identified, please reach out to
  `help@arch.jhu.edu <mailto:help@arch.jhu.edu>`__ for further guidance prior to storing or processing any data.

Filesystems at a Glance
***********************

TODO: Filesystem table may need to be updated after the merge is finalized. The following reflects the combined storage systems available on Cluster One.

.. list-table::
   :header-rows: 1
   :widths: 18 12 10 8 15 10

   * - File System
     - System Type
     - Total Size
     - Default Quota
     - Intended for
     - Backed Up?

   * - /home/
     - NVMe SSD (ZFS) / WEKA
     - TODO
     - 50 GB per user
     - Configs, notebooks, small scripts
     - Limited

   * - /scratch4/
     - IBM GPFS
     - 3.8 PB
     - 1 TB per group
     - Small files, working data (genomics, bioinformatics)
     - No

   * - /scratch16/
     - IBM GPFS
     - 3.6 PB
     - By request
     - Large files, working data (physics, simulations)
     - No

   * - /data/
     - IBM GPFS
     - 5.1 PB
     - 1 TB per group
     - Long-term, high-value data
     - No

   * - /scratch/
     - WEKA
     - 800 TB
     - 20 TB per group
     - AI/ML workloads, GPU nodes
     - No

   * - /vast/
     - VAST (Krieger IT)
     - N/A
     - By request
     - High-performance flash storage
     - No

Local Scratch
=============

Each compute node has a local 1+ TB NVMe hard drive mounted as "/tmp". The latency to these NVMe flash drives is orders of magnitude lower than for spinning disk (GPFS), usually microseconds versus milliseconds. Users who read/write many small files may want to use this space instead of the scratch filesystems. It will provide better performance. Make sure you write files back to "scratch" or "data" before the job ends. Likewise, make sure you delete files and directories at the end of jobs.

/home/
======

Each user receives 50 GB of storage in ``/home/``. This area is intended for frequently used code, scripts, and configuration files.

.. warning::
   ``/home/`` is **not intended for I/O** from jobs. Use ``/scratch`` instead.

Limited file recovery may be possible, but is **not guaranteed**.

/scratch4/
==========

This default scratch space is optimized for high file-count and smaller file sizes using a 4 MB block size.

- 1 TB per group (default)
- Suitable for: **genomics, bioinformatics, mechanical engineering**
- Purged automatically after 90 days of inactivity (based on access time)
- Not backed up or recoverable

/scratch16/
===========

This scratch space is optimized for sequential I/O and streaming workloads.

- No default allocation. Available **by request** with justification
- 16 MB block size
- Suitable for: **physics, large-scale simulations, chemistry**
- Same purge policy applies
- Not backed up or recoverable

/data/
======

This area is ideal for storing high-value data generated during or after computation, including processed results and intermediate analysis. Files you want to retain longer than the scratch purge window should be stored here.

- 1 TB per group (default)
- ``/data/`` is **not backed up**, so users must implement their own preservation strategy.

/vast/
======

This all-flash storage is provided by **Krieger IT** for researchers who have purchased space.

- Mounted at ``/vast/`` on Rockfish nodes
- Available to all JHU researchers
- Request form and pricing info:

  - `Request VAST Storage & View Pricing <https://jh.qualtrics.com/jfe/form/SV_4SJJTnPMp8dHKwm>`__

Quota Reporting with ``quotas.py``
**********************************

ARCH provides a command-line tool called ``quotas.py`` to help users monitor their disk usage across the filesystems.

This tool runs automatically at login and displays the current usage for your home directory and your research group's shared allocations. However, you can manually run it at any time to check your usage or monitor quotas for your research group.

Usage:

.. code-block:: console

   quotas.py

Example Output:

.. code-block:: text

  +---------------------------------------------------------------------+
  |          Usage for user as of Thu May  1 10:01:05 2025              |
  +---------------------------+-------------+-------------+-------------+
  |             FS            |     Used    |    Quota    |    Used %   |
  +---------------------------+-------------+-------------+-------------+
  |      /home/$user/          |   64.33 MB  |   50.00 GB  |    0.13%    |
  |     /scratch/$PI/          |   83.27 GB  |   10.00 TB  |      0%     |
  +---------------------------+-------------+-------------+-------------+

Fields:

- **FS**: Filesystem Path
- **Used**: Current usage for the filesystem
- **Quota**: Allocated quota for the user or group
- **Used %**: Percentage of usage relative to quota

.. tip::
   File quotas are just as important as storage size. Exceeding your file quota may prevent new files from being written even if space remains.
