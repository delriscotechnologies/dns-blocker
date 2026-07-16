<h1 align="center">DNS-BLOCKER</h1>

<p align="center">
  Network-wide DNS filtering with Pi-hole and Cisco OpenDNS for ads, trackers, phishing, and unwanted content across a home network.
</p>

---

DNS Blocker documents a two-layer filtering setup built around a repurposed 2010 iMac running Zorin OS. Pi-hole handles local DNS blocking for every device on the network, while OpenDNS acts as the upstream resolver and applies category-based filtering and basic threat protection.

The router assigns the server a reserved local address and distributes Pi-hole as the network DNS service. Pi-hole blocks configured ad and tracker domains, then forwards permitted queries to OpenDNS. The server is administered from a Windows computer over SSH, so phones, laptops, televisions, and other clients receive protection without browser extensions or per-device configuration.

This repository contains static technical documentation only. It does not include an installer, router configuration, Pi-hole database, query logs, credentials, blocklist copies, or a deployable server image.

> DNS is a critical network service. A wrong router address, failed server, or overly aggressive blocklist can interrupt connectivity across every client. Keep a tested rollback path and make changes only on networks you own or administer.

## Project Stages

1. **DNS foundation** - understand normal resolution and where a DNS policy can block a request.
2. **OpenDNS filtering** - register the home network, select filtering categories, and verify policy enforcement.
3. **Dedicated host** - update Zorin OS, enable SSH, and reserve a stable address for the iMac.
4. **Pi-hole installation** - download and review the official installer before running it with elevated privileges.
5. **Blocklist management** - add trusted community lists, update gravity, and allowlist legitimate services when needed.
6. **Router adoption** - advertise Pi-hole to clients, keep OpenDNS upstream, and verify queries in the Pi-hole dashboard.

## Scope and Safeguards

- Reserve the Pi-hole server address through DHCP so the router never advertises a stale DNS destination.
- Point clients to Pi-hole and configure OpenDNS inside Pi-hole; advertising OpenDNS directly as a secondary client resolver can bypass local blocking.
- Use a second Pi-hole for real DNS redundancy instead of a public fallback that silently bypasses policy.
- Download the official Pi-hole installer, inspect it locally, and avoid piping an unreviewed remote script directly into a privileged shell.
- Restrict the Pi-hole dashboard and SSH service to the trusted local network; use strong credentials and SSH keys where possible.
- Keep router credentials, OpenDNS account details, public addresses, local hostnames, client identities, and DNS query logs out of Git.
- Enable OpenDNS and Pi-hole logging intentionally, protect the resulting browsing metadata, and retain it only as long as needed.
- Review community blocklists before use and monitor false positives; larger lists do not automatically provide better protection.
- Back up router settings and Pi-hole configuration before major changes, then document a known-good recovery resolver.
- Update Zorin OS, Pi-hole, and blocklists regularly, and verify filtering after every network change.
- The HTML page is documentation only; it does not configure the router or install Pi-hole automatically.

## References

- [Pi-hole installation](https://docs.pi-hole.net/main/basic-install/)
- [Pi-hole upstream DNS providers](https://docs.pi-hole.net/guides/dns/upstream-dns-providers/)
- [OpenDNS Home Internet Security](https://www.opendns.com/home-internet-security/)
- [OpenDNS support](https://www.opendns.com/support/)
