.. include:: <isonum.txt>

# Zero to Robot: Introduction

Welcome to WPILib, the standard programming library for *FIRST*\ |reg| Robotics Competition
(FRC\ |reg|) and FIRST Tech Challenge (FTC).
This guide gets you from parts on a table to a driving robot.

.. rubric:: Choose Your Programming Language
   :class: wl-shared-text

WPILib supports multiple languages. Pick one: your tools and steps are the same regardless of choice.

.. list-table::
   :header-rows: 1
   :widths: 11 16 8 8 22 35

   * - Language
     - Style
     - OnBot
     - Desktop
     - Best for
     - Notes
   * - **Blockly**
     - Graphical (blocks)
     - ✓
     - ✓
     - Beginners with no prior syntax knowledge
     - Outputs Python under the hood
   * - **Java**
     - Text, statically typed
     - ✓
     - ✓
     - New teams, most teams
     - Most community examples
   * - **C++**
     - Text, statically typed
     - ✗
     - ✓
     - Teams that already know C++
     - Highest performance; manual memory management adds
       complexity for beginners
   * - **Python**
     - Text, dynamically typed
     - ✓
     - ✓
     - Teams already using Python
     - Easiest syntax; growing set of community examples
   * - **LabVIEW**
     - Graphical (dataflow)
     - ✓
     - ✗
     - Teams with a LabVIEW background
     - Graphical dataflow programming

All five are available for both FRC and FTC. OnBot runs directly in the
browser on the Systemcore with nothing to install; LabVIEW is OnBot
only.

.. tip::

   **New to programming entirely?** Start with :doc:`Coding Basics <coding-basics>`
   for the core concepts you'll see in robot code, or go straight to
   `Codecademy Java <https://www.codecademy.com/learn/learn-java>`_ or
   `Python learning guides <http://docs.python-guide.org/en/latest/intro/learning/>`_
   for a full course. You can wire and configure your robot first (Steps 1 and 3)
   while learning to code in parallel.

.. rubric:: What You Need
   :class: wl-shared-text

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item-card:: FRC Robot Components
      :class-card: sw-card-frc

      **FRC Hardware**
      ^^^
      - Systemcore controller
      - Power Distribution Hub (PDH) or Panel (PDP)
      - Vivid VH-109 Radio
      - Voltage Regulator Module (VRM), for radio power
      - Motor controllers (SPARK MAX, Talon FX, etc.)
      - Drive motors and wheels
      - 12 V robot battery and fuse
      - Ethernet cable and USB-A cable

   .. grid-item-card:: FTC Robot Components
      :class-card: sw-card-ftc

      **FTC Hardware**
      ^^^
      - Systemcore + Motioncore controllers
      - FTC legal motor controllers
      - Drive motors and wheels
      - 12 V robot battery
      - USB-C cable for programming
      - Wi-Fi for wireless deploy

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item-card:: What Gets Installed
      :class-card: sw-card-shared

      **Software: Only If You Need It**
      ^^^
      OnBot teams don't need to download anything to write code. You only
      need desktop software if you're not using OnBot, or if you're an
      FRC team that needs the Driver Station.

      - **WPILib**: robot programming library + VS Code, for desktop
        development
      - **FRC Driver Station**: required for FRC teams. Runs on Windows,
        macOS, and Linux, but only the Windows version is competition
        legal
      - **RobotPy**: Python framework, for desktop Python teams
      - Vendor libraries (REVLib, Phoenix 6, etc.), installed per project

   .. grid-item-card:: Practice with the XRP
      :link: ../xrp-robot/index
      :link-type: doc
      :class-card: sw-card-shared

      **No Full Robot Yet?**
      ^^^
      The XRP is a desktop robot that runs real WPILib code.
      Great for learning before build season, and for FTC teams
      getting a head start on Systemcore programming.

.. rubric:: The Steps
   :class: wl-shared-text

Complete these in order. You will have a driving robot by the end of
Step 4, and Step 5 is there if you get stuck along the way.

.. note::

   **FTC teams:** Robot assembly and Motioncore-specific wiring arrive with
   Systemcore and Motioncore in the 2027-2028 season, but you don't need to
   wait to get started. Powering and connecting to the Systemcore
   (Step 1, Parts 2-3) and installing your tools (Step 2) already apply
   today. Practice with the :doc:`XRP robot <../xrp-robot/index>` in the
   meantime; the same WPILib code runs on Systemcore when your hardware
   is ready.

.. grid:: 1 2 3 5
   :gutter: 3

   .. grid-item-card:: Build Your Robot
      :link: step-1/index
      :link-type: doc
      :class-card: sw-card-shared

      **01**
      ^^^
      Wire the control system: power distribution, Systemcore,
      motor controllers, and radio.

   .. grid-item-card:: Set Up Your Environment
      :link: step-2/index
      :link-type: doc
      :class-card: sw-card-shared

      **02**
      ^^^
      Choose OnBot or VS Code, and get your Driver Station installed.

   .. grid-item-card:: Configure Your Control System
      :link: step-3/index
      :link-type: doc
      :class-card: sw-card-shared

      **03**
      ^^^
      Configure your Systemcore and radio. Required every season
      before you can deploy code.

   .. grid-item-card:: Write and Drive
      :link: step-4/index
      :link-type: doc
      :class-card: sw-card-shared

      **04**
      ^^^
      Create your first robot project, deploy code to the robot,
      and enable it with the Driver Station.

   .. grid-item-card:: Troubleshooting
      :link: step-5/index
      :link-type: doc
      :class-card: sw-card-shared

      **05**
      ^^^
      Something not working? Find your symptom and fix it here.

.. rubric:: Tips for New Teams
   :class: wl-shared-text

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item::

      .. tip::

         **Get driving first**

         Wire one drive motor per side, deploy arcade drive, and make sure
         the robot moves before adding anything else. Every mechanism you add
         before the robot drives is a variable you can't isolate.

   .. grid-item::

      .. tip::

         **Check the Driver Station log**

         When something goes wrong on the robot, open the Driver Station log
         viewer. It records exactly when the robot disconnected, what threw
         an exception, and why the robot disabled.
