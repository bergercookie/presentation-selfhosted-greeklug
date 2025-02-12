---
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Make your own home lab
info: |
  Build, manage, and secure your personal self-hosted setup

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
layout: image-right
image: https://www.cnet.com/a/img/resize/d07ee1249a5dbddf4d06f9275d6354bf91fda6a1/hub/2017/01/14/6d8103f7-a52d-46de-98d0-56d0e9d79804/se7en.png?auto=webp&width=1920
hideInToc: true
---

# What's in the ~~box~~ presentation?

<Toc text-sm minDepth="1" maxDepth="2" />

<!--
Getting started includes:
* What's this presentation about?
* Requirements
* Reasons to do it / not do it
* Hardware to buy

<br>

* go through an example app to host - see the technical problems and solve them in the next sections
* Network view: See how apps, overall software and the hardware in our self-hosted setup all fit together
* Go through some example apps
-->

---
src: ./pages/getting-started.md
---

---
src: ./pages/host-one.md
---

<!-- Router DNS -->

<!-- TODO -->

---
src: ./pages/questions-to-answer0.md
---

---
src: ./pages/router-dns.md
---

<!-- Reverse proxy -->

---
src: ./pages/questions-to-answer.md
---

---
src: ./pages/reverse-proxy.md
---

<!-- SSL -->

---
src: ./pages/questions-to-answer.md
---

---
src: ./pages/ssl.md
---

<!-- VPN -->

<!-- TODO -->

---
src: ./pages/questions-to-answer.md
---

---
src: ./pages/vpn.md
---

---
src: ./pages/questions-to-answer.md
---

---
src: ./pages/backup.md
---

---
src: ./pages/network-segmentation.md
---

---
src: ./pages/apps-to-host-suggestions.md
---

---
src: ./pages/summary.md
---
