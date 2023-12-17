---
title: Patching LK locally
author: supernova
pubDatetime: 2023-09-24
postSlug: ""
featured: false
draft: false
tags:
  - wiki
  - patch
ogImage: ""
description: If the online method doesn't work try this manual method!
---

1. Go back to the [MTK Client](https://github.com/bkerler/mtkclient/archive/refs/heads/main.zip) folder

2. Open the console again in `MTK Client` folder
   ![](https://i.imgur.com/RJtobaI.png)

3. Make sure your phone is powered off, hold down both **Vol+, Vol-** and connect the usb cable.

4. Run the command `python mtk r lk lk.bin`. There will now be a `lk.bin` file in **MTK Client** folder.

   ![](https://i.imgur.com/gL4Qpc2.png)

5. Download [lkpatcher](https://codeload.github.com/R0rt1z2/lkpatcher/zip/refs/heads/main) and extract it. Navigate to the `lkpatcher folder`. It should contain a file `main.py`.

   ![](https://i.ibb.co/r68tF52/Screenshot-from-2023-08-02-16-29-59.png)

   ![](https://i.ibb.co/R9VhQPn/Screenshot-from-2023-08-02-16-30-22.png)

6. Move `lk.bin` to **lkpatcher folder**. Open the console in **lkpatcher** folder

   ![](https://i.imgur.com/RJtobaI.png)

7. Run command `python main.py lk.bin -o lk-patched.bin`. A `lk-patched.bin` file will be created. Move it to **MTK Client** folder.

   > ✴️ If you get errors, use command `python mtk r lk2 lk.bin` in _step 4_

   ![](https://i.ibb.co/9rc1cKF/Untitled.jpg)

8. Run command `python mtk w lk lk-patched.bin`
