## 3DS Console Preservation & Homebrew Integration
# Platform: Nintendo 3DS (New Model)

# System Version: 11.17.0-50U

# Storage Configuration: 128GB SDXC (Formatted FAT32, 64KB Cluster Size)

## Project Overview
This project involved the end-to-end modification of a New Nintendo 3DS console to bypass manufacturer-imposed software locks. The goal was to expand device utility, enable region-free gaming, and facilitate the installation of digital backups and homebrew applications following the official closure of the Nintendo eShop.

## Technical Implementation
Storage Optimization: Executed a non-standard formatting of a 128GB SDXC card from exFAT to FAT32 using a 64KB allocation unit size. This specific configuration was required to ensure compatibility with the 3DS firmware while preventing graphical glitches in the GBA Virtual Console.

Custom Firmware (CFW): Successfully deployed Luma3DS via the MSET9 exploit. This involved leveraging a PC-side Python script to manipulate the console's System Settings data management, triggering a memory overflow to execute unsigned code.

Software Suites:

FBI: Open Source Title Manager for .cia package installation.

hShop (3hs): Network-based content management.

Homebrew Launcher: Framework for 3rd-party application execution.

## Key Skills Demonstrated
Hardware/Software Interfacing: Bridging legacy hardware with modern PC environments and file systems.

Advanced Troubleshooting: Identifying and resolving cluster size and environment path discrepancies.

Technical Documentation: Adhering to strict, version-specific protocols to maintain system integrity.

Environment Setup: Manual configuration of Python binaries and system variables.

## Tools Used
Python 3.14.3: Required for exploit script execution (Manual binary install).

MSET9: Exploitation framework for ARM11 kernel access.

GUIFormat: Low-level disk formatting for high-capacity SDXC cards.

Luma3DS / GodMode9 (GM9): CFW kernel and multi-purpose system tool.

## Technical Challenges & Resolutions
Challenge 1: Storage Capacity vs. File System Limitations
Problem: The 3DS natively supports SDHC cards (up to 32GB). My 128GB SDXC card arrived factory-formatted as exFAT, which the 3DS cannot recognize.

Resolution: Performed a low-level format to FAT32 using GUIFormat, bypassing Windows' native 32GB partition limit for FAT32 volumes.

Challenge 2: Optimizing Allocation Unit Size (Cluster Size)
Problem: Standard 32KB clusters on a 128GB card cause UI lag and graphical artifacts in GBA Virtual Console titles.

Resolution: Manually configured the Allocation Unit Size to 64KB (65536 bytes). Verified the configuration via chkdsk to ensure 100% compatibility and system speed.

Challenge 3: Python Environment & Path Resolution
Problem: The MSET9 exploit requires Python 3.x. The Microsoft Store version of Python operates in a sandboxed environment (WindowsApps), preventing it from correctly manipulating files on the SD card.

Resolution: Uninstalled the Store version and performed a manual installation of Python 3.14.3 from the official binaries.

Verification: Confirmed the fix using where python to ensure the path was directed to the local AppData directory rather than the restricted sandbox.

Challenge 4: Firmware Version Constraints (v11.17.0)
Problem: System version 11.17.0 patched most entry-point exploits, typically requiring hardware-based solutions (flashcarts).

Resolution: Successfully implemented the MSET9 exploit by manipulating Data Management files on the SD card to trigger a controlled memory overflow, bypassing the need for additional hardware.

#system image links

Original System Version: https://github.com/jsknill/3DS-Console-Preservation-Homebrew-Integration/blob/main/20260208_105754%5B1%5D.jpg

H Shop https://github.com/jsknill/3DS-Console-Preservation-Homebrew-Integration/blob/main/20260209_184559%5B1%5D.jpg

Homebrew Launcher https://github.com/jsknill/3DS-Console-Preservation-Homebrew-Integration/blob/main/20260209_184617%5B1%5D.jpg

Universal Updater https://github.com/jsknill/3DS-Console-Preservation-Homebrew-Integration/blob/main/20260209_184623.jpg

Homebrew launcher https://github.com/jsknill/3DS-Console-Preservation-Homebrew-Integration/blob/main/20260209_184833.jpg

FBI Luma and GM9 https://github.com/jsknill/3DS-Console-Preservation-Homebrew-Integration/blob/main/20260209_184914.jpg
