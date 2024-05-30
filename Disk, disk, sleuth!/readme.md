# Disk, disk, sleuth!

## Description
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: dds1-alpine.flag.img.gz

## Solution

we can use autospy

you can install with sudo apt install autopsy

```console

┌──(root㉿DESKTOP)-[/picoCTF/picoCTF2021/Disk, disk, sleuth!]
└─# srch_strings dds1-alpine.flag.img | grep pico
ffffffff81399ccf t pirq_pico_get
ffffffff81399cee t pirq_pico_set
ffffffff820adb46 t pico_router_probe
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_564ff1a0}
```
