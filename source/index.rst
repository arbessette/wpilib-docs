.. include:: <isonum.txt>

.. meta::
   :google-site-verification: POR_nG8b56eXGxmUIutST7jcA_Vl58ypSdJTzJ1g0zg

WPILib Documentation
====================

.. raw:: html

   <div class="wl-hero">
     <h1 class="wl-hero-title">
       Welcome!
     </h1>
     <p class="wl-hero-copy">
       WPILib is the standard programming library for <em>FIRST</em> Robotics,
       supporting teams competing in
       <strong class="wl-hero-frc"><em>FIRST</em> Robotics Competition (FRC)</strong>
       and
       <strong class="wl-hero-ftc"><em>FIRST</em> Tech Challenge (FTC)</strong>.
     </p>
   </div>

   <div id="landing-tab-root">

     <!-- ── TAB SELECTOR ──────────────────────────── -->
     <div class="wl-tab-selector">
       <p class="wl-tab-prompt">Where are you starting from?</p>
       <div class="wl-tab-buttons">
         <button class="wl-tab-btn" id="btn-new" onclick="wlSelectTab('new')">New to FIRST Programming</button>
         <button class="wl-tab-btn" id="btn-returning" onclick="wlSelectTab('returning')">Returning WPILib User</button>
       </div>
     </div>

     <!-- ── NEW USER PANEL ────────────────────────── -->
     <div class="wl-panel" id="panel-new">

       <!-- Screen 1: Experience level -->
       <div id="new-s1">
         <div class="wl-welcome">
           <h2 class="wl-welcome-h">You're in the right place.</h2>
           <p class="wl-welcome-p">No coding background needed. We'll get your tools installed and your robot moving.</p>
         </div>
         <h3 class="wl-sh">Where are you right now?</h3>
         <div class="wl-legend">
           <span class="wl-legend-item"><span class="wl-legend-dot wl-legend-dot-frc"></span>FRC</span>
           <span class="wl-legend-item"><span class="wl-legend-dot wl-legend-dot-ftc"></span>FTC</span>
           <span class="wl-legend-item"><span class="wl-legend-dot wl-legend-dot-shared"></span>Shared</span>
           <span class="wl-legend-note">Every card below is clickable.</span>
         </div>
         <a class="wl-card wl-card-shared wl-btn wl-feature-card" href="docs/zero-to-robot/introduction.html">
           <span class="wl-num wl-shared-text">→</span>
           <div>
             <div class="wl-card-title">Zero to Robot</div>
             <div class="wl-card-desc">The full path: wire your robot, install tools, configure, and drive.</div>
           </div>
         </a>
         <div class="wl-tip wl-tip-shared">
           <strong>Already written code before?</strong>
           See <a href="docs/zero-to-robot/new-to-wpilib.html">New to WPILib</a> first to understand how the pieces fit together.
         </div>
       </div>

     </div>

     <!-- ── RETURNING PANEL ────────────────────────── -->
     <div class="wl-panel" id="panel-returning">

       <div class="wl-welcome">
         <h2 class="wl-welcome-h">Welcome back. Here is what has changed for 2027.</h2>
         <p class="wl-welcome-p">Run through the checklist below before your first practice session. Several tools were removed in 2027 : check the deprecations section if you have not yet migrated.</p>
       </div>

       <div class="wl-grid">
         <a class="wl-card wl-card-shared wl-btn" href="docs/zero-to-robot/returning.html">
           <span class="wl-num wl-shared-text">0</span>
           <div>
             <div class="wl-card-title">Returning this season</div>
             <div class="wl-card-desc">The full FRC checklist and FTC status, in one place.</div>
           </div>
         </a>
         <a class="wl-card wl-card-shared wl-btn" href="docs/zero-to-robot/step-2/index.html">
           <span class="wl-num wl-shared-text">1</span>
           <div>
             <div class="wl-card-title">Ready to install</div>
             <div class="wl-card-desc">Skip the explanation and go straight to installing WPILib and your dev tools.</div>
           </div>
         </a>
       </div>

       <div class="wl-ret-grid">

         <!-- ── FRC column ── -->
         <div class="wl-ret-column">

           <div class="wl-ret-card wl-ret-frc">
             <div class="wl-ret-label wl-frc-label">FRC</div>
             <h3 class="wl-ret-h">Pre-Season Checklist</h3>
             <ul>
               <li>Download and run the <strong><a href="docs/zero-to-robot/step-2/wpilib-setup.html">2027 WPILib installer</a></strong></li>
               <li><strong><a href="docs/software/systemcore-info/index.html">Update your Systemcore</a></strong> if needed</li>
               <li>Use <strong><a href="docs/software/vscode-overview/importing-last-years-robot-code.html">Import Project</a></strong> in VS Code to migrate your 2026 code</li>
               <li><strong><a href="docs/software/vscode-overview/3rd-party-libraries.html">Re-add all vendor libraries</a></strong> : they do not carry over on import</li>
               <li>Check for <strong><a href="docs/software/vscode-overview/3rd-party-libraries.html">vendor library updates</a></strong> in the Dependency Manager</li>
               <li>Test with the <strong><a href="docs/software/wpilib-tools/robot-simulation/simulation-gui.html">simulator</a></strong> before deploying to hardware</li>
             </ul>
           </div>

           <div class="wl-ret-card wl-ret-frc">
             <div class="wl-ret-label wl-frc-label">FRC</div>
             <h3 class="wl-ret-h">Removed in 2027 : No Longer Available</h3>
             <p class="wl-ret-copy">These tools were <strong>removed in the 2027 season</strong>. Migrate now if you haven't already.</p>
             <ul>
               <li><strong>Shuffleboard</strong> : migrate to <a href="https://github.com/Gold872/elastic-dashboard">Elastic</a> or AdvantageScope</li>
               <li><strong>SmartDashboard</strong> : migrate to Glass or Elastic (uses deprecated NT v3)</li>
               <li><strong>PathWeaver</strong> : migrate to <a href="https://github.com/mjansen4857/pathplanner">PathPlanner</a> or <a href="https://sleipnirgroup.github.io/Choreo/">Choreo</a></li>
               <li><strong>RobotBuilder</strong> : will be removed with control system change in 2027</li>
             </ul>
           </div>

           <div class="wl-ret-card wl-ret-frc">
             <div class="wl-ret-label wl-frc-label">FRC</div>
             <h3 class="wl-ret-h">What is New for 2027</h3>
             <ul>
               <li>FRC now uses Systemcore: see the hardware migration guide</li>
               <li>2027 field images and AprilTag layout data included in WPILib</li>
               <li>Windows 10 is no longer supported: Windows 11 is required</li>
               <li>Vendor library updates required: check the Dependency Manager</li>
             </ul>
             <a href="docs/yearly-overview/index.html" class="wl-frc-text wl-ret-link">Full 2027 changelog</a>
           </div>

         </div>

         <!-- ── FTC + shared column ── -->
         <div class="wl-ret-column">

           <div class="wl-ret-card wl-ret-ftc">
             <div class="wl-ret-label wl-ftc-label">FTC</div>
             <h3 class="wl-ret-h">FTC Teams : Your Options Right Now</h3>
             <p class="wl-ret-copy wl-ret-copy-spacious">WPILib FTC support launches with Systemcore in fall 2027 for the 2027-2028 FTC season. The FRC Systemcore release is earlier, in January 2027:</p>
             <strong class="wl-ret-subhead">Using REV Control Hub / Expansion Hub?</strong>
             <ul class="wl-ret-compact-list">
               <li>Continue programming with the <strong>FTC SDK</strong> as normal : Java or Blocks</li>
               <li>Full documentation at <a href="https://ftc-docs.firstinspires.org">ftc-docs.firstinspires.org</a></li>
               <li>REV Duo hardware remains legal and fully supported for the current season</li>
             </ul>
             <strong class="wl-ret-subhead wl-ret-subhead-spaced">Using Systemcore with WPILib?</strong>
             <ul class="wl-ret-compact-list">
               <li>Systemcore and Motioncore bring full WPILib support to FTC</li>
               <li>Same Java / C++ / Python toolchain as FRC : skills transfer directly</li>
               <li>Try the <a href="docs/xrp-robot/index.html">XRP Platform</a> to start learning WPILib today</li>
               <li><a href="docs/ftc/index.html">WPILib FTC overview</a></li>
             </ul>
           </div>

           <div class="wl-ret-card wl-ret-shared">
             <div class="wl-ret-label wl-shared-label">FRC + FTC</div>
             <h3 class="wl-ret-h">Looking Ahead to 2028</h3>
             <ul>
               <li>Continued improvements to <strong>Systemcore</strong> and <strong>Motioncore</strong> toolchains</li>
               <li>Expanded <strong>FTC</strong> WPILib documentation and library support</li>
               <li>Watch the WPILib blog for 2028 season previews</li>
             </ul>
             <a href="https://wpilib.org/blog" class="wl-shared-text wl-ret-link">Follow the WPILib blog for previews</a>
           </div>

         </div>

       </div>
     </div>

   </div>


   <script>
   function wlSelectTab(tab) {
     document.querySelectorAll('.wl-panel').forEach(p => p.classList.remove('active'));
     document.querySelectorAll('.wl-tab-btn').forEach(b => b.classList.remove('active'));
     document.getElementById('panel-' + tab).classList.add('active');
     document.getElementById('btn-' + tab).classList.add('active');
     try { localStorage.setItem('wpilib-tab', tab); } catch(e) {}
   }
   (function() {
     var saved; try { saved = localStorage.getItem('wpilib-tab'); } catch(e) {}
     wlSelectTab(saved || 'new');
   })();
   </script>

