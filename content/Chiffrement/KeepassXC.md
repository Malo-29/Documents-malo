---
tags: [securite, chiffrement, mots-de-passe, open-source]
created: 2026-05-19
---

# 🔑 KeePassXC — Gestionnaire de mots de passe local

> KeePassXC est un gestionnaire de mots de passe **100% local**, open source, multiplateforme. Aucune donnée ne transite par un serveur tiers. C'est ma référence pour stocker et générer des identifiants.

## Pourquoi pas LastPass / Bitwarden cloud ?

- **LastPass** : a subi plusieurs fuites de données majeures (2022 notamment)
- **Bitwarden cloud** : open source mais tes mots de passe restent sur leurs serveurs
- **KeePassXC** : la base reste sur **ton disque**, tu contrôles tout

> Bitwarden auto-hébergé est une bonne alternative si tu veux synchronisation multi-appareils.

## Deux versions à connaître

| | KeePass | KeePassXC |
|---|---|---|
| Original | ✅ (Windows) | Fork multiplateforme |
| Interface | Vieillissante | Moderne |
| macOS/Linux | ❌ natif | ✅ natif |
| Plugins | Nombreux | Intégrés |
| Recommandé | Non | ✅ Oui |

**KeePassXC** est le fork recommandé : même format `.kdbx`, interface moderne, actif et audité.

## Structure d'une base `.kdbx`

Une base KeePassXC est un **fichier `.kdbx`** chiffré avec AES-256. Elle s'ouvre avec :
- Un **mot de passe maître** (obligatoire)
- Un **fichier clé** (optionnel, recommandé pour 2FA locale)
- Une **clé matérielle YubiKey** (optionnel)

>  Si tu perds ton mot de passe maître ET ton fichier clé, la base est irrécupérable.

## Comment j'organise ma base

```
📁 Ma base KeePassXC
├── 📂 Mail
│   ├── ProtonMail
│   ├── Infomaniak
│   └── Riseup
├── 📂 Services en ligne
│   ├── GitHub
│   └── ...
├── 📂 Chiffrement
│   ├── Passphrase Veracrypt volume A
│   └── Passphrase GPG
├── 📂 Banque & Finance
└── 📂 Divers
```

## Synchronisation avec MEGA

Ma base `.kdbx` est stockée dans mon **[[Veracrypt|volume Veracrypt]]** lui-même synchronisé sur **[[MEGA]]**. La double couche de chiffrement garantit :
1. MEGA ne voit qu'un volume chiffré opaque (Veracrypt)
2. Même si quelqu'un extrayait le `.kdbx`, il lui faudrait casser AES-256

> Ne jamais stocker le fichier clé au même endroit que la base `.kdbx`.

## Fonctionnalités clés

### Générateur de mots de passe
KeePassXC génère des mots de passe forts configurables : longueur, caractères spéciaux, exclusions. Je génère systématiquement des mots de passe de **32+ caractères** pour tous les services.

### Auto-type
Remplit automatiquement les formulaires de connexion dans le navigateur via un raccourci clavier (`Ctrl+Shift+V` par défaut). Fonctionne sans extension.

### Intégration navigateur (KeePassXC-Browser)
Extension disponible pour Firefox et Chromium. Communique avec KeePassXC via **KeePassHTTP** de façon locale (pas de réseau). Je connecte l'extension une fois, elle détecte les champs de login automatiquement.

### TOTP intégré
KeePassXC peut stocker et générer des **codes TOTP** (authentification à deux facteurs). Pratique mais à utiliser avec précaution : si ta base est compromise, le 2FA ne protège plus rien.

### Historique des mots de passe
Chaque entrée conserve l'historique des anciens mots de passe. Utile pour retrouver un ancien identifiant après un changement.

## Bonnes pratiques

- [ ] Mot de passe maître de **30+ caractères** (phrase de passe ou aléatoire)
- [ ] Fichier clé stocké sur une **clé USB dédiée**, pas dans le cloud
- [ ] Sauvegarde de la base sur **au moins 2 supports différents**
- [ ] Verrouillage automatique après inactivité activé
- [ ] Ne jamais réutiliser un mot de passe (utiliser le générateur systématiquement)

## Sur mobile

KeePass est compatible avec plusieurs apps Android/iOS :
- **Strongbox** (iOS) — payant, très bien intégré
- **KeePassDX** (Android) — gratuit, open source
- **Keepass2Android** (Android) — alternative

Sur **[[GrapheneOS]]**, j'utilise KeePassDX via F-Droid.

## Voir aussi

- [[Veracrypt]] — pour stocker la base de façon chiffrée
- [[MEGA]] — cloud où réside le volume Veracrypt
- [[GPG]] — autre outil de chiffrement complémentaire
