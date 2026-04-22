---
layout: section
---

# Host [one]{style="color: green;"} app

Ubuntu server up and running, how do you host a new app?

<!--
* You have installed a fresh Ubuntu server on your computer of choice, now what?
-->

---
hideInToc: true
layoutClass: gap-8
transition: none
---

# Host [one]{style="color: green;"} app

e.g., [Grocy 🍲](https://grocy.info/)


> ERP beyond your fridge - Grocy is a web-based self-hosted groceries &
> household management solution for your home

<br>

<img src="/assets/grocy-demo.png" alt="Grocy demo" style="width: 100%;">

---
layout: two-cols-header
hideInToc: true
layoutClass: gap-8
transition: none
---

# Host [one]{style="color: green;"} app

e.g., [Grocy 🍲](https://grocy.info/)

::left::

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
      - /home/myuser/selfhosted/grocy/config/:/config
    restart: unless-stopped
```

</v-click>

<!--
Here's how I would add a new app to my self-hosted setup ...

* Install docker on your server.
* Setup directories for your app's config and data  - sync config with git

* Why use docker - docker-compose?
  + Isolation from host system
  + App vendors/developers already provide docker images and docker-compose
      sample configs
  + `docker-compose` already supports restarting the app on server boot or crash
-->

---
layout: two-cols-header
hideInToc: true
transition: none
---

# Host [one]{style="color: green;"} app

- Run `docker-compose up` to start the app
- Access the app at [http://localhost:8080](http://localhost:8080)

<br>

<v-click>
<img src="/assets/grocy-up.png" alt="Grocy up" style="width: 100%;">
</v-click>

<br>

<v-click>
🎉 🎉 🎉 🎉 🎉 🎉 🎉 🎉
<br>
🎉 🎉 🎉 🎉 🎉 🎉 🎉 🎉
<br>
🎉 🎉 🎉 🎉 🎉 🎉 🎉 🎉
</v-click>


