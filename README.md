# OpenBSD router configuration

Configuration files for my [OpenBSD](https://www.openbsd.org) router.  The best operating system for the job, hands down.

Tested on OpenBSD 7.5 / -current.

 - [pf](https://www.openbsd.org/faq/pf/) firewall
 - DHCP/NAT
 - NTP
 - Unbound for internet/local DNS resolution (DNS-over-TLS)
 - WiFi via attached access point

## Hardware

 - Router: 4x i226-V 2.5G LAN 12th Gen Intel N100 (8GB DDR5, 128GB NVMe)
 - Access Point: ASUS RT-AC68U
 - Modem: ARRIS Surfboard S33 DOCSIS 3.1

Eventually I may switch the router to a [Protectli Vault](https://protectli.com/).  I want to use [coreboot](https://www.coreboot.org/) however the Protectli devices are expensive and/or have slower CPUs.

## Other Resources

 - https://www.openbsd.org/faq/pf/example1.html
 - https://www.openbsd.org/faq/current.html
 - https://github.com/jwillikers/openbsd-router
