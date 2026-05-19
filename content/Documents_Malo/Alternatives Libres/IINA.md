---
tags: [media, video, macos, outil, open-source]
created: 2026-05-19
---

# 🎬 IINA — Lecteur vidéo macOS

> IINA est mon lecteur vidéo principal sur macOS. Open source, moderne, basé sur mpv (moteur de rendu de référence), il remplace avantageusement VLC sur Mac.

## Pourquoi IINA plutôt que VLC ?

| Critère | VLC | IINA |
|---|---|---|
| Interface | Vieillissante | Natif macOS, épuré |
| Moteur de rendu | libVLC | mpv (supérieur) |
| Touch Bar | ❌ | ✅ |
| Picture in Picture | Basique | ✅ Natif |
| Formats supportés | Très large | Très large (même base) |
| macOS uniquement | Non | Oui |
| Open source | ✅ | ✅ |

IINA est **exclusivement macOS**. Si tu es sur Linux, mpv directement ou VLC restent les références.

## Installation

```bash
# Via Homebrew (recommandé)
brew install --cask iina

# Ou téléchargement direct
# https://iina.io
```

## Formats supportés

IINA lit quasi tous les formats vidéo et audio :
- Vidéo : MKV, MP4, AVI, MOV, WebM, FLV, TS, M2TS...
- Audio : FLAC, MP3, AAC, OGG, OPUS...
- Sous-titres : SRT, ASS/SSA, VTT, SUP (sous-titres image)

## Fonctionnalités clés

### Sous-titres automatiques
Téléchargement de sous-titres intégré via OpenSubtitles. Clic droit → Sous-titres → Chercher en ligne.

### Lecteur de playlists
Glisser-déposer plusieurs fichiers → playlist automatique. Navigation avec touches `<` et `>`.

### Picture in Picture
Bouton PiP dans les contrôles → lecture flottante au-dessus de tout autre contenu.

### Raccourcis clavier

| Action | Raccourci |
|---|---|
| Play/Pause | `Espace` |
| Avance 5s | `→` |
| Recul 5s | `←` |
| Avance rapide | `Shift+→` |
| Volume + | `↑` |
| Volume - | `↓` |
| Plein écran | `F` |
| Sous-titres | `v` |
| Vitesse + | `]` |
| Vitesse - | `[` |
| Vitesse normale | `\` |

### Vitesse de lecture
IINA supporte des vitesses de 0.25x à 4x avec interpolation audio (voix naturelle à 1.5x). Pratique pour les cours ou podcasts.

## Paramètres que j'utilise

**Préférences → Sous-titres :**
- Taille : 40-45
- Ombre : activée
- Langue par défaut : fr, en

**Préférences → Avancé → mpv :**
On peut passer des options mpv directement. Exemple pour upscaling GPU :
```
profile=gpu-hq
scale=ewa_lanczossharp
```

## IINA vs mpv natif

mpv est le moteur sous-jacent d'IINA. Pour les utilisateurs Linux ou les power users macOS, mpv en ligne de commande offre encore plus de contrôle. IINA est mpv avec une belle interface native macOS.

## Voir aussi

- [[Handbrake]] — pour convertir/compresser des vidéos
- [[Torrenting]] — pour télécharger des vidéos via BitTorrent
- [[Calibre]] — équivalent pour les ebooks