.. raw:: html

   <hr class="wl-core-intro"/>
   <h2 class="wl-sh wl-core-heading">Core Documentation</h2>
   <p class="wl-core-copy">Shared across all supported programs.</p>

   <h3 class="wl-sh">Foundations</h3>
   <div class="wl-core-grid">
     <a class="wl-core-card" href="docs/hardware/hardware-basics/hardware-overview.html"><div class="wl-core-title">Hardware Overview</div><div class="wl-core-desc">Motors, sensors, pneumatics, cameras, and FRC-legal components.</div></a>
     <a class="wl-core-card" href="docs/software/what-is-wpilib.html"><div class="wl-core-title">Software Overview</div><div class="wl-core-desc">WPILib tools, VS Code extensions, vendor libraries, and the full software ecosystem.</div></a>
     <a class="wl-core-card" href="docs/software/commandbased/index.html"><div class="wl-core-title">Robot Programming</div><div class="wl-core-desc">Command-based framework, subsystems, triggers, and drive code patterns.</div></a>
   </div>

   <h3 class="wl-sh">Everyday Tools</h3>
   <div class="wl-core-grid">
     <a class="wl-core-card" href="docs/software/dashboards/index.html"><div class="wl-core-title">Dashboards</div><div class="wl-core-desc">Elastic, AdvantageScope, Glass, and NetworkTables for real-time telemetry.</div></a>
     <a class="wl-core-card" href="docs/software/wpilib-tools/robot-simulation/index.html"><div class="wl-core-title">Simulation</div><div class="wl-core-desc">Test robot code on your laptop : no hardware required.</div></a>
     <a class="wl-core-card" href="docs/api-reference.html"><div class="wl-core-title">API Reference</div><div class="wl-core-desc">Java, C++, and Python class and method documentation.</div></a>
   </div>

   <h3 class="wl-sh">Advanced &amp; Autonomy</h3>
   <div class="wl-core-grid">
     <a class="wl-core-card" href="docs/software/pathplanning/index.html"><div class="wl-core-title">Path Planning</div><div class="wl-core-desc">Autonomous trajectories with PathPlanner, Choreo, and WPILib built-in tools.</div></a>
     <a class="wl-core-card" href="docs/software/advanced-controls/index.html"><div class="wl-core-title">Advanced Controls</div><div class="wl-core-desc">PID, feedforward, state-space, kinematics, and system identification.</div></a>
   </div>

   <div class="wl-legacy-note">
     <strong>Still using a legacy control system?</strong>
     This site covers the 2027 Systemcore-based control system.
     FRC teams using a roboRIO should use the
     <a href="https://docs.wpilib.org/en/stable/index.html">2026 WPILib documentation</a>.
     FTC teams using a REV Control Hub or Expansion Hub should use the
     <a href="https://ftc-docs.firstinspires.org/en/latest/">FTC documentation</a>.
   </div>

