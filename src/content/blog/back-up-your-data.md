---
title: Back up your data
author: supernova
pubDatetime: 2023-08-31
postSlug: ""
featured: false
draft: false
tags:
  - wiki
  - backup
ogImage: ""
description: Back up important partitons to restore system in case it gets bricked or needs to be restored to RealmeUI.
canonicalURL: https://guide.driedpampas.ro.eu.org/backup-data
---


> ⚠️ This method makes a backup of entire partitions, so you can restore your base system in case you want to go back to stock.

> 📛 PERSONAL DATA IS NOT BACKED UP USING THIS METHOD
{: .prompt-danger }

> ✨ Use GDrive, another cloud service, or transfer your personal data to a physical media, wherever you feel it is safe.
{: .prompt-info }

## Prerequisites
- [USB2SER](https://drive.google.com/file/d/1_SWiU9Ip9-sf8D-7VVIxcfXUpjsKlAdz/view?usp=drive_link)
- [USBDk](https://github.com/daynix/UsbDk/releases/download/v1.00-22/UsbDk_1.0.22_x64.msi)
- [Python from Microsoft Store](https://apps.microsoft.com/store/detail/python-310/9PJPW5LDXLZ5)
- [MTK Client archive](https://github.com/bkerler/mtkclient/archive/refs/heads/main.zip)

## 1. Install python, USB2SER (find the `cdc-acm.inf` file, right click and press `Install`) and USBdk

## 2. Run `pip3 install -r requirements.txt` in a cmd in `MTK Client's folder to install all required dependencies. Prepare a folder in which to store backed up partitions.

## 3. Turn your phone off, hold volume buttons, run this command `python mtk rl --skip userdata "<full path to store the backup files>" ` and connect your phone to your computer (Replace `<full path to store the backup files>` with the path of the folder you made in Step 2). If you want to back up specific partitions, use this command `python mtk r partition-name partition-name.img` (replace `partition-name` with the partition you want to back up. For example, for `boot` it would be `python mtk r boot boot.img`)
![](https://i.imgur.com/wBPSBxg.png)

> ## This is what will show while the backup is running:
{: .prompt-info }
![](https://i.imgur.com/PTG4sik.png)

## 4. After the command finishes, check the folder to make sure the backup was made to the correct location and that there are *51 files*
![](https://i.imgur.com/HL49pJa.png){: width="400" }

## To flash the entire backup back to your device use `python mtk wl (folder name)` in a command prompt. To only flash some files use `python mtk w (partition) (file name)`.

> 📛 A preloader file will be backed up inside `mtk client` folder. Keep that file as safe as possible, as it's crucial to restoring the firmware.

> 📛 DO NOT FLASH SOMEONE ELSE'S BACKUP FILES (only se firmware packages provided for that purpose and their instructions)
{: .prompt-danger }