<h1 align="center">DNS-BLOCKER</h1>

<p align="center">
  Network-wide DNS filtering with Pi-hole and Cisco OpenDNS for ads, trackers, phishing, and unwanted content across a home network.
</p>

<p align="center">
  <a href="https://delriscotechnologies.github.io/dns-blocker/">Full Write-Up</a>
</p>

---

DNS Blocker documents a two-layer filtering setup built around a repurposed 2010 iMac running Zorin OS. Pi-hole handles local domain blocking, while OpenDNS acts as the upstream resolver and applies category-based filtering and basic threat protection.

The router assigns the server a reserved local address and distributes Pi-hole as the network DNS service. Pi-hole evaluates each query against its configured lists and forwards permitted queries to OpenDNS. Phones, laptops, televisions, and other clients receive the same DNS policy without browser extensions or per-device filtering software.

Blocked queries are answered according to the configured product and blocking mode. Pi-hole can return a null or sinkhole address, `NXDOMAIN`, `NODATA`, or `REFUSED`; a blocked query is not simply dropped. The write-up uses HaGeZi Multi PRO because the project recommends it as a balanced list. Multi ULTIMATE is more aggressive and can cause legitimate services to fail.

This repository contains static technical documentation only. It does not include an installer, router configuration, Pi-hole database, query logs, credentials, blocklist copies, or a deployable server image.

> DNS is a critical network service. A wrong router address, failed server, or overly aggressive blocklist can interrupt connectivity across every client. Keep a tested rollback path and make changes only on networks you own or administer.

## References

- [Pi-hole installation](https://docs.pi-hole.net/main/basic-install/)
- [Pi-hole blocking modes](https://docs.pi-hole.net/ftldns/blockingmode/)
- [OpenDNS Home Internet Security](https://www.opendns.com/home-internet-security/)
- [HaGeZi DNS blocklists](https://github.com/hagezi/dns-blocklists)
