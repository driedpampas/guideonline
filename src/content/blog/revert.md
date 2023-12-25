---
title: Revert
author: supernova
pubDatetime: 2023-12-23
postSlug: ""
featured: false
draft: false
tags:
  - wiki
  - revert
ogImage: ""
description: Use this to revert to stock RealmeUI 3 and lock the bootloader.
---

## Flashing stock RUI 3

1. Open the console in [MTK Client's](https://github.com/bkerler/mtkclient/archive/refs/heads/main.zip) folder

![](https://i.imgur.com/RJtobaI.png)

2. Send the payload with `python mtk payload`. It should look like this: 

   ![](https://i.imgur.com/WSQsVj1.png)
   
3. Make sure your phone is powered off, hold down both **Vol+, Vol-** and connect the usb cable.

4. MTK Client should output something like this:

   ![](https://i.imgur.com/lr7HIN0.png)
   
6. The phone is now in BROM mode. Run the [SP Flash tool](https://drive.google.com/file/d/11XeUnCYtARZg2kx7J2JWWeLULieSIYrx/view?usp=sharing) [flash_tool.exe]
7. Click on `Options > Option...`
8. Make sure the right **COM Port** is selected, UART enabled and baud rate is set to **921600**.

   ![](https://i.imgur.com/hnMsyeN.png)

9. Get [SG's C.18 RUI3 Firmware](https://drive.google.com/file/d/1YHSIr4itg_5dPE2IbWAH9N8g6L5CGmaG/view?usp=drive_link) and unpack it
10. Load `MT6785_Android_scatter.txt` from SG's firmware

    ![](https://i.imgur.com/8APQvkx.png)	

11. Remember to have `Download Only` mode

    ![](https://i.imgur.com/M3aUNBs.png)

12. Place your phone on a stable surface, to not disconnect anything. This process will take up to 15-20 minutes. To get C.18 on your phone, click `Download`. [**No progress? Click me**](#if-you-click-download-but-there-is-no-progress-go-to-options--option--general-and-untick-storage-life-cycle-check-if-still-no-progress-go-back-to-options--option--connection-and-try-another-com-port)

    ![](https://i.imgur.com/uSXflCJ.png)

13. If everything goes well, it should look like this:

    ![](https://i.imgur.com/qeJWt3a.png)

## Locking bootloader

1. Make sure your phone is off and Hold down both **Vol+, Vol-** - **(Don't leave the buttons until the command is done)** 
2. Type `python mtk e metadata,userdata,md_udc` - This command wipes your data - and connect your phone. It should look like this:

   ![](https://i.imgur.com/HfPsrpU.png)

3. Lock the bootloader using command `python mtk da seccfg lock`.