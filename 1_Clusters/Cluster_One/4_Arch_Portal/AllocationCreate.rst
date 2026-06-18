Creating a PI Account
************************

.. _Arch Portal: TODO: Arch Portal URL

Johns Hopkins Principal Investigators (PIs) may request projects and resource allocations using the `Arch Portal`_. Once an allocation is approved, users may request accounts. PIs or their designated proxies are responsible for adding users to the appropriate allocations once it is created.

Key features of the portal include:

- Requesting new projects and allocations (PIs)
- Managing users and adding them to allocations
- Uploading publications, grants, and ROI reports
- Assigning proxy account managers
- Monitoring usage across groups and allocations

.. warning::
   Allocations are reset quarterly under a "use it or lose it" model. Unused core-hours do not carry over.

.. note::
    All users should review the :doc:`Good Citizen guidelines <../../../4_Support/Citizen>` before requesting an allocation or account.

**Getting Started**

When you first navigate to the `Arch Portal`_, you'll be prompted to log in or create an account.
PIs should click **Request Allocation (only for PIs)**.

TODO: Add screenshot of Arch Portal registration page


You will then be asked to enter your JHED ID (as your username), email address, and a password.
**Important:** You must use your JHED ID. Using anything else will delay access and break services such as Globus.

TODO: Add screenshot of registration form


After submitting your request, you should see a confirmation message. You can then log in with your new credentials.

TODO: Add screenshot of confirmation page


**Upgrading to PI Status**

After logging in, you'll land on your dashboard. To enable project and allocation creation, upgrade your account to PI:

1. Click your username in the top-right corner.
2. Select **User Profile**.
3. Click **Upgrade Account**.

TODO: Add screenshots of login/dashboard and upgrade flow


Once administrators approve your request, your **PI Status** will change from a red X to a green check mark.

TODO: Add screenshot showing PI status approval


**Creating a Project**

Once PI status is approved, you can create a project:

1. From the top menu, select **Project -> Add a Project**.
2. Fill out the project form with a clear title and detailed description.

TODO: Add screenshots of project creation flow


In the description, include:

- Scientific or academic goals
- The type of computations or analyses you expect to run
- Resource requirements (cores, GPUs, storage)
- Anticipated outcomes (e.g., publications, presentations, deliverables)

This information helps administrators allocate resources appropriately.

**Requesting a Resource Allocation**

After creating a project, open the project page and click **Request Resource Allocation**.

TODO: Add screenshots of allocation request flow


Provide a justification for your allocation request, explaining how the resources will support your project's goals.

**Adding Users**

With a project and allocation in place, you can add users:

1. Click **Add Users** on the project page.
2. Search by JHED ID. Users must have already created an account in the `Arch Portal`_ to appear.

TODO: Add screenshots of user management


Select the users to add. Accounts are not active on the cluster until this step is completed.
You may also assign certain users as **Managers**, giving them rights to manage other users within the project.

**Project Summary**

After adding users and requesting allocations, your project page will display active users, allocations, and other details.

TODO: Add screenshot of project summary page
