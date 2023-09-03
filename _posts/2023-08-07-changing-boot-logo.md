---
title: Changing boot logo
date: 2023-08-07
categories: [wiki]
tags: [wiki, system, boot-logo, mods]
---

# This will modify the boot LOGO that displays BEFORE the boot ANIMATION (example below)
![](https://i.imgur.com/W2trsoc.png){: height="400" }

# Prerequisites
- [platform-tools](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)
- [Logo Builder](https://drive.google.com/file/d/1_MSwPHimxn72IYRxSiH1QIkFOb3MuMs-/view?usp=sharing)
- [logo.img](https://drive.google.com/file/d/1dOtqcEptXq0L6GCBZsv3xa1YQSqv_f7M/view?usp=sharing) file

## 1. Download prerequisites, unpack [Logo Builder](https://drive.google.com/file/d/1_MSwPHimxn72IYRxSiH1QIkFOb3MuMs-/view?usp=sharing) and place [logo.img](https://drive.google.com/file/d/1dOtqcEptXq0L6GCBZsv3xa1YQSqv_f7M/view?usp=sharing) into the same folder.

## 2. Enter the folder and run `LogoBuilder.exe`

## 3. Click `Create new project` and change file type to `logo.img (logo.img)` and select the `logo.img` file you downloaded
<img src="https://i.imgur.com/lC1tNgI.png" width=700>

## 4. You will see some prompts. Move the slider up or down until you can see the images clearly. The program will need a few seconds to finish loading. Scroll down on this page to see how they should look.
<p><img src="https://i.imgur.com/soFZkwG.png" height=350><img src="https://i.imgur.com/gGV4W77.png" height=350><img src="https://i.imgur.com/3yX35I0.png" height=350><img src="https://i.imgur.com/4Hauwjd.png" height=350><img src="https://i.imgur.com/vNHYcZC.png" height=350></p>

## 5. Once it's done click the folder icon in the bottom-left corner.
<img src="https://i.imgur.com/938vEwI.png">

## 6. In the folder edit or replace `img1.png`
<img src="https://i.imgur.com/8Rbt5BJ.png">

# There are 2 ways to get the new logo on your device: using `fastboot` or `adb sideload in recovery`

## Fastboot
### 1. Once finished with the editing, go back to the app and click `Make`. It will take a bit to make the file.
<img src="https://i.imgur.com/rga03Gy.png">

### It will be finished when you see this
<img src="https://i.imgur.com/60tBCMA.png">

### 2. Go back to the project folder and scroll until you see `logo.bin`
<img src="https://i.imgur.com/GWYEyvI.png">

### 3. Copy this file to the `platform-tools folder`. Make sure `USB Debugging` is enabled on your device and run the command `adb reboot bootloader`. When your phone shows `fastboot_unlock_verify ok`, run this command `fastboot flash logo logo.bin`. When it finishes run `fastboot reboot` and your phone will restart and show your new boot logo. 
<img src="https://i.imgur.com/bP8LQBI.png">

## ADB sideload
### 1. Download and copy these files to project folder: [updater-script](https://drive.google.com/file/d/13_QkS4s3rBpwP3hWYQoGXYjD9ftoYFvy/view?usp=drivesdk), [update-binary](https://drive.google.com/uc?id=1UHfDA262JRcx6coWq6sf26fTII8DxFoi&export=download).
<img src="https://i.imgur.com/cIv2aWz.png">

### 2. Go back to the app and click `Make`. It will take a bit to make the file.
<img src="https://i.imgur.com/rga03Gy.png">

### It will be finished when you see this
<img src="https://i.imgur.com/60tBCMA.png">

### 3. Go back to the project folder and scroll until you see `update.zip`
<img src="https://i.imgur.com/c72BIGx.png">

### 4. Copy this file to the `platform-tools folder`. Make sure `USB Debugging` is enabled on your device and run the command `adb reboot recovery`. When your phone boots into recovery, select `Apply update > Apply from ADB` and run `adb sideload update.zip`. Once finished, in the recovery, go back to `Reboot system now` and your phone will restart and show your new boot logo. 

# IF you want to REMOVE the CUSTOM BOOT LOGO:

## Download the [logo.img](https://drive.google.com/file/d/1dOtqcEptXq0L6GCBZsv3xa1YQSqv_f7M/view?usp=sharing) file and move it to the `platform-tools` folder. Make sure `USB Debugging` is enabled on your device and run the command `adb reboot bootloader`. When your phone shows `fastboot_unlock_verify ok`, run this command `fastboot flash logo logo.bin`. When it finishes run `fastboot reboot` and your phone will restart and show the original boot logo. 


