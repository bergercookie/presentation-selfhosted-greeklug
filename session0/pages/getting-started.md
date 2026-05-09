---
hideInToc: true
---

# Homelab?

Your software/hardware setup to self-host services/apps of your
choice.

This includes:

* Hardware: compute, NAS, network equipment (router, switches, etc.), etc.
* Software: OS, containerization, reverse proxy, VPN, DNS, apps, etc.

<!--
Η δική σου ρύθμιση λογισμικού/υλικού για να φιλοξενείς υπηρεσίες/εφαρμογές της επιλογής σου.

Αυτό περιλαμβάνει:

* Υλικό: υπολογιστής, NAS, δικτυακός εξοπλισμός (router, switches, κλπ.)
* Λογισμικό: λειτουργικό σύστημα, containerization, reverse proxy, VPN, DNS, εφαρμογές, κλπ.
-->

---
hideInToc: true
---

# What's this about?

Describe my current self-hosted setup

* What tools to use
* What are the challenges
* What are some tips to manage your self-hosted setup
* What apps you could self-host / example scenarios


<!--

* Εργαλεία
* Προβλήματα και προκλήσεις

* Αυτή είναι η **προσωπική μου εμπειρία**, τα δικά σας αποτελέσματα μπορεί να διαφέρουν
* Κάποια **πολύ τεχνικά** για κάποιους - άλλα σημεία είναι **πολύ γενικά** για άλλους
* _έμπνευση_ και _συμβουλές_ για να φτιάξεις το δικό σου setup.

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

**Η ιδέα - Η Υπόθεση**

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

* 💵 **ακριβή**
* 📺 Σε ενοχλούν οι **διαφημίσεις**
* 👁️ παραβίαση ιδιωτικότητας - **εμπιστοσύνη** δεδομένων σου
* 🔒 **vendor lock-in**
* 🌼 Θέλεις να μάθεις πώς να το κάνεις μόνος σου

___

* Δεν ελέγχεις τους όρους χρήσης, μπορεί να αλλάξουν το προϊόν, να το κλείσουν, κλπ.
* Δες τα exports της βάσης δεδομένων του Notion

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
Υπάρχει πραγματικός κίνδυνος απώλειας δεδομένων / κωδικών κλπ.
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
-->

---
hideInToc: true
---

# What do I need?

1. [A computer]{style="color: green;"} to run the services
   - Options: Raspberry PI, mini-PC NUC-variants (e.g., [Lenovo ThinkCentre](https://www.skroutz.gr/s/55659444/Lenovo-ThinkCentre-M910q-Tiny-Refurbished-Grade-A-Core-i5-6400T-4GB-500GB-HDD-No-OS-Repainted.html)),  old laptop
2. [DNS name]{style="color: green;"}
   - Options: Cloudflare(https://www.cloudflare.com/) / [GoDaddy](https://www.godaddy.com/) etc, ~10€/year 
   - Prefer Cloudflare; Alternatively free dynamic DNS from [DuckDNS](https://www.duckdns.org/) (but this is more work)
3. VPS with [public, static IP]{style="color: green;"}
   - Options: [DigitalOcean](https://www.digitalocean.com/), [Linode](https://www.linode.com/), [Oracle Cloud](https://www.oracle.com/cloud/free/) etc.
   - Prefer Oracle Cloud (Free tier has unlimited egress traffic)
4. [Dedicated router]{style="color: green;"} hardware
   - Options: ISP Router software, [Raspberry Pi](https://www.raspberrypi.org/) with [Pi-hole](https://pi-hole.net/), [OPNsense](https://opnsense.org/), [OpenWRT](https://openwrt.org/)
   - Prefer OpenWRT
5. [NAS]{style="color: green;"} for media and backups storage
   - Dedicated hardware, with multiple bays for RAID (e.g., [Synology](https://www.synology.com/) / [QNAP](https://www.qnap.com/))


<!--
1. Υπολογιστής για να τρέχεις τις υπηρεσίες
2. Όνομα DNS για να πάρεις SSL πιστοποιητικά
3. VPS για VPN peer για απομακρυσμένη πρόσβαση
4. Router
   - Γέφυρα επικοινωνίας με VPN
   - Ίδια πρόσβαση σαν να είσαι σπίτι
   - LAN DNS resolution
   - Ορισμοί ζωνών και firewall rules μεταξύ ζωνών
   - "Φορητό" setup - αν αλλάξεις πάροχο δεν ξανα-σετάρεις το router

* Γιατί να αποφύγεις το router του ISP (περιοριστικό / πιθανώς χωρίς VPN, ζώνες, κλπ.)
-->

