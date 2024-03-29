# **Improving Security**

### **IMPORTANT NOTICE:**
### **Do NOT follow these steps with macOS 13 Ventura or macOS 14 Sonoma. By following these steps, you will cause your ThinkCentre to be unable to boot with either of the two versions. If you ever want to upgrade to Ventura or Sonoma, please redownload the stock configuration or undo the changes made to your configuration.**

**Because this ThinkCentre does not have officially supported hardware for macOS 13 Ventura or macOS 14 Sonoma, sacrifices to security have been made for compatibility. If you would like to undo these changes and, in turn, make your system more secure, you can make the following changes in the "config.plist" of the configuration. I recommend using [ProperTree](https://github.com/corpnewt/ProperTree/) to make these changes.**

## Changes to Make

* NVRAM -> Add -> 7C436110-AB2A-4BBB-A880-FE41995C9F82 -> csr-active-config

**Change the data value of <030A0000> to <00000000>.**

## Extra Security Measures

**If you want to improve security even more, you can follow the [Security and FileVault](https://dortania.github.io/OpenCore-Post-Install/universal/security.html) section of the OpenCore Post-Install guide. FileVault has already been enabled for you, so you do not need to follow that section of the guide.**
