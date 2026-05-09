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

* Use [Tailscale](https://tailscale.com/) to create point-to-point between
    mobile devices and home network.
* Self-host [Headscale](https://headscale.net/) as the Tailscale control node.
* Split DNS configuration
  + If at home, resolve *.srv.bergercookie.dev via the homelab router directly.
  + If away, resolve *.srv.bergercookie.dev forward queries from VPN DNS
    resolver to home router.

---
hideInToc: true
transition: none
---

# Secure access using [VPN]{style="color: green;"}

<v-click>

## Why use Tailscale (and not WireGuard directly)?

</v-click>
<v-click>

* Point-to-point communication (no added latency, no single point of failure)
* Easy to add new nodes to the network (no need to move private keys etc.)
* Good tooling, UI to manage nodes, users, and apply access control (no need for
  direct iptables usage)

</v-click>
<v-click>

## Why _not_ use Tailscale?

* Not trivial to connect to multiple Tailscale networks at the same time (e.g.,
    work and home)

</v-click>
<v-click>

## Why self-host Headscale (and not use Tailscale's control node)?

</v-click>
<v-click>

If in the Tailscale free tier

* Restrictions on the number of users and devices (i.e., cannot give to friends
    and family)
* Cannot set ACLs (Access Control Lists) to restrict access to specific nodes

At the same time, we piggyback on Tailscale's apps.

</v-click>

---
hideInToc: true
transition: none
---

# Secure access using [VPN]{style="color: green;"}

<div v-click class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/caddy-configuration-p47.json"
  class="w-[1000px]"
  :darkMode="true"
  :background="false"
/>
</div>



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

* Tailscale/headscale allows for split DNS configuration per interface.

-->
