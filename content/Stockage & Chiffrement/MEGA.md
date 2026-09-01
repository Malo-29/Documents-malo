---
tags:
  - stockage
  - cloud
  - chiffrement
aliases:
  - mega
  - cloud
---
# ☁️ MEGA

#stockage #cloud #chiffrement

> MEGA est mon service de stockage cloud principal. Je l'utilise comme alternative à Google Drive ou iCloud, avec un avantage clé : le chiffrement de bout en bout côté client. Possibilité de faire du multi-comptes et de se partager les documents au compte central, donnant une capacité de stockage illimité.

---

## Pourquoi MEGA ?

- **Chiffrement E2EE** : les fichiers sont chiffrés *avant* d'être envoyés aux serveurs. MEGA ne peut pas lire mes données.
- **Open source** (client) : le code des applications est public et auditable.
- **Généreux en stockage** : 20 Go gratuits, extensibles.
- **Multi-plateforme** : macOS, Linux, Windows, iOS, Android, et client Web.
- **Pas de GAFAM** : fondé par Kim Dotcom, basé en Nouvelle-Zélande, hors juridiction UE/US.

---

## Mon usage

J'utilise MEGA comme **hub central de synchronisation** entre mes appareils. La structure de mon cloud reflète celle de mon système local.

Un point clé : j'y stocke des [[Veracrypt|volumes Veracrypt chiffrés]] pour les données les plus sensibles. Ainsi, même si MEGA était compromis, les fichiers restent illisibles sans la clé de déchiffrement.

---

## Installation et configuration

1. Télécharger MEGAsync sur [mega.io](https://mega.io/desktop)
2. Créer un compte avec une adresse mail qui ne me lie pas à mon identité (ex. [[Addy.io|alias]])
3. **Sauvegarder la clé de récupération** (64 caractères) dans [[KeepassXC]] — sans elle, les données sont irrécupérables si le mot de passe est perdu.
4. Choisir les dossiers à synchroniser (sync sélective recommandée)

### Sync sélective
Je ne synchronise pas tout automatiquement. Je choisis quels dossiers sont en sync permanente, et j'uploade manuellement les archives et sauvegardes ponctuelles.

---

## Sécurité supplémentaire

- Activer l'**authentification à deux facteurs** (2FA) — stocker le code TOTP dans [[KeepassXC]]
- Ne jamais utiliser MEGA depuis un réseau non sécurisé sans [[MullvadVPN|VPN]]
- Pour les données très sensibles : utiliser un [[Veracrypt|volume Veracrypt]] stocké dans MEGA

---

## Limites

- Vitesse de transfert limitée sur le plan gratuit
- Pas d'intégration native avec des outils comme Obsidian (contrairement à iCloud ou OneDrive)
- Nécessite de faire confiance au client (même si open source)

---

## Voir aussi

- [[Veracrypt]] — Chiffrement des volumes stockés dans MEGA
- [[KeepassXC]] — Où stocker la clé de récupération
- [[Gérer ses données sur internet]]
