Frequently Asked Questions
##########################

.. contents::
   :local:
   :depth: 1

.. dropdown:: What type of data can I upload ARCH systems?

   Data subject to restrictions - including but not limited to, HIPAA, PHI, or CUI is **not permitted** on Cluster One.  
   If your research involves an IRB and the data is de-identified, please reach out to  
   `help@arch.jhu.edu <mailto:help@arch.jhu.edu>`__ for further guidance, prior to storing or processing any data.

.. dropdown:: How do I connect to a cluster?

   Use your JHED ID and run:

   .. code-block:: console

      ssh -XY <your_jhed>@login.clusterone.arch.jhu.edu

.. dropdown:: What default resources do I receive?

   TODO: Each user/group receives

.. dropdown:: How do I request an allocation?

   PIs must submit a short proposal through the Arch Portal.  
   TODO: Allocations are available for standard, GPU, and large-memory usage.  
   For more information, visit :doc:`Accounting portal <../1_Clusters/Cluster_One/4_Arch_Portal/index>`.

.. dropdown:: How can I request a piece of software or feature become available?

   For requests related to software installations or new features, please use the following form:

   - `Software Request Form <https://jh.qualtrics.com/jfe/form/SV_d5aGrhrF7ytYMQK>`__

.. dropdown:: How do I find my group or personal utilization?

   .. code-block:: console

      sbalance -a <group>
      test-sbalance -u $USER

.. dropdown:: How do I request interactive jobs?

   Use the `interact` utility to request interactive sessions.

   .. code-block:: console

      interact -usage

.. dropdown:: How do I select the correct Slurm account?

   If you have access to multiple accounts, specify one using:

   .. code-block:: console

      #SBATCH -A johndoe1

.. dropdown:: How do I attach to a compute node where my job is running?

   First, find the job and node using `sqme`, then attach:

   .. code-block:: console

      srun --jobid=<job_id> -w <node> --pty /bin/bash

.. dropdown:: How do I check job efficiency?

   Use `seff`, `reportseff`, or `jobstats` after your job completes:

   .. code-block:: console

      seff <job_id>
      reportseff <job_id>
      jobstats <job_id> 

   .. note::
      Jobstats is only available for GPU jobs.

.. dropdown:: How do I download large datasets?

   Use Globus to transfer data.  
   For large numbers of small files, compress them into tarballs first:

   .. code-block:: console

      tar -czf mydata.tgz mydata/

.. dropdown:: How do I use FileZilla?

   TODO