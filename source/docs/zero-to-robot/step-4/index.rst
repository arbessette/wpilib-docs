# Step 4: Write and Drive

.. container:: sw-step-badge

   .. container:: sw-step-n

      04

   .. container::

      .. container:: sw-step-info-title

         Write and Drive

      .. container:: sw-step-info-sub

         Step 4 of 5

.. rubric:: Choose Your Environment

Writing the code itself is largely the same experience across FRC and FTC.
Both programs can write code in VS Code (Part 1 below covers Java, C++,
and Python), directly on the Systemcore through OnBot, or visually
through Blockly, with no local install required for either.

.. grid:: 1 1 3 3
   :gutter: 3

   .. grid-item-card:: VS Code (Java, C++, Python)
      :link: ../step-2/wpilib-setup
      :link-type: doc
      :class-card: sw-card-shared

      **FRC + FTC**
      ^^^
      The full desktop IDE. Covered in Part 1 below: project templates,
      vendor libraries, and deploy.

   .. grid-item-card:: OnBot (Java, Python, LabVIEW)
      :link: ../../ftc/index
      :link-type: doc
      :class-card: sw-card-shared

      **FRC + FTC**
      ^^^
      Write, save, and deploy code directly from a browser running on
      the Systemcore itself. No VS Code install required.

   .. grid-item-card:: Blockly
      :link: https://ftc-docs.firstinspires.org/en/latest/programming_resources/blocks/Blocks-Tutorial.html
      :link-type: url
      :class-card: sw-card-shared

      **FRC + FTC**
      ^^^
      Drag-and-drop visual programming in the browser. A good starting
      point even if you already know Java.

.. note::

   **Going with OnBot or Blockly?** Parts 1-5 below are the VS Code path;
   they are not OnBot or Blockly instructions. Systemcore-specific creation,
   deployment, and driving steps for those environments are still being
   written. Current FTC Control Hub users should follow the
   `official FTC programming tutorials
   <https://ftc-docs.firstinspires.org/en/latest/programming_resources/index.html>`_.

.. card:: Blocks Programming Samples →
   :link: blocks-drivetrain-samples
   :link-type: ref
   :class-card: sw-card-shared

   **FRC + FTC: Blockly**
   ^^^
   Preview the built-in differential-drive and mecanum projects, then open
   :guilabel:`Samples...` in the Blocks interface to create an editable copy.

.. rubric:: Part 1: Create Your Robot Project

Open the WPILib VS Code and create a new project from the template.

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item-card:: Create a Drivetrain Program
      :link: creating-test-drivetrain-program-cpp-java-python
      :link-type: doc
      :class-card: sw-card-shared

      **FRC + FTC: Java / C++ / Python**
      ^^^
      Step-by-step guide: new project, vendor libraries, arcade drive
      code, and deploy to the robot.

   .. grid-item-card:: New Project Checklist

      **Quick reference**
      ^^^
      - Open WPILib VS Code (not system VS Code)
      - Press :kbd:`Ctrl+Shift+P` → *WPILib: Create a new project*
      - Choose **Template → TimedRobot**
      - Set team number and project folder
      - Add vendor libraries via *Manage Vendor Libraries*

.. rubric:: Part 2: Install Vendor Libraries

Vendor libraries add support for motor controllers and sensors.
They are per-project and must be added each time you create or import a
project.

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item-card:: Common Vendor Libraries

      - **REVLib**: SPARK MAX, SPARK Flex, and the 2027 A301 on Motioncore
      - **Phoenix 6**: Talon FX, CANcoder, Pigeon 2
      - **PathplannerLib**: autonomous trajectories
      - **PhotonLib**: PhotonVision camera support

   .. grid-item-card:: How to Add a Library

      - :kbd:`Ctrl+Shift+P` → *WPILib: Manage Vendor Libraries*
      - Select *Install new libraries (online)*
      - Paste the vendor JSON URL from their docs
      - Build the project to download dependencies

.. note::

   **Using an A301 with Motioncore?** Keep its firmware and REVLib versions
   compatible, and identify the Motioncore channel with ``CANBusMap`` rather
   than a raw integer. Motioncore channel D0 is not the same bus as Systemcore
   bus 0. See the current `A301 testing guide
   <https://github.com/wpilibsuite/SystemcoreTesting/blob/main/A301.md>`_
   for the required version pair and channel examples.

.. rubric:: Part 3: Basic Arcade Drive

A minimal drivetrain has three long-lived objects: the two motor controllers
and the ``DifferentialDrive``. Create them once as fields of the robot class
(or in its constructor), not inside ``teleopPeriodic()``. The periodic method
should only read the controller and command the existing drive object.

