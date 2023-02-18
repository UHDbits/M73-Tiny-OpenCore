# **Improving Security**

### **IMPORTANT NOTICE:**
### **Do NOT follow these steps with macOS 13 Ventura. By following these steps, you will cause your ThinkCentre to be unable to boot with macOS 13 Ventura. If you ever do want to upgrade to Ventura, please make sure to redownload the stock configuration, or undo the changes made to the configuration.**

**Due to the fact that this ThinkCentre does not have offically supported hardware for macOS 13 Ventura, sacrifices to security have been made for Ventura compatibility. If you would like to undo these changes, and in turn make your system more secure, please make the following changes in the "config.plist" of the configuration. I recommend using [ProperTree](https://github.com/corpnewt/ProperTree/) to make these changes.**

## Changes to Make

* NVRAM -> Add -> 7C436110-AB2A-4BBB-A880-FE41995C9F82 -> boot-args 

**Delete the values inside of the "boot-args" string. (amfi_get_out_of_my_way=1 ipc_control_port_options=0)**

* NVRAM -> Add -> 7C436110-AB2A-4BBB-A880-FE41995C9F82 -> csr-active-config

**Change the data value of <030A0000> to <00000000>.**

## Extra Security Measures

**If you want to improve security even more, you can follow the [Security and FileVault](https://dortania.github.io/OpenCore-Post-Install/universal/security.html) section of the OpenCore Post-Install guide. FileVault has already been enabled for you, so you do not need to follow that section of the guide.**
