
# uefi-install-rocky-linux (version 1.2.0)

Install Rocky Linux from a local block device in UEFI mode

## Usage:

Boot the server into the Rescue Console, connect to the server via SSH and run these commands as root:

```
# cd ~

# git clone https://github.com/makhomed/uefi-install-rocky-linux

# cd uefi-install-rocky-linux/

# mv uefi-install-rocky-linux.toml.example uefi-install-rocky-linux.toml

# vim uefi-install-rocky-linux.toml

# ./uefi-install-rocky-linux
```

The script ```uefi-install-rocky-linux``` will print an error message in case of any errors, or display the summary screen after successful execution if no errors in the configuration file are detected.

The summary screen after successful execution will look like this:

```
Install Rocky Linux 9.5

UEFI boot from /dev/disk/by-id/ata-INTEL_SSDSC2KB960G8_PHYF82857386960CGN /dev/disk/by-id/ata-INTEL_SSDSC2KB960G8_PHYF82857217960CGN

Using kickstart https://example.com/linux-server-name-kickstart.cfg

VNC password: E3klJrWI

IP addresses: 11.22.33.44 2001:0DB8:4ED2:3217::55

Press <Enter> to reboot
```

After pressing `<Enter>`, the server will reboot. It will then automatically start the requested Rocky Linux installation by booting from the local block device in UEFI mode, as specified in the configuration file.

It is possible to install Rocky Linux in a fully or semi-automated way using kickstart files. For more details, refer to [Automatically installing RHEL](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/9/html-single/automatically_installing_rhel/index) in the [Red Hat Enterprise Linux Documentation](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/).

