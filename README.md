# ubuntu-surface4

A guide to duel boot your Microsoft Surface 4

![](assets/ubuntu-surface4.png)

Please &#9733; this repo if you found it useful &#9733; &#9733; &#9733;


## Instructions

### Preparing the Installer
1. Download and install [etcher](https://etcher.io/)

2. Download [Ubuntu 16.04 LTS](https://www.ubuntu.com/download/desktop/contribute?version=16.04.3&architecture=amd64)

3. Using etcher, burn the downloaded *.iso file to a flashdrive

### Prepare the Windows Machine

1. Using the diskmgmt tool, shrink your C: Windows partition

2. Disable Windows secure boot

### Install Ubuntu

Boot into your flashdrive and install the operating system.
Make sure you use the largest empty partition so you don't erase your Windows operation system.

### Patch the Bootloader

1. Boot into your flashdrive again and open a command prompt.

2. Mount your newly installed operating system partition (probably `/dev/nvme0n1p5`) to `/mnt`

3. Download the bootloader patches to `/mnt/boot/efi/EFI/Boot`

```sh
sudo su
mount /dev/nvme0n1p5 /mnt
cd /mnt/boot/efi/EFI/Boot
curl -OL https://github.com/jamrizzi/ubuntu-surface4/blob/master/bootloader-patch/HashTool.efi
curl -OL https://github.com/jamrizzi/ubuntu-surface4/blob/master/bootloader-patch/bootx64.efi
```

### Patch the kernel

1. Boot into your new operating system

2. Install the surface kernel patches (you may need an external keyboard for this step)

```sh
sudo su
add-apt-repository ppa:tigerite/kernel
apt-get update
apt-get install linux-surface
```


## Support

Submit an [issue](https://github.com/jamrizzi/ubuntu-surface4/issues/new)


## Buy Me Coffee

A ridiculous amount of coffee was consumed in the process of building this project.

[Add some fuel](https://jamrizzi.com/#!/buy-me-coffee) if you'd like to keep me going!


## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D


## License

[MIT License](https://github.com/jamrizzi/ubuntu-surface4/blob/master/LICENSE)

[Jam Risser](https://jamrizzi.com) &copy; 2017


## Credits

* [Jam Risser](https://jamrizzi.com) - Author


## Changelog

0.0.1 (2017-09-20)
* Initial release
