---
tags: [media, torrenting, p2p, open-source]
created: 2026-05-19
---

# 🌊 Torrenting — BitTorrent & qBittorrent

> Le BitTorrent est un protocole de partage de fichiers pair-à-pair (P2P). C'est la technologie derrière le "torrent". Je l'utilise avec qBittorrent, un client open source sans publicité.

## Comment fonctionne BitTorrent

Contrairement au téléchargement classique (tu → serveur → fichier), BitTorrent est **décentralisé** :

```
Classique :  Toi ←———— Serveur central
BitTorrent : Toi ←———— Peer A
                  ←———— Peer B
                  ←———— Peer C
                  ↕ (tu redistribues aussi)
```

### Vocabulaire

| Terme | Définition |
|---|---|
| **Torrent** | Fichier `.torrent` ou lien magnet qui décrit le contenu |
| **Tracker** | Serveur qui coordonne les peers (qui a quoi) |
| **Seeder** | Utilisateur qui partage à 100% (ratio > 1) |
| **Leecher** | Utilisateur qui télécharge (ratio < 1) |
| **Ratio** | Upload / Download — éthique de maintenir > 1 |
| **Magnet link** | Lien direct sans fichier `.torrent` intermédiaire |
| **DHT** | Réseau distribué de trackers (pas besoin de tracker central) |

### Trackers publics de référence

Les trackers coordonnent les peers. En cas de tracker mort, le DHT prend le relais. Trackers souvent inclus dans les torrents publics :

```
udp://tracker.opentrackr.org:1337/announce
udp://open.stealth.si:80/announce
udp://tracker.torrent.eu.org:451/announce
```

Pour les trackers privés (ratio obligatoire, contenu de qualité) : sur invitation uniquement.

## qBittorrent — Mon client

**[qbittorrent.org](https://www.qbittorrent.org)** — Client BitTorrent open source, sans pub, multiplateforme. Alternative aux clients propriétaires comme uTorrent (adware) ou BitTorrent Inc.

### Installation

```bash
# macOS (Homebrew)
brew install --cask qbittorrent

# Linux (Debian/Ubuntu)
sudo apt install qbittorrent

# Windows
# Télécharger l'installateur sur le site officiel
```

### Configuration recommandée

**Préférences → Connexion :**
- Port aléatoire à chaque démarrage 
- UPnP / NAT-PMP : selon configuration réseau
- Activer le protocole chiffrement des connexions : Activé

**Préférences → BitTorrent :**
- DHT : (permet les torrents sans tracker)
- PeX (Peer Exchange) 
- Local Peer Discovery 
- Ratio maximum : définir à 2.0 (bonne pratique)

**Préférences → Avancé :**
- Résoudre les IPs des peers : désactiver (économie ressources)
- Interface réseau : choisir l'interface VPN si tu utilises un VPN

### Liaison avec un VPN (Kill Switch)

 Sans VPN, ton IP est visible de tous les peers du torrent.

Avec [[MullvadVPN]] :
1. Activer le kill switch dans Mullvad
2. Dans qBittorrent → Préférences → Avancé → Interface réseau → Choisir l'interface Mullvad (ex. `wg0` ou `tun0`)
3. qBittorrent ne transmet que si le VPN est actif

### Interface Web (optionnel)

qBittorrent dispose d'une **WebUI** accessible depuis le navigateur. Utile pour télécharger à distance (ex. depuis un Raspberry Pi ou serveur).

Préférences → WebUI → Activer l'interface web → Définir port + identifiants.

## Trouver des torrents

- **[Rutracker.org](https://rutracker.org)** — films, musique, logiciels (interface en russe), c'est celui que j'utilise car on peut créé un compte sans invitation, je vais essayer de passer en tracker privé dès que j'aurai une connexion internet stable (pour pouvoir seeder en masse), pour plus d'info DM

## Légalité

BitTorrent est un **protocole neutre et légal**. Son usage pour télécharger des œuvres protégées par copyright est illégal dans de nombreux pays. En France, la Hadopi (désormais Arcom) envoie des avertissements basés sur les IP loggées par les trackers.

Un VPN avec politique no-log ([[MullvadVPN]]) masque l'IP réelle.

## Voir aussi

- [[MullvadVPN]] — protection de l'IP lors du torrent
- [[IINA]] — pour lire les vidéos téléchargées
- [[Calibre]] — pour gérer les ebooks téléchargés
- [[Ressources Internet]] — sites pour trouver des torrents
