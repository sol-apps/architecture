---
solhann_app: true
slug: architecture
title: How solhann.net Works
description: A friendly, no-jargon tour of how this little platform turns an idea into a live website — and keeps every app safe in its own room.
emoji: 🏗️
---

# 🏗️ How solhann.net Works

A friendly, no-jargon tour of how this little platform turns an idea into a live website — and keeps every app safe in its own room.

**Live:** https://architecture.solhann.net
**Gallery:** https://create.solhann.net

---

Built on the [solhann.net](https://create.solhann.net) platform. Static site — every push to `main`
auto-deploys via GitHub Actions → rsync → `/var/www/apps/architecture/`. The front matter above is what the
gallery reads to render this app's tile, so keep `title` / `description` / `emoji` up to date.
