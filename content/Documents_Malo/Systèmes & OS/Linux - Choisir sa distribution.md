---
aliases:
  - linux
  - distribution linux
  - distro
tags:
  - os
  - linux
  - alternatives
---
# 🐧 Linux — Choisir sa distribution

#os #linux #alternatives

> Linux n'est pas un système d'exploitation — c'est un noyau. Les **distributions** (distros) combinent ce noyau avec des logiciels pour former un OS complet. Il en existe des centaines ; voici comment choisir.

---

## Pourquoi Linux ?

- **Open source** : le code est public, auditable, modifiable
- **Gratuit** (sauf exceptions)
- **Respect de la vie privée** : aucun telemetry imposé, aucun Microsoft/Apple
- **Léger** : tourne sur du vieux matériel
- **Stable** pour les serveurs (la majorité d'internet tourne sous Linux)
- **Personnalisable** à l'extrême

---

## Concepts clés

### Distribution
Une distro = noyau Linux + gestionnaire de paquets + environnement de bureau + logiciels préinstallés.

### Environnement de bureau (DE)
L'interface graphique : GNOME, KDE Plasma, XFCE, i3, etc. Indépendant de la distro.

### Gestionnaire de paquets
Installe et met à jour les logiciels :
- `apt` → Debian/Ubuntu
- `dnf` → Fedora
- `pacman` → Arch
- `nix` → NixOS

---

## Distributions par niveau

### 🟢 Débutant — Facilité d'installation et d'usage

#### Ubuntu
- La plus connue, communauté immense
- Installation guidée, matériel bien supporté
- Interface GNOME claire
- → Idéale pour la première installation

#### Linux Mint
- Basée sur Ubuntu, interface encore plus proche de Windows (Cinnamon DE)
- Très stable, très intuitive
- → Recommandée pour quelqu'un venant de Windows

#### Pop!_OS
- Ubuntu modifiée par System76
- Excellent support des GPU (NVIDIA notamment)
- Tiling window manager optionnel
- → Idéale pour les créatifs et les joueurs

---

### 🟡 Intermédiaire — Plus de contrôle, toujours accessible

#### Fedora
- Sponsorisée par Red Hat, très à jour
- GNOME vanilla (pur, sans modifications)
- RPM Fusion pour les paquets propriétaires
- → Pour ceux qui veulent du moderne sans partir à l'aventure

#### Manjaro
- Basée sur Arch, mais avec un installeur graphique et des dépôts stables
- Accès à l'AUR (Arch User Repository) : bibliothèque de paquets communautaires gigantesque
- → Porte d'entrée vers l'écosystème Arch sans douleur

#### Debian
- Ultra-stable, conservatrice dans ses mises à jour
- Base de Ubuntu et beaucoup d'autres
- → Pour les serveurs ou ceux qui privilégient la stabilité absolue

---

### 🔴 Avancé — Contrôle total, configuration manuelle

#### Arch Linux
- **Installation entièrement manuelle** depuis le terminal
- On construit son système pièce par pièce
- Rolling release : toujours à la dernière version
- Documentation (Arch Wiki) : la meilleure resource Linux du web
- → Pour comprendre Linux en profondeur, pas pour les pressés

#### Gentoo
- Tout est compilé depuis les sources
- Optimisations très fines possibles
- → Pour les puristes et les curieux de compilation

#### NixOS
- Paradigme unique : système entièrement **déclaratif et reproductible**
- Configuration dans un fichier `.nix` → système identique sur n'importe quelle machine
- Rollbacks atomiques (impossible de "casser" le système)
- → Avancé mais très intéressant pour la reproductibilité

---

### 🔒 Distributions orientées vie privée et sécurité

#### Tails
- **Système amnésique** : tout s'efface à l'extinction
- Tourne depuis une clé USB, ne laisse aucune trace
- Tout le trafic passe par [[Tor]]
- → Pour des usages ponctuels très sensibles

#### Whonix
- Deux VMs : une passerelle Tor, une station de travail
- La station ne peut accéder à internet que via Tor
- → Pour une isolation réseau très forte en usage quotidien

#### Qubes OS
- Sécurité par **compartimentalisation** : chaque tâche dans une VM séparée
- Navigation, email, documents — tout isolé
- Très exigeant en RAM (16+ Go recommandés)
- → Le système le plus sécurisé pour un usage desktop

---

## Mon usage

J'utilise Linux en dual boot avec macOS. Voir [[Dual Boot macOS + Linux]] pour les détails de configuration.

---

## Voir aussi

- [[Dual Boot macOS + Linux]]
- [[GrapheneOS]] — Équivalent Linux pour Android
- [[Tor]] — Réseau d'anonymisation intégré dans Tails/Whonix
