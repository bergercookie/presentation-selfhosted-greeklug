---
theme: default
# theme: bricks
# theme: nord
colorSchema: light
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev

background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Make your own home lab
info: |
  Build, manage, and secure your personal self-hosted setup | Part 2

# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
hideInToc: true
addons:
    - slidev-addon-excalidraw
---

# Make your own homelab

## Build, manage, and secure your personal self-hosted setup

---
hideInToc: true
---

# Previously on homelab ...

* What's a homelab? Definition and terms
* Environment setup, tools to use, prior knowledge
* App bringup
* Reverse proxying
* SSL certificate issuing
* VPN configuration
* Backup strategies - data redundancy

---
layout: image-right
image: https://www.cnet.com/a/img/resize/d07ee1249a5dbddf4d06f9275d6354bf91fda6a1/hub/2017/01/14/6d8103f7-a52d-46de-98d0-56d0e9d79804/se7en.png?auto=webp&width=1920
hideInToc: true
disabled: true
---

# What's in the ~~box~~ presentation?

<Toc text-sm minDepth="1" maxDepth="2" />


---
src: ./scenarios-base.md
routeAlias: scenarios-base
---

---
transition: fade
routeAlias: media-server
---

# 📽️ Media server

## Goals

1. Cross platform: Watch content (movies, TV series, etc.) across devices, OS-es
2. Convenient, easy-to-use: Provide native or progressive web apps
3. Watch from anywhere
4. Easy to *download* new content
5. Easy to *share* content with friends and family

<!--

* Cross platform not only in terms of applications but also in terms of
    supporting a
    `server - client` model

-->

---
transition: fade
hideInToc: true
---

# 📽️ Media server

<div v-click class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/media-server0.json"
  class="w-[700px]"
  :darkMode="false"
  :background="false"
/>
</div>

<!--

Πώς μεταφράζω εγώ αυτές τις προδιαγραφές

-->

---
transition: fade
hideInToc: true
---

# 📽️ Media server

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/media-server1.json"
  class="w-[700px]"
  :darkMode="false"
  :background="false"
/>
</div>

---
transition: fade
hideInToc: true
---

# 📽️ Media server <sup style="font-size: 0.4em"><a href="https://demo.jellyfin.org/stable">Jellyfin</a></sup>


<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/media-server2.json"
  class="w-[700px]"
  :darkMode="false"
  :background="false"
/>
</div>

<!--

* Don't self-host the notifiers
  + If anything goes wrong (even with other homelab functionalities) or if
    you've forgotten to sign in VPN, you still get notifications
  + Get utility email from google + app-specific password
* Radarr, Sonarr, etgc. are too technical for users. Use `Jellyseerr`, it's
    simpler and prettier.
* Include prowlarr alongside radarr and sonarr to aggregate indexers and make it
    easier to manage them
* Use bazarr to automatically download subtitles
* Radarr, Sonarr, etc. notify Jellyfin to refresh media library when new content
    is downloaded
* Radarr, Sonarr, etc. also notify Jellyseerr, in turn notifies the user
* Use `transmission-openvpn` docker image to run transmission in a VPN container
    for better security and privacy. Make sure to set up proper volume mounts to
    access downloaded content and configuration files.
-->

---
hideInToc: true
src: ./scenarios-base.md
---

---
transition: fade
hideInToc: true
routeAlias: knowledge-base
---

# 📚 Documents / knowledge base

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/kb0.json"
  class="w-[700px]"
  :darkMode="false"
  :background="false"
/>
</div>


<!--

Βασική υπόθεση: Να μπορείτε να κάνετε τα εξής μόνοι σας με υπηρεσίες στο δικό
σας homelab

-->

---
transition: fade
hideInToc: true
---

# 📚 Documents / knowledge base <sup style="font-size: 0.4em"><a href="https://demo.kavitareader.com">Kavita</a> · <a href="https://trilium.srv.bergercookie.dev">Trilium</a></sup>

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/kb1.json"
  class="w-[700px]"
  :darkMode="false"
  :background="false"
/>
</div>

<!--

- Το calibre-web είναι απλά ένα ωραίο Web UI πάνω από το calibre για ebooks.

