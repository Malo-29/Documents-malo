---
tags: [anki, collaboration, partage, open-source]
created: 2026-05-19
---

#  AnkiCollab — Partage collaboratif de decks

> AnkiCollab est un greffon Anki qui permet de partager et synchroniser des decks en temps réel entre plusieurs utilisateurs. C'est le Google Docs du deck Anki.

## Concept

AnkiCollab crée une plateforme centralisée où un deck maître est hébergé. Les abonnés reçoivent automatiquement les mises à jour : nouvelles cartes, corrections, suppressions.

```
Créateur du deck → AnkiCollab Cloud → Abonnés (sync automatique)
```

## Différence avec AnkiWeb

| | AnkiWeb | AnkiCollab |
|---|---|---|
| Objectif | Sync personnelle multi-appareils | Partage entre utilisateurs distincts |
| Mises à jour | Seulement tes cartes | Les cartes du créateur originales |
| Contribution | Non | ✅ (les abonnés peuvent proposer des cartes) |
| Gratuit | ✅ | ✅ |

## Installation

Outils → Greffons → Acquérir des greffons → coller le code AnkiCollab

## Usage — Créer un deck partagé

1. Outils → AnkiCollab → Upload Deck
2. Sélectionner le deck à partager
3. Obtenir un lien d'invitation ou un identifiant de deck
4. Partager le lien aux collaborateurs

## Usage — S'abonner à un deck

1. Outils → AnkiCollab → Subscribe to Deck
2. Coller l'identifiant ou le lien du deck
3. Le deck apparaît dans ta collection, synchronisé avec la source

## Cas d'usage

- Partager un deck entre plusieurs élèves de la même prépa
- Maintenir un deck de référence mis à jour par un prof ou un élève avancé
- Collaborer à plusieurs sur un gros deck thématique

## Voir aussi

- [[Anki - Vue d'ensemble]]
- [[Anki - Greffons]]
