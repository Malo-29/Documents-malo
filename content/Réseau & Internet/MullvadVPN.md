---
aliases:
  - mullvad
  - vpn
tags:
  - réseau
  - vpn
  - vie-privée
---
# 🦔 MullvadVPN

#réseau #vpn #vie-privée

> Mullvad est mon VPN principal. Son modèle éthique, son refus des logs et son mode de paiement anonyme en font le standard du secteur en matière de vie privée.

---

## Qui est Mullvad ?

Mullvad VPN est une entreprise **suédoise** fondée en 2009. Elle se distingue radicalement des autres VPN commerciaux :

### Éthique et modèle
- **Pas de compte lié à une identité** : à l'inscription, on reçoit un numéro de compte aléatoire (à conserver dans [[KeepassXC]]). Aucun email, aucun nom.
- **Paiement anonyme possible** : espèces par courrier, Bitcoin, Monero, carte cadeau
- **Audité indépendamment** : audits réguliers publiés
- **Loi suédoise** : pas de conservation obligatoire de logs (contrairement à la France)
- **Pas de logs** : vérifiable via le code source et les audits

### Contre-pied aux pratiques marketing
Mullvad ne fait **aucune promesse de "VPN magique"** : ils sont transparents sur ce qu'un VPN peut et ne peut pas faire.

---

## Ce qu'un VPN fait (et ne fait pas)

### Ce qu'il fait
- Masque le trafic à l'**ISP** (opérateur télécom / box)
- Masque l'**IP réelle** aux sites web
- Chiffre le trafic sur les **réseaux publics** (café, aéroport)
- Permet de contourner les **restrictions géographiques**

### Ce qu'il ne fait PAS
- Rendre **totalement anonyme** (Mullvad connaît l'IP de connexion tant que la session est active)
- Protéger des **cookies et trackers** dans le navigateur
- Remplacer [[Tor]] pour un anonymat fort

---

## Installation et configuration

1. Télécharger sur [mullvad.net](https://mullvad.net)
2. Générer un numéro de compte → le stocker dans [[KeepassXC]]
3. Payer (minimum 5€/mois)
4. Choisir un serveur → recommandation : pays sans obligations de rétention de logs

### Protocoles disponibles
- **WireGuard** ✅ (recommandé : rapide, moderne, code simple à auditer)
- OpenVPN (plus ancien mais robuste)

### Kill switch
Activer le **kill switch** : coupe internet si la connexion VPN tombe, évitant toute fuite d'IP.

---

## Mullvad Browser

Mullvad a développé, en partenariat avec le Tor Project, le **Mullvad Browser** : un navigateur durci comme Tor Browser mais fonctionnant sur le réseau normal (avec VPN). Voir [[Configurer son navigateur]].

---

## Voir aussi

- [[ProtonVPN]] — VPN alternatif, écosystème Proton
- [[Tor]] — Anonymat renforcé au-delà du VPN
- [[NextDNS]] — DNS filtrant complémentaire
- [[Configurer son navigateur]]
