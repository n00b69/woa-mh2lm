<img align="right" src="https://github.com/n00b69/woa-mh2lm/blob/main/mh2lm.png" width="350" alt="Windows 11 running on mh2lm">

# Running Windows on the LG G8x

## Updating drivers

### Prerequisites
- [Mass storage image](https://github.com/n00b69/woa-mh2lm/releases/download/Files/msc.img)
  
- [Drivers](https://github.com/n00b69/woa-mh2lm/releases/tag/Drivers)

- [UEFI image](https://github.com/n00b69/woa-mh2lm/releases/tag/UEFI)

### Reboot into fastboot mode
> If you don't have access to fastboot, use the instructions in the [partitioning guide](1-partition.md) to flash the engineering ABL.
- With the device turned off, hold the **volume down** button, then plug the cable in.

#### Boot into the mass storage mode UEFI
> Replace `path\to\msc.img` with the actual path of the image
```cmd
fastboot boot path\to\msc.img
```

#### Enabling mass storage mode
> Once booted into the UEFI, use the volume buttons to navigate the menu and the power button to confirm
- Select **UEFI Boot Menu**.
- Select **USB Attached SCSI (UAS) Storage**.
- Press the **power** button twice to confirm.

> [!Note]
> After 1-2 minutes **WINMH2LM** should automatically appear in Windows Explorer. If it does, skip to the "Installing drivers" step, else continue with the "Diskpart" steps.

### Diskpart
```cmd
diskpart
```

#### Select the phone's Windows volume
> Use `list volume` to find it, replace `$` with the actual number of **WINMH2LM**
```diskpart
select volume $
```

#### Assign the letter x
```diskpart
assign letter x
```

#### Exit diskpart
```diskpart
exit
```

### Installing Drivers
> Unpack the driver archive, then open the `OfflineUpdater.cmd` file (if an error shows up, run `OfflineUpdaterFix.cmd` instead)

> If it asks you to enter a letter, enter the drive letter of **WINMH2LM** (which should be **X**), then press enter

### Reboot your device
> Force reboot your phone by holding **volume down** + **power** until you see the LG logo.
>
> If you end up in Android instead of Windows, simply use the WOA Helper app to switch back.

## Finished!



