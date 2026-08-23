---
solhann_app: true
slug: architecture
title: Greenlight Architecture
description: An inspectable map of the greenlight pipeline — every box on every machine, every line labelled with the credential that authorises it.
emoji: 🟩
---

# 🟩 Greenlight Architecture

An inspectable, isometric map of how solhann.net works now that greenlight is the
front door: three machines (laptop, preview box, prod), two GitHub orgs
(`sol-forge` dev / `sol-apps` prod), and every line between them labelled with the
credential that authorises it and coloured by how dangerous that credential is.

Built for reasoning about the system, not just admiring it:

- **Click any box or line** for what-it-does / how-it's-built / **risk** notes.
- **Trace a flow** step by step: new app, change to an existing app, the legacy
  direct-push lane, and a schema change.
- The one human gate — approving the PR — is marked on the map, because merging
  IS deploying.

The whole page is a single `index.html`; the diagram is generated from a data
model at the top of the script, so editing the architecture doc means editing
that data. It ships through the same pipeline it describes (legacy lane —
this app predates greenlight).

**Live:** https://architecture.solhann.net
**Gallery:** https://create.solhann.net
