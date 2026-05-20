---
aliases:
  - thunderbird
  - client mail
tags:
  - email
  - client
---
# 📬 Thunderbird

#email #client

> Thunderbird est mon client mail de bureau. Il me permet de centraliser tous mes comptes email dans une interface unique, open source et extensible.

---

## Pourquoi Thunderbird ?

- **Open source**, maintenu par la Mozilla Foundation
- Gère **plusieurs comptes** simultanément (Proton, Infomaniak, Riseup…)
- Support natif de **GPG** (via OpenPGP intégré depuis v78)
- **Filtres et dossiers** puissants
- Disponible sur macOS, Linux, Windows
- **Aucun tracking**, aucune pub

---

## Configuration d'un compte

Thunderbird détecte automatiquement les paramètres IMAP/SMTP pour la plupart des fournisseurs connus. Pour les autres :

| Paramètre | Valeur typique |
|-----------|---------------|
| Protocole entrant | IMAP (SSL/TLS, port 993) |
| Protocole sortant | SMTP (SSL/TLS, port 465 ou STARTTLS 587) |
| Authentification | Mot de passe normal ou OAuth2 |

### Proton Mail
Proton utilise un chiffrement côté client incompatible avec IMAP standard. Il faut utiliser le **Proton Mail Bridge** (application séparée) qui crée un pont local IMAP/SMTP. Voir [[ProtonMail]].

### Infomaniak Mail
Compatible IMAP/SMTP standard. Voir [[Infomaniak]].

### Riseup
Compatible IMAP/SMTP standard. Voir [[Riseup]].

---

## Chiffrement GPG dans Thunderbird

Depuis Thunderbird 78, **OpenPGP est intégré nativement** — plus besoin d'Enigmail.

1. Aller dans *Paramètres du compte* → *Chiffrement de bout en bout*
2. Importer ou générer une clé OpenPGP
3. Configurer la clé publique à utiliser pour ce compte
4. Thunderbird peut alors **signer, chiffrer et déchiffrer** les emails automatiquement

Voir [[GPG]] pour les détails sur la gestion des clés.

---

## Filtres de messages

Les filtres sont l'un des points forts de Thunderbird. Je les utilise pour :
- Trier automatiquement les newsletters vers un dossier dédié
- Marquer comme lu certains types de notifications
- Rediriger selon l'expéditeur ou l'objet

Accès : *Outils → Filtres de messages*

---

## Extensions utiles

| Extension | Usage |
|-----------|-------|
| **ImportExportTools NG** | Sauvegarde et export des mails |
| **Cardbook** | Gestionnaire de contacts CardDAV |
| **ThunderHTMLedit** | Édition HTML avancée |

---

## Voir aussi

- [[ProtonMail]] — Compte principal chiffré
- [[Infomaniak]] — Alternative éthique suisse
- [[Riseup]] — Email militant
- [[GPG]] — Chiffrement des emails
- [[Addy.io]] — Alias utilisés avec Thunderbird
