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

   **Going with OnBot or Blockly?** Parts 1-5 below walk through the VS Code
   path. Systemcore-specific OnBot/Blockly deploy-and-drive steps are
   still being written; in the meantime,
   `Running Your OpMode (All Languages) <https://ftc-docs.firstinspires.org/en/latest/programming_resources/tutorial_specific/blocks/running_op_modes/Running-Your-Op-Mode.html>`_
   covers the current system and carries over conceptually.

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

      - **REVLib**: SPARK MAX and SPARK Flex
      - **Phoenix 6**: Talon FX, CANcoder, Pigeon 2
      - **PathplannerLib**: autonomous trajectories
      - **PhotonLib**: PhotonVision camera support

   .. grid-item-card:: How to Add a Library

      - :kbd:`Ctrl+Shift+P` → *WPILib: Manage Vendor Libraries*
      - Select *Install new libraries (online)*
      - Paste the vendor JSON URL from their docs
      - Build the project to download dependencies

.. rubric:: Part 3: Basic Arcade Drive

A minimal working drivetrain. Replace ``PWMSparkMax`` with your actual
controller class.

.. tab-set-code::

   ```java
   // In Robot.java, inside teleopPeriodic()
   PWMSparkMax leftMotor  = new PWMSparkMax(0);
   PWMSparkMax rightMotor = new PWMSparkMax(1);
   DifferentialDrive drive = new DifferentialDrive(leftMotor, rightMotor);

   @Override
   public void teleopPeriodic() {
       // left stick Y = speed, right stick X = rotation
       drive.arcadeDrive(-m_stick.getY(), m_stick.getX());
   }
   ```

   ```c++
   // In Robot.h / Robot.cpp
   frc::PWMSparkMax leftMotor{0};
   frc::PWMSparkMax rightMotor{1};
   frc::DifferentialDrive drive{leftMotor, rightMotor};

   void Robot::TeleopPeriodic() {
     // left stick Y = speed, right stick X = rotation
     drive.ArcadeDrive(-m_stick.GetY(), m_stick.GetX());
   }
   ```

   ```python
   # In robot.py, inside teleopPeriodic()
   self.left_motor = wpilib.PWMSparkMax(0)
   self.right_motor = wpilib.PWMSparkMax(1)
   self.drive = wpilib.drive.DifferentialDrive(self.left_motor, self.right_motor)

   def teleopPeriodic(self):
       # left stick Y = speed, right stick X = rotation
       self.drive.arcadeDrive(-self.stick.getY(), self.stick.getX())
   ```

.. card:: Full drivetrain walkthrough →
   :link: creating-test-drivetrain-program-cpp-java-python
   :link-type: doc
   :class-card: sw-card-shared

   Complete guide: project setup, motor controller configuration,
   and deploy steps for Java, C++, and Python.

.. rubric:: Part 4: Deploy to the Robot

.. grid:: 1 1 2 2
   :gutter: 3

   .. grid-item-card:: Deploy over Wi-Fi

      Connect to the robot Wi-Fi network (XXXX_Robot), then press
      :kbd:`Ctrl+Shift+P` → *WPILib: Deploy Robot Code*.

   .. grid-item-card:: Deploy over USB

      Connect USB-A to USB-B from laptop to Systemcore.
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

      - Robot on floor or safely elevated
      - All team members clear of moving parts
      - Driver Station shows "Robot Code" (green)
      - Joystick connected and recognized in DS
      - Battery voltage above 12.0 V

   .. grid-item-card:: Enable steps

      - Open FRC Driver Station
      - Select **TeleOperated** mode
      - Click **Enable** (or press Enter)
      - Move joystick: robot should respond
      - Press **Disable** (or Spacebar) to stop

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
