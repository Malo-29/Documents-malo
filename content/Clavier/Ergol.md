---
tags: [clavier, ergonomie, productivite, dactylo, francais]
created: 2026-05-19
---

# ⌨️ Ergol — Disposition clavier française optimisée

> Ergol est une disposition de clavier conçue pour le français moderne, développée par la communauté française. Elle maximise le confort typographique, réduit les mouvements des doigts, et prend en compte les touches mortes pour les caractères accentués.

## Pourquoi changer de disposition ?

### Le problème d'AZERTY

AZERTY a été conçu au XIXe siècle pour les machines à écrire mécaniques, sans réflexion ergonomique. Ses défauts :
- Lettres fréquentes (`e`, `a`, `i`) mal placées
- Accents difficiles d'accès
- Ponctuation nécessitant Shift systématiquement
- Charge déséquilibrée entre les doigts et les mains

### Pourquoi pas BÉPO ?

BÉPO est la disposition française optimisée historique. Ergol s'en distingue :

| Critère | AZERTY | BÉPO | Ergol |
|---|---|---|---|
| Optimisation FR | ❌ | ✅ | ✅✅ |
| Compatibilité raccourcis | ✅ | ❌ (Ctrl+Z, Ctrl+C cassés) | ✅ (préservés) |
| Transition | — | Difficile | Modérée |
| Touches de base QWERTY | Non | Non | Oui (couche) |
| Programmeurs | Non adapté | Partiellement | ✅ |

**La force d'Ergol** : les raccourcis clavier universels (`Ctrl+Z`, `Ctrl+C`, `Ctrl+V`, `Ctrl+S`) sont maintenus sur les positions d'origine. BÉPO les déplace, ce qui crée des conflits avec tous les logiciels.

## Principes de conception d'Ergol

1. **Minimiser les déplacements** : les lettres les plus fréquentes en français sont sur la rangée de repos (`ASDFGHJKL`)
2. **Bigrammes confortables** : les enchaînements fréquents (`ou`, `er`, `en`, `qu`...) sont conçus pour être fluides
3. **Touches mortes** : les accents s'obtiennent via des touches mortes logiques plutôt que des positions dédiées
4. **Compatibilité programmeur** : tous les symboles de programmation sont accessibles sans contorsion

## Apprendre Ergol

### Site officiel

**[ergol.org](https://ergol.org)** — Documentation complète, justification des choix de conception, carte des touches interactive.

### Entraînement : deux sites complémentaires

#### Ducktypist
**[ducktypist.com](https://ducktypist.com)**

Spécialisé dans l'apprentissage des dispositions alternatives (Ergol, BÉPO, Dvorak...). Propose des exercices progressifs adaptés à la disposition choisie, avec focus sur les lettres les moins naturelles en début d'apprentissage.

**Workflow recommandé au départ :**
1. Sélectionner "Ergol" comme disposition
2. Commencer par les exercices de rangée de repos
3. Progresser par couche (lettres → ponctuation → chiffres)
4. 15-20 minutes par jour minimum

#### Monkeytype
**[monkeytype.com](https://monkeytype.com)**

Le site de référence pour mesurer sa vitesse de frappe. Très personnalisable : durée, langue, mots courants, citations, code. Je l'utilise pour tester ma progression et atteindre mes objectifs de vitesse.

**Réglages que j'utilise :**
- Mode : `time 60` (60 secondes)
- Langue : `french`
- Ponctuation : activée
- Chiffres : activés (progressivement)
- Theme : sombre personnalisé

**Objectifs de vitesse indicatifs :**

| Niveau | WPM (mots/min) | Frappe |
|---|---|---|
| Débutant | < 30 | Regarder le clavier |
| Intermédiaire | 40-60 | Début de mémoire musculaire |
| Avancé | 60-90 | Frappe fluide sans regarder |
| Expert | 90+ | Vitesse de pensée |

> Note : En phase de transition vers Ergol, la vitesse chute temporairement à 15-25 WPM. C'est normal. La régularité est clé.

## La transition en pratique

### Phase 1 — Découverte (semaines 1-2)
- Apprendre la position des lettres avec Ducktypist
- Imprimer la carte des touches et l'afficher
- Utiliser Ergol pour toutes les frappes, même lentement

### Phase 2 — Consolidation (semaines 3-6)
- Exercices Ducktypist quotidiens (focus sur les erreurs)
- Mesures Monkeytype pour suivre la progression
- Accepter la lenteur, ne pas revenir à AZERTY

### Phase 3 — Automatisation (mois 2-3)
- La frappe devient automatique sur les lettres courantes
- Travailler les bigrammes rares et la ponctuation
- Objectif : dépasser son ancienne vitesse AZERTY

### Phase 4 — Optimisation (mois 3+)
- Affiner les réglages des touches mortes
- Personnaliser si besoin (Ergol est modifiable)
- Atteindre et dépasser 70 WPM en français

## Installation

### macOS

1. Télécharger le fichier de disposition depuis [ergol.org](https://ergol.org)
2. Copier dans `~/Library/Keyboard Layouts/`
3. Redémarrer ou se déconnecter/reconnecter
4. Préférences Système → Clavier → Sources de saisie → Ajouter Ergol

### Linux

Ergol est intégré à **xkeyboard-config** (distributions récentes).

```bash
# X11
setxkbmap fr ergol

# Wayland (GNOME)
gsettings set org.gnome.desktop.input-sources sources "[('xkb', 'fr+ergol')]"
```

### Windows

Utiliser **Keyman** ou **KbdEdit** avec le fichier de disposition Ergol fourni sur le site.

## Reconfigurer Anki pour Ergol

Si certains raccourcis Anki deviennent inconfortables avec Ergol, le greffon [[Customize Keyboard Shortcuts]] permet de les redéfinir.

## Voir aussi

- [[Anki - Greffons]] — pour reconfigurer les raccourcis si besoin
- [[Python]] — pour automatiser des remappages système
