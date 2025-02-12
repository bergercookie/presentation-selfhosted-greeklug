---
layout: section
---

# Host [one]{style="color: green;"} app

Ubuntu server up and running, how do you host a new app?

---
layout: two-cols-header
hideInToc: true
layoutClass: gap-8
transition: none
---

<!--
you have a computer up and running at your place, now what?
-->

# Host [one]{style="color: green;"} app

e.g., [Grocy 🍲](https://grocy.info/)

::left::

<div style="gap: 1rem;">

> ERP beyond your fridge - Grocy is a web-based self-hosted groceries &
> household management solution for your home

</div>

- Install [`docker` and `docker-compose`](https://docs.docker.com/engine/install/ubuntu/)
- Create directories to keep the app data and the docker-compose file

  ```sh
  mkdir -p ~/selfhosted/grocy/config
  mkdir -p ~/dotfiles/docker/compose/grocy/
  ```

- Create `docker-compose.yml` file

::right::

<v-click>

```yaml {all|2|3|4|5-8|9-10|11|13|all}
services:
  grocy:
    image: lscr.io/linuxserver/grocy:latest
    container_name: grocy
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Etc/UTC
    port:
      - 8080:80
    volumes:
      - ~/selfhosted/grocy/config/:/config
    restart: unless-stopped
```

</v-click>

<br>
<br>
<br>

<!--
Here's how I would add a new app to my self-hosted setup ...

* Install docker on your server.
* Setup directories for your app's config and data  - sync config with git

* Why use docker - docker-compose?
  + Isolation from host system
  + Apps already provide docker images and docker-compose examples
  + docker-compoes already supports restarting the app on server boot or crash
-->

---
layout: two-cols-header
hideInToc: true
transition: none
---

# Host [one]{style="color: green;"} app

::left::

- Run `docker-compose up` to start the app
- Access the app at [http://localhost:8080](http://localhost:8080)

<br>
<v-click at="2">
🎉 🎉 🎉 🎉
<br>
🎉 🎉 🎉 🎉
<br>
🎉 🎉 🎉 🎉
<br>
🎉 🎉 🎉 🎉
</v-click>

::right::

<v-click>
<img src="/assets/grocy-up.png" alt="Grocy up" style="width: 100%;">
</v-click>
