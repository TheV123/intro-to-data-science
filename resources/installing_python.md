---
title: Installing Python
layout: default
parent: Resources
nav_order: 1
---
#### TABLE OF CONTENTS
- [Installing Python](#installing-python)
  - [Windows](#windows)
  - [MacOS](#macos)


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
