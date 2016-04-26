# rtl8812AU_8821AU_linux

rtl8812AU_8821AU linux kernel driver for AC1200 (801.11ac) Wireless Dual-Band USB Adapter

## Compiling with DKMS

```sh
# sudo cp -R . /usr/src/rtl8812AU_8821AU_linux-1.0
# sudo dkms add -m rtl8812AU_8821AU_linux -v 1.0
# sudo dkms build -m rtl8812AU_8821AU_linux -v 1.0
# sudo dkms install -m rtl8812AU_8821AU_linux -v 1.0
```

### Compiling for Raspberry Pi 2

Install kernel headers and other dependencies.

```sh
# sudo apt-get install linux-image-rpi2-rpfv linux-headers-rpi2-rpfv dkms build-essential bc
```

Append following at the end of your ``/boot/config.txt``, reboot your Pi

```sh
kernel=vmlinuz-3.10-3-rpi2
initramfs initrd.img-3.10-3-rpi2 followkernel
```

Edit Makefile and turn on ``CONFIG_PLATFORM_ARM_RPI``, turn off ``CONFIG_PLATFORM_I386_PC``

```sh
CONFIG_PLATFORM_I386_PC = n
CONFIG_PLATFORM_ARM_RPI = y
```

```sh
# cd /usr/src/rtl8812AU_8821AU_linux
# sudo make clean
# sudo make
# sudo make install
# sudo modprobe -a 8812au
```

## Contributors
<!-- DO NOT EDIT - CONTRIBUTORS.md is autogenerated from git commit log by contributors.sh script. -->

- Anand Babu (AB) Periasamy
- Andreas Hofmann
- Andrew Mann
- AndyPi
- Anton
- archshift
- bits3rpent
- Chen Minqiang
- Daiki Tamada
- HackDefendr
- Harshavardhana
- Joe Acosta
- John Lenz
- Karl-Philipp Richter
- Marco Milanesi
- mpoly
- pgroenbech
- scrivy
- Vicent Llongo
- Victor Azizi
