---
aliases:
  - veracrypt
  - chiffrement disque
tags:
  - chiffrement
  - sécurité
  - stockage
---
# 🔐 Veracrypt

#chiffrement #sécurité #stockage

> Veracrypt est le standard open source pour le chiffrement de volumes. Je l'utilise pour protéger mes données les plus sensibles, y compris celles stockées dans le cloud.

---

## Qu'est-ce que Veracrypt ?

Veracrypt est un logiciel de **chiffrement de disque à la volée** (on-the-fly encryption). Il crée des volumes chiffrés — des conteneurs ou des partitions entières — qui apparaissent comme un disque normal une fois montés, mais sont illisibles sans le mot de passe.

- Fork de TrueCrypt (abandonné en 2014)
- Open source, audité indépendamment
- Supporte AES-256, Serpent, Twofish
- Disponible sur macOS, Linux, Windows

---

## Concepts clés

### Volume de conteneur (fichier)
Un fichier `.vc` qui agit comme un disque virtuel. C'est ce que j'utilise majoritairement : je crée un fichier, je le monte, je travaille dessus, je le démonte. Ce fichier peut être stocké n'importe où — y compris dans [[MEGA]].

### Volume chiffré sur partition
Chiffrement d'une partition entière ou d'un disque externe. Plus adapté aux disques durs externes.

### Volume caché (plausible deniability)
Veracrypt permet de créer un **volume caché à l'intérieur d'un volume normal** : si on est forcé de donner un mot de passe, on donne celui du volume extérieur (avec des faux fichiers), le volume caché reste invisible. Fonctionnalité avancée.

---

## Créer un volume conteneur

1. Ouvrir Veracrypt → *Créer un volume*
2. Choisir *Créer un fichier conteneur chiffré*
3. Choisir l'emplacement (ex. dans mon dossier MEGA)
4. Algorithme recommandé : **AES** + hash **SHA-512**
5. Définir la taille (ex. 10 Go)
6. Choisir un mot de passe fort (≥ 20 caractères) — stocker dans [[KeepassXC]]
7. Bouger la souris pour générer l'entropie
8. Formater en **ExFAT** (compatible macOS + Linux)

---

## Monter et démonter

```bash
# Via l'interface graphique : simplement double-cliquer sur le fichier .vc
# Ou via terminal (macOS/Linux) :
veracrypt --mount /chemin/vers/volume.vc /media/point_de_montage
veracrypt --dismount /media/point_de_montage
```

> [!warning] Toujours démonter avant d'éteindre ou de fermer la session. Un volume non démonté peut être corrompu.

---

## Mon workflow avec MEGA

1. Le fichier `.vc` est synchronisé dans [[MEGA]] comme n'importe quel fichier
2. Je le monte localement avec Veracrypt
3. Je travaille dessus normalement
4. Je démonte avant que MEGA ne le synchronise (ou je mets le dossier en pause)
5. MEGA synchronise le fichier chiffré — illisible pour MEGA et quiconque intercepterait le transfert

> [!tip] Ne pas monter et synchroniser simultanément — risque de corruption du fichier `.vc` si MEGA upload en cours de modification.

---

## Algorithme recommandé

Pour un usage courant, **AES-256** est amplement suffisant et le plus rapide sur les processeurs modernes (accélération matérielle). Pour une paranoïa maximale : cascade AES-Twofish-Serpent.

---

## Voir aussi

- [[MEGA]] — Où je stocke mes volumes
- [[KeepassXC]] — Gestion des mots de passe de volumes
- [[GPG]] — Autre approche du chiffrement (fichiers individuels)
