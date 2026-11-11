**English** · [Français](README.fr.md)

**Anthony Hunt** · [Project page on ingevision.cloud](https://ingevision.cloud/?lang=en&p=revue-maquettes) · [LinkedIn](https://www.linkedin.com/in/anthony-hunt-3948a9196) · [GitHub profile](https://github.com/anthohunt)

> Showcase repository: the code and data of this project are private; this README describes it.

# Mock-up review room

The place where a client reviews the clickable mock-up of their future app: one address per project, every version kept on a timeline, comments pinned to the exact screen element or user story, and a checker that refuses a mock-up that does not follow the house template.

## The problem

A mock-up sent as a loose file gets lost between emails: nobody knows which version the client looked at, the feedback arrives as a vague paragraph, and every new project reinvents its own review page. The coding agents that build the mock-ups also need a way in that does not involve knowing anyone's password.

## How it works

- **One address per project**, behind a password door: one password for the owner, one per client. Passwords are only kept as salted hashes.
- **Agents get a pass, not a password**: a 15-minute pass for a single project, never written down.
- **One shared template** for every mock-up: a top band with the dated versions and a "now" marker, user journeys and stories on the left, the app in the middle, comments on the right; full screen, a built-in tutorial, and a phone layout where panels move below the app instead of covering it.
- **Comments are anchored**: on a screen element, a section, a user story or a whole journey, in threads that stay with the version they were written on. "Comments done" notifies the builder by email.
- **Every published version is kept** in git with a tag, so an earlier mock-up can always be reopened.
- **A conformity checker** (read-only) opens the published mock-up like a client would and fails it on any gap: wrong address, outdated template, undated version, missing tutorial, a JavaScript error, horizontal scrolling on a 390-pixel phone screen.

## What is built

In service since 8 November 2026, used for this website and for client projects. The template is versioned and every mock-up carries the version it was built with, so outdated copies are caught.

## What is public

This page only. The mock-ups and comments belong to the projects reviewed.

## Tech stack

- JavaScript and CSS (template and comment panel)
- Node.js and Playwright (conformity checker)
- nginx, Docker (password door and per-project hosting)
- Python (publishing, passes, comment notifications)
