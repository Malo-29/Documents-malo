---
aliases:
  - tor
  - onion routing
  - anonymat
tags:
  - réseau
  - anonymat
  - vie-privée
---
# 🧅 Tor

#réseau #anonymat #vie-privée

> Tor est le réseau d'anonymisation le plus robuste disponible. Je l'utilise pour des navigations nécessitant un anonymat renforcé, au-delà de ce qu'un VPN peut offrir.

---

## Comment fonctionne Tor ?

Tor (The Onion Router) achemine le trafic à travers **3 nœuds relais** chiffrés successivement :

```
Moi → [Nœud d'entrée] → [Nœud intermédiaire] → [Nœud de sortie] → Destination
```

Chaque nœud ne connaît que :
- Le nœud précédent (d'où vient le paquet)
- Le nœud suivant (où il va)

**Personne ne connaît à la fois la source et la destination.** C'est le principe de l'oignon : chaque couche de chiffrement est pelée par un nœud différent.

### Différence avec un VPN

| | VPN | Tor |
|-|-----|-----|
| Anonymat | Partiel (VPN connaît IP + destination) | Fort (aucun nœud ne voit tout) |
| Vitesse | Rapide | Lent |
| Confiance requise | VPN provider | Aucun tiers unique |
| Contenu .onion | ❌ | ✅ |

---

## Tor Browser

La façon la plus simple d'utiliser Tor est le **Tor Browser**, basé sur Firefox avec de nombreux durcissements :

1. Télécharger sur [torproject.org](https://www.torproject.org)
2. Lancer → connexion automatique au réseau Tor
3. Ne jamais installer d'extensions (cassent l'anonymat)
4. Ne pas se connecter à des comptes liés à l'identité réelle
5. Ne pas télécharger de fichiers et les ouvrir hors-ligne (risque de fuite IP)

---

## Sites .onion

Le réseau Tor donne accès aux **services cachés** (adresses `.onion`) : sites dont le serveur est aussi anonymisé. Exemples légitimes :
- ProtonMail .onion : `protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion`
- DuckDuckGo : `duckduckgogg42xjoc72x3sjasowoarfbgcmvfimaftt6twagswzczad.onion`
- The New York Times : `nytimesn7cgmftshazwhfgzm37qxb44r64ytbb2dj3x62d2lljsciiyd.onion`

---

## Limites

- **Lenteur** significative (3 sauts réseau)
- Le **nœud de sortie** voit le trafic non-HTTPS en clair → toujours utiliser HTTPS
- **Pas fait pour** : streaming, torrenting, se connecter à ses comptes habituels
- Certains sites bloquent Tor
- L'**anonymat n'est pas parfait** : comportement en ligne, cookies, empreinte navigateur peuvent désanonymiser

---

## Tor vs VPN : quand utiliser quoi ?

- **VPN** ([[MullvadVPN]], [[ProtonVPN]]) : usage quotidien, vitesse importante, masquer le trafic à l'ISP
- **Tor** : anonymat renforcé, accès .onion, recherches très sensibles
- **Tor sur VPN** : possible, ajoute une couche mais le VPN connaît quand même l'usage de Tor

---

## Voir aussi

- [[MullvadVPN]] — VPN pour l'usage quotidien
- [[Configurer son navigateur]] — Firefox durci pour la navigation normale
- [[Gérer ses données sur internet]]
