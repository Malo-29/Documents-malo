---
aliases:
  - grapheneos
  - android
  - pixel
tags:
  - os
  - mobile
  - android
  - vie-privée
  - sécurité
---
# 📱 GrapheneOS

#os #mobile #android #vie-privée #sécurité

> GrapheneOS est un Android durci, centré sur la vie privée et la sécurité. Je l'utilise sur un Google Pixel comme remplacement d'Android stock ou d'iOS.

---

## Qu'est-ce que GrapheneOS ?

GrapheneOS est un **système d'exploitation mobile open source** basé sur Android (AOSP), développé par la GrapheneOS Project Foundation. Il conserve la compatibilité avec les applications Android tout en supprimant toute dépendance à Google et en ajoutant de nombreux renforcements de sécurité.

---

## Pourquoi GrapheneOS ?

### Le problème des OS mobiles classiques
- **Android stock** : télémétrie Google omniprésente, mises à jour dépendantes des constructeurs
- **iOS** : closed-source, lié à l'écosystème Apple, accès de Apple à de nombreuses données
- **Android des constructeurs** (Samsung, Xiaomi…) : couches de logiciels supplémentaires, souvent des spywares préinstallés

### Ce que GrapheneOS apporte
- **Zéro Google** par défaut (installable via sandbox si nécessaire)
- **Mises à jour de sécurité rapides** (directement depuis GrapheneOS Project)
- **Sandboxing renforcé** : les apps sont encore plus isolées entre elles
- **Hardening du noyau** : mitigations supplémentaires contre les exploits
- **Permissions granulaires** : réseau, capteurs, caméra révocables par app
- **Verrouillage du bootloader** après installation (sécurité maximale)

---

## Compatibilité : Pixels uniquement

GrapheneOS ne fonctionne **que sur les Google Pixel**. Raison : les Pixel sont les seuls appareils Android avec :
- Un bootloader re-verrouillable après installation d'un OS tiers
- Les meilleures puces de sécurité (Titan M)
- Un support matériel long et fiable

**Pixels supportés** : Pixel 6, 6a, 7, 7a, 8, 8a, 8 Pro, 9, 9 Pro (voir liste à jour sur grapheneos.org).

---

## Installation

L'installation se fait via un **installateur web** (WebUSB) depuis un navigateur Chromium :

1. Aller sur [grapheneos.org/install/web](https://grapheneos.org/install/web)
2. Activer le mode développeur sur le Pixel + OEM unlocking
3. Connecter le Pixel en USB
4. Suivre l'installateur (environ 15 minutes)
5. **Reverrouiller le bootloader** à la fin — crucial pour la sécurité

---

## Fonctionnalités clés

### Profils d'utilisation
GrapheneOS supporte les **profils Android** comme Android stock, mais les utilise différemment :
- Profil principal : usage personnel
- Profils secondaires : apps peu fiables, travail, etc.
- Chaque profil est chiffré indépendamment

### Sandboxed Google Play
Pour utiliser des apps qui nécessitent Google Play Services, GrapheneOS propose une installation **isolée** de Google Play : les apps croient avoir accès aux services Google, mais dans une sandbox sans accès au reste du système.

### Permissions réseau par app
Chaque app peut se voir **retirer l'accès au réseau** — fonctionnalité absente d'Android stock. Idéal pour les apps qui n'ont aucune raison d'être connectées.

---

## Applications recommandées sur GrapheneOS

| Usage | App recommandée |
|-------|----------------|
| Navigateur | Vanadium (intégré) ou Firefox |
| Email | [[Thunderbird]] mobile |
| Messagerie | [[Beeper]], Signal, [[Matrix - Element\|Element]] |
| Cartes | Organic Maps (OpenStreetMap, hors-ligne) |
| Clavier | Anysoft Keyboard ou AOSP |
| Store | F-Droid (open source) + Accrescent |

---

## Limites

- **Pixel uniquement** → contrainte d'achat
- Certaines apps bancaires refusent de fonctionner (vérification d'intégrité Android)
- Pas d'accès natif à Google Pay, certains services Google
- Communauté technique — nécessite un minimum d'investissement

---

## Voir aussi

- [[Beeper]] — Messagerie sur GrapheneOS
- [[Matrix - Element]] — Messagerie chiffrée
- [[MullvadVPN]] — VPN sur mobile
- [[Linux - Choisir sa distribution]] — Philosophie similaire sur desktop
