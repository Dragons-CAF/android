Android Source based on Code Aurora Forum (CAF)  
==============================================================
 
 **Tag : LA.UM.6.4.r1-05400-8x98.0**  
 **Version : 8.1**  

 **Supported device(s)**  
 
   - OnePlus 5 (Cheeseburger)
 
Downloading the Source  
==============================================================    

1. Initialize the repo with default.xml  
`repo init -u git://github.com/Dragons-CAF/android.git -b O.1`

2. Sync the complete source code   
`repo sync -c -f -j8 --force-sync --no-clone-bundle --no-tags`

Building the System  
==============================================================  
**[Set up environment]**  
Initialize the environment with the envsetup.sh script.  git a
`$ . build/envsetup.sh`  

**[Choose a Target]**  
Choose which target to build with lunch.  
`$ lunch`  
      
**[Build the code]**  
Build everything with make. GNU make can handle parallel tasks with a -jN argument.  
`$ make -j4`  

**[Flash a Device]**  
Let device enter fastboot mode, run  
`$ adb reboot bootloader`  

Once the device is in fastboot mode, run  
`$ fastboot flash boot boot.img`  
`$ fastboot flash system system.img`
`$ fastboot flash recovery recovery.img`  

If you want flash new /data partition, run  
`$ fastboot flash userdata userdata.img`

