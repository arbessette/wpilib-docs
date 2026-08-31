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

Start at the top of this sequence and stop when a check fails:

1. **Power:** Systemcore and radio status lights are on and the Driver Station
   reports a plausible battery voltage.
2. **Network:** the laptop can reach ``robot.local`` over USB or the robot
   network.
3. **Communication:** the Driver Station communication indicator is green.
4. **Code:** the Driver Station robot-code indicator is green.
5. **Input:** the controller appears in the USB/controller view and its axes
   move.
6. **Output:** the robot is enabled and the configured motor channels match
   the wiring.

The first failed check identifies which section below to investigate. Change
one thing at a time, then repeat the check.

.. rubric:: Code & Drive Issues (Step 4)

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item-card:: "No Robot Communication"
      :class-card: sw-card-err

      Verify Systemcore and radio power first. Connect directly over USB and
      try ``robot.local``. If USB works, investigate the radio, Wi-Fi, team
      number, and firewall rather than redeploying code.

   .. grid-item-card:: "No Robot Code"
      :class-card: sw-card-err

      Communication works, but no user program is running. Re-deploy from
      WPILib VS Code, then inspect the deploy output and Driver Station log for
      the first error. Fix that error before deploying again.

   .. grid-item-card:: Robot does not move
      :class-card: sw-card-err

      Confirm the robot-code and joystick indicators are green. Safely elevate
      the drivetrain, verify axes in the Driver Station USB/controller view,
      then compare the PWM ports or CAN IDs in code with the physical wiring.

   .. grid-item-card:: Robot moves in wrong direction
      :class-card: sw-card-err

      Disable the robot and invert the affected drivetrain side in code. Do not
      swap motor power leads as a substitute for correct software configuration.

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
