---
tags: [anki, greffon]
created: 2026-05-19
---

#  Greffons Anki — Documentation complète

> Cette note centralise tous mes greffons Anki avec leur rôle, pourquoi je les utilise et comment les configurer. Anki est open source et extensible à l'infini via des greffons Python installés depuis AnkiWeb.

→ Pour la vue d'ensemble d'Anki : [[Anki - Vue d'ensemble]]

---

## Comment installer un greffon

1. Outils → Greffons → Acquérir des greffons
2. Coller le code numérique du greffon depuis [ankiweb.net/shared/addons](https://ankiweb.net/shared/addons)
3. Redémarrer Anki

---

##  Navigation & Interface

### Advanced Browser
**Code :** `874215009`

Améliore massivement l'interface de navigation des cartes (Browser). Ajoute des colonnes configurables : date de création, intervalle actuel, facilité, type de carte, deck de destination, champs personnalisés.


---

### Advanced Copy Fields
**Code :** `1898445115`

Copie le contenu d'un champ vers un autre en masse, avec possibilité de transformation (minuscules, majuscules, regex). Utile pour réorganiser des données entre champs après import.

---

### Advanced Review Bottom Bar
**Code :** `1136455830`

Personnalise la barre de boutons en bas de l'écran de révision. Permet de changer l'ordre des boutons, leur couleur, leur taille, ou d'ajouter des infos supplémentaires (intervalle prévu après chaque bouton).

**Pourquoi :** Voir les intervalles prévus (ex. "Correct → 21 jours") aide à choisir entre Difficile et Correct de façon éclairée.

---

### BetterSearch
**Code :** `1052724801`

Améliore la barre de recherche dans le Browser avec autocomplétion, historique des recherches, et raccourcis pour les recherches fréquentes (`deck:`, `tag:`, `note:`, etc.).

---

### Opening the Same Window Multiple Times
**Code :** `1991305865`

Permet d'ouvrir plusieurs fenêtres Anki simultanément (Browser + Reviewer + Éditeur). Par défaut, Anki n'autorise qu'une seule instance de chaque fenêtre.

---

## Statistiques & Suivi

### Review Heatmap 
**Code :** `1771074083`

Affiche une heatmap de tes révisions sur l'écran principal. Chaque jour est coloré selon le nombre de cartes révisées.

---

### True Retention
**Code :** `613684242`

Calcule la rétention réelle (taux de réussite) en excluant les cartes en apprentissage initial (qui faussent les statistiques). La vraie rétention porte uniquement sur les cartes matures.

---

### More Decks Stats and Time Left
**Code :** `1556734708`

Affiche des statistiques supplémentaires sur l'écran d'accueil : temps estimé de révision par deck, total de cartes dues, répartition Apprentissage/Révision/Nouveau.

---

### Progress Graphs and Stats for Learned and Matured Cards
**Code :** `266436365`

Ajoute des graphiques dans les statistiques Anki : évolution du nombre de cartes matures, cartes apprises dans le temps, projection de la collection.

---

### Search Stats Extended
**Code :** `1613056169`

Affiche des statistiques dans le Browser sur la sélection actuelle : nombre de cartes, rétention moyenne, intervalle moyen, répartition des états.

---

### Study Time Stats
**Code :** `1247171788`

Suit le temps passé à étudier par jour, semaine, mois. Affiche des graphiques de productivité dans les statistiques Anki.

---

### See Previous Card Ratings in Reviewer
**Code :** `1906621385`

Affiche l'historique des notations précédentes d'une carte pendant la révision. Utile pour voir si une carte a souvent été ratée.

---

##  Performance & Algorithme

### FSRS Helper 
**Code :** `759844606`

Extension de l'algorithme FSRS (Free Spaced Repetition Scheduler). Propose :
- **Postpone** : reporter des cartes prévues aujourd'hui
- **Advance** : avancer des cartes futures
- **Load Balance** : répartir la charge sur les jours suivants
- **Easy Days** : alléger certains jours de la semaine
- **Disperse Siblings** : écarter les cartes liées dans le temps

---

### Speed Focus Mode
**Code :** `1046608507`

Ajoute un timer configurable pendant la révision :
- **Auto-alert** : alerte sonore si la réponse tarde trop
- **Auto-reveal** : montre la réponse automatiquement après X secondes
- **Auto-answer** : note automatiquement la carte après Y secondes

---

##  Édition & Création de cartes

### Image Occlusion Enhanced 
**Code :** `1374772155`

Ajoute un type de note spécial pour masquer des zones d'une image. On dessine des rectangles sur un schéma, et Anki génère une carte par zone masquée.

---

### Batch Editing
**Code :** `291119185`

Modifie plusieurs cartes simultanément depuis le Browser : ajout/suppression de tags, modification d'un champ, changement de deck — tout en masse.

---

### Extended Editor for Field (Tables, Search & Replace)
**Code :** `1824067020`

Ajoute dans l'éditeur de cartes :
- Un éditeur de tableaux HTML visuels
- Une fonction rechercher/remplacer dans les champs
- Des raccourcis de formatage supplémentaires

---

### Symbols As You Type
**Code :** `2040501954`

Remplace automatiquement des séquences de caractères par des symboles spéciaux pendant la frappe. Configurable librement.

Exemple de règles :
```
-> → →
<= → ≤
!= → ≠
EUR → €
```

---

### Special Fields
**Code :** `1102281552`

Ajoute des comportements spéciaux à certains champs : champs protégés (ne pas écraser à l'import), champs copiés automatiquement, champs calculés.

---

### Mac OSX Dictionary Lookup
**Code :** `1009670940`

Permet de sélectionner un mot dans une carte et d'ouvrir le Dictionnaire macOS (ou autre dictionnaire) directement. Raccourci configurable.

---

## 🔗 Intégrations & Collaboration

### AnkiConnect 
**Code :** `2055492159`

Expose une API REST locale (port 8765) permettant à d'autres logiciels de piloter Anki : ajouter des cartes, lancer des révisions, récupérer des statistiques.

Permet l'intégration avec Obsidian (plugin Obsidian-Anki), VS Code, et des scripts Python personnalisés. Exemple : créer une carte Anki directement depuis une note Obsidian.

```python
# Exemple : ajouter une carte via AnkiConnect
import requests, json

note = {
    "action": "addNote",
    "version": 6,
    "params": {
        "note": {
            "deckName": "HGG",
            "modelName": "Basic",
            "fields": {"Front": "Question", "Back": "Réponse"},
            "tags": ["auteur"]
        }
    }
}
requests.post("http://localhost:8765", json=note)
```

---

### AnkiCollab
**Code :** voir [[AnkiCollab]]

Plateforme de partage collaboratif de decks. Voir la note dédiée.

---

### Anki Terminator V2 (by Shige)
**Code :** Shige's collection

Sidebar IA dans le reviewer Anki. Intègre ChatGPT / DeepSeek directement dans la fenêtre de révision pour obtenir des explications sur une carte difficile.

Au lieu de quitter Anki pour chercher une explication, on interroge l'IA directement. Pratique pour comprendre pourquoi une réponse est correcte.

Le greffon **Subfolder for Anki Terminator V2** organise les fichiers associés dans un sous-dossier propre.

---

### Anki Leaderboard (by Shige)
**Code :** Shige's collection

Tableau de scores partageable avec des amis pour comparer les nombres de cartes révisées. Motivation sociale à l'effort quotidien.

---

## Utilitaires divers

### Auto Sync
**Code :** `2018923290`

Synchronise automatiquement avec AnkiWeb à l'ouverture et à la fermeture d'Anki. Évite d'oublier de synchroniser manuellement.

---

### Colorful Tags / Hierarchical Tags
**Code :** `594329229` / `1835859645`

- **Colorful Tags** : attribue une couleur à chaque tag dans le Browser et l'éditeur
- **Hierarchical Tags** : organise les tags en arborescence (`HGG::Auteurs::Rousseau`)


---

### Contanki — Controller Support
**Code :** `1343485857`

Permet d'utiliser une manette de jeu (PS4, Xbox, Switch Pro) pour naviguer et noter les cartes Anki.

---

### Customize Keyboard Shortcuts
**Code :** `24411424`

Redéfinit tous les raccourcis clavier d'Anki. Utile pour adapter aux habitudes (ex. remapper les touches de notation si on est sur disposition [[Ergol]]).

---

## Voir aussi

- [[Anki - Vue d'ensemble]]
- [[AnkiCollab]]
- [[AnkiConnect]] (lien vers l'API dans [[Python]])
- [[Ergol]] — si on reconfigure les raccourcis pour la disposition Ergol