.. tab-set-code::

   ```java
   // Fields in the Robot class; construct these only once.
   private final PWMSparkMax leftMotor = new PWMSparkMax(0);
   private final PWMSparkMax rightMotor = new PWMSparkMax(1);
   private final DifferentialDrive drive =
       new DifferentialDrive(leftMotor::setThrottle, rightMotor::setThrottle);
   private final Gamepad controller = new Gamepad(0);

   @Override
   public void teleopPeriodic() {
       drive.arcadeDrive(-controller.getLeftY(), -controller.getRightX());
   }
   ```

   ```c++
   // Members of the Robot class; construct these only once.
   wpi::PWMSparkMax leftMotor{0};
   wpi::PWMSparkMax rightMotor{1};
   wpi::DifferentialDrive drive{
       [&](double output) { leftMotor.SetThrottle(output); },
       [&](double output) { rightMotor.SetThrottle(output); }};
   wpi::Gamepad controller{0};

   void Robot::TeleopPeriodic() {
     drive.ArcadeDrive(-controller.GetLeftY(), controller.GetRightX());
   }
   ```

   ```python
   def __init__(self):
       super().__init__()
       # Construct hardware objects only once, during robot startup.
       self.left_motor = wpilib.PWMSparkMax(0)
       self.right_motor = wpilib.PWMSparkMax(1)
       self.drive = wpilib.DifferentialDrive(
           self.left_motor, self.right_motor
       )
       self.controller = wpilib.Gamepad(0)

   def teleopPeriodic(self):
       self.drive.arcadeDrive(
           -self.controller.getLeftY(), -self.controller.getRightX()
       )
   ```

.. card:: Full drivetrain walkthrough →
   :link: creating-test-drivetrain-program-cpp-java-python
   :link-type: doc
   :class-card: sw-card-shared

   Complete guide: project setup, motor controller configuration,
   and deploy steps for Java, C++, and Python.

.. important::

   The snippets above show object placement and control flow, but omit imports,
   class declarations, motor inversion, and safety setup. Start from the tested
   complete example in the full drivetrain walkthrough rather than pasting an
   isolated snippet into an empty file.

.. rubric:: Part 4: Deploy to the Robot

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item-card:: Deploy over Wi-Fi

      Connect to the robot Wi-Fi network (XXXX_Robot), then press
      :kbd:`Ctrl+Shift+P` → *WPILib: Deploy Robot Code*.

   .. grid-item-card:: Deploy over USB

      Connect the laptop to the Systemcore's USB device port with the
      appropriate data-capable cable.
      WPILib auto-detects USB and deploys without Wi-Fi.

.. card:: Running and testing your program →
   :link: running-test-program
   :link-type: doc
   :class-card: sw-card-frc

   Connect Driver Station, plug in joystick, verify robot code
   is running, and enable teleop for the first time.

.. rubric:: Part 5: Enable and Drive

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item-card:: Pre-enable checklist

      - First test: robot safely elevated with every drive wheel off the floor
      - All team members clear of moving parts
      - Driver Station shows "Robot Code" (green)
      - Joystick connected and recognized in DS
      - Driver Station reports a plausible robot battery voltage

   .. grid-item-card:: Enable steps

      - Open FRC Driver Station
      - Select **TeleOperated** mode
      - Announce that the robot is about to enable, then click **Enable**
      - Move joystick: robot should respond
      - Click **Disable** or press :kbd:`Enter` to stop

.. warning::

   The :kbd:`Space` bar triggers **Emergency Stop**; it is not the ordinary
   disable shortcut. An emergency-stopped robot must be rebooted before it can
   be enabled again.

.. tip::

   **Something not working?** See :doc:`Step 5: Troubleshooting <../step-5/index>`.

.. container:: sw-success

   .. container:: sw-success-h

      ✓ You have a driving robot.

   Explore the
   :doc:`Command-Based framework <../../software/commandbased/index>`
   for structured programs,
   :doc:`path planning <../../software/pathplanning/index>`
   for autonomous, and
   :doc:`simulation <../../software/wpilib-tools/robot-simulation/index>`
   to test code without hardware.

.. container:: sw-nav

   :doc:`← Step 3: Configure Your Control System <../step-3/index>`

   .. container:: sw-next

      :doc:`Step 5: Troubleshooting → <../step-5/index>`

.. toctree::
   :maxdepth: 1
   :hidden:

   creating-test-drivetrain-program-cpp-java-python
   running-test-program
