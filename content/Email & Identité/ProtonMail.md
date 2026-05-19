---
aliases:
  - proton
  - protonmail
tags:
  - email
  - chiffrement
  - vie-privée
---
# ProtonMail

#email #chiffrement #vie-privée

> ProtonMail est l'une de mes adresses emails principales pour les communications sensibles. Basé en Suisse, chiffré de bout en bout, conçu pour la vie privée.

---

## Pourquoi Proton ?

- **Chiffrement E2EE** entre comptes Proton (automatique) et avec n'importe qui via GPG
- Siège en **Suisse**, soumis aux lois suisses (parmi les plus protectrices d'Europe)
- **Zero-knowledge** : Proton ne peut pas lire mes emails
- Open source (code audité)
- **Pas de pub**, modèle économique basé sur les abonnements
- Fait partie de l'écosystème Proton : ProtonDrive, ProtonCalendar, [[ProtonVPN]]

---

## Proton Mail Bridge : attention nécessite un abonnement payant

Proton utilise un chiffrement côté client qui n'est **pas compatible avec IMAP standard**. Pour l'utiliser dans [[Thunderbird]], il faut installer **Proton Mail Bridge** :

1. Télécharger sur [proton.me/mail/bridge](https://proton.me/mail/bridge)
2. Se connecter avec son compte Proton
3. Bridge crée un serveur IMAP/SMTP **local** (127.0.0.1)
4. Dans Thunderbird, configurer le compte avec ces paramètres locaux
5. Bridge gère le chiffrement/déchiffrement de façon transparente

> [!info] Bridge doit tourner en arrière-plan pour que Thunderbird puisse recevoir et envoyer des mails Proton.

---

## Proton Pass

L'écosystème Proton inclut aussi **Proton Pass**, un gestionnaire de mots de passe. Je lui préfère [[KeepassXC]] (local, open source, plus de contrôle), mais Proton Pass est une bonne alternative cloud.

---

## Envoi chiffré vers des non-utilisateurs Proton

Deux méthodes :
1. **GPG** : si le destinataire a une clé publique GPG (voir [[GPG]])
2. **Mot de passe** : Proton permet d'envoyer un email chiffré avec un mot de passe partagé hors-bande

---

## Voir aussi

- [[Thunderbird]] — Client utilisé avec Proton via Bridge
- [[GPG]] — Chiffrement inter-opérable
- [[ProtonVPN]] — VPN du même écosystème
- [[Infomaniak]] — Alternative suisse
