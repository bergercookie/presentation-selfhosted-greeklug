---
transition: none
---

# Access homelab apps via [reverse proxy]{style="color: green;"}

<v-clicks>

* Point all `*.homelab.lan` queries to homelab server IP address
  + OpenWRT: `/*.homelab.lan/192.168.33.30`

* Setup [caddy](https://caddyserver.com/) as another docker-compose-based
    service. Listen on ports `80`, `443`.<br>Delegate to the right app based on
    the name in the request

* Setup new docker network for caddy and apps to share

* When client connects to the `http(s)://<service-name>.homelab.lan`
    caddy reverse-proxies the request to the appropriate app container:

   * `babybuddy.homelab.lan` -> `babybuddy` container
   * `grocy.homelab.lan` -> `grocy` container
   * ...
</v-clicks>

---
transition: none
hideInToc: true
---

# Access homelab apps via [reverse proxy]{style="color: green;"}

Create homelab bridge network

```bash
docker network create homelab_net
```

Connect app to homelab bridge network

<v-click>

<<< @/snippets/babybuddy-docker-compose.yml {all|5-6,15-17}{lines: true}

</v-click>

---
transition: none
hideInToc: true
---

# Access homelab apps via [reverse proxy]{style="color: green;"}

Connect caddy to new network

<<< @/snippets/caddy-docker-compose.yml {all|11-15|7-8,18-20}{lines: true}

---
transition: none
hideInToc: true
---

# Access homelab apps via [reverse proxy]{style="color: green;"}

Sample caddy configuration file

<<< @/snippets/babybuddy-section-caddyfile.txt {all|5-10}{lines: true}
