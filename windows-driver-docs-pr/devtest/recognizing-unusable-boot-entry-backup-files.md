---
title: Recognizing Unusable Boot Entry Backup Files
description: Recognizing Unusable Boot Entry Backup Files
ms.assetid: ff61c8e9-ad6b-4f3f-9c4b-72c24c27eda6
keywords:
- NVRAM boot options WDK ,
- EFI NVRAM boot options WDK ,
ms.author: windowsdriverdev
ms.date: 04/20/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# Recognizing Unusable Boot Entry Backup Files


## <span id="ddk_recognizing_unusable_boot_entry_backup_files_tools"></span><span id="DDK_RECOGNIZING_UNUSABLE_BOOT_ENTRY_BACKUP_FILES_TOOLS"></span>


Unfortunately, boot entry backup copies are not always usable.

In an EFI environment, applications and drivers identify disk partitions by a partition GUID. If the disk partition GUID changes for any reason, then the partition GUID in the boot entry backup copy is no longer valid and the EFI boot loader cannot use the backup copy to boot the system.

The following Bootcfg sample shows a boot entry that was imported with invalid partition GUIDs.

```
Boot entry ID:    4
OS Friendly Name: Windows Server 2003 - mydebug
OsLoadOptions:    /debug /debugport=com1 /baudrate=115200
BootFilePath:     (null)
OsFilePath:       (null)
```

In this case, you must recreate the boot entry by copying another boot entry from the operating system installation, and then changing the parameters.

 

 





