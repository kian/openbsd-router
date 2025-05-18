# OpenBSD router configuration

Configuration files for my [OpenBSD](https://www.openbsd.org) router.  The best operating system for the job, hands down.  Inspired by [jaywillikers/openbsd-router](https://github.com/jwillikers/openbsd-router).

Tested on OpenBSD 7.5 / -current.

 - [pf](https://www.openbsd.org/faq/pf/) firewall
 - IPv6 ([dhcp6leased](https://man.openbsd.org/dhcp6leased.8), [rad](https://man.openbsd.org/rad.8))
 - DHCP/NAT
 - NTP
 - Unbound for internet/local DNS resolution (DNS-over-TLS)
 - WiFi via attached access point

## Hardware

 - Router: 4x i226-V 2.5G LAN 12th Gen Intel N100 (8GB DDR5, 128GB NVMe)
 - Access Point: ASUS RT-AC68U
 - Modem: ARRIS Surfboard S33 DOCSIS 3.1

Eventually I may switch the router to a [Protectli Vault](https://protectli.com/).  I want to use [coreboot](https://www.coreboot.org/) however the Protectli devices are expensive and/or have slower CPUs / 1Gbps NICs.

## Serial Console

I am using a [USB-C to RJ45 cable](https://www.amazon.com/dp/B08F7VY86M) to access the device's serial console.

Add the following to `/etc/boot.conf` to invoke the serial console at every boot.
```
set tty com0
```

If you want an interactive console, modify `/etc/ttys` as [described in the OpenBSD FAQ](https://www.openbsd.org/faq/faq7.html#SerCon):

```
tty00	"/usr/libexec/getty std.9600"	vt220 	on  secure
```

To access the device from MacOS, find the device name and use the built in `cu`:

```
$ ls -al /dev/tty.usbserial*
...
$ sudo cu -l /dev/tty.usbserial-CHANGEME
```

On Windows, you can use [plink](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) or [SimplySerial](https://github.com/fasteddy516/SimplySerial).

## Credits / Resources

 - https://github.com/jwillikers/openbsd-router
 - https://www.openbsd.org/faq/pf/example1.html
 - https://www.openbsd.org/faq/current.html
 - https://kirill.korins.ky/articles/edgerouter-4-under-openbsd-with-failover-wan/
