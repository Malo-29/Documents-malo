---
tags: [vie-privee, internet, donnees-personnelles, securite]
created: 2026-05-19
---

# 🛡️ Gérer ses données sur internet — Réduire son empreinte numérique

> Nos données sont la matière première de l'économie numérique. Cette fiche synthétise les principes et actions concrètes pour reprendre le contrôle.

## Comprendre le problème

### Ce qui est collecté sur toi
- **Données déclarées** : nom, mail, date de naissance
- **Métadonnées** : qui tu appelles, quand, combien de temps
- **Données comportementales** : pages visitées, durée, clics
- **Données de localisation** : GPS, IP, réseau Wi-Fi
- **Fingerprint** : configuration navigateur, GPU, polices (voir [[Configurer son navigateur]])

### Qui collecte ?
- GAFAM (Google, Apple, Meta, Amazon, Microsoft)
- Data brokers (Acxiom, Experian, LexisNexis) — revendent les profils
- Votre FAI (Free, Orange, SFR) — peut logger le trafic DNS
- Sites web (cookies tiers, pixels tracking)

## Principe de base : minimisation des données

> **Ne donner que ce qui est strictement nécessaire.**

- Fausse date de naissance sur les services qui la demandent sans raison
- Alias mail via [[Addy.io]] plutôt que son vrai mail
- Numéro VOIP ou SIM secondaire pour les inscriptions
- Pseudonyme pour les services non critiques

## Actions concrètes par couche

### Couche réseau
- [[MullvadVPN]] ou [[ProtonVPN]] : masque l'IP réelle et chiffre le trafic vis-à-vis du FAI
- [[NextDNS]] : DNS chiffré, bloque traceurs niveau réseau
- [[Tor]] : anonymisation forte pour la navigation sensible
- [[AdGuardHome + Raspberry Pi]] : blocage DNS pour tout le réseau domestique

### Couche navigateur
→ Voir [[Configurer son navigateur]] pour le détail complet

### Couche mail
- [[ProtonMail]] ou [[Infomaniak]] pour le mail principal
- [[Addy.io]] pour les alias jetables
- [[GPG]] pour chiffrer les échanges sensibles
- Éviter Gmail, Outlook (scan du contenu pour ciblage pub)

### Couche stockage
- [[MEGA]] + [[Veracrypt]] pour les fichiers
- [[CryptPad]] pour la collaboration
- [[Standard Notes]] pour les notes
- Éviter Google Drive, iCloud, Dropbox (accès en clair pour la plateforme)

### Couche applications
- Désinstaller les apps inutiles sur mobile
- Sur Android : [[GrapheneOS]] avec permissions fines
- Couper les autorisations localisation, micro, caméra par défaut
- Préférer les PWA aux apps natives (moins de permissions)

## Se désinscrire des data brokers

Des services comme **Justdeleteme.com** référencent la difficulté de suppression de chaque service. Pour les data brokers :
- Service payant **DeleteMe** (automatisé)
- Manuellement : rechercher son nom + "opt out" sur chaque broker

## Le paradoxe de la vie privée

Plus tu es précis dans tes habitudes (même VPN, même horaires), plus tu es identifiable malgré les outils. La vraie protection combine :
1. **Bons outils** (VPN, Tor, chiffrement)
2. **Bonne hygiène** (alias mails, mots de passe uniques via [[KeepassXC]])
3. **Comportements cohérents** (ne pas connecter son vrai compte Google via Tor)

## Ressources pour aller plus loin

→ Voir [[Ressources Internet]] — FMHY, PrivacyGuides, etc.

- [privacyguides.org](https://www.privacyguides.org) — référence communautaire sur les outils privacy
- [tosdr.org](https://tosdr.org) — résumés des CGU des grandes plateformes
- [justdeleteme.xyz](https://justdeleteme.xyz) — difficulté de suppression de compte

## Voir aussi

- [[Configurer son navigateur]]
- [[Addy.io]]
- [[GPG]]
- [[KeepassXC]]
- [[Veracrypt]]
