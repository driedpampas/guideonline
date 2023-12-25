---
title: FAQ
author: supernova
pubDatetime: 2023-08-05
postSlug: ""
featured: true
draft: false
tags:
  - wiki
  - faq
  - error
ogImage: ""
description: Frequently Asked Questions
canonicalURL: https://guide.driedpampas.ro.eu.org/faq
---

# FAQ (Frequently Asked Questions)

### 1. Why is there no progress when using SPFlash Tool?
- If you click download, but there is no progress, go to `Options > Option > Connection` and try another COM port. If still no progress, go back to `Options > Option > General` and untick `Storage Life Cycle Check`.

### 2. I patched my lk, but the phone still says `fastboot_verify_fail`
- Use command `python mtk r lk2 lk.bin` in *step 4*
- #### AND / OR
- Use [local method](posts/patching-lk-locally)

### 3. I can't reboot to fastboot using `adb reboot bootloader`.
- Try to access fastboot by turning the phone off and holding **Power and Volume Down** 

### 4. I got a `Signature Verification error` in recovery mode. What do I do?
- Tap `Yes` to continue anyway, this goes the same to any other ZIPs you flash.