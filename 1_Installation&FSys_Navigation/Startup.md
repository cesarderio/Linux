# BIOS, UEFI, and the Linux Startup Process:

<br>

## BIOS - Basic Input/Output System:

- BIOS is firmware on a chip on the motherboard, providing the first layer of interaction between the hardware and the OS.
- It initializes hardware components during the boot process.

<br>

## UEFI - Unified Extensible Firmware Interface:

- UEFI is the modern successor to BIOS.
- Offers features like secure boot, Trusted Platform Module (TPM) support, GUI-based configuration options, and support for larger disk sizes.

<br>

## Linux Run Levels:

- **0**: Power off
- **1**: Rescue/emergency single-user mode, typically for root/administrative access
- **3**: Multi-user mode without a graphical user interface, commonly used for servers
- **5**: Multi-user mode with a graphical user interface
- **6**: Reboot

Commands:
- View current run level: `runlevel`
- Reboot the system: `sudo init 6`
- Shutdown the system: `sudo init 0`

Scripts:

- **S** (Start script): Scripts that start services.
- **K** (Kill script): Scripts that stop services.

<br>

### DRACUT Utility:

- A tool that can be used to customize the Linux startup process, especially the initial ramdisk (initrd).

<br>

## Linux Startup Process:

- **Initializes BIOS or UEFI**: Checks system integrity and loads the Master Boot Record (MBR).
- **MBR loads GRUB**: The bootloader (GRUB, located at `/boot/grub/grub.cfg` on Ubuntu) presents the boot menu.
- **Kernel Loading**: After a menu entry is selected, GRUB loads the compressed Linux kernel (`vmlinuz`) and executes `mkinitrd` to prepare for mounting the root filesystem.
    - **vmlinuz**: The compressed Linux kernel.
    - **mkinitrd** (make initial RAM disk): Creates an initrd to mount the root filesystem.
- **Run `/sbin/init`**: The first process that the kernel starts, leading to the establishment of a temporary RAM disk (initrd) until the kernel is fully booted.
- **initrd**: Initializes a RAM disk used during the boot process.
- **Launch runlevel-configured programs**: Based on the target run level.

<br>

## TPM - Trusted Platform Module:

- A dedicated microcontroller designed for secure hardware cryptographic processing.
- Commonly built into server motherboards or available as an add-on.
- The Linux kernel can detect the presence of a TPM chip.
- Encryption tied to the TPM chip ensures that encrypted data is bound to the specific hardware.
- Removing an encrypted storage device prevents decryption or access when used on different hardware.
- The OS disk must be decrypted with the TPM before the OS boot continues.

<br>

## UEFI and Secure Boot:

- Secure Boot is a feature of UEFI firmware.
- Ensures that only trusted software with a valid digital signature is loaded during the boot process.
- Can be disabled for older OS versions or dual-boot configurations.
