# Step 5: Troubleshooting

.. container:: sw-step-badge

   .. container:: sw-step-n

      05

   .. container::

      .. container:: sw-step-info-title

         Troubleshooting

      .. container:: sw-step-info-sub

         Step 5 of 5

Problems can show up at any point in Zero to Robot. Find the section
below that matches where you're stuck.

.. rubric:: Code & Drive Issues (Step 4)

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item-card:: "No Robot Communication"
      :class-card: sw-card-err

      Check Wi-Fi connection to robot network.
      Verify Systemcore and radio are powered. Try USB deploy cable as a fallback.

   .. grid-item-card:: "No Robot Code"
      :class-card: sw-card-err

      Code was not deployed or crashed on startup.
      Re-deploy from VS Code. Check the Driver Station log for exceptions.

   .. grid-item-card:: Robot does not move
      :class-card: sw-card-err

      Verify joystick axis mapping in Driver Station USB tab.
      Confirm motor controller wiring and correct PWM port numbers in code.

   .. grid-item-card:: Robot moves in wrong direction
      :class-card: sw-card-err

      Invert one motor controller in code (``motor.setInverted(true)``)
      or flip the motor power leads on the controller.

.. rubric:: Radio & Configuration Issues (Step 3)

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item-card:: Can't reach radio.local
      :link: ../step-3/radio-programming
      :link-type: doc
      :class-card: sw-card-frc

      Disconnect other network connections, disable firewalls, and confirm
      mDNS is installed. Full steps in the Troubleshooting section of the
      full radio guide.

   .. grid-item-card:: Systemcore update won't finish
      :link: ../step-3/imaging-your-systemcore
      :link-type: doc
      :class-card: sw-card-shared

      On Wi-Fi, the Systemcore reboots as part of the update; reconnect
      and refresh the page. On USB, look for the success message.

.. rubric:: Install Issues (Step 2)

.. grid:: 1
   :gutter: 3

   .. grid-item-card:: WPILib VS Code won't open or commands are missing
      :link: ../step-2/index
      :link-type: doc
      :class-card: sw-card-shared

      Confirm you're launching the **WPILib** VS Code shortcut, not the
      system VS Code install. Re-run the installer if the WPILib icon
      doesn't appear in the activity bar.

.. rubric:: Still Stuck?

.. card:: Support Resources
   :link: ../../software/support/support-resources
   :link-type: doc
   :class-card: sw-card-shared

   Community forums and additional documentation for FRC and FTC teams.

.. container:: sw-nav

   :doc:`← Step 4: Write and Drive <../step-4/index>`

.. toctree::
   :maxdepth: 1
   :hidden:
