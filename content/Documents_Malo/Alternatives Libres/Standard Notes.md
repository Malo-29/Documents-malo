---
aliases:
  - standard notes
  - standardnotes
tags:
  - alternatives
  - notes
  - chiffrement
  - vie-privée
---
# 🔒 Standard Notes

#alternatives #notes #chiffrement #vie-privée

> Standard Notes est mon application de prise de notes chiffrée. Toutes mes notes sont chiffrées de bout en bout — ni Standard Notes ni personne d'autre ne peut les lire.

---

## Pourquoi Standard Notes ?

### Le problème des apps de notes classiques
- **Apple Notes** : chiffrement optionnel, synchronisé sur iCloud (Apple a potentiellement accès)
- **Notion** : données sur les serveurs de Notion, aucun chiffrement E2EE
- **Google Keep** : Google lit et analyse les contenus
- **Obsidian** (ce vault) : fichiers locaux, mais sans chiffrement natif si le disque n'est pas chiffré

### Ce que Standard Notes apporte
- **Chiffrement E2EE** : les notes sont chiffrées *avant* de quitter l'appareil
- **Open source** (client et serveur)
- **Auto-hébergeable**
- Synchronisation multi-appareils (macOS, iOS, Android, Linux, Web)
- **Gratuit** pour les fonctionnalités de base

---

## Fonctionnement du chiffrement

Standard Notes utilise **XChaCha20-Poly1305** pour le chiffrement des notes. La clé de chiffrement est dérivée du mot de passe avec **Argon2**. Même avec accès au serveur, les notes sont illisibles.

---

## Organisation

- **Tags** : organisation par étiquettes (pas de dossiers)
- **Smart Views** : vues filtrées (ex. "notes modifiées cette semaine")
- **Archives** : pour les notes inactives sans les supprimer

---

## Éditeurs (plan payant)

Le plan gratuit offre uniquement l'éditeur texte basique. Le plan payant (Productivity/Professional) débloque :
- Markdown avec aperçu
- Code editor (coloration syntaxique)
- Spreadsheet editor
- Supercharged Markdown (tables, todo lists)

---

## Mon usage

Standard Notes accueille mes **notes sensibles** : réflexions personnelles, informations confidentielles, brouillons privés. Pour les notes d'études et fiches, j'utilise ce vault Obsidian — non chiffré en soi, mais stocké dans un [[Veracrypt|volume Veracrypt]] ou sur [[MEGA]] (E2EE).

---

## Alternative : Notesnook

[Notesnook](https://notesnook.com) est une alternative récente, également E2EE et open source, avec une interface plus moderne et un éditeur riche inclus dans le plan gratuit.

---

## Voir aussi

- [[Veracrypt]] — Chiffrement du disque pour Obsidian
- [[Cryptpad]] — Notes collaboratives chiffrées
- [[KeepassXC]] — Stockage du mot de passe Standard Notes
