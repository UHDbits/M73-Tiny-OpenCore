<div align="center">
  
  ### NOTE: macOS Ventura will NOT work on this config. Not only will you likely need to patch for the next release, due to the Macs that are similar to this computer being dropped, but changes also have to be made to the actual config itself. Please wait for updates as I attempt to get Ventura working on the i7 version of my ThinkCentre (which this config will soon be transitioning over to, the i7 variant, although it should still work on the i3 variant).
  
  # OpenCore 0.8.1 EFI for the ThinkCentre M73 Tiny
  
  [![OpenCore 0.8.1](https://img.shields.io/badge/OpenCore-0.8.1-15b8d7)](https://github.com/acidanthera/OpenCorePkg)
  [![macOS Monterey 12.2.1](https://img.shields.io/badge/macOS-Monterey%2012.2.1-blueviolet)](https://apple.com/macos/monterey)
  [![Supported CPU: Intel Core i3-4130T](https://img.shields.io/badge/Supported%20CPU-Core%20i3--4130T-blue)](https://ark.intel.com/content/www/us/en/ark/products/77481/intel-core-i34130t-processor-3m-cache-2-90-ghz.html)
  [![Supported GPU: Intel HD4400](https://img.shields.io/badge/Supported%20GPU-HD4400-blue)](https://ark.intel.com/content/www/us/en/ark/products/graphics/81497/intel-hd-graphics-4400.html)

  <img src="https://github.com/UHDbits/M73-Tiny-OpenCore/raw/main/Images/ThinkCentre.png" alt="ThinkCentre M73 Tiny" width="400px"/>
  
  | ![Catalina About This Mac](/Images/About%20This%20Mac/DarkCatalinaAboutThisMac.png#gh-dark-mode-only) ![Catalina About This Mac](Images/About%20This%20Mac/LightCatalinaAboutThisMac.png#gh-light-mode-only) | ![Monterey About This Mac](/Images/About%20This%20Mac/DarkMontereyAboutThisMac.png#gh-dark-mode-only) ![Monterey About This Mac](/Images/About%20This%20Mac/LightMontereyAboutThisMac.png#gh-light-mode-only) |
  | ----------------------------------------- | ----------------------------------------- |
  
  ## ⚠️ WARNING ⚠️
  
  **I do NOT recommend using prebuilt OpenCore EFIs. They might not work with your exact configuration of your computer, may have features enabled that you don't want, may be outdated, and are harder to diagnose. This is meant to be used to help with creation of a custom OpenCore EFI, or should only be used at your own risk.**
  
  ## Contents
  
  [**System Specifications**](#system-specifications)

  [**Directions**](#directions)

  [**Updating OpenCore/macOS**](#updating-opencoremacos)

  [**Known Issues**](#known-issues)
  
  ## System Specifications
  
  | Component | Model |
  | :-: | :-: |
  | CPU | Intel Core i3-4130T (2c4t) @ 2.90GHz |
  | RAM | 2x4GB of DDR3-1600 |
  | GPU | Intel HD Graphics 4400 (known issues) |
  | Storage | SanDisk Ultra 512GB SSD |
  | Audio | Realtek ALC283 (known issues) |
  | Internal WiFi/Bluetooth | Intel Centrino Wireless-N (not working) |
  | USB WiFi | TP-Link Archer T3U (driver not included, can be found [here](https://github.com/chris1111/Wireless-USB-OC-Big-Sur-Adapter)) |
  | Ethernet | Intel I217-V |
  
  **If your system does not meet these exact specifications (other then the USB WiFi adapter), I can not guarantee this config will work for you. If you try it, and it doesn't work for you, you can create an issue and I will try to help you make it work.**

  ## Directions
  
  **Follow the steps below by going to the links and following the according directions on the OpenCore guide. The step is optional (but may be required to get some features working) if it is labeled with a &#42;. If the step labeled has &#42;&#42;, that means it's optional, but extremely recommended.**

  | Step # | Link/Directions |
  | :-: | :-: |
  | 1 | [Creating the USB (do not put the EFI folder in the EFI partition, and do not download "OpenCorePkg").](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/#making-the-installer) |
  | 2 | Mount your EFI partition if not already done, and take the "EFI" folder in this repo and copy it into the EFI partition. Make sure you copy the "EFI" folder itself, and not the folders inside of it directly into the EFI partition.
  | 3 | [Intel BIOS Settings (scroll to the bottom of this page if not done already, and Disable/Enable as many of the settings as possible. If it tells you to enable anything in the actual OpenCore config, ignore it.)](https://dortania.github.io/OpenCore-Install-Guide/config.plist/haswell.html#intel-bios-settings)
  | 4 | [Installation Process (skip "Double checking Your Work". Check "OpenCore Multiboot Guide" if you want to multiboot.)](https://dortania.github.io/OpenCore-Install-Guide/installation/installation-process.html)
  | 5** | [Moving OpenCore from USB to macOS Drive (Skip legacy part at the bottom)](https://dortania.github.io/OpenCore-Post-Install/universal/oc2hdd.html)
  | 6** | [Fixing iMessage and other services with OpenCore (This is extremely recommended even if you don't use iServices, because otherwise you will have a generic serial number which isn't the best idea.)](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html)
  | 7* | [Optimizing Power Management (CPUFriend is already included in the OpenCore config)](https://dortania.github.io/OpenCore-Post-Install/universal/pm.html)

  ## Updating OpenCore/macOS
  
  ### Updating OpenCore with a newer version of my config
  **If you want to upgrade OpenCore with a newer version of my config, just download the new EFI folder, mount the EFI partition, and copy it over. Note, if you've made any changes to the config, make sure to save them in a text document because these changes will be overwritten.**

  ### Updating OpenCore/macOS manually
  **If you want to update OpenCore manually, you can follow [this guide](https://dortania.github.io/OpenCore-Post-Install/universal/update.html#updating-opencore) (harder to follow, but recommended and tells you how to upgrade macOS), or follow [this guide](https://www.insanelymac.com/forum/topic/347035-guide-updating-and-maintaining-opencore-new-method/) (easier to follow, but not recommended.)**

  ## Known Issues

  ### Monterey 12.3+ crashes during setup
  **Monterey 12.3 and newer crashes during the "Migration Assistant" part of setup. Sometimes, you can get past the screen, but it'll freeze later. I do not know how to fix this, and I think it's fault of the HD4400, which is impossible to fix. Upgrading the CPU and iGPU may fix it.**

  ### HD4400 Glitching and Freezing
  **The HD4400 has many issues in macOS. For example, some icons may be missing (image below), some random freezes may happen, icons may get replaced, and more. In newer version of macOS, this can make the system almost unusable. This is impossible to fix at the moment, and the only thing you can do is upgrade your CPU to one with a HD4600 iGPU.**

  ![Example of Missing Icons](/Images/Missing%20Icons/DarkMissingIcons.png#gh-dark-mode-only) ![Example of Missing Icons](Images/Missing%20Icons/LightMissingIcons.png#gh-light-mode-only)

  ### Headphone Audio Glitching
  **Out of the box, you may notice that audio through headphones is inaudible. This is a glitch with AppleALC, and can be fixed by going into System Preferences -> Audio, and by moving the "Balance" slider left or right. This will not change the actual balance of the headphones, but it will fix the issue.**

  ![Move the "Balance" slider left or right](/Images/Headphones%20Fix/DarkHeadphonesFix.png#gh-dark-mode-only) ![Move the "Balance" slider left or right](/Images/Headphones%20Fix/LightHeadphonesFix.png#gh-light-mode-only)
  
  [**Jump to Top**](#opencore-081-efi-for-the-thinkcentre-m73-tiny)

</div>
