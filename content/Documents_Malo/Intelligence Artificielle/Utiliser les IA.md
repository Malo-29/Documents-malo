---
aliases:
  - ia
  - intelligence artificielle
  - claude
  - chatgpt
tags:
  - ia
  - productivité
  - outils
---
# 🤖 Utiliser les IA

#ia #productivité #outils

> Les IA génératives sont devenues des outils centraux dans mon quotidien, notamment pour les études. Voici ma façon de les intégrer de manière critique et efficace.

---

## Ma philosophie

Les IA sont des **outils d'amplification**, pas des oracles. Je les utilise pour :
- Accélérer des tâches répétitives
- Avoir un interlocuteur pour tester des idées
- Générer des supports de révision (flashcards [[Anki|Anki]])
- Déboguer du code, corriger des textes

Je garde toujours un **regard critique** sur les sorties : hallucinations, biais, erreurs factuelles sont courants. L'IA ne remplace pas la vérification des sources.

---

## Outils que j'utilise

### Claude (Anthropic)
Mon assistant principal pour les études. Utilisé via [claude.ai](https://claude.ai).

Points forts :
- Raisonnement long et structuré
- Excellent pour la production de documents (fiches, DM, synthèses)
- Génération de flashcards Anki au format exact souhaité
- Respectueux des consignes de format

Je lui ai défini un profil détaillé (**mémoire persistante**) pour qu'il connaisse mon contexte : ECG2, maths approfondies, HGG, objectif HEC, workflows précis pour Anki, LaTeX, etc.

### ChatGPT (OpenAI)
Utile pour des tâches rapides, browsing web, ou génération d'images (DALL-E). Je l'utilise moins pour les études structurées.

### Perplexity
Pour les **recherches avec sources citées**. Pratique quand je veux une synthèse rapide sur un sujet avec références vérifiables.

---

## Anki Terminator — IA dans Anki

Le greffon **Anki Terminator V2** (par Shige) intègre un sidebar IA directement dans l'interface de révision Anki. Il permet :
- De générer des explications pendant la révision
- De créer de nouvelles cartes depuis l'interface
- D'utiliser Claude, ChatGPT ou DeepSeek selon la configuration

Voir [[Anki]] pour plus de détails sur les greffons.

---

## Bonnes pratiques

### Prompt engineering
- Être **très précis** sur le format de sortie attendu
- Donner du **contexte** (niveau, objectif, contraintes)
- Utiliser des **exemples** pour montrer ce qu'on veut
- Décomposer les tâches complexes en étapes

### Ce que j'évite
- Soumettre des données personnelles sensibles
- Copier-coller sans relecture critique
- Faire confiance aux dates, chiffres ou citations sans vérification

---

## Confidentialité

Les IA generatives envoient les messages à des serveurs tiers. Je ne soumets donc pas :
- Données personnelles identifiantes
- Documents confidentiels
- Mots de passe ou clés

Pour des usages sensibles, certains modèles sont auto-hébergeables (Ollama + Llama, Mistral local).

---

## Voir aussi

- [[Anki]] — Greffon Anki Terminator, génération de cartes
- [[Python]] — Scripts d'automatisation avec l'API des IA
- [[Configurer son navigateur]] — Extensions IA dans le navigateur
