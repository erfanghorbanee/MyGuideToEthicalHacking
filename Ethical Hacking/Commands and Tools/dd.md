# dd

The `dd` command is a low-level utility that copies and converts raw data. 

## Example

`dd if=/dev/sda of=/mnt/dest/image.dd bs=512`

1. **`dd`**: This is the command itself, which stands for "data duplicator." It is a versatile and powerful tool for copying data at the block level, making it useful for tasks such as backing up entire disk drives.

2. **`if=/dev/sda`**: This part specifies the input file (`if`) for the `dd` command. In this case, `/dev/sda` refers to the first SATA hard disk drive in the system. This is effectively the source from which data will be copied.

3. **`of=/mnt/dest/image.dd`**: This specifies the output file (`of`) for the `dd` command. Here, the data read from `/dev/sda` will be written to a file named `image.dd`, which is located in the directory `/mnt/dest/`. This directory is assumed to be a mounted file system where you want to store the disk image.

4. **`bs=512`**: This sets the block size (`bs`) to 512 bytes. The `bs` parameter defines how much data `dd` reads and writes at a time. In this case, it will read and write 512 bytes of data in each block. This size is significant because 512 bytes is the traditional size of a sector on a hard disk, so it aligns with the underlying hardware architecture for many disk drives.

### What the command does:

This `dd` command creates a bit-by-bit copy of the entire `/dev/sda` disk, storing this copy in a file named `image.dd` within `/mnt/dest/`. It is effectively creating an exact clone of the entire drive, including all partitions, boot sectors, and filesystems present on the original disk.

### Uses and considerations:

- **Backup and Recovery**: This command is commonly used for creating backups of entire drives. The resulting `image.dd` file can be used to restore the drive's state at the point the image was taken.
- **Forensic Analysis**: In digital forensics, this type of command is used to create exact replicas of drives for analysis, without affecting the data on the original device.
- **Data Recovery**: It can also be used to recover data from failing drives or corrupted partitions by making a safe copy of the data to another location.

### Caution:

Using `dd` requires caution as it performs low-level copying and can overwrite data irreversibly. Always ensure the destination (`of=`) is correctly specified, and be very careful when specifying the input (`if=`) to avoid data loss.


## dc3dd

A patched version of GNU dd with added features for computer forensics, developed at the DoD Cyber Crime Center by Jesse Kornblum. It supports:

- On the fly hashing with multiple algorithms (MD5, SHA-1, SHA-256, and SHA-512) with variable sized piecewise hashing
- writing errors directly to a file
- combined error log, pattern wiping, verify mode, progress reports, split output
