
# What the heck is Ubuntu MATE?

From the [official website][ubuntu_mate]:
> The MATE Desktop has a rich history and is the continuation of the GNOME2 desktop, which was the default desktop environment on many Linux and Unix operating systems for over a decade. This means that MATE Desktop is tried, tested and very reliable.

> While MATE Desktop provides the essential user interfaces to control and use a computer, Ubuntu MATE adds a collection of additional applications to turn your computer into a truly powerful workstation.

This particular Ubuntu flavour actually provides ready-to-run image for the Raspberry Pi 2 and Raspberry Pi 3. Since I recently got one of the latter series, I decided to give the MATE a spin.

It turned out the excitement ended just about after the completion of installation process.

First of all, the operating system was running noticeably more slowly than the official OS supported by the Raspberry community, [Raspbian][raspbian].

I'm appending Pi 3's specs for reference:
>- Quad Core 1.2GHz Broadcom BCM2837 64bit CPU
- 1GB RAM
- BCM43438 wireless LAN and Bluetooth Low Energy (BLE) on board
- 40-pin extended GPIO
- 4 USB 2 ports
- 4 Pole stereo output and composite video port
- Full size HDMI
- CSI camera port for connecting a Raspberry Pi camera
- DSI display port for connecting a Raspberry Pi touchscreen display
- Micro SD port for loading your operating system and storing data
- Upgraded switched Micro USB power source up to 2.5A

# Wi-Fi device not ready?!?

Second, despite having had proper access to the Wi-Fi router during installation, MATE wasn't able to detect the device upon first boot. The solution? Fortunately, that was a simple one - the network manager service needed to be restarted:

```
sudo service network-manager restart
```

Nevertheless, that wasn't enough to keep MATE on my Raspberry Pi 3 SD card. If you don't trust me, go ahead and give it a try :)

[ubuntu_mate]: https://ubuntu-mate.org/what-is-ubuntu-mate/
[raspbian]: https://www.raspberrypi.org/downloads/raspbian/


---

