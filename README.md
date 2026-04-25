# Samsung Galaxy J1 Ace (SM-J110H) Stock Apps & ODEX Files



This repository contains stock system applications extracted from the official Samsung Galaxy J1 Ace (SM-J110H) firmware. 

### ⚠️ Why are there .odex files?
These apps are **Odexed**. This means the application code is stored outside the APK in a separate `.odex` file to save space and improve performance on legacy hardware. 

**An APK from this repository will NOT work unless you also copy its matching .odex file.**

📱 Method 1: Manual Installation (Root Required)

Use this method if you are installing directly on the device using a file manager like Total Commander.



Download: Obtain the APK and ODEX files releases .

Copy Files: Transfer both the .apk and the .odex file to your device storage.

Move to System: Open your root file explorer and move both files to:/system/app/

Set Permissions:

Files (.apk & .odex): Long-press and set permissions to 644 (rw-r--r--).

Folder: If you created a sub-folder, set it to 755 (rwxr-xr-x).

Wipe Cache: Boot into recovery (TWRP) and wipe Dalvik Cache.

Reboot: Restart your phone to let the system rebuild the app. 


## 💻 Method 2: ADB Installation (Direct PC Push)

This is the fastest method if you have a computer and ADB access. This pushes files directly into the system partition.

```bash
# 1. Mount the system partition as writable
adb shell su -c "mount -o remount,rw /system"

# 2. Push APK and ODEX directly to /system/app/
# Replace <path_of_.apk> with the file location on your PC
adb push <path_of_.apk> /system/app/
adb push <path_of_.odex> /system/app/

# 3. Set the correct permissions (644)
# Replace "FileName" with the name of the app you just pushed
adb shell su -c "chmod 644 /system/app/FileName.*"

# 4. Reboot your phone
adb reboot


