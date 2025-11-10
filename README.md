# 📱✨ EASY FIX GUIDE ✨📱: Unbrick and Restore Tecno Devices (MTK Bypass Method) 💾

This guide provides simple, step-by-step instructions to fix Tecno devices that are **stuck in a boot loop** 🔄 or completely **bricked** (not turning on) by using a special **MediaTek (MTK) security bypass** method.

---

## ⚠️ GENERAL DISCLAIMER ⚠️

> **I do not own or host any of the files linked in this guide.** All linked software and firmware files (drivers, tools, ROMs) belong to their respective creators and manufacturers.
>
> **You follow this guide entirely at your own risk.** Although this is a fixing guide, working with device firmware and security bypass tools carries inherent risks, including the potential to further damage your device. **I am not responsible for any damage, data loss, or bricking that may occur.**
>
> **🚨 DATA LOSS WARNING: Following this procedure and performing the final factory reset will erase ALL data on your device. Back up anything critical if your device is partially working.**

---

## 🛑 IMPORTANT NOTES 🛑: Best Setup for Success ✅

* **💻 Use a Fresh Computer:** If you run into problems, it is highly recommended to try this process on a different computer, ideally one with a **fresh install of Windows 11**.
* **🛡️ Security Check:** We will be installing special drivers and using tools that Windows might block. **It is highly recommended** to:
    * **Turn off Windows Defender/Antivirus** completely.
    * **Disable Driver Signature Enforcement** (A guide for this super easy step can be followed here: **[Youtube Guide](https://youtu.be/niMW_nCdk3w)**).
    * **Do not use a computer with personal or sensitive files** for this process.
* **🔑 Custom DA Check:** Some Tecno Devices Have Custom DA (Download Agent). Check for your device here **[Link](https://www.hovatek.com/forum/thread-23243.html)** and if that's the case then proceed with hovatek's guide to unbrick/fix bootloop on your device.
* **🔒 File Password:** The password to all files is **`AhmadMorningstar`**.

---

## 🛠️ Part 1: Install ADB and Fastboot Tools 💻

The Fastboot tool is essential for sending the new firmware files to your phone in the final steps.

[How to install ADB & Fastboot on Windows 10/11 Youtube Guide](https://youtu.be/kLEPkRtYEY8)

1. **⬇️ Download the Installer:** Download the **15 Seconds ADB Installer 1.5.6 (Latest)** from the official source: [Link to ADB Installer](https://androidmtk.com/download-15-seconds-adb-installer).
2. **⚙️ Run Installer:** Run the downloaded executable file as **administrator**.
3. **✅ Confirm Installation:** When the Command Prompt window appears asking `Y/N?`, type **`Y`** and press **`Enter`** for every prompt then pop up will appear simply check the always trust and hit install to install ADB, Fastboot, and the drivers.
4. **🏁 Finish:** Once complete, you can safely close the window and proceed to the next part.

---

## 📦 Part 2: Get Ready (Files and Tools) 📥

Here are the files and tools you need to download and have ready on your computer:

| Type | Item | Download Link | Notes |
| :--- | :--- | :--- | :--- |
| **MTK Drivers** | **Signed MTK Drivers** | [First](https://www.hovatek.com/redirectcode.php?link=aHR0cHM6Ly9tZWdhLm56LyMhM2g4QlNZNUohMHNmdnlydTZIbDZGc3J5VU8ydjlZaTFtbXRzRTR3cnplNjhMNHJqU0dOaw==) - [Second](https://www.hovatek.com/redirectcode.php?link=aHR0cHM6Ly9tZWdhLm56LyMhSDFrMHphNlIhRmpmaHNjT2xuVVFtdU9qLTlNbDA5MTMzLWVBVXpLTmdGMGJENUthQktvaw==) | You **must** install **both driver files** (Auto and Manual). |
| **Driver Filter** | **LibUSB Win32** | [Link](https://sourceforge.net/projects/libusb-win32/) | Used to manage and install the correct driver filter for the bypass tools. |
| **Bypass Tool** | **MTK AUTH Bypass Tool V7** | [Link 1](https://androidfilehost.com/?fid=7161016148664809945) - [Link 2](https://drive.google.com/file/d/1XElJ8yOeOJMVTJoero7dXbn7VeJq82C9/view?usp=sharing) | Used to temporarily **crash** the phone's security. |
| **Bypass Tool** | **MTK AUTH Bypass Tool V30** | [Link 1](https://www.needrom.com/download/mtk-auth-bypass-tool-mabt-v30) - [Link 2](https://androidfilehost.com/?fid=17825722713688280402) - [Link 3](https://drive.google.com/file/d/1NBXKwa0MLIH_Vj_JZ4Y6ZQwsdkQUTvyZ/view?usp=sharing) | Used to **reboot** the crashed phone into **Fastboot Mode**. |
| **Software** | **Tecno Stock Firmware/ROM** | *Simply Search your device model (e.g., [For KI5Q](https://www.needrom.com/download/tecno-spark-10-ki5q/))* | **Crucial:** Make absolutely sure these files are for your **exact** phone model. |

### 📂 ROM Extraction (Crucial Step!)

The firmware you downloaded is likely a compressed file (e.g., `.zip`, `.rar`).

* **Extract:** Use a utility like 7-Zip or WinRAR to **extract the entire contents** of the downloaded firmware file into a simple, easy-to-access folder (e.g., `C:\TecnoFlash`).
* **Location:** You will be navigating to this folder later using Command Prompt/PowerShell.

---

## ⚙️ Part 3: Install the Special MTK Drivers 🔌

These special drivers allow your computer to communicate with your phone while it is off (the **Preloader** state).

1. **🔗 Plug In the Phone:** Take your **bricked/bootlooping Tecno device** and plug it into your computer using a reliable/high-quality USB cable.
2. **💾 Install the Drivers:** Install **both files** from the **Signed MTK Drivers** package you downloaded.
3. **🖥️ Open Device Manager:** Type `"Device Manager"` in the Windows search bar and open the application.
4. **➕ Add Legacy Hardware:**
    * In Device Manager, click on the **"Action"** menu at the top.
    * Choose **"Add legacy hardware."**
5. **➡️ Go Through the Wizard:** Click **Next** until you reach the screen that lets you select a file source.
6. **📁 Load the Driver Manually:**
    * Choose `"Install the hardware that I manually select from a list (Advanced)"` and click **Next**.
    * Click the **"Have Disk"** button.
    * Click **"Browse"** and navigate to the folder where you downloaded the MTK drivers.
    * Go inside the folder named **`CDC`** and select the file named **`cdc-acm.inf`**. Then click **OK**.
    * Select **"MediaTek USB VCOM (Android)"** from the list.
    * Click **Next**, **Next**, and **Finish**.

---

## 🔑 Part 4: Apply the LibUSB Filter (Crucial Step!) 🎯

This step ensures the bypass tools (V7 and V30) can correctly communicate with the phone using the drivers you just installed.

1. **🚀 Open LibUSB:** Install and open the **LibUSB Win32** application.
2. **🧹 Clear Filters:** Click the button that says **"Uninstall all filter"** then click **OK**. This clears any conflicting drivers.
3. **🔧 Install Filter:** Click the button that says **"Install Filter."**
4. **📱 Select Device:** In the list of connected devices, **pick your connected Tecno device** (it may appear as "MediaTek USB Port" or similar).
5. **✅ Install:** Hit **Install** and wait for the process to complete.
6. **_Minimize:** Do **NOT** close the LibUSB application; simply **minimize it** and proceed to the next step.

---

## 🔓 Part 5: Bypass Tecno Security 💥

We use the V7 bypass tool to temporarily crash and unlock your phone so we can load new software onto it.

1. **⬆️ Open V7 Tool:** Open the **MTK AUTH Bypass Tool V7**.
2. **💣 Crash the Phone:** Click the button that says **"Crash PL Only."**
    * For **bootlooping** phones: Wait until the screen goes **off** right before the Tecno logo tries to show up again, then hit the **CRASH PL ONLY** button. (**NOTE:** You can also hold the power button and click exactly when the device turns off before it reboots.)
    * For **bricked** phones: Hit the **CRASH PL ONLY** button, then **Hold down the Power button** until the V7 application shows a **"Success"** message.
3. **🥳 Wait for Success:** Wait for the V7 application to confirm success.
4. **❌ Close V7:** Close the V7 tool.

---

## 🚀 Part 6: Enter Fastboot Mode and Flash the Fix 💾

Fastboot Mode is a special mode on the phone that allows you to install system files.

1. **⬆️ Open V30 Tool:** Open the **MTK AUTH Bypass Tool V30**.
2. **🧘 Don't Panic:** Your Tecno may still be bootlooping or remain black/bricked after the V7 crash. **Do not disconnect it.**
3. **⚡ Enter Fastboot:** Click the button that says **"Reboot Fastboot."**
    * For the **bootlooping** device: Wait for the app to find your device and initiate the process.
    * For the **bricked** device: Hold down the power button and wait until the app finds your device and starts the process.
4. **✅ Wait for Success:** Keep trying and waiting until the app's output box shows **"SUCCESS"** and your phone **restarts** and shows the **"Fastboot Mode"** screen.
5. **⌨️ Use Fastboot Commands:** With your phone in **Fastboot Mode**, open your computer's **Command Prompt** (or PowerShell) and navigate to the folder containing your **extracted** Tecno firmware files.
6. **⬇️ Flash the Files:** Use these commands one-by-one, pressing **Enter** after each one. The phone will be receiving the new files.

```bash
# Example commands. You must flash ALL required files for your specific ROM.

# Flash the boot image
fastboot flash boot boot.img

# Flash the vbmeta image
fastboot flash vbmeta vbmeta.img

# Flash system and other partitions (adapt to your ROM's contents)
# fastboot flash system system.img
# fastboot flash super super.img
# fastboot flash recovery recovery.img
# Example commands. You must flash ALL required files for your specific ROM.

# Flash the boot image
fastboot flash boot boot.img

# Flash the vbmeta image
fastboot flash vbmeta vbmeta.img

# NOTE: You will likely need to flash other essential files (e.g., system.img or super.img)
# that are required by your Tecno model.

# Reboot the phone when done:
fastboot reboot
# if its still bootlooping/bricked repeat the entire step and then
fastboot reboot recovery
# then on recovery use volume buttons and power for navigation click on the Wipe/Data Factory reset and cache then reboot to system
🎉 Success! Your phone should now start up correctly! Be patient—the first startup may take a long time (5–10 minutes).
