---
aliases:
  - gpg
  - pgp
  - openpgp
  - chiffrement
tags:
  - chiffrement
  - email
  - sécurité
---
# 🔑 GPG — Chiffrement asymétrique

#chiffrement #email #sécurité

> GPG (GNU Privacy Guard) est l'implémentation libre du standard OpenPGP. Je l'utilise pour chiffrer des fichiers, signer des messages et sécuriser mes communications email.

---

## Principe du chiffrement asymétrique

GPG repose sur une **paire de clés** :

- **Clé publique** → à distribuer librement. Tout le monde peut l'utiliser pour chiffrer un message que *seul moi* peux lire.
- **Clé privée** → secrète, protégée par une passphrase. Je l'utilise pour déchiffrer et signer.

```
Alice veut écrire à Bob de façon privée :
  Alice chiffre avec la clé PUBLIQUE de Bob
  → Seul Bob (avec sa clé PRIVÉE) peut déchiffrer
```

La **signature** fonctionne à l'inverse : je signe avec ma clé privée, n'importe qui vérifie avec ma clé publique que c'est bien moi qui ai écrit.

---

## Installer GPG

```bash
# macOS (via Homebrew)
brew install gnupg

# Linux (Debian/Ubuntu)
sudo apt install gnupg

# macOS avec interface graphique : GPG Suite (gpgtools.org)
```

---

## Générer sa paire de clés

```bash
gpg --full-generate-key
```

Options recommandées :
- Type : **RSA and RSA** ou **Ed25519** (plus moderne)
- Taille : **4096 bits** (RSA) ou courbe par défaut (Ed25519)
- Expiration : **2 ans** (renouvelable — mieux qu'une clé sans expiration)
- Nom et email associés à la clé

> [!warning] Générer immédiatement un **certificat de révocation** et le stocker en lieu sûr ([[Veracrypt|volume chiffré]]).
> ```bash
> gpg --output revocation.asc --gen-revoke MON_EMAIL
> ```

---

## Opérations courantes

### Chiffrer un fichier
```bash
gpg --encrypt --recipient destinataire@email.com fichier.txt
# Produit fichier.txt.gpg
```

### Déchiffrer
```bash
gpg --decrypt fichier.txt.gpg > fichier.txt
```

### Signer un fichier
```bash
gpg --sign fichier.txt          # Signature intégrée
gpg --detach-sign fichier.txt   # Signature séparée (.sig)
```

### Vérifier une signature
```bash
gpg --verify fichier.txt.sig fichier.txt
```

### Chiffrer ET signer
```bash
gpg --encrypt --sign --recipient destinataire@email.com fichier.txt
```

---

## Gérer ses clés

```bash
# Lister les clés
gpg --list-keys               # Clés publiques
gpg --list-secret-keys        # Clés privées

# Exporter sa clé publique (à partager)
gpg --armor --export MON_EMAIL > ma_cle_publique.asc

# Importer la clé publique de quelqu'un
gpg --import cle_contact.asc

# Publier sur un serveur de clés
gpg --keyserver keys.openpgp.org --send-keys MON_ID_CLE
```

---

## Intégration avec Thunderbird

Depuis Thunderbird 78, OpenPGP est natif. Voir [[Thunderbird#Chiffrement GPG dans Thunderbird]].

---

## Web of Trust

GPG inclut un concept de **réseau de confiance** : on peut signer la clé de quelqu'un pour certifier qu'on a vérifié son identité. Plus une clé est signée par des gens de confiance, plus elle est crédible. Pour les usages courants, ce n'est pas indispensable.

---

## Voir aussi

- [[Thunderbird]] — Intégration GPG dans le client email
- [[ProtonMail]] — Chiffrement natif entre comptes Proton
- [[Veracrypt]] — Chiffrement de volumes (alternative pour les fichiers)
- [[KeepassXC]] — Stocker la passphrase de la clé GPG
