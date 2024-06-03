---
title: Installation
layout: default
parent: Resources
nav_order: 1
---
#### TABLE OF CONTENTS
- [Installing Python](#installing-python)
  - [Windows](#windows)
  - [MacOS](#macos)
- [Installing an IDE](#installing-an-ide)
  - [Installing VS Code](#installing-vs-code)
    - [Windows](#windows-1)
    - [MacOS](#macos-1)
  - [Installing PyCharm](#installing-pycharm)
    - [Windows](#windows-2)
    - [MacOS](#macos-2)


# Installing Python 
Before you can work with Python and install packages, you need to have Python installed on your system. Here's how you can install Python on different operating systems:

## Windows

1. **Download Python Installer**
    - Go to the official Python website: [Python Downloads](https://www.python.org/downloads/windows/).
    - Click on the link for the latest version of Python to download the installer.

2. **Run the Installer**
    - Locate the downloaded installer file (usually in your Downloads folder) and double-click to run it.

3. **Add Python to PATH**
    - In the installer window, check the box that says "Add Python to PATH". This will allow you to use Python from the command line.
    - Click "Install Now" to begin the installation and follow steps in the installation wizard

4. **Complete Installation**
    - Follow the on-screen instructions to complete the installation process.
    - Once the installation is complete, you can verify the installation by opening Command Prompt and typing `python --version`. This should display the version of Python you just installed.

## MacOS 

1. **Install Homebrew (if not already installed)**
    - Homebrew is a package manager for macOS that simplifies the installation of software.
    - Open the Terminal application.
    - Paste the following command into the Terminal and press Enter:
      ```sh
      /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
      ```
    - Follow the on-screen instructions to complete the Homebrew installation.

2. **Install Python using Homebrew**
    - Once Homebrew is installed, you can install Python by running:
      ```sh
      brew install python
      ```
    - This will download and install the latest version of Python.

3. **Verify Installation**
    - After the installation is complete, you can verify it by opening the Terminal and typing:
      ```sh
      python3 --version
      ```
    - This should display the version of Python you just installed.

# Installing an IDE 
Integrated Development Environments (IDEs) provide helpful assistance towards programming by providing features such as Intellisense, refactoring support, and have a rich plugin ecosystem. I would recommend using VSCode or Pycharm for this class, but students can code in whatever they want to

## Installing VS Code

### Windows

1. **Download VS Code Installer**
    - Visit the official Visual Studio Code website: [VS Code Downloads](https://code.visualstudio.com/Download).
    - Click on the "Windows" download button to download the installer.

2. **Run the Installer**
    - Locate the downloaded installer file (usually in your Downloads folder) and double-click to run it.

3. **Follow Installation Prompts**
    - Accept the license agreement.
    - Select the destination folder for the installation.
    - Choose whether to create a desktop icon.
    - Select additional tasks (optional), such as adding VS Code to the PATH.
    - Click "Install" to begin the installation process.

4. **Launch VS Code**
    - Once the installation is complete, click "Finish" to launch VS Code.
    - You can also open VS Code from the Start Menu or by double-clicking the desktop icon (if created).

### MacOS

1. **Download VS Code Installer**
    - Visit the official Visual Studio Code website: [VS Code Downloads](https://code.visualstudio.com/Download).
    - Click on the "macOS" download button to download the installer.

2. **Install VS Code**
    - Open the downloaded `.zip` file. This will extract the VS Code application.
    - Move the extracted `Visual Studio Code.app` to your `Applications` folder.

3. **Launch VS Code**
    - Open your Applications folder and double-click on `Visual Studio Code` to launch it.
    - You can also add VS Code to your Dock for easy access.

## Installing PyCharm

### Windows

1. **Download PyCharm Installer**
    - Visit the official JetBrains PyCharm website: [PyCharm Downloads](https://www.jetbrains.com/pycharm/download/).
    - Select the "Windows" option and choose either the Community (free) or Professional (paid) edition, then click "Download".

2. **Run the Installer**
    - Locate the downloaded installer file (usually in your Downloads folder) and double-click to run it.

3. **Follow Installation Prompts**
    - Choose the installation destination folder.
    - Select additional tasks such as creating desktop shortcuts, adding PyCharm to the PATH, and associating `.py` files with PyCharm.
    - Click "Install" to begin the installation process.

4. **Launch PyCharm**
    - Once the installation is complete, click "Finish" to launch PyCharm.
    - You can also open PyCharm from the Start Menu or by double-clicking the desktop icon (if created).

### MacOS

1. **Download PyCharm Installer**
    - Visit the official JetBrains PyCharm website: [PyCharm Downloads](https://www.jetbrains.com/pycharm/download/).
    - Select the "macOS" option and choose either the Community (free) or Professional (paid) edition, then click "Download".

2. **Install PyCharm**
    - Open the downloaded `.dmg` file.
    - Drag and drop the PyCharm icon into the `Applications` folder.

3. **Launch PyCharm**
    - Open your Applications folder and double-click on `PyCharm` to launch it.
    - You can also add PyCharm to your Dock for easy access.

For further customization and extensions, refer to the documentation:
- [VS Code Documentation](https://code.visualstudio.com/docs)
- [PyCharm Documentation](https://www.jetbrains.com/pycharm/documentation/)