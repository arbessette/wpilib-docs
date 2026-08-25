# Programming Snippets

Quick, copy-paste code for common tasks. Each snippet links to the full
reference page for more detail.

.. rubric:: Motors

Spin a motor at a set speed:

.. tab-set::

   .. tab-item:: Java
      :sync: java

      .. code-block:: java

         private final Spark m_motor = new Spark(0);

         public void runIntake() {
           m_motor.set(0.8);
         }

   .. tab-item:: C++
      :sync: c++

      .. code-block:: c++

         wpi::Spark m_motor{0};

         void RunIntake() {
           m_motor.Set(0.8);
         }

   .. tab-item:: Python
      :sync: python

      .. code-block:: python

         self.motor = wpilib.Spark(0)

         def run_intake(self):
             self.motor.set(0.8)

   .. tab-item:: Blocks
      :sync: blocks

      .. admonition:: Coming Soon

         A Blocks (Blockly) version of this snippet will be added here.

   .. tab-item:: LabVIEW
      :sync: labview

      .. admonition:: Coming Soon

         A LabVIEW version of this snippet will be added here.

See :doc:`Using Motor Controllers </docs/software/hardware-apis/motors/using-motor-controllers>`
for the full guide, including CAN motor controllers and where to put this
code in Command-Based vs. TimedRobot programs.

.. rubric:: Sensors

Read a digital input (limit switch, beam break, etc.):

.. tab-set::

   .. tab-item:: Java
      :sync: java

      .. remoteliteralinclude:: https://raw.githubusercontent.com/wpilibsuite/allwpilib/v2027.0.0-alpha-6/wpilibjExamples/src/main/java/org/wpilib/snippets/digitalinput/Robot.java
         :language: java
         :lines: 15-16,20-21

   .. tab-item:: C++
      :sync: c++

      .. remoteliteralinclude:: https://raw.githubusercontent.com/wpilibsuite/allwpilib/v2027.0.0-alpha-6/wpilibcExamples/src/main/cpp/snippets/DigitalInput/cpp/Robot.cpp
         :language: c++
         :lines: 15-17,21-22

   .. tab-item:: Python
      :sync: python

      .. admonition:: Coming Soon

         A Python version of this snippet will be added here.

   .. tab-item:: Blocks
      :sync: blocks

      .. admonition:: Coming Soon

         A Blocks (Blockly) version of this snippet will be added here.

   .. tab-item:: LabVIEW
      :sync: labview

      .. admonition:: Coming Soon

         A LabVIEW version of this snippet will be added here.

See :doc:`Digital Inputs </docs/software/hardware-apis/sensors/digital-inputs-software>`
for the full guide, plus analog inputs, encoders, and gyros.

.. rubric:: Autonomous & Loops

.. admonition:: Coming Soon

   Common autonomous and loop patterns (timed sequences, state machines,
   command groups) will be added here.

.. toctree::
   :maxdepth: 1
   :hidden:
