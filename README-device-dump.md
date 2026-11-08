# Deeper Connect Air — device dump

Raw dumps pulled from a Deeper Connect Air (Allwinner H616, Armbian-based AtomOS) via a root shell obtained over UART (U-Boot `extraargs=init=/bin/bash` bypass — LUKS auto-unlocks with no passphrase prompt).

## Files (this Release's assets)

- `mmcblk2-full.img.part-00..NN` — full raw eMMC block device dump (`dd` of `/dev/mmcblk2`). Reassemble: `cat mmcblk2-full.img.part-* > mmcblk2-full.img`
- `rootfs-live.tar.part-00..NN` — live rootfs tar pulled over SSH. Reassemble: `cat rootfs-live.tar.part-* > rootfs-live.tar`
- `mmcblk2boot0.bin`, `mmcblk2boot1.bin` — eMMC boot0/boot1 (U-Boot SPL/bootloader) partitions.
- `SHA256SUMS.txt` — checksums of the original (unsplit) files, verify after reassembly.

## Verify after reassembly

```
sha256sum -c SHA256SUMS.txt
```
