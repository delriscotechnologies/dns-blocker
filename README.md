<h1 align="center">DNS-BLOCKER</h1>

<p align="center">
  Network DNS filtering with Pi-hole and OpenDNS for devices configured to use Pi-hole as their DNS resolver.
</p>

<p align="center">
  <a href="https://delriscotechnologies.github.io/dns-blocker/">Full Write-Up</a>
</p>

---

DNS Blocker documents a two-layer DNS filtering setup using Pi-hole for local domain blocking and OpenDNS as the upstream resolver for category-based filtering.

Devices using Pi-hole receive domain filtering without browser extensions or per-device filtering software. Alternative DNS resolvers, including those advertised over IPv6, can bypass it.

> DNS is a critical network service. A wrong router address, failed server, or overly aggressive blocklist can interrupt connectivity across the network.

## References

- [Pi-hole installation](https://docs.pi-hole.net/main/basic-install/)
- [Pi-hole blocking modes](https://docs.pi-hole.net/ftldns/blockingmode/)
- [OpenDNS Home Internet Security](https://www.opendns.com/home-internet-security/)
- [HaGeZi DNS blocklists](https://github.com/hagezi/dns-blocklists)
