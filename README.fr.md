[English](README.md) · **Français**

**Anthony Hunt** · [Fiche du projet sur ingevision.cloud](https://ingevision.cloud/?p=revue-maquettes) · [LinkedIn](https://www.linkedin.com/in/anthony-hunt-3948a9196) · [Profil GitHub](https://github.com/anthohunt)

> Dépôt vitrine : le code et les données de ce projet sont privés ; ce README le décrit.

# Salle de revue des maquettes

L'endroit où un client relit la maquette cliquable de sa future appli : une adresse par projet, chaque version gardée sur une frise, des commentaires accrochés à l'élément d'écran ou à la user story concernés, et un vérificateur qui refuse une maquette hors du gabarit commun.

## Le problème

Une maquette envoyée en fichier se perd entre les mails : on ne sait plus quelle version le client a vue, les retours arrivent en paragraphe vague, et chaque projet réinvente sa page de revue. Les agents de code qui construisent les maquettes ont aussi besoin d'entrer sans connaître le mot de passe de personne.

## Comment ça marche

- **Une adresse par projet**, derrière une porte à mot de passe : un mot de passe pour le propriétaire, un par client. Les mots de passe ne sont gardés qu'en empreinte salée.
- **Les agents reçoivent un laissez-passer, pas un mot de passe** : valable 15 minutes, pour un seul projet, jamais écrit.
- **Un gabarit commun** à toutes les maquettes : un bandeau en haut avec les versions datées et un repère « maintenant », parcours et user stories à gauche, l'appli au centre, commentaires à droite ; plein écran, tutoriel intégré, et sur téléphone des panneaux qui passent sous l'appli au lieu de la couvrir.
- **Des commentaires accrochés** à un élément d'écran, une section, une user story ou un parcours entier, en fils qui restent avec la version sur laquelle ils ont été écrits. « Commentaires terminés » prévient le constructeur par mail.
- **Chaque version publiée est gardée** dans git avec une étiquette : une ancienne maquette se rouvre toujours.
- **Un vérificateur de conformité** (lecture seule) ouvre la maquette publiée comme un client et la refuse au moindre écart : mauvaise adresse, gabarit périmé, version non datée, tutoriel absent, erreur JavaScript, défilement horizontal sur un téléphone de 390 pixels.

## Ce qui est construit

En service depuis le 8 novembre 2026, utilisé pour ce site et pour des projets clients. Le gabarit est versionné et chaque maquette porte la version avec laquelle elle a été faite : les copies périmées sont repérées.

## Ce qui est public

Cette page seulement. Les maquettes et les commentaires appartiennent aux projets relus.

## Technologies

- JavaScript et CSS (gabarit et panneau de commentaires)
- Node.js et Playwright (vérificateur de conformité)
- nginx, Docker (porte à mot de passe et hébergement par projet)
- Python (publication, laissez-passer, avis de commentaires)
