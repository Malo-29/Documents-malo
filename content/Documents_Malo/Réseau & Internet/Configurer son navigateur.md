---
tags: [internet, securite, vie-privee, navigateur]
created: 2026-05-19
---

# 🌐 Configurer son navigateur — Browser Hardening

> Un navigateur non configuré est une passoire à données. Cette fiche documente ma configuration pour limiter le pistage, les pubs et les fuites d'informations, sans sacrifier l'ergonomie.

## Quel navigateur ?

| Navigateur | Base | Vie privée | Recommandé |
|---|---|---|---|
| Chrome | Chromium (Google) | ❌ | Non |
| Edge | Chromium (Microsoft) | ❌ | Non |
| Brave | Chromium | ✅ | Oui (débutant) |
| Firefox | Gecko (Mozilla) | ✅ avec config | ✅ Oui |
| Librewolf | Firefox durci | ✅✅ | Oui (avancé) |
| Tor Browser | Firefox + Tor | ✅✅✅ | Pour anonymat fort |

**Mon choix principal : Firefox** configuré manuellement + **Librewolf** pour la navigation sensible.

## Configuration Firefox — `about:config`

Accéder à `about:config` dans la barre d'adresse, puis modifier :

```
privacy.resistFingerprinting = true
privacy.trackingprotection.enabled = true
privacy.trackingprotection.fingerprinting.enabled = true
privacy.trackingprotection.cryptomining.enabled = true
geo.enabled = false
media.navigator.enabled = false
network.dns.disablePrefetch = true
network.prefetch-next = false
dom.battery.enabled = false
browser.send_pings = false
webgl.disabled = true  ← casse certains sites, à évaluer
```

## Configuration Firefox — Paramètres classiques

**Confidentialité et sécurité :**
- Protection contre le pistage : **Stricte**
- Cookies : bloquer les cookies tiers
- Ne pas pister : activer
- Suggestions dans la barre d'adresse : tout désactiver
- Envoyer des données techniques : tout désactiver
- Moteur de recherche par défaut : **DuckDuckGo** ou **Brave Search**

**DNS over HTTPS :**
Activer dans Paramètres → Confidentialité → DNS over HTTPS → Fournisseur personnalisé → `https://dns.nextdns.io/[MON_ID]` (voir [[NextDNS]])

## Extensions indispensables

### uBlock Origin ⭐
Le bloqueur de contenu de référence. Basé sur des listes de filtres.
- **Mode par défaut** : bloque pub + traceurs
- **Mode avancé** : contrôle par domaine (pour utilisateurs avertis)
- Listes à activer en plus des défauts : EasyList, EasyPrivacy, uBlock filters, AdGuard Annoyances

### Firefox Multi-Account Containers
Isole les sites dans des "conteneurs" étanches. Exemple : Facebook dans un conteneur dédié ne peut pas pister ma navigation ailleurs.

```
📦 Conteneurs suggérés :
├── 🔵 Personnel (réseaux sociaux)
├── 🟠 Shopping
├── 🟢 Travail / Études
├── 🔴 Banque
└── ⚫ Anonyme (pour tester)
```

### Privacy Badger (EFF)
Bloque les traceurs tiers de façon adaptative en apprenant quels domaines te pistent.

### ClearURLs
Supprime automatiquement les paramètres de tracking dans les URLs (`?utm_source=...`, `?fbclid=...`, etc.)

### LocalCDN / Decentraleyes
Remplace les requêtes vers des CDN tiers (Google Fonts, jQuery CDN…) par des ressources locales. Réduit le fingerprinting et la dépendance aux GAFAM.

### KeePassXC-Browser
Connexion avec [[KeepassXC]] pour remplir automatiquement les formulaires de connexion.

### SponsorBlock (YouTube)
Passe automatiquement les segments sponsorisés dans les vidéos YouTube, basé sur des contributions communautaires.

## Moteur de recherche

- **DuckDuckGo** : privacy, bon équilibre, résultats corrects
- **Brave Search** : index propre (pas de dépendance Google/Bing)
- **SearXNG** : méta-moteur open source, auto-hébergeable
- **Startpage** : résultats Google mais sans pistage (proxy)

❌ Éviter : Google, Bing, Yahoo (collecte massive)

## Fingerprinting — Comprendre et réduire

Le **fingerprinting** consiste à identifier un utilisateur sans cookies, via des caractéristiques du navigateur : résolution écran, polices installées, fuseau horaire, GPU, etc.

Pour tester son fingerprint : [coveryourtracks.eff.org](https://coveryourtracks.eff.org)

Réductions possibles :
- `privacy.resistFingerprinting = true` dans Firefox
- Utiliser Librewolf ou Tor Browser (tous identiques → masse dans la foule)
- Extensions comme CanvasBlocker

## Librewolf — Firefox pré-durci

[Librewolf](https://librewolf.net) est un fork de Firefox avec toutes les configurations de privacy appliquées par défaut :
- `resistFingerprinting` activé
- Telemetry désactivée
- uBlock Origin pré-installé
- Pas de pocket, pas de Firefox account

Idéal si tu ne veux pas tout configurer manuellement.

## HTTPS partout

Firefox active par défaut **HTTPS-Only Mode** depuis la v91. Activer dans Paramètres → Confidentialité → Activer le mode HTTPS uniquement.

## Voir aussi

- [[Tor]] — pour l'anonymat fort
- [[NextDNS]] — DNS chiffré complémentaire
- [[AdGuardHome + Raspberry Pi]] — blocage réseau niveau DNS
- [[VPN]] — [[MullvadVPN]] et [[ProtonVPN]]
- [[Gérer ses données sur internet]]
