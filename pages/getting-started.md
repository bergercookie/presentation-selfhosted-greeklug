---
hideInToc: true
---

# Homelab?

Your personal software/hardware setup at home to self-host services/apps of your
choice.

This includes:

* Hardware: computer, NAS, router, network setup
* Software: OS, containerization, reverse proxy, VPN, DNS, apps

---
hideInToc: true
---

# What's this about?

Describe my current self-hosted setup

* What tools to use
* What are the challenges
* What are some tips to manage your self-hosted setup
* What apps you could self-host


<!--
* This is my personal experience building this; YMMV
* This is what I'd like to discuss; How I built it and how you could potentially reach something similar for your own needs.

* Some bits too technical for some
* Some other bits too generic for others

Ultimately a bit all over the place but hopefully _inspiration_ and _tips_ on
how to build your own setup.
-->

---

# Getting Started

💡 Hey, I have a computer - can I build/host my own:

<v-clicks>

- ✔️Todoist
- ✍️Notion
- 🖼️Google Photos
- 📽️ Netflix

</v-clicks>

<!--

The premise:

-->

---
hideInToc: true
---

# Why do it?

<v-clicks>

* 💵 commercial app is too pricy
* 📺 you hate ads
* 👁️ you have privacy concerns
* 🔒 you want to avoid vendor lock-in
* 🌼 you want to learn how to do it yourself

</v-clicks>

<!--
* See Notion database exports
-->

---
hideInToc: true
---

# Why skip it?

<v-clicks>

* You manage your data (security, backups)
* You manage your hardware
* You do more work (setup, debugging, maintenance)

</v-clicks>

<!--
There is a real risk of losing data / passwords etc.
-->

---
hideInToc: true
---

# Prior knowledge

<v-clicks>

- Familiarity with Linux and the command line.
- A good understanding of networking concepts: IP addresses, ports, DNS,
  routing, etc.
- Basic knowledge of Docker and containers.
- Familiar with TLS/SSL and certificates.
- Basic understanding of web servers and reverse proxies.

</v-clicks>

<!--
* some of the topics should still be useful for beginners
-->

---
hideInToc: true
---

# What do I need?

1. [A computer]{style="color: green;"} to run the services
   - Alternatives: Raspberry PI, mini-PC NUC-variants,  old laptop
2. [DNS name]{style="color: green;"}
   - ~10€/year from Cloudflare(https://www.cloudflare.com/) / [GoDaddy](https://www.godaddy.com/) etc.
   - Prefer Cloudflare; Alternatively free dynamic DNS from [DuckDNS](https://www.duckdns.org/) (but this is more work)
3. VPS with [public, static IP]{style="color: green;"}
   - Options: [DigitalOcean](https://www.digitalocean.com/), [Linode](https://www.linode.com/), [Oracle Cloud](https://www.oracle.com/cloud/free/) etc.
   - Prefer Oracle Cloud (Free tier has unlimited egress traffic)
4. [Dedicated router]{style="color: green;"} hardware
   - Use [OpenWRT](https://openwrt.org/)
   - Alternatively use a [Raspberry Pi](https://www.raspberrypi.org/) with [Pi-hole](https://pi-hole.net/)
5. [NAS]{style="color: green;"} for media and backups storage
   - Dedicated hardware, with multiple bays for RAID (e.g., [Synology](https://www.synology.com/) / [QNAP](https://www.qnap.com/))

<!--
1. Computer for actually running the services
2. DNS Domain name for getting SSL certificates
3. VPS for VPN peer for remote access
4. Router
   - Bridge communication with VPN
   - Allow same Access as if you were at home
   - LAN DNS resolution
   - Zone definitions and firewall rules between zones


* Mention why to avoid ISP router (restrictive / probably no VPN support, zones,
    etc.)
-->
