---
aliases:
  - adguardhome
  - pihole
  - raspberry pi dns
tags:
  - réseau
  - dns
  - auto-hébergement
  - publicités
---
# 🍓 AdGuardHome + Raspberry Pi

#réseau #dns #auto-hébergement #publicités

> AdGuardHome est un DNS filtrant auto-hébergé. Installé sur un Raspberry Pi, il bloque publicités et trackers pour **tous les appareils du réseau**, sans rien installer sur chacun d'eux.

---

## Principe

AdGuardHome transforme un Raspberry Pi en **serveur DNS local**. Quand un appareil du réseau fait une requête DNS :

```
Appareil → Raspberry Pi (AdGuardHome) → DNS public (si non bloqué)
                     ↓
              Domaine dans liste de blocage → BLOQUÉ (réponse vide)
```

Résultat : les publicités et trackers sont bloqués **au niveau réseau**, avant même d'atteindre les appareils. Fonctionne pour toutes les apps, pas seulement le navigateur.

---

## Matériel nécessaire

- **Raspberry Pi** (modèle 3B+, 4 ou Zero 2W recommandé)
- Carte microSD (16 Go minimum)
- Câble ethernet (recommandé pour la stabilité)
- Alimentation

---

## Installation

### 1. Préparer le Pi
1. Télécharger **Raspberry Pi OS Lite** (sans interface graphique — suffisant)
2. Flasher sur la carte SD avec **Raspberry Pi Imager**
3. Activer SSH dans les options avancées
4. Connecter au réseau, récupérer l'IP du Pi

### 2. Installer AdGuardHome
```bash
# Se connecter en SSH
ssh pi@192.168.x.x

# Télécharger et installer AdGuardHome
curl -s -S -L https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

3. Accéder à l'interface web sur `http://192.168.x.x:3000`
4. Suivre l'assistant de configuration

### 3. Configurer le routeur
Dans les paramètres DNS de la box/routeur, remplacer les DNS par l'IP du Raspberry Pi.

---

## Configuration des listes de blocage

Dans *Filtres → Listes de blocage DNS* :

| Liste | URL |
|-------|-----|
| AdGuard DNS filter | https://adguardteam.github.io/AdGuardSDNSFilter/Filters/filter.txt |
| EasyList | https://easylist.to/easylist/easylist.txt |
| OISD | https://big.oisd.nl/ |
| Steven Black | https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts |

---

## Avantages sur NextDNS

- **Aucune donnée ne quitte le réseau local** — contrairement à [[NextDNS]] (cloud)
- **Gratuit sans limite** de requêtes
- **Contrôle total** des listes et des logs
- **Interface locale** riche : statistiques, logs en temps réel, whitelist/blacklist personnalisées

---

## Limites

- Ne protège que sur le **réseau local** (pas en mobilité, sauf avec un VPN maison)
- Nécessite un Raspberry Pi actif en permanence
- Configuration initiale plus technique que NextDNS
- Si le Pi tombe, plus de DNS → plus d'internet (configurer un DNS de secours)

---

## DNS de secours

Dans AdGuardHome, configurer des serveurs DNS upstream :
- `https://dns.mullvad.net/dns-query` (Mullvad)
- `https://cloudflare-dns.com/dns-query` (Cloudflare, rapide)

Et dans le routeur, mettre un DNS secondaire en secours (ex. `9.9.9.9` Quad9) au cas où le Pi est indisponible.

---

## Voir aussi

- [[NextDNS]] — Alternative cloud (plus simple, moins de contrôle)
- [[MullvadVPN]] — VPN pour la protection en mobilité
- [[Linux - Choisir sa distribution]] — Raspberry Pi OS est une distribution Linux
