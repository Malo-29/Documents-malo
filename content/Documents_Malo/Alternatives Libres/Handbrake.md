---
tags: [media, video, compression, encodage, open-source]
created: 2026-05-19
---

# 🎞️ Handbrake — Compression & Encodage Vidéo

> Handbrake est un transcodeur vidéo open source multiplateforme. Je l'utilise pour compresser des vidéos, changer leur format, ou préparer des fichiers pour différents appareils.

## À quoi ça sert concrètement ?

- Réduire la taille d'une vidéo (GoPro 4K → fichier raisonnable)
- Convertir MKV → MP4 pour compatibilité maximale
- Préparer une vidéo pour publication (web, mobile)
- Extraire une vidéo d'un DVD/Blu-ray

## Installation

```bash
# macOS
brew install --cask handbrake

# Linux
sudo apt install handbrake
# ou Flatpak :
flatpak install flathub fr.handbrake.ghb
```

## Interface — Comprendre les paramètres

### Source
Glisser la vidéo source ou choisir un dossier. Handbrake détecte automatiquement les pistes vidéo, audio et sous-titres.

### Préréglages (Presets)

Handbrake propose des préréglages prêts à l'emploi :

| Préréglage | Usage |
|---|---|
| **H.265 MKV 1080p30** | Qualité maximale, fichier modéré |
| **H.265 MKV 720p30** | Bon compromis taille/qualité |
| **Fast 1080p30** | Encodage rapide, qualité correcte |
| **Discord Small** | Partage Discord (<8 Mo) |

**Mon préréglage habituel : H.265 MKV 1080p30** pour l'archivage, Fast 1080p30 pour le partage.

### Codec vidéo

| Codec | Compression | Compatibilité | CPU |
|---|---|---|---|
| H.264 (AVC) | Bonne | Universelle | Rapide |
| H.265 (HEVC) | Très bonne | Bonne (2015+) | Plus lent |
| AV1 | Excellente | Émergente | Très lent |
| VP9 | Très bonne | Web (YouTube) | Lent |

→ **H.265 pour archivage** (moitié plus petit qu'H.264 même qualité), **H.264 pour compatibilité maximale**.

### RF (Constant Quality) — Le paramètre le plus important

Le RF (Rate Factor) contrôle la qualité. C'est l'inverse d'une compression : plus RF est bas, meilleure est la qualité et plus grand est le fichier.

```
H.264 :  RF 18-22 = qualité haute  |  RF 28+ = qualité faible
H.265 :  RF 22-28 = qualité haute  |  RF 32+ = qualité faible
```

**Mon réglage : RF 22 pour H.265** → excellent rapport qualité/taille.

### Audio

- **AAC** : format universel, bon pour tout usage
- **AC3/EAC3** : home cinema, Dolby
- **FLAC** : lossless (taille importante)
- **Copier le flux** : sans recompression (préserve l'original)

### Sous-titres

Handbrake peut intégrer (burn-in) ou laisser les sous-titres en piste séparée. Le burn-in les rend permanents dans l'image.

### Accélération matérielle

Préférences → Vidéo → Encoder avec le GPU :
- **Apple VideoToolbox** sur macOS (processeurs Apple Silicon ou Intel Iris)
- **NVENC** sur Linux/Windows avec GPU Nvidia
- Le GPU encode plus vite mais qualité légèrement inférieure au CPU

Pour l'archivage : encoder en CPU. Pour la vitesse : GPU.

## Cas d'usage typique

### Réduire une vidéo 4K pour le partage

1. Charger la vidéo 4K
2. Préréglage : H.265 MKV 1080p30
3. RF : 24
4. Audio : AAC 160kbps
5. Démarrer l'encodage

Résultat typique : vidéo 4K de 10 Go → 1-2 Go en 1080p H.265.

### Convertir MKV → MP4

1. Charger le MKV
2. Format de sortie : MP4
3. Codec vidéo : H.264 (compatibilité maximale)
4. Audio : copier si AAC déjà, sinon convertir en AAC
5. Sous-titres : laisser en piste ou burn-in selon besoin

## File d'attente

Handbrake permet d'ajouter plusieurs jobs en file d'attente. Idéal pour encoder plusieurs vidéos en une nuit.

## Voir aussi

- [[IINA]] — pour lire les vidéos encodées
- [[Torrenting]] — pour télécharger des vidéos
- [[Calibre]] — pour les ebooks (même logique de gestion)
