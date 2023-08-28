# airgap-ca

Checklist:
- [ ] OS image downloading & verifying (PGP or whatever)
- [ ] Tools downloading & verifying (PGP or whatever)
- [ ] Generating bootable (EFI) image with read-only root file system
- [ ] Unprivileged user
- [ ] USBGuard predefined whitelist
    - [ ] [Storage devices][usbguard-storage]
- [ ] Secure boot
    - [ ] Tooling to roll self-signed keys
- [ ] Custom kernel configuration
    - [ ] Investigate if selected distribution has required features enabled (see below)
    - [ ] (otherwise) Disable networking support
- [ ] dm-verity
    - [ ] Setting up keys into kernel keyring
        - [Default genkey config][kernel-x509-cfg]
        - [Via UEFI(?)][x509-via-uefi]
        - [Oracle blogpost: The Machine Keyring][the-machine-keyring]
        - _I think I saw a script to append new keys to an existing kernel image somewhere..._
    - [ ] erofs setup

[kernel-x509-cfg]: https://github.com/torvalds/linux/blob/42a7f6e3ffe06308c1ec43a7dac39a27de101574/certs/default_x509.genkey
[x509-via-uefi]: https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/managing_monitoring_and_updating_the_kernel/signing-a-kernel-and-modules-for-secure-boot_managing-monitoring-and-updating-the-kernel
[the-machine-keyring]: https://blogs.oracle.com/linux/post/the-machine-keyring
[usbguard-storage]: https://usbguard.github.io/documentation/rule-language#allow-usb-mass-storage-devices-usb-flash-disks-and-block-everything-else
