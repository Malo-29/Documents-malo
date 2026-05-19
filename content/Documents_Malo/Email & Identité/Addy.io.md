---
aliases:
  - addy
  - alias email
  - anonaddy
tags:
  - email
  - identité
  - vie-privée
  - alias
---
# 🎭 Addy.io — Alias Email

#email #identité #vie-privée #alias

> Addy.io me permet de créer des alias email à la volée pour ne jamais donner ma vraie adresse. Un outil essentiel pour limiter le spam et protéger mon identité en ligne.

---

## Principe : pourquoi des alias ?

Chaque fois que je m'inscris sur un site, je donne mon email. Résultat :
- **Spam** si le site est compromis ou vend ses bases
- **Tracking** entre services (même email = même identité liée)
- **Impossibilité de savoir** quel service a fuité mon adresse

Avec des alias, je crée une adresse unique par service (`amazon-xk7h2@addy.io`). Si je reçois du spam dessus, je sais exactement qui a fuité, et je désactive l'alias en un clic.

---

## Qu'est-ce qu'Addy.io ?

- Ex-AnonAddy, renommé Addy.io
- **Open source** (auto-hébergeable)
- Gratuit avec des fonctionnalités généreuses (20 alias actifs en gratuit, illimités en payant)
- Les emails reçus sur l'alias sont **redirigés** vers ma vraie adresse
- Je peux **répondre** via l'alias — le destinataire ne voit jamais ma vraie adresse

---

## Fonctionnement

```
Expéditeur → alias@addy.io → Addy.io → ma vraie adresse (Proton, etc.)
         ←  Ma réponse semble venir de alias@addy.io
```

---

## Utilisation pratique

### Créer un alias
1. Se connecter sur [app.addy.io](https://app.addy.io)
2. *Générer un alias* → choisir le format (UUID, aléatoire, ou custom)
3. Copier l'alias et l'utiliser à l'inscription

### Types d'alias
- **UUID** : `550e8400-e29b@addy.io` — complètement aléatoire
- **Custom** : `malosaout-amazon@mondomaine.addy.io` — plus mémorisable
- **Catch-all** : tout ce qui arrive sur `*@mondomaine` est redirigé (si on a son domaine)

### Gérer les alias
- Désactiver un alias → tous les mails envoyés dessus rebondissent (le service croit que l'adresse n'existe plus)
- Supprimer un alias → définitif
- Ajouter une description → pour se souvenir à quoi correspond chaque alias

---

## Intégration avec le navigateur

L'extension de navigateur **Addy.io** permet de générer un alias directement dans un champ email, sans quitter la page.

---

## Alternative : SimpleLogin

[SimpleLogin](https://simplelogin.io) est une alternative similaire, rachetée par Proton. Si on est déjà dans l'écosystème [[ProtonMail|Proton]], SimpleLogin est directement intégré.

---

## Voir aussi

- [[ProtonMail]] — Adresse destination principale
- [[Thunderbird]] — Client qui reçoit les redirections
- [[Gérer ses données sur internet]] — Stratégie globale de protection
- [[Configurer son navigateur]] — Extension alias dans le browser
