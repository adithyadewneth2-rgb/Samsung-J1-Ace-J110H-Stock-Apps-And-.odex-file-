# Samsung Galaxy J1 Ace (SM-J110H) Stock Apps & ODEX Files

This repository contains stock system applications extracted from the official Samsung Galaxy J1 Ace (SM-J110H) firmware. 

### ⚠️ Why are there .odex files?
These apps are **Odexed**. This means the application code (`classes.dex`) is stored outside the APK in a separate `.odex` file to save space and improve performance on legacy hardware. 

**An APK from this repository will NOT work unless you also copy its matching .odex file.**

---

## 🛠 Installation Instructions (Root Required)

To install these apps manually, follow these steps:

1. **Copy Files**: Transfer both the `.apk` and the `.odex` file to your device.
2. **Move to System**: Use a root file explorer (like Total Commander) to move the files to:
   `/system/app/`
3. **Set Permissions**:
   * **Files (.apk & .odex)**: Set to `644` (`rw-r--r--`)
   * **Folder (if applicable)**: Set to `755` (`rwxr-xr-x`)
4. **Wipe Cache**: For best results, wipe the **Dalvik Cache**.
5. **Reboot**: Restart your phone. The system will "rebuild" the apps during boot.

---

## 💻 ADB Installation Method

If you have ADB access and a rooted shell:

```bash
# Example for SecCalculator2
adb push SecCalculator2_ESS.apk /sdcard/
adb push SecCalculator2_ESS.odex /sdcard/
adb shell
su
mount -o remount,rw /system
cp /sdcard/SecCalculator2_ESS.* /system/app/
chmod 644 /system/app/SecCalculator2_ESS.*
reboot
