<img align="right" src="https://github.com/n00b69/woa-mh2lm/blob/main/mh2lm.png" width="350" alt="Windows 11 running on mh2lm">

# Running Windows on the LG G8x

## Troubleshooting Issues
> Below you will find a list of common problems and their solutions

## The device reboots in mass storage mode
> This happens for some users, it is unknown why it happens, to bypass this, do the following:
- Reboot back into the modified TWRP and run `adb shell parted /dev/block/sda`, then run `print`.
- Run `set $ esp off` and `set $ msftdata on`, replacing **$** with the actual number of the esp partition (should be 31).
- Boot into fastboot mode using `adb reboot bootloader`, then download [**LGG8XMassStorageBoot.img**](https://github.com/n00b69/woa-mh2lm/releases/download/Files/LGG8XMassStorageBoot.img) and boot into it using `fastboot boot path\to\LGG8XMassStorageBoot.img`.
- After you finish the installation guide, before booting the Windows UEFI, return to TWRP, reopen **parted** and run `set $ esp on` and `set $ msftdata off`.

##### Finished!

## Cannot mount Windows in Android
If mounting Windows produces an empty folder, you either don't have Windows installed, or your rom does not have mount support.

Solution: Install **LineageOS 20**

##### Finished!

## Cannot write to Windows in Android
> This is caused by shutting down Windows instead of restarting it.
- To solve this, boot to Windows and then press "restart", then as the screen shuts off boot to fastboot and flash your Android boot image.
- Or, disable hibernation in Windows using [this](https://github.com/n00b69/woa-beryllium/releases/tag/1.0) script.
> Alternatively, if you have already set up the Switch to Android app, simply use this to switch to Android.

##### Finished!

## USB does not work
Enable USB host mode using the [additional materials guide](materials.md#toggling-usb-host-mode).

##### Finished!

## 0xc000021a BSOD
This usually means that winlogon.exe has failed, and you may need to reapply the Windows image.

##### Finished!

## The computer restarted unexpectedly or encountered an unexpected error
If you stumble upon this error, you may need to redeploy the Windows image. Use the [reinstall guide](reinstall.md) for this.

##### Finished!

## INACCESSIBLE_BOOT_DEVICE BSOD
This Blue Screen of Death likely means some broken driver installation. To fix this, reinstall the drivers using the [reinstall guide](reinstall.md).

##### Finished!













