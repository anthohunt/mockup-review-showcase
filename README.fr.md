[English](README.md) · **Français**

# Salle de revue des maquettes

**Un client relit la maquette cliquable de sa future appli, et chaque remarque devient un ticket épinglé sur l'écran qu'elle concerne.**

[![Un client commente un bouton, valide une correction, passe en vue téléphone puis ouvre le suivi (clic : vidéo complète)](docs/demo.fr.gif)](https://drive.google.com/file/d/1kWTjTzTzcR9my6LDSRhe65YpRfEufQX8/view)

*Un client commente un bouton, valide une correction, passe en vue téléphone, puis ouvre le suivi des retours. [Vidéo complète (1:09)](https://drive.google.com/file/d/1kWTjTzTzcR9my6LDSRhe65YpRfEufQX8/view)*

## Ce qu'on fait avec

- **Un lien par projet.** Le client donne son nom et entre : aucun compte.
- **Tout se commente.** En mode Commenter, un clic sur n'importe quel élément, une section ou une user story, ou une phrase sélectionnée. Chaque remarque est soit un changement sur le site, soit une question au développeur, avec des captures au besoin.
- **Chaque fil est un ticket.** Un numéro et un statut. Un fil corrigé attend que le client le valide ; un clic sur un fil ouvre son écran et encadre l'élément.
- **Versions et vues.** Un onglet par version ; les anciennes restent en ligne avec leurs fils. Un interrupteur montre la maquette dans un cadre de téléphone de 390 pixels.
- **Propositions.** Ce que personne n'a demandé est construit éteint ; le client le regarde, puis le garde ou non.
- **Commentaires terminés.** Un bouton prévient le constructeur par mail que le client a fini.

## Architecture

![Architecture : le client passe une porte à mot de passe vers le hub nginx, qui sert les maquettes et le gabarit commun ; les commentaires vont au service de commentaires, qui prévient le constructeur par mail ; l'agent de maquette publie chaque version, copiée en ligne et étiquetée dans un dépôt git privé](docs/architecture.fr.svg)

## Déploiement

- **Hébergement.** VPS personnel, Docker derrière Traefik : hub nginx, porte à mot de passe et service de commentaires (Python).
- **Accès.** Un mot de passe par projet, un pour le propriétaire ; les agents reçoivent un laissez-passer de 15 minutes pour un seul projet.
- **Gabarit.** Une seule copie, chargée par toutes les maquettes ; un vérificateur en lecture seule (Node.js, Playwright) refuse une maquette qui s'en écarte.
- **En service.** Depuis le 8 novembre 2026 : 10 projets, 43 versions archivées (17 novembre 2026).

---

**Anthony Hunt** · [ingevision.cloud](https://ingevision.cloud/?p=revue-maquettes) · [LinkedIn](https://www.linkedin.com/in/anthony-hunt-3948a9196) · [GitHub](https://github.com/anthohunt)

Le code, les maquettes et leurs commentaires sont privés.
