=====================
Installing Git/Unity
=====================

This is a guide on how to install Git/Unity, as well as a IDE to edit Scripts.

Installing Git 
--------------

Prerequisites
~~~~~~~~~~~~~
Before installing anything on your computer, create a free account at `GitHub <https://github.com/signup>`_. 

.. note::
   Make sure you verify your email address after signing up, and keep track of which email you used. You will need to plug that exact email into your command prompt later!

Windows
~~~~~~~

`This is the download link for git on Windows <https://gitforwindows.org/>` 

1. Click the download button 
2. Follow the setup wizard
3. Open command prompt and run the following command

.. code-block:: bash

   git --version

It should print the version of Git you installed

4. Set your git identity:

.. code-block:: bash

   git config --global user.name "Your Name" 
   git config --global user.email "your.email@example.com" # Use the same email you used in the GitHub Verification! 
   git config --global init.defaultBranch main

macOS
-----

1. Open your Terminal (you can find it using Spotlight by pressing ``Cmd + Space``).
2. Type the following command and press Enter:

.. code-block:: bash

   git --version

3. **If Git is not installed**, a window will pop up asking you to install the **Xcode Command Line Tools**. Click **Install** and accept the terms. 
4. Once the installation finishes, restart your Terminal and set up your Git identity:

.. code-block:: bash

   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   git config --global init.defaultBranch main


Linux
-----

1. Open your terminal application.
2. Update your package manager and install Git using your distribution's command:

*For Ubuntu or Debian:*

.. code-block:: bash

   sudo apt update && sudo apt install git -y

*For Fedora:*

.. code-block:: bash

   sudo dnf install git -y

3. Set up your Git identity:

.. code-block:: bash

   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   git config --global init.defaultBranch main

Testing Your GitHub Link (Do This Immediately)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To make sure your computer and GitHub account are synced perfectly right now, let's run a quick test.

1. Open your terminal or command prompt.
2. Run the following command to download a basic public testing template from GitHub:

.. code-block:: bash

   git clone https://github.com/github/training-kit.git

3. **What to look for:**
   
   * **If a popup window appears:** Click **"Sign in with your browser"**, click authorize, and you are fully synced!
   * **If it downloads immediately without a popup:** You are already linked and good to go!
   * **If you get an error:** Double-check that your ``git config --global user.email`` exactly matches your GitHub account email.

4. Once the test succeeds, you can safely delete the downloaded test folder from your computer.

Installing Unity
----------------

The Unity Version we will be using for the 2026-2027 school year is **Unity 6.3 LTS**. 

Step 1: Download & Install Unity Hub
------------------------------------

The Unity Hub is a lightweight manager that handles your different project versions, downloads, and user licenses.

1. Go to the `Official Unity Download Page <https://unity.com>`_ and click the download button for your operating system:

   * **Windows:** Click ``Download for Windows`` to get the installer executable.
   * **macOS:** Click ``Download for Mac`` to get the DMG disk image.
   * **Linux:** Click ``Download for Linux`` to grab the official AppImage file.

2. Run the installer file and launch the **Unity Hub** application.
3. Sign in using your free Unity ID account. If you do not have one, click **Create account** to sign up, then check your inbox to verify your email.
4. Click the **Settings** gear icon in the top right corner, select the **Licenses** tab, click **Add**, and choose the free **Unity Personal** license option.

Step 2: Pick and Install Your Preferred Code Editor (IDE)
----------------------------------------------------------

.. note::
   **Already have an IDE installed?** If you are an experienced programmer who already uses an environment like traditional **Visual Studio** or **JetBrains Rider**, you do not need to switch! Unity fully integrates with all three major choices. Pick your preference below.

* **VS Code (Highly Recommended for Beginners):** Extremely lightweight and clean. Keeps your laptop lightning-fast and responsive.
* **Visual Studio:** The traditional massive development suite. Very powerful but relies on a heavy system installation wizard.
* **JetBrains Rider:** A premium, cross-platform professional gaming IDE built with heavy native engine integrations specifically tailored for Unity.

.. warning::
    JetBrains Rider and Visual Studio are full IDES, which means they can take up a lot of system reasources. While they are highly optimized, it is best practice to check if your laptop/desktop can handle them.
    However, for most people, it just means a longer startup time.

Get your choice ready:

* **For VS Code (Lightweight):**
  1. Download the installer for your system from the `Official VS Code Website <https://visualstudio.com>`_.
  2. Open VS Code, open the **Extensions** tab on the left sidebar (4-blocks icon), search for **Unity**, and install the official **Unity extension** bundle developed by Microsoft.

* **For Visual Studio (Traditional / Heavyweight):**
  1. Open the **Visual Studio Installer** manager app on your machine.
  2. Switch to the *Workloads* tab, find the **Game development with Unity** checkbox, check it, and click Modify/Install to add the necessary C# files.

* **For JetBrains Rider (Premium / Cross-Platform):**
  1. Download and install Rider from the `Official JetBrains Website <https://jetbrains.com>`_ or via the JetBrains Toolbox app.
  2. Ensure the built-in **Unity Support** tool plugin is activated under your Rider preferences menu.

Step 3: Install Unity 6.3 LTS & Pick Component Modules
------------------------------------------------------

1. Go back to the main Hub window and click the **Installs** tab on the left sidebar.
2. Click the **Install Editor** button in the top right corner.
3. Locate **Unity 6.3 LTS** (listed as version ``6000.3.x``) under official releases and click **Install**.
4. **CRITICAL STEP - Component Module Checkboxes:** A popup menu will appear listing extra development tools. Look closely at the check boxes:

   * **If using VS Code or Rider:** Look at the top section labeled *Dev Tools* and **UNCHECK** Visual Studio. Leaving this checked forces an unnecessary multi-gigabyte download that will slow down your laptop.
   * **If using traditional Visual Studio:** Ensure the **Microsoft Visual Studio Community** box is **CHECKED**.
   * **Platform Support Checkboxes:** Scroll down the list and make sure the box for your specific operating system is checked (e.g., ``Windows Build Support``, ``Mac Build Support``, or ``Linux Build Support``) so you can build your games locally.

5. Click **Continue** to start downloading the Unity Editor engine files.

Step 4: Link Your Editor to Unity (Configuration)
-------------------------------------------------

No matter which of the Big 3 code editors you installed, you must tell Unity to hand off your C# scripts to that specific application.

1. Open your Unity Hub, go to the **Projects** tab, and create or open a new game project. Wait for the primary Unity Editor workspace interface to finish loading.
2. Access the Preferences configuration screen by following the specific menu path for your native computer operating system:

   * **Windows / Linux:** In the top header bar, go to **Edit** ➔ **Preferences**
   * **macOS:** In the top menu bar, go to **Unity** ➔ **Settings** (or **Preferences** on older Mac versions)

3. Look at the left sidebar menu of the popup configuration panel and click **External Tools**.
4. Locate the **External Script Editor** dropdown selection field at the very top of the window.
5. Click the dropdown box and select your specific editor program app from the listing array:

   * Select **Visual Studio Code**, **Visual Studio**, or **Rider**.
   * *Troubleshooting Check:* If your preferred application does not show up automatically in the list, click **Browse...**, navigate manually to your system's local installation directory folder, and choose the application executable launcher tool.

You have now installed Git/Unity, and are ready to begin making games! Please make your way over to the Unity Overview to learn what to do next!