- Το Kavita είναι κυρίως για manga/comics, αλλά δουλεύει και για ebooks. Έχει περισσότερα features, καλύτερη συντήρηση, δεν κάνει import τη βιβλιοθήκη calibre.

  - Αποθηκεύει πρόοδο/σελίδα ανά βιβλίο.

- Ξεκάθαροι νικητές σε όλα εκτός από knowledge base/σημειώσεις, όπου υπάρχουν πολλές καλές επιλογές.

  - Επέλεξα το trilium γιατί:
    + Server/client, PWA
    + Πλούσια χαρακτηριστικά
    + Όχι tags, αλλά ίδια σημείωση σε πολλά paths
    + Επεκτάσιμο με JS/TS
    + Journaling
    + Templates
    + Καλή υποστήριξη σε android
-->

---
transition: fade
hideInToc: true
---

# 📚 Documents / knowledge base <sup style="font-size: 0.4em"><a href="https://demo.kavitareader.com">Kavita</a> · <a href="https://paperless.srv.bergercookie.dev/dashboard">Paperless</a> · <a href="https://trilium.srv.bergercookie.dev">Trilium</a></sup>

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/kb2.json"
  class="w-[700px]"
  :darkMode="false"
  :background="false"
/>
</div>


---
transition: fade
hideInToc: true
---

# 📚 Documents / knowledge base <sup style="font-size: 0.4em"><a href="https://demo.kavitareader.com">Kavita</a> · <a href="https://paperless.srv.bergercookie.dev/dashboard">Paperless</a> · <a href="https://trilium.srv.bergercookie.dev">Trilium</a></sup>

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/kb3.json"
  class="w-[700px]"
  :darkMode="false"
  :background="false"
/>
</div>

---
hideInToc: true
src: ./scenarios-base.md
---

---
transition: fade
routeAlias: personal-productivity
---

# 🏭 Personal productivity

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/prod0.json"
  class="w-[700px]"
  :darkMode="false"
  :background="false"
/>
</div>

<!--

* Υπηρεσίες που θα ωφεληθείτε από το να είναι self-hosted, για λόγους απορρήτου,
  ασφάλειας, ευκολίας
* Χρησιμοποιώ καθημερινά, αναπόσπαστο μέρος του homelab μου.

-->

---
hideInToc: true
transition: fade
---

# 🏭 Personal productivity <sup style="font-size: 0.4em"><a href="https://demo.firefly-iii.org">Firefly III</a> · <a href="https://babybuddy.srv.bergercookie.dev">Baby Buddy</a> · <a href="https://miniflux.srv.bergercookie.dev">Miniflux</a></sup>

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/prod1.json"
  class="w-[700px]"
  :darkMode="false"
  :background="false"
/>
</div>

<!--
* Caldav
* Cardav

Παρόμοια προτόκολα για interoperability μεταξύ servers και clients
-->

---
hideInToc: true
src: ./scenarios-base.md
---


---
transition: fade
routeAlias: homelab-infra
---

# 🏗️ Homelab infrastructure

* Enable secure and convenient access to homelab services
* Receive timely notifications for service security updates (esp. if
  public-facing)
* Version-control homelab config files
* Monitor logs, start and stop containers, etc.
* Monitor service and computer uptimes
* Monitor usage stats (CPU, RAM, disk, network) and logs
* Access files/directories in homelab PC

<!--

* Caddy for reverse proxying (with subdomain naming) + TLS certificates
* Tailscale for VPN
* diun - only enable for security updates - otherwise too much noise if you have
    many services
* Using file browser, should probably go for `copyparty` instead

-->

---
hideInToc: true
transition: fade
---

# 🏗️ Homelab infrastructure

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/infra0.json"
  class="w-[700px]"
  :darkMode="false"
  :background="false"
/>
</div>

---
hideInToc: true
transition: fade
---

# 🏗️ Homelab infrastructure <sup style="font-size: 0.4em"><a href="https://srv.bergercookie.dev">Homepage</a> · <a href="https://dockge.srv.bergercookie.dev">Dockge</a> · <a href="https://files.srv.bergercookie.dev">Files</a> · <a href="https://openobserve.srv.bergercookie.dev">OpenObserve</a> · <a href="https://uptime.srv.bergercookie.dev">Uptime Kuma</a></sup>

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/infra1.json"
  class="w-[700px]"
  :darkMode="false"
  :background="false"
