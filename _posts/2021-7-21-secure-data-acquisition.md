---
layout: post
title: Secure Data Acquisition
date: 2021-07-21 9:40:00 --0000
permalink: /posts/secure-data-acquisition/
---

Many data repositories require hard drive encryption. One of the software that can encrypt an entire hard drive for the Windows 10 Home edition is DiskCryptor. Their most recent build was a beta published on April 27, 2020. On their GitHub page, they suggested that we keep a backup and a Windows 2 Go drive on hand just in case.

There are instructions for creating a disk backup [here](https://www.windowscentral.com/how-make-full-backup-windows-10), and for creating a bootable drive [here](https://www.windowscentral.com/how-create-windows-10-usb-bootable-media-uefi-support).

The other option is [VeraCrypt](https://www.veracrypt.fr/en/Home.html). The current version, 1.24-Update7, can only encrypt the system drive (C:) and the data drive (D:) separately. 