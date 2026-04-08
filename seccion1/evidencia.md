# Research Questions 
1. What is LUKS and what is its relationship with dm-crypt in the Linux kernel? Explain the role of the device mapper in the encryption process.

LUKS (Linux Unified Key Setup) is the standard used in Linux for disk encryption. Its main purpose is to provide a standardized format for managing encryption keys, allowing multiple passwords and ensuring compatibility across systems.
dm-crypt, on the other hand, is a subsystem of the Linux kernel responsible for performing the actual encryption and decryption of data in real time.
The relationship between them is hierarchical: LUKS acts as the management layer (handling keys and access), while dm-crypt works as the encryption engine.
The Device Mapper plays a key role in this process. It creates a virtual block device that maps encrypted data from the physical disk into a decrypted view that the operating system can use. This allows the system to interact with encrypted storage as if it were a normal disk, hiding the complexity of encryption.


2. What is the difference between Full Disk Encryption (FDE) and Filesystem-Level Encryption (FLE)? Mention 2 advantages and 2 limitations of each.

The main difference between FDE and FLE lies in the scope of encryption.
Full Disk Encryption (FDE) encrypts the entire disk or partition, including system files, metadata, and swap space. In contrast, Filesystem-Level Encryption (FLE) encrypts only specific files or directories.
FDE Advantages:

Provides complete protection, including metadata and system files.
Simple to use, since only one password is needed for the whole system.

FDE Limitations:

Less flexible, as it does not allow different access levels for users.
Can impact performance because all disk sectors are encrypted.

FLE Advantages:

More flexible, allowing selective encryption of sensitive files.
Supports multiple users with different encryption keys.

FLE Limitations:

Metadata such as filenames may remain visible.
Risk of leaving temporary or system files unencrypted.


3.  What is LVM and what are its three abstraction layers (PV, VG, LV)? What advantages does LVM offer over traditional partitioning in a server environment?

LVM (Logical Volume Manager) is a storage management system in Linux that provides a flexible way to manage disk space by abstracting physical storage.
It is based on three layers:
Physical Volume (PV): The actual physical disks or partitions.
Volume Group (VG): A pool of storage created by combining one or more PVs.
Logical Volume (LV): Virtual partitions created from the VG, used by the operating system.

Advantages of LVM:

Dynamic scalability: Volumes can be resized without needing to unmount or reformat the system in many cases.
Flexible management: New disks can be added to expand storage without affecting running applications.


4.  Explain what happens during the boot process of a system with LUKS+LVM: at what point is the decryption password requested and what role does GRUB play in this process?

During the boot process of a system using LUKS and LVM, several steps occur before the operating system loads completely.
First, the system firmware (BIOS/UEFI) loads the bootloader (GRUB). If the /boot partition is encrypted, GRUB will request the decryption password at this stage. Otherwise, GRUB loads the Linux kernel and the initramfs without requiring a password.
The key step happens during the initramfs stage. At this point, the system detects that the root filesystem is encrypted with LUKS and prompts the user to enter the decryption password.
Once the correct password is provided, dm-crypt decrypts the disk and unlocks the LUKS container. Then, LVM activates and detects the logical volumes inside the decrypted container. Finally, the root filesystem is mounted, and the operating system continues booting normally.


# List of screenshots

Figure 1.1.1 – Boot menu and selection of Debian installer
Figure 1.1.2 – Language selection screen
Figure 1.1.3 – Location (region) configuration
Figure 1.1.4 – Keyboard layout selection
Figure 1.1.5 – Network configuration (automatic DHCP)
Figure 1.1.6 – Hostname configuration
Figure 1.1.7 – Domain name configuration (optional)
Figure 1.1.8 – Root password setup
Figure 1.1.9 – Creation of new user account
Figure 1.1.10 – User password configuration
Figure 1.1.11 – Disk partitioning method selection
Figure 1.1.12 – Selection of LVM with disk encryption
Figure 1.1.13 – Disk selection for partitioning
Figure 1.1.14 – LUKS encryption password setup
Figure 1.1.15 – Partition scheme confirmation
Figure 1.1.16 – Installation of base system
Figure 1.1.17 – GRUB bootloader installation
