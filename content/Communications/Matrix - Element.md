---
aliases:
  - matrix
  - element
  - décentralisation
tags:
  - communication
  - messagerie
  - décentralisation
  - chiffrement
---
# 🔷 Matrix & Element

#communication #messagerie #décentralisation #chiffrement

> Matrix est le protocole de communication décentralisé et chiffré que je vise à terme pour remplacer les messageries propriétaires. Element est son client principal.

---

## Qu'est-ce que Matrix ?

Matrix est un **protocole ouvert de communication en temps réel**, décentralisé et chiffré de bout en bout. Ce n'est pas une application — c'est un standard, comme l'email.

### Principes fondamentaux

- **Décentralisé** : il n'existe pas un seul serveur Matrix. N'importe qui peut héberger le sien (homeserver). Les serveurs se parlent entre eux, comme des serveurs email.
- **Fédéré** : un compte sur `matrix.org` peut communiquer avec un compte sur `mon-serveur.fr`
- **E2EE natif** : chiffrement de bout en bout via le protocole **Megolm** (basé sur Signal Protocol)
- **Ouvert** : spécification publique, implémentations multiples

---

## Comparaison avec les messageries classiques

| Critère | WhatsApp | Signal | Matrix |
|---------|----------|--------|--------|
| Décentralisé | ❌ | ❌ | ✅ |
| Open source | ❌ | ✅ | ✅ |
| E2EE | ✅ | ✅ | ✅ |
| Auto-hébergeable | ❌ | ❌ | ✅ |
| Interopérable | ❌ | ❌ | ✅ |
| Pas de numéro requis | ❌ | ❌ | ✅ |

---

## Element — le client principal

[Element](https://element.io) est le client Matrix le plus complet, disponible sur :
- Web (app.element.io)
- macOS, Windows, Linux
- iOS, Android

### Créer un compte
1. Aller sur [app.element.io](https://app.element.io)
2. *Créer un compte* → choisir un homeserver
   - `matrix.org` : serveur par défaut, grande communauté
   - Serveur auto-hébergé : contrôle total
3. **Sauvegarder la clé de sécurité** (backup des clés E2EE)

### Format d'un identifiant Matrix
```
@monpseudo:matrix.org
@monpseudo:mon-serveur.fr
```

---

## Salons et espaces

Matrix supporte :
- **Messages directs** (chiffrés E2EE par défaut)
- **Salons de groupe** (chiffrés ou publics)
- **Espaces** : groupes de salons (équivalent des serveurs Discord)

---

## Auto-hébergement avec Synapse ou Conduit

Pour contrôle total :
- **Synapse** : implémentation de référence en Python, robuste mais lourde
- **Conduit** : implémentation légère en Rust, idéale sur un Raspberry Pi ou VPS

L'auto-hébergement permet de ne dépendre d'aucun tiers pour ses communications.

---

## Mon horizon : remplacer Beeper par Matrix

[[Beeper]] me convient au quotidien, mais repose sur des bridges vers des plateformes propriétaires. Mon objectif à terme est de **migrer mes contacts vers Matrix** pour des communications véritablement décentralisées et contrôlées.

La migration est progressive : Matrix est aujourd'hui ma messagerie pour les contacts tech-savvy, et l'horizon pour les autres.

---

## Éthique et gouvernance

- La **Matrix Foundation** gère le protocole (non-profit)
- **Element** (l'entreprise) développe le client et est distincte de la Foundation
- Le protocole ne peut pas être "racheté" ou fermé — c'est un standard ouvert

---

## Voir aussi

- [[Beeper]] — Client qui utilise Matrix en sous-main
- [[GrapheneOS]] — OS mobile sur lequel je l'utilise
- [[GPG]] — Autre approche du chiffrement des communications
