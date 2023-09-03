---
title: Updating a Custom ROM
date: 2023-08-25
categories: [wiki]
tags: [wiki, updating, custom-rom]
---

## If your ROM has an OTA Updater use that if possible to install updates.

## Prerequisites:
- excluding `recovery image` and `vbmeta` the prerequisites remain the same as [`Prerequisites`](https://github.com/driedpampas/realme-8-megaguide?tab=readme-ov-file#prerequisites-1)

### 1. Rreboot to recovery mode with the command `fastboot reboot recovery` 
![](https://i.imgur.com/1zwXUmj.png)

### 2. In recovery, go to `Factory reset > Format cache partition` and hit `Yes`. Go back and select `Apply update > Apply from ADB`. You should see this when running `adb devices`:
![](https://i.imgur.com/MoiIS9k.png)

### 3. Now run the command `adb sideload custom-rom.zip` (replace *custom-rom.zip* with custom ROM package name). For example, I updated Pixel Experience Plus to the latest release:
![](https://i.imgur.com/WfOU1Yy.png)

### You might need to sideload GApps again

### 4. [Optional] If you were using KSU you'll need to reflash it. In recovery select `Apply update > Apply from ADB` and run `adb sideload kernelsu.zip`.