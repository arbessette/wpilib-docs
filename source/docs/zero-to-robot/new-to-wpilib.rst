New to WPILib
==============

You know how to write code. WPILib is what lets that code talk to the
robot: motors, sensors, and everything else wired into the control system.

.. rubric:: How the Pieces Fit Together
   :class: wl-shared-text

Same building blocks whether you're on FRC or FTC.

.. grid:: 1 2 3 5
   :gutter: 3

   .. grid-item-card:: Robot Class

      The entry point for your program. Defines what runs when the robot
      is enabled, disabled, or switches modes.

   .. grid-item-card:: Subsystems

      A piece of the robot (drivetrain, arm, intake) wrapped in code
      that owns its own motors and sensors.

   .. grid-item-card:: Commands

      An action a subsystem performs, like "drive forward" or "raise the
      arm to height." You schedule commands; you don't call them directly.

   .. grid-item-card:: OpModes

      Coming from FTC, this is what you already know. A WPILib Robot
      Class does the same job.

   .. grid-item-card:: Hardware APIs

      The classes for motor controllers, encoders, and other devices.
      This is what actually puts a signal on the wire.

.. rubric:: Where FRC and FTC Differ
   :class: wl-shared-text

Really just the Driver Station and what the motors plug into. FRC uses
the FRC Driver Station, with motor controllers wired directly to the
Systemcore; FTC gets its own Driver Station app, and motors and servos
plug into Motioncore instead. Everything above is the same either way.
The :doc:`Zero to Robot introduction <introduction>` covers those
program-specific steps.

.. tip::

   **Need to back up?** If the robot still needs to be built or wired,
   start with the :doc:`hardware overview </docs/hardware/hardware-basics/hardware-overview>`
   before writing code against hardware that isn't connected yet.

.. container:: sw-nav

   .. container:: sw-next

      :doc:`Continue to Zero to Robot: Introduction → <introduction>`
