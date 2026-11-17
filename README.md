**English** · [Français](README.fr.md)

# Mock-up review room

**A client reviews the clickable mock-up of their future app, and every remark becomes a ticket pinned to the screen it is about.**

[![A client comments on a button, validates a fix, switches to the phone view and opens the tracking list (click for the full video)](docs/demo.gif)](https://drive.google.com/file/d/1bsHL1GMqEnPEjqY7Iu4WtfTM4GwBkhOU/view)

*A client comments on a button, validates a fix, switches to the phone view, then opens the tracking list. Interface in French. [Full video (1:09)](https://drive.google.com/file/d/1bsHL1GMqEnPEjqY7Iu4WtfTM4GwBkhOU/view)*

## Using it

- **One link per project.** The client enters the project password, then a name and an email: no account.
- **Comment anything.** In comment mode, click any element, a section or a user story, or select a sentence. Each remark is either a change to the site or a question for me, with screenshots if needed.
- **Status.** Each thread has a number and a status. A fixed thread waits for the client to validate it; clicking a thread opens its screen and highlights the element.
- **Versions and views.** One tab per version; older versions stay online with their own threads. A switch shows the mock-up in a 390-pixel phone frame.
- **Proposals.** Anything the AI adds without being asked is built switched off; the client looks at it, then keeps it or not.
- **Comments done.** One button emails me that the client has finished.

## Architecture

![Architecture: the client opens the nginx hub, which checks the project password with the password door and serves the mock-ups and the shared template; threads go to the comment service, which emails the owner; the AI mock-up agent publishes each version on the hub and tags it in a private git archive](docs/architecture.svg)

<details><summary>French version</summary>

![Architecture : le client ouvre le hub nginx, qui vérifie le mot de passe du projet auprès de la porte et sert les maquettes et le gabarit commun ; les fils vont au service de commentaires, qui prévient le propriétaire par mail ; l'agent IA de maquette publie chaque version sur le hub et l'étiquette dans un dépôt git privé](docs/architecture.fr.svg)

</details>

## Deployment

- **Hosting.** Personal VPS, Docker behind Traefik: nginx hub, password door and comment service (both Python).
- **Access.** One password per project, one for me; AI agents get a 15-minute pass (by default) for a single project.
- **Template.** One copy, loaded by every mock-up; a read-only checker (Node.js, Playwright) fails a mock-up that drifts from it.
- **In use.** Since 8 November 2026: 10 projects, 43 versions archived (17 November 2026).

---

**Anthony Hunt** · [ingevision.cloud](https://ingevision.cloud/?lang=en&p=revue-maquettes) · [LinkedIn](https://www.linkedin.com/in/anthony-hunt-3948a9196) · [GitHub](https://github.com/anthohunt)

The code, the mock-ups and their comments are private.
