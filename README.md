---
solhann_app: true
slug: architecture
title: Greenlight Architecture
description: An inspectable map of the Greenlight pipeline on Forgejo — every box on every machine, every line labelled with the credential that authorises it.
---

# Greenlight Architecture

An inspectable, isometric map of how Greenlight works since its apps moved to
Forgejo (October 2026): three machines (laptop, dev box, prod), two forges
(Forgejo at `git.greenlit.page` for the apps Greenlight builds, GitHub for the
platform's own repos), and every line between them labelled with the credential
that authorises it and coloured by how dangerous that credential is.

Built for reasoning about the system, not just admiring it:

- **Click any box or line** for what-it-does / how-it's-built / **risk** notes.
  A selection is addressable — `#n/deployd`, `#e/e_hook` — so you can link
  someone straight to the piece you mean.
- **Trace a flow** step by step: a new app, a change to an existing app, access
  (grants and sign-in through Keycloak), a schema change, and how the platform's
  own repos ship.
- The one human gate — approving the pull request — is marked on the map,
  because merging IS deploying, and deployd re-verifies that approval on the
  merged commit before anything reaches prod.
- **Hide the laptop** (button, top right) drops the owner's own machine — the
  platform CLI, the pb-dev workbench, the secret store, and the lanes into prod
  that only a person at that keyboard can use. The header counts and the
  overview change with it, and the flow that starts there is disabled rather
  than silently truncated. The choice sticks, and `?nolaptop` shares it as a link.

Line **weight and dash** carry the credential class alongside hue, so the drawing
still parses in greyscale or with colour-blindness — the one gate-altering line
(gl-provisiond's org-owner token) is the heaviest thing on the map.

The whole page is a single `index.html`; the diagram is generated from a data
model at the top of the script, so editing the architecture doc means editing
that data. Its sources of truth are `PIPELINE.md` and `platform/forgejo/README.md`
in the Greenlight workspace; when they change, this data should follow.

This page is one of the platform's own repos, on GitHub, and ships through the
GitHub pipeline it draws in its bottom corner. The build agent can write to this
repo, so it is in the gated lane: a change needs a reviewed pull request, not a
direct push.

**Live:** https://architecture.solhann.net