----

.. toctree::
   :maxdepth: 1
   :caption: Start Here
   :hidden:

   New to WPILib <docs/zero-to-robot/new-to-wpilib>
   Returning Teams <docs/zero-to-robot/returning>
   Zero to Robot <docs/zero-to-robot/introduction>

.. toctree::
   :maxdepth: 1
   :caption: FRC, FTC, and Control Systems
   :hidden:

   docs/ftc/index
   docs/xrp-robot/index
   docs/romi-robot/index

.. toctree::
   :maxdepth: 1
   :caption: Tools, Dashboards, and Networking
   :hidden:

   docs/software/vscode-overview/index
   docs/software/vscode-overview/3rd-party-libraries
   docs/software/driverstation/index
   docs/software/dashboards/index
   docs/software/telemetry/index
   docs/software/wpilib-tools/outlineviewer/index
   docs/software/wpilib-tools/wpical/index
   docs/networking/networking-introduction/index
   docs/networking/networking-utilities/index

.. toctree::
   :maxdepth: 1
   :caption: Hardware and Wiring
   :hidden:

   docs/controls-overviews/control-system-hardware
   docs/hardware/hardware-basics/hardware-overview
   docs/hardware/hardware-basics/status-lights-ref
   docs/software/can-devices/index

.. toctree::
   :maxdepth: 1
   :caption: Programming Fundamentals
   :hidden:

   docs/software/what-is-wpilib
   docs/controls-overviews/control-system-software
   docs/software/basic-programming/index
   docs/software/hardware-apis/index
   docs/software/commandbased/index
   docs/software/python/index
   docs/software/programming-snippets
   docs/software/examples-tutorials/wpilib-examples
   docs/software/examples-tutorials/third-party-examples

.. toctree::
   :maxdepth: 1
   :caption: Robot Behavior and Autonomy
   :hidden:

   docs/software/kinematics-and-odometry/index
   docs/software/pathplanning/index
   docs/software/advanced-controls/index
   docs/software/wpilib-tools/robot-simulation/index

.. toctree::
   :maxdepth: 1
   :caption: Reference
   :hidden:

   docs/yearly-overview/index
   docs/api-reference
   docs/software/support/support-resources
   docs/software/frc-glossary

.. toctree::
   :maxdepth: 1
   :caption: Contributing
   :hidden:

   docs/contributing/wpilib-docs/index
   docs/contributing/wpilib/index
   docs/legal/privacy-policy
   Report an Issue <https://github.com/wpilibsuite/frc-docs/issues>
