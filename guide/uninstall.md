<img align="right" src="https://github.com/n00b69/woa-mh2lm/blob/main/mh2lm.png" width="350" alt="Windows 11 running on mh2lm">

# Running Windows on LG G8x

## Uninstalling Windows

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [Parted script](https://github.com/n00b69/woa-mh2lm/releases/download/Files/parted)
  
- [TWRP or Orange Fox](https://github.com/n00b69/woa-mh2lm/releases/tag/Recoveries)

### Boot TWRP on the device
> Use the Magisk module linked above if you don't already have it installed

#### Unmount all partitions
> Go to mount in TWRP and unmount all partitions

### Run parted
> Put parted in your platform tools folder, then run
```cmd
adb push parted /cache && chmod 755 /cache/parted && /parted /dev/block/sda
```

#### Delete Windows Partition
> Use `print all` to make sure that partition 32 is Windows
```sh
rm 32
```

#### Delete ESP Partition
> Use `print all` to make sure that partition 31 is ESP
```sh
rm 31
```

#### Resize userdata Partition
> Use `print all` to make sure that partition 30 is userdata
```sh
resizepart 30
126GB
```

#### Exit Parted
```sh
quit
```

### Format data
Go to the Wipe menu in TWRP and press Format Data, then type `yes`

#### Check if Android boots
Reboot your device and check if Android boots.

## Finished!