/>
</div>

---
hideInToc: true
src: ./scenarios-base.md
---

---
routeAlias: utilities
title: 🛠️ Utilities - lightning round
---

# 🛠️ Utilities - lightning round <sup style="font-size: 0.4em"><a href="https://demo.immich.app">Immich</a> · <a href="https://docs.getgrist.com">Grist</a> · <a href="https://stirlingpdf.io">Stirling PDF</a> · <a href="https://demo.firefly-iii.org">Firefly III</a> · <a href="https://podfetch.srv.bergercookie.dev">Podfetch</a></sup>

<div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 2rem; text-align: center; align-items: center;">

<div v-click style="display: flex; flex-direction: column; align-items: center;">
  <p style="font-size: 1.3em;">Store photos & videos</p>
  <img src="/public/assets/immich.svg" style="border-radius: 12px; width: 80px; height: 80px;" />
  <p><strong style="font-size: 1.5em;">Immich</strong></p>
</div>

<div v-click style="display: flex; flex-direction: column; align-items: center;">
  <p style="font-size: 1.3em;">Spreadsheet-database hybrid</p>
  <img src="/public/assets/grist.svg" style="border-radius: 12px; width: 80px; height: 80px;" />
  <p><strong style="font-size: 1.5em;">Grist</strong></p>
</div>

<div v-click style="display: flex; flex-direction: column; align-items: center;">
  <p style="font-size: 1.3em;">All-in-one PDF toolkit</p>
  <img src="/public/assets/stirling-pdf.svg" style="border-radius: 12px; width: 80px; height: 80px;" />
  <p><strong style="font-size: 1.5em;">Stirling PDF</strong></p>
</div>

<div v-click style="display: flex; flex-direction: column; align-items: center;">
  <p style="font-size: 1.3em;">Track baby milestones</p>
  <img src="/public/assets/baby-buddy.svg" style="border-radius: 12px; width: 80px; height: 80px;" />
  <p><strong style="font-size: 1.5em;">Baby Buddy</strong></p>
</div>

<div v-click style="display: flex; flex-direction: column; align-items: center;">
  <p style="font-size: 1.3em;">Personal finance manager</p>
  <img src="/public/assets/firefly-iii.svg" style="border-radius: 12px; width: 80px; height: 80px;" />
  <p><strong style="font-size: 1.5em;">Firefly III</strong></p>
</div>

<div v-click style="display: flex; flex-direction: column; align-items: center;">
  <p style="font-size: 1.3em;">Low-latency voice chat</p>
  <img src="/public/assets/mumble.svg" style="border-radius: 12px; width: 80px; height: 80px;" />
  <p><strong style="font-size: 1.5em;">Mumble</strong></p>
</div>

<div v-click style="display: flex; flex-direction: column; align-items: center;">
  <p style="font-size: 1.3em;">Minimalist RSS reader</p>
  <img src="/public/assets/miniflux.svg" style="border-radius: 12px; width: 80px; height: 80px;" />
  <p><strong style="font-size: 1.5em;">Miniflux</strong></p>
</div>

<div v-click style="display: flex; flex-direction: column; align-items: center;">
  <p style="font-size: 1.3em;">Auto-download podcasts</p>
  <img src="/public/assets/podfetch.svg" style="border-radius: 12px; width: 80px; height: 80px;" />
  <p><strong style="font-size: 1.5em;">Podfetch</strong></p>
</div>

</div>

---
hideInToc: true
src: ./scenarios-base.md
---

---
layout: cover
---

# 🧠 Wrap-up - the big picture

---
---

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/overall.json"
  class="w-[950px]"
  :darkMode="false"
  :background="false"
/>
</div>

<!--

* Ξεκινήστε από κάποιο απλό service, εξοικειωθείτε με αυτό, δείτε τα προβλήματα που προκύπτουν, λύστε τα, προσθέστε και άλλα.

-->

---
layout: image
image: /assets/self-host-all.jpg
backgroundSize: 50%
hideInToc: true
---

# <div style="color: black">The end 👋👋👋</div>
