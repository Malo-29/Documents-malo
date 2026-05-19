---
aliases:
  - beeper
  - messagerie unifiée
tags:
  - communication
  - messagerie
  - vie-privée
---
# 💬 Beeper

#communication #messagerie #vie-privée

> Beeper est mon client de messagerie unifié du quotidien. Il agrège plusieurs réseaux de messagerie dans une seule application, avec un focus sur la simplicité et la confidentialité.

---

## Qu'est-ce que Beeper ?

Beeper est un **client de messagerie multi-protocoles** qui permet de centraliser dans une seule interface :
- iMessage
- WhatsApp
- Telegram
- Signal
- Instagram DM
- Facebook Messenger
- Twitter/X DM
- LinkedIn
- et d'autres via des bridges [[Matrix - Element|Matrix]]

> [!info] Beeper repose sur le protocole **Matrix** en arrière-plan. Chaque réseau est connecté via un "bridge" Matrix. Voir [[Matrix - Element]] pour comprendre la technologie sous-jacente.

---

## Pourquoi Beeper ?

### Problème résolu
Jongler entre 5 applications de messagerie différentes est épuisant. Beeper les regroupe toutes, avec :
- Une **boîte de réception unifiée**
- Des **notifications centralisées**
- Une **interface cohérente** entre tous les réseaux

### Avantages
- Chiffrement de bout en bout là où les protocoles le supportent (Signal, iMessage, Matrix natif)
- Basé sur Matrix : mes messages peuvent migrer vers n'importe quel client Matrix
- **Open source** (client et bridges)
- Application disponible sur macOS, iOS, Android, Windows, Linux

---

## Configuration

1. Télécharger Beeper sur [beeper.com](https://beeper.com)
2. Créer un compte (adresse email)
3. Connecter les réseaux un par un via les instructions de chaque bridge
4. Pour iMessage sur non-Apple : nécessite un Mac ou iPhone actif (bridge via relais)

---

## Limites

- La **confidentialité dépend du réseau d'origine** : un DM Instagram reste vu par Meta, même lu dans Beeper
- Beeper a accès aux clés de déchiffrement pour les réseaux qui ne supportent pas E2EE nativement (WhatsApp Web, par exemple)
- Moins adapté pour des communications très sensibles → utiliser [[Matrix - Element]] directement dans ce cas

---

## Mon usage au quotidien

J'utilise Beeper comme point d'entrée pour **toutes mes conversations sociales et informelles**. C'est l'application que j'ouvre en premier. Pour les communications qui nécessitent une sécurité maximale, je passe sur Matrix/Element directement.

---

## Voir aussi

- [[Matrix - Element]] — Le protocole derrière Beeper, et mon horizon pour remplacer tout le reste
- [[GrapheneOS]] — Où Beeper tourne sur mobile de façon plus sécurisée
