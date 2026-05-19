---
tags: [anki, productivite, repetition-espacee, open-source, memoire]
created: 2026-05-19
---

#  Anki — Vue d'ensemble

> Anki est un logiciel de répétition espacée (SRS — Spaced Repetition System) open source. C'est l'outil le plus puissant que j'utilise pour mémoriser à long terme : vocabulaire, formules, dates, définitions, tout y passe.

## Pourquoi Anki ?

### Le principe de la répétition espacée

La courbe de l'oubli d'Ebbinghaus montre qu'on oublie exponentiellement si on ne révise pas. La répétition espacée optimise le moment de révision : juste avant d'oublier.

```
Révision 1 → +1 jour
Révision 2 → +3 jours
Révision 3 → +7 jours
Révision 4 → +21 jours
...
```

Anki calcule automatiquement la prochaine date de révision selon ta réponse (Encore / Difficile / Correct / Facile).

### Pourquoi Anki plutôt que Quizlet ?

| Critère | Quizlet | Anki |
|---|---|---|
| Algorithme SRS | Basique | ✅ FSRS (état de l'art) |
| Open source | ❌ | ✅ |
| Gratuit | Partiel | ✅ (desktop/Android) |
| Personnalisable | Peu | ✅ Infiniment (greffons) |
| Formats de cartes | Limités | ✅ Custom |
| Synchronisation | Cloud Quizlet | ✅ AnkiWeb (gratuit) |

## Algorithme FSRS

FSRS (Free Spaced Repetition Scheduler) est l'algorithme de dernière génération intégré à Anki depuis la v23.10. Il modélise la mémoire avec deux paramètres :
- **Stabilité** (S) : durée avant d'oublier à 90%
- **Difficulté** (D) : facilité intrinsèque de la carte

L'algorithme apprend de ton historique de révisions et optimise les intervalles. C'est supérieur à l'ancien SM-2 utilisé par Anki historiquement.

> Le greffon [[FSRS Helper]] aide à gérer FSRS avancé.

## Types de notes que j'utilise

### Basic (Basique)
```
Recto : Question
Verso : Réponse
```
→ Usage : définitions, faits, formules simples

### Basic (and reversed card)
```
Recto : A → Verso : B
ET
Recto : B → Verso : A
```
→ Usage : vocabulaire bilingue (mot FR ↔ mot EN)

### Cloze (texte à trous)
```
La capitale de la France est {{c1::Paris}}.
```
→ Usage : phrases avec un élément à retrouver, citations

### Image Occlusion Enhanced
→ Masquer des parties d'une image (schéma, carte, graphique)
→ Voir le greffon [[Image Occlusion Enhanced]]

### Type de note custom (Math)
Pour les flashcards mathématiques, j'utilise un note type avec MathJax activé :
- Champ Question en HTML avec `\( ... \)` pour le LaTeX inline
- Rendu automatique par MathJax dans le reviewer Anki


```

## Synchronisation — AnkiWeb

AnkiWeb synchronise gratuitement les cartes entre desktop, mobile et web.

1. Créer un compte sur [ankiweb.net](https://ankiweb.net)
2. Dans Anki desktop : Synchroniser (icône ou `Ctrl+Y`)
3. Sur mobile (AnkiDroid/AnkiMobile) : se connecter au même compte

AnkiMobile (iOS) est payant (~30€). AnkiDroid (Android) est gratuit et open source.

## Format d'import — Mes conventions

### Format CSV pour import

```
Question;Réponse
Qui est Rousseau ?;Philosophe des Lumières, auteur du Contrat social (1762)
```

Séparateur : `;` — Importable via Fichier → Importer

### Format MathJax dans les cartes

```
Définition : matrice inversible;\(A \in \mathcal{M}_n(\mathbb{R})\) est inversible si \(\exists B \text{ t.q. } AB = BA = I_n\)
```

## Raccourcis clavier essentiels

| Action | Raccourci |
|---|---|
| Démarrer la révision | `Entrée` |
| Montrer la réponse | `Espace` |
| Encore (oublié) | `1` |
| Difficile | `2` |
| Correct | `3` |
| Facile | `4` |
| Ajouter une carte | `A` |
| Parcourir les cartes | `B` |
| Statistiques | `Shift+S` |

## Greffons installés

→ Voir le dossier [[Anki - Greffons/]] pour la documentation détaillée de chaque greffon.

**Liste complète :**
- [[Advanced Browser]]
- [[Advanced Copy Fields]]
- [[Advanced Review Bottom Bar]]
- [[Anki Leaderboard]]
- [[Anki Terminator V2]]
- [[AnkiCollab]]
- [[AnkiConnect]]
- [[Auto Sync]]
- [[Batch Editing]]
- [[BetterSearch]]
- [[Colorful Tags - Hierarchical Tags]]
- [[Contanki]]
- [[Customize Keyboard Shortcuts]]
- [[Extended Editor Tables]]
- [[FSRS Helper]]
- [[Image Occlusion Enhanced]]
- [[Mac OSX Dictionary Lookup]]
- [[More Decks Stats]]
- [[Opening Same Window]]
- [[Progress Graphs Stats]]
- [[Review Heatmap]]
- [[Search Stats Extended]]
- [[See Previous Card Ratings]]
- [[Special Fields]]
- [[Speed Focus Mode]]
- [[Study Time Stats]]
- [[Symbols As You Type]]
- [[True Retention]]

## Voir aussi

- [[AnkiCollab]] — partage de decks
- [[Standard Notes]] — pour les notes non-SRS
