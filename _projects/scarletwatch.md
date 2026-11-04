---
layout: page
title: ScarletWatch
description: Self-hosted alerts when a closed Rutgers course section opens
importance: 2
summary: A self-hosted tool that sends a free phone notification the moment a closed Rutgers course section opens, with a web dashboard and a command-line interface.
tech:
  - Python
  - FastAPI
  - SQLite
  - HTMX
  - Docker
---

**Python, FastAPI, SQLite, HTMX, Docker** · [Source on GitHub](https://github.com/nithin-sai-ega/scarletwatch)

{% include figure.liquid loading="eager" path="assets/img/scarletwatch-dashboard.jpg" alt="The ScarletWatch dashboard showing watched course sections and their open or closed status" class="img-fluid rounded z-depth-1" %}

- Built a self-hosted watcher that checks Rutgers' public Schedule of Classes data about once a minute and sends a free push notification, Discord message, or email the moment a closed section opens.
- Designed it to be polite to the server: one request per semester per cycle however many sections are watched, a 30-second minimum interval enforced in code, and exponential backoff that honors `Retry-After`.
- Guarded against bad data, such as empty lists or sudden drops in size, so a glitch is skipped and never triggers a false alert.
- Modeled each watch as a state machine that alerts exactly once per closed-to-open change, retries undelivered alerts, and records how long each section stayed open.
- Built a FastAPI and HTMX dashboard that works in light and dark mode and on a phone, where you add sections by index number or by searching the course catalog, remove them, and send a test notification.
- Packaged it with a command-line tool, a Docker image, and a systemd unit so it can run on a laptop, a Raspberry Pi, or a server.
- Wrote 182 tests using recorded fixtures and mocked HTTP, with linting, type checking, and CI on Python 3.11 to 3.13.
- Made it deliberately unable to register for you: it never logs in to any Rutgers system and stores no credentials, and it's an unofficial project not affiliated with Rutgers.
