---
tags: [media, ebook, bibliotheque, outil, open-source]
created: 2026-05-19
---

# 📚 Calibre — Bibliothèque numérique

> Calibre est le gestionnaire d'ebooks de référence. Open source, puissant, il permet de gérer une bibliothèque, convertir entre formats, et envoyer des livres sur liseuse.

## Ce que fait Calibre

- **Bibliothèque** : organiser livres par auteur, série, tags, notes
- **Conversion** : EPUB ↔ MOBI ↔ PDF ↔ AZW3 ↔ HTML ↔ TXT...
- **Édition** : modifier les métadonnées (titre, auteur, couverture)
- **Envoi vers liseuse** : Kindle, Kobo, PocketBook...
- **Visionneuse intégrée** : lire les ebooks directement dans Calibre
- **Serveur de contenu** : accès à la bibliothèque via navigateur (réseau local)

## Installation

```bash
# macOS
brew install --cask calibre

# Linux (Debian/Ubuntu)
sudo apt install calibre
# ou via le script officiel (version plus récente) :
sudo -v && wget -nv -O- https://download.calibre-ebook.com/linux-installer.sh | sudo sh /dev/stdin
```

## Organisation de la bibliothèque

### Structure recommandée
Calibre gère son propre dossier `Calibre Library/` avec une structure interne. Ne pas modifier manuellement les fichiers à l'intérieur.

### Colonnes personnalisées
Ajouter des colonnes via Préférences → Ajouter une colonne personnalisée :
- `lu` (booléen : oui/non)
- `priorité` (1-5)
- `langue` (texte)

### Tags
Utiliser les tags pour catégoriser : `physique`, `histoire`, `roman`, `à-lire`, `référence`...

## Conversion de formats

Glisser un fichier → Clic droit → Convertir les livres → Convertir individuellement

**Paramètres importants :**
- Format de sortie : EPUB (universel) ou AZW3 (Kindle)
- Marge du texte : 5% (pour la lisibilité)
- Taille de police de base : 12

### Cas typique : PDF → EPUB
Les PDFs sont mal convertis (mise en page fixe). Préférer télécharger directement en EPUB via [[Ressources Internet]].

## Envoi vers liseuse

1. Connecter la liseuse via USB
2. Calibre la détecte automatiquement
3. Sélectionner les livres → Envoyer à l'appareil
4. Calibre convertit au format natif si nécessaire

Pour Kindle : nécessite le format AZW3 ou MOBI. Calibre convertit automatiquement.

## Suppression DRM 

Les ebooks achetés sur Amazon/Kobo sont souvent protégés par DRM (Digital Rights Management) qui empêche leur lecture ailleurs.

Le plugin **DeDRM** (anciennement Apprentice Alf) permet de supprimer ces protections pour un usage personnel légal. Sa légalité varie selon les pays.

Installation : Préférences → Plugins → Charger le plugin depuis un fichier.

## Serveur de contenu

Calibre peut exposer la bibliothèque en réseau local :

Préférences → Partage sur Internet → Démarrer le serveur

Accessible depuis `http://[IP_machine]:8080` → lecture dans le navigateur ou téléchargement.

## Voir aussi

- [[IINA]] — pour les vidéos (équivalent médias)
- [[Ressources Internet]] — Anna's Archive, Z-Library pour trouver des ebooks
- [[Torrenting]] — téléchargement de livres via BitTorrent
- [[Handbrake]] — compression vidéo
