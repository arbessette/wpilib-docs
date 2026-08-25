# Step 3: Configure Your Control System

.. container:: sw-step-badge

   .. container:: sw-step-n

      03

   .. container::

      .. container:: sw-step-info-title

         Configure Your Control System

      .. container:: sw-step-info-sub

         Step 3 of 5

Before you can deploy code, the Systemcore must be configured with the
current season's software and the radio must be programmed for your
team number.

.. warning::

   **Re-configure every season.**
   The Systemcore image is season-specific. A robot that worked last year will
   not accept code deploys until the Systemcore is updated with the current
   year's image.

.. rubric:: Part 1: Image the Systemcore

No special software is required, the Systemcore images itself through its
own web interface at ``robot.local``.

1. Download the current season's ``.llupdate`` file from the
   `Systemcore releases page <https://github.com/LimelightVision/systemcore-os-public/releases/latest>`_.
   Make sure to grab the alpha or beta update that matches your unit.
2. Connect to the Systemcore over Wi-Fi or USB.
3. Open a browser and navigate to ``robot.local``.
4. Click the settings (gear) icon and open the configure/update section.
5. Under **OS Update**, click **Select File**, choose the ``.llupdate``
   file you downloaded, then click **Flash Update**. This takes several
   minutes.

.. note::

   **USB connection:** a success message appears once the update finishes.

   **Wi-Fi connection:** the Systemcore reboots as part of the update.
   Manually reconnect and refresh the page to see the completion status.

.. card:: Full Systemcore imaging guide
   :link: imaging-your-systemcore
   :link-type: doc
   :class-card: sw-card-shared

   Complete reference, including OS version prerequisites and the
   Limelight Hardware Client fallback for older units.

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item-card:: Using a roboRIO?
      :link: https://docs.wpilib.org/en/stable/index.html
      :link-type: url
      :class-card: sw-card-frc

      **FRC Legacy**
      ^^^
      Teams still running a roboRIO should refer to the
      2026 WPILib docs for imaging instructions.

   .. grid-item-card:: FTC Legacy (REV)?
      :link: https://ftc-docs.firstinspires.org/en/latest/hardware_and_software_configuration/configuring/index.html
      :link-type: url
      :class-card: sw-card-ftc

      **FTC Legacy**
      ^^^
      Teams on REV Control Hub / Expansion Hub should refer to the
      official FTC hardware configuration guide instead. This page
      covers Systemcore only.

.. rubric:: Part 2: Configure the Radio

The steps below are FRC-specific. FTC teams still configure their radio,
it's just built into the Systemcore itself rather than a separate device.
Systemcore-specific radio configuration steps for FTC are still being
written; see :doc:`Step 1: Confirm It's Alive <../step-1/index>` in the
meantime for the built-in connection details.

FRC teams use one of two radios: the current Vivid VH-109, or a legacy
OpenMesh OM5P.

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item-card:: Vivid VH-109
      :class-card: sw-card-frc

      **FRC: Current Standard**
      ^^^
      Follow the steps below to configure this radio.

   .. grid-item-card:: Legacy OpenMesh Radios
      :link: openmesh
      :link-type: doc
      :class-card: sw-card-frc

      **FRC: Legacy Reference**
      ^^^
      Hardware specs, indicator LED meanings, and troubleshooting for
      teams still running OM5P radios.

The Vivid VH109 radio must be programmed with your team number and the
correct firmware before the robot can communicate wirelessly.

1. Connect the radio directly to your computer with an Ethernet cable
   in the :guilabel:`DS` port, and make sure it's powered (Weidmuller
   connectors or PoE).
2. Open a browser and navigate to ``http://radio.local/``.
3. Select :guilabel:`Robot Radio Mode`.
4. Enter your team number and, if desired, a suffix to identify your
   network.
5. Enter the 6 GHz and 2.4 GHz WPA/SAE keys. Teams will use these to
   connect to the robot's network.
6. Repeat the same steps on a second radio in :guilabel:`Access Point
   Mode`, using the exact same team number, suffix, and keys, if you
   have one for testing at home.

.. tip::

   **Only have one radio?** You don't need an access point radio to test
   at home. See the alternative setups in the full radio guide below.

.. card:: Full Radio Programming Guide
   :link: radio-programming
   :link-type: doc
   :class-card: sw-card-frc

   Firmware updates, alternative one-radio setups, and troubleshooting
   for teams that can't reach the configuration page.

.. rubric:: Part 3: Verify Power-Up

- Systemcore boots and status light cycles
- Radio powers on
- Radio SSID appears as <TEAM>_Robot in Wi-Fi list
- Connect laptop to robot Wi-Fi: Driver Station shows
  "Robot Communication" in green

.. container:: sw-nav

   :doc:`← Step 2: Set Up Your Environment <../step-2/index>`

   .. container:: sw-next

      :doc:`Step 4: Write and Drive → <../step-4/index>`

.. toctree::
   :maxdepth: 1
   :hidden:

   imaging-your-systemcore
   radio-programming
   openmesh
