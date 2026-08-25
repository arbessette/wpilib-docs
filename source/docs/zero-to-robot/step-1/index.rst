# Step 1: Build Your Robot

.. container:: sw-step-badge

   .. container:: sw-step-n

      01

   .. container::

      .. container:: sw-step-info-title

         Build Your Robot

      .. container:: sw-step-info-sub

         Step 1 of 5

.. rubric:: Part 1: Assemble Your Robot

.. grid:: 1
   :gutter: 3

   .. grid-item-card:: Kitbot / Starter Bot Assembly
      :link: kitbot-starterbot-assembly
      :link-type: doc
      :class-card: sw-card-shared

      **FRC + FTC**
      ^^^
      Step-by-step guide to assembling the FRC Kit of Parts chassis or
      an FTC starter bot into a drive-ready robot.

.. rubric:: Part 2: Power the Systemcore

How you power the Systemcore depends on your hardware revision.

**Alpha units:** connect the Systemcore directly to your robot's power
distribution board. Use 18 AWG wire with white Weidmuller ferrules.

.. warning::

   Do not use both power inputs on Alpha units (Bridge + Weidmuller)
   at the same time.

**Beta units:** power comes through the MicroFit Pwr/Bridge port only.

1. If you have a Motioncore, connect the Pwr/Bridge port on Systemcore
   to the Bridge port on Motioncore using one of the provided MicroFit
   cables.
2. Without a Motioncore, use the MicroFit-to-XT30 cable included in
   your kit. If you need bare wires instead, cut the ends off an XT30
   extension cable.

.. warning::

   Never power the Systemcore through a regulator (such as a VRM). It
   needs battery voltage directly, and some regulators can't supply
   enough current under full load.

.. rubric:: Part 3: Confirm It's Alive

Once powered, the Systemcore hosts its own network so you can connect
to it directly, before any radio or field network is involved.

.. list-table::
   :header-rows: 1

   * - Connection
     - Address
   * - Built-in Wi-Fi SSID
     - ``SYSTEMCORE``
   * - Wi-Fi access point IP
     - ``172.30.0.1``
   * - USB (Windows)
     - ``172.26.0.1``
   * - USB (macOS / Linux)
     - ``172.27.0.1``

.. note::

   Units on OS image 9 or earlier use ``172.28.0.1`` (USB, Windows) or
   ``172.29.0.1`` (USB, macOS/Linux) instead.

.. rubric:: Part 4: Wire the Rest of the Control System

Motor controllers, radio, CAN bus, and pneumatics wiring still follow
the reference guides below.

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item::

      .. rubric:: FRC
         :class: wl-frc-text

   .. grid-item::

      .. rubric:: FTC
         :class: wl-ftc-text

   .. grid-item-card:: Basic Robot Wiring
      :link: basic-robot-wiring
      :link-type: doc
      :class-card: sw-card-frc

      **FRC**
      ^^^
      Simplified wiring reference for drivetrain-only builds.
      Good starting point for rookie teams.

   .. grid-item-card:: Basic FTC Robot Wiring
      :link: ../../ftc/basic-ftc-robot-wiring
      :link-type: doc
      :class-card: sw-card-ftc

      **FTC Coming 2027-2028**
      ^^^
      Covers just enough to power a drivetrain on Systemcore
      and Motioncore. Skip the extras until you're ready.

   .. grid-item-card:: FRC Robot Wiring Overview
      :link: intro-to-frc-robot-wiring
      :link-type: doc
      :class-card: sw-card-frc

      **FRC**
      ^^^
      Full walkthrough of control system wiring with diagrams:
      PDH, radio, motor controllers, and pneumatics.

   .. grid-item-card:: FTC Robot Wiring Overview
      :link: ../../ftc/ftc-robot-wiring-overview
      :link-type: doc
      :class-card: sw-card-ftc

      **FTC Coming 2027-2028**
      ^^^
      Every connection for a competition-ready build, including
      mechanisms and sensors beyond the basic drivetrain.

.. note::

   **These two FRC guides still describe the roboRIO-era control
   system** and haven't been updated for Systemcore yet. Use them for
   PDH, motor controller, and radio wiring; Systemcore itself is
   covered in Part 2 above.

.. tip::

   **Not sure which PDH or PDP you have?**
   The **Power Distribution Hub (PDH)** is the REV Robotics unit
   (rectangular, 20 slots). The older
   **Power Distribution Panel (PDP)** is the Cross The Road Electronics unit
   (oval shape, 16 slots). Both are legal; wiring diagrams for each are in
   the wiring overview above.

.. container:: sw-nav

   :doc:`← Introduction <../introduction>`

   .. container:: sw-next

      :doc:`Step 2: Set Up Your Environment → <../step-2/index>`

.. toctree::
   :maxdepth: 1
   :hidden:

   Kitbot / Starter Bot Assembly <kitbot-starterbot-assembly>
   FRC Robot Wiring Overview <intro-to-frc-robot-wiring>
   Basic Robot Wiring <basic-robot-wiring>
