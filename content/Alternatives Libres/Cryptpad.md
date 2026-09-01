---
tags: [productivite, open-source, chiffrement, collaboration, alternative]
created: 2026-05-19
---

# 🔒 CryptPad — Suite collaborative chiffrée

> CryptPad est une **suite bureautique collaborative en ligne**, open source, dont le chiffrement est intégral : même les administrateurs du serveur ne peuvent pas lire vos documents. C'est mon alternative à Google Docs.

## Pourquoi CryptPad ?

| Critère | Google Docs | CryptPad |
|---|---|---|
| Chiffrement | ❌ Google lit tout | ✅ Zero-knowledge |
| Compte requis | Oui | Non (usage anonyme possible) |
| Open source | ❌ | ✅ |
| Auto-hébergeable | ❌ | ✅ |
| Collaboration temps réel | ✅ | ✅ |

## Fonctionnalités disponibles

- **Pad** — éditeur de texte riche (≈ Google Docs)
- **Tableur** — feuilles de calcul (≈ Google Sheets)
- **Présentation** — diaporamas (≈ Google Slides)
- **Kanban** — gestion de tâches
- **Formulaire** — sondages (≈ Google Forms)
- **Code** — éditeur de code collaboratif
- **Whiteboard** — tableau blanc

## Comment ça fonctionne (chiffrement)

Le chiffrement/déchiffrement se passe **entièrement dans le navigateur** (côté client). Le serveur ne stocke que des blobs chiffrés illisibles. La clé de déchiffrement est contenue dans l'**URL** après le `#` — fragment jamais envoyé au serveur.

```
https://cryptpad.fr/pad/#/2/pad/edit/[CLÉ_CHIFFRÉE]
```

Si tu perds l'URL, tu perds l'accès définitivement.

## Instance que j'utilise

J'utilise l'instance officielle **[cryptpad.fr](https://cryptpad.fr)**, gérée par l'association française XWiki SAS, financée par des donations et des abonnements.

> Pour une confidentialité maximale, on peut auto-héberger CryptPad sur un VPS.

## Cas d'usage typiques

- Rédiger un document avec quelqu'un sans créer de compte Google
- Partager des notes sensibles (le lien = la clé)
- Travailler à plusieurs sur un document sans laisser de trace
- Remplacer Google Forms pour un sondage anonyme

## Compte vs anonyme

- **Sans compte** : les documents sont liés au navigateur (localStorage). Si tu vides les données, tu perds l'accès.
- **Avec compte** : les documents sont dans un drive chiffré, accessible depuis n'importe quel appareil.

## Limites

- Stockage limité sur l'instance gratuite (1 Go)
- Moins fluide que Google Docs sur connexion lente
- Fonctionnalités de tableur moins avancées qu'Excel ou [[LibreOffice]]

## Voir aussi

- [[Standard Notes]] — pour les notes personnelles chiffrées
- [[GPG]] — pour chiffrer des fichiers individuellement
- [[KeepassXC]] — pour gérer le mot de passe du compte
