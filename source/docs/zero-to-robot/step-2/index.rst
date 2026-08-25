# Step 2: Set Up Your Environment

.. container:: sw-step-badge

   .. container:: sw-step-n

      02

   .. container::

      .. container:: sw-step-info-title

         Set Up Your Environment

      .. container:: sw-step-info-sub

         Step 2 of 5

Choose how you'll write code. **OnBot** runs in the browser with nothing
to install; **VS Code** is the full desktop IDE. Both work for FRC and FTC.

.. tab-set::

   .. tab-item:: OnBot
      :sync: onbot

      OnBot runs directly in the browser, hosted on the Systemcore itself.
      There's nothing to download or install.

      .. note::

         **Systemcore-specific OnBot setup steps are still being written.**
         In the meantime,
         `Running Your OpMode (All Languages) <https://ftc-docs.firstinspires.org/en/latest/programming_resources/tutorial_specific/blocks/running_op_modes/Running-Your-Op-Mode.html>`_
         covers the current system and carries over conceptually.

      .. tip::

         **FRC teams:** OnBot replaces the code editor, not the Driver
         Station. You'll still need the FRC Driver Station installed
         locally for competition; see the **VS Code** tab's Part 2, or
         install it directly from
         `GitHub releases <https://github.com/wpilibsuite/FirstDriverStation-Public>`_.

   .. tab-item:: VS Code
      :sync: vscode

      The WPILib installer and VS Code setup below are the same install for
      **FRC and FTC**. Where a tool or step is program-specific (like the FRC
      Driver Station or simulation), it's labeled.

      .. rubric:: System Requirements

      .. grid:: 1 1 3 3
         :gutter: 3

         .. grid-item-card:: Coding Only
            :class-card: sw-card-shared

            **FRC + FTC: macOS / Linux**
            ^^^
            - macOS 12+ or modern Linux distro
            - WPILib + VS Code for writing code
            - Can run Driver Station for testing only, cannot image Systemcore
            - Deploy code over USB or Wi-Fi (needs network access)
            - Robot simulation is currently FRC only

         .. grid-item-card:: Windows for Coding
            :class-card: sw-card-shared

            **FRC + FTC: Windows**
            ^^^
            - Windows 10 or 11
            - WPILib + VS Code for writing code
            - Robot simulation is currently FRC only

         .. grid-item-card:: Required for Driver Station
            :class-card: sw-card-frc

            **FRC only: Windows**
            ^^^
            - Windows 11 (required for 2027+)
            - 8 GB RAM minimum, 16 GB recommended
            - Driver Station must be run on Windows for competition
            - All WPILib tools available

      .. warning::

         **Windows 10 is no longer supported as of 2027.**
         Upgrade to Windows 11 before installing the Driver Station.

      .. rubric:: Installation Steps

      .. grid:: 1 1 2 2
         :gutter: 3

         .. grid-item-card:: WPILib Installer
            :link: wpilib-setup
            :link-type: doc
            :class-card: sw-card-shared

            **Part 1: FRC + FTC**
            ^^^
            Installs Visual Studio Code, WPILib extensions, and all
            desktop tools (Glass, Elastic, OutlineViewer).
            Required for Java, C++, and Python teams.

         .. grid-item-card:: FRC Driver Station
            :link: first-driver-station
            :link-type: doc
            :class-card: sw-card-frc

            **Part 2: FRC only, Windows**
            ^^^
            Installs the FRC Driver Station, distributed via GitHub releases.
            Required on the laptop that will drive the robot at competition.

         .. grid-item-card:: RobotPy Setup
            :link: python-setup
            :link-type: doc
            :class-card: sw-card-shared

            **Part 3: FRC + FTC, Python teams only**
            ^^^
            Install RobotPy and the required Python packages.
            Java and C++ teams can skip this part.

         .. grid-item-card:: FTC Driver Station
            :link: ../../ftc/index
            :link-type: doc
            :class-card: sw-card-ftc

            **Coming 2027-2028**
            ^^^
            Systemcore and Motioncore bring their own Driver Station app for
            FTC. See the FTC overview for status.

         .. grid-item-card:: Offline Installation
            :link: offline-installation-preparations
            :link-type: doc
            :class-card: sw-card-shared
            :columns: 12 12 12 12

            **Optional: FRC + FTC**
            ^^^
            Preparing to install without internet access?
            Download the offline installer packages in advance.

      .. rubric:: Verify Your Installation

      After completing all parts above, confirm the installation is working:

      .. grid:: 1 2 3 3
         :gutter: 3

         .. grid-item-card:: Open VS Code
            :class-card: sw-card-shared

            **FRC + FTC**
            ^^^
            Launch the WPILib VS Code shortcut (not the system VS Code).
            You should see the WPILib icon (W) in the activity bar.

         .. grid-item-card:: Run WPILib Command
            :class-card: sw-card-shared

            **FRC + FTC**
            ^^^
            Press :kbd:`Ctrl+Shift+P` (or :kbd:`Cmd+Shift+P` on Mac)
            and type *WPILib*. You should see WPILib commands in the palette.

         .. grid-item-card:: Check Driver Station
            :class-card: sw-card-frc

            **FRC only**
            ^^^
            Open the FRC Driver Station (Windows only). It should launch
            without errors. "No Robot Communication" is expected.

      .. tip::

         **Vendor libraries are not installed here.**
         Libraries like REVLib and Phoenix 6 are added per-project in Step 4
         using the WPILib Dependency Manager. You do not need them yet.

.. container:: sw-nav

   :doc:`← Step 1: Build Your Robot <../step-1/index>`

   .. container:: sw-next

      :doc:`Step 3: Configure Your Control System → <../step-3/index>`

.. toctree::
   :maxdepth: 1
   :hidden:

   offline-installation-preparations
   first-driver-station
   wpilib-setup
   python-setup
   step-2-next-steps
