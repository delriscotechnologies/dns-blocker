<h1 align="center">DNS-BLOCKER</h1>

<p align="center">
  Network-wide DNS filtering with Pi-hole and Cisco OpenDNS for ads, trackers, phishing, and unwanted content across a home network.
</p>

<p align="center">
  <a href="https://delriscotechnologies.github.io/dns-blocker/">Full Write-Up</a>
</p>

---

DNS Blocker documents a two-layer DNS filtering setup using Pi-hole for local domain blocking and OpenDNS as the upstream resolver for category-based filtering.

The setup applies one DNS policy across devices on the home network without requiring browser extensions or per-device filtering software.

> DNS is a critical network service. A wrong router address, failed server, or overly aggressive blocklist can interrupt connectivity across the network.

## References

- [Pi-hole installation](https://docs.pi-hole.net/main/basic-install/)
- [Pi-hole blocking modes](https://docs.pi-hole.net/ftldns/blockingmode/)
- [OpenDNS Home Internet Security](https://www.opendns.com/home-internet-security/)
- [HaGeZi DNS blocklists](https://github.com/hagezi/dns-blocklists)
