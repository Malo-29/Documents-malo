---
aliases:
  - nextdns
  - dns
tags:
  - réseau
  - dns
  - vie-privée
  - publicités
---
# 🔵 NextDNS

#réseau #dns #vie-privée #publicités

> NextDNS est mon service DNS filtrant dans le cloud. Il bloque publicités, trackers et domaines malveillants pour tous mes appareils, sans installation lourde.

---

## Qu'est-ce que le DNS ?

Le **DNS (Domain Name System)** est l'annuaire d'internet : il traduit `google.com` en adresse IP `142.250.74.46`. Chaque requête web passe par un DNS.

Par défaut, ce DNS est celui de l'opérateur (Free, Orange…) qui :
- Voit **tous les domaines que je consulte**
- Peut **bloquer ou rediriger** des sites
- Peut **vendre ces données** à des tiers

Un DNS alternatif (NextDNS, AdGuard, Cloudflare) résout ces problèmes.

---

## Pourquoi NextDNS ?

- **Filtrage configurable** : je choisis quelles listes de blocage activer (publicités, trackers, malwares, contenus adultes…)
- **Fonctionne sur tous les appareils** sans installer de logiciel
- Chiffré : DNS-over-HTTPS (DoH) ou DNS-over-TLS (DoT)
- **Logs optionnels** et supprimables automatiquement
- Plan gratuit : 300 000 requêtes/mois (suffisant pour un usage personnel)

---

## Configuration

### Créer un profil
1. S'inscrire sur [nextdns.io](https://nextdns.io)
2. Un **ID de configuration** unique est généré (ex. `abc123`)
3. Configurer les listes de blocage :
   - **AdGuard DNS filter** ✅ (publicités)
   - **EasyList** ✅ (publicités)
   - **EasyPrivacy** ✅ (trackers)
   - **Malware** ✅

### Appliquer sur macOS
```bash
# Via l'application NextDNS (recommandé)
# Ou manuellement dans Préférences Système → Réseau → DNS
# Ajouter les serveurs DNS NextDNS fournis
```

### Appliquer sur le routeur
Configurer le DNS dans les paramètres de la box/routeur → s'applique à tous les appareils du réseau.

### Appliquer sur iOS/Android
Utiliser l'application NextDNS ou configurer via le profil DNS privé (iOS) / DNS privé (Android).

---

## Listes de blocage recommandées

| Liste | Bloque |
|-------|--------|
| AdGuard DNS filter | Publicités et trackers généraux |
| EasyPrivacy | Trackers de suivi |
| Steven Black Hosts | Publicités, malwares, fake news |
| OISD | Liste unifiée généraliste |

---

## Différence avec AdGuardHome

| | NextDNS | [[AdGuardHome + Raspberry Pi\|AdGuardHome]] |
|-|---------|-------------|
| Hébergement | Cloud (NextDNS) | Auto-hébergé |
| Installation | Aucune | Raspberry Pi requis |
| Disponibilité | Partout | Réseau local seulement (sans config avancée) |
| Contrôle | Partiel | Total |
| Coût | Gratuit (limité) | Coût du Pi |

---

## Voir aussi

- [[AdGuardHome + Raspberry Pi]] — Alternative auto-hébergée
- [[MullvadVPN]] — VPN complémentaire
- [[Configurer son navigateur]] — uBlock Origin pour le blocage dans le navigateur
