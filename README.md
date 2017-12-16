Downloading the Source  
==============================================================    

1. Repo sync all code with default.xml  
`repo init -u git://github.com/Dragons-CAF/android.git -b O.1`
   `repo sync`
2. Root your device   
3. Pull the necessary libraries from your device by executing the script `pull_library.sh`   

NOTE : If you face errors like "BlahBlah" file not found or Permission Denied, connect your device in TWRP mode, mount System & Pull the blobs)

4. After pull_library.sh be executed, a directory  named "vendor" should be generated. Copy this directory to root of project.

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

