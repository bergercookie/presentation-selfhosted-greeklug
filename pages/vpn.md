---
hideInToc: true
transition: none
---

# Secure access using [VPN]{style="color: green;"}

## 🎯 Goals

I'd like to

* Access my apps remotely
* Access by the same name, regardless of whether I'm
    at home or away.

To do that we

* Use [Wireguard](https://www.wireguard.com/) to create a VPN server at your
  public-facing VPS server
* Use <ins>systemd-resolved</ins> for split DNS resolution based on interface
  (`.af` for VPN, `.lan` for home)

  + If at home, resolve *.srv.bergercookie.dev via the homelab router directly.
  + If away, resolve *.srv.bergercookie.dev forward queries from VPN DNS
    resolver to home router.

Alternative:

* [Tailscale](https://tailscale.com/) - easier to set up, but not
    fully open-source and with restrictions

---
hideInToc: true
---

# Secure access using [VPN]{style="color: green;"}


<div v-click class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/name-resolution.json"
  class="w-[1000px]"
  :darkMode="true"
  :background="false"
/>
</div>

<!--

Use systemd-resovled since it allows for split DNS configuration per interface.

-->
