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
---

# What's in the ~~box~~ presentation?

<Toc text-sm minDepth="1" maxDepth="2" />


---
src: ./scenarios-base.md
---

---
transition: fade
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

# 📽️ Media server

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
src: ./scenarios-base.md
---

---
transition: fade
hideInToc: true
---

# 📚 Document management / knowledge base

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/kb0.json"
  class="w-[650px]"
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

# 📚 Document management / knowledge base

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/kb1.json"
  class="w-[650px]"
  :darkMode="false"
  :background="false"
/>
</div>

<!--

* calibre-web is just a nice Web UI on top of calibre's ebook management
    functionalities.

* Kavita is more for manga and comics, but you can still use it for ebooks. It
  has more features and it's better maintained. Can't really import your calibre
  library

  * Stores your progress/page for each book

* Clear winners in all but the knowledge base / note-taking category, where
  there are multiple good options

  * I choose trilium because
    + Server/client architecture, PWA
    + rich features
    + no tags, but, same note in multiple paths
    + extensible with JS/TS
    + Journaling
    + Support for templates
    + Decent support on android
-->

---
transition: fade
hideInToc: true
---

# 📚 Document management / knowledge base

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/kb2.json"
  class="w-[650px]"
  :darkMode="false"
  :background="false"
/>
</div>


---
transition: fade
hideInToc: true
---

# 📚 Document management / knowledge base

<div class="flex flex-col items-center">
<Excalidraw
  drawFilePath="./drawings/kb3.json"
  class="w-[650px]"
  :darkMode="false"
  :background="false"
/>
</div>

---
src: ./scenarios-base.md
---

---
layout: image
image: /assetes/tika.png
transition: fade
---

<!-- # 🏭 Personal productivity -->
<!---->
<!-- ```mermaid {scale: 0.85} -->
<!-- mindmap -->
<!--   root((Personal productivity)) -->
<!--     🎯 Task Management -->
<!--       Vikunja -->
<!--     ☎️ Contacts and Calendars -->
<!--       Baikal -->
<!--         Android contacts <br> DavX5 -->
<!---->
<!--       Radicale -->
<!--         Android calendar <br> DavX5 -->
<!---->
<!--     🔑 Password Management -->
<!--       Vaultwarden -->
<!--     🥧 Inventory and Household -->
<!--       Grocy -->
<!--       Mealie -->
<!-- ``` -->

<!--

* Υπηρεσίες που χρησιμοποιώ καθημερινά και θεωρώ ως αναπόσπαστο κομμάτι του
    homelab μου.

-->

---
src: ./scenarios-base.md
---


---
transition: fade
---

# 🏗️ Homelab infrastructure maintenance

---
src: ./scenarios-base.md
---

---
transision: fade
---

# 🛠️ Utilities - lightning round
