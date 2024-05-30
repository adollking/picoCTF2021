# Matryoshka doll

## Description

Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another.
What's the final one? Image: this


## Solution

```console

┌──(root㉿DESKTOP)-[/picoCTF/picoCTF2021/Matryoshka doll]
└─# binwalk dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383938, name: base_images/2_c.jpg
651612        0x9F15C         End of Zip archive, footer length: 22
```

ah we got zip inside image, lets exctract with 7z

```console 
┌──(root㉿DESKTOP)-[/picoCTF/picoCTF2021/Matryoshka doll]
└─# 7z x  dolls.jpg

7-Zip 23.01 (x64) : Copyright (c) 1999-2023 Igor Pavlov : 2023-06-20
 64-bit locale=en_US.UTF-8 Threads:4 OPEN_MAX:1024

Scanning the drive for archives:
1 file, 651634 bytes (637 KiB)

Extracting archive: dolls.jpg
--
Path = dolls.jpg
Type = zip
Offset = 272492
Physical Size = 379142

Everything is Ok

Size:       383938
Compressed: 651634

┌──(root㉿DESKTOP)-[picoCTF/picoCTF2021/Matryoshka doll]
└─# ll
total 644
drwxrwxrwx 1 root root   4096 May 28 15:41 base_images
-rwxrwxrwx 1 root root 651634 Mar 16  2021 dolls.jpg
-rwxrwxrwx 1 root root    868 May 28 15:40 readme.md
```
repeat proses until get 4_c.jpeg

and get flag.txt

```console
 cat flag.txt
picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}
```
