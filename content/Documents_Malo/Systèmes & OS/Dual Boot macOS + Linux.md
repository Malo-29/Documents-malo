---
aliases:
  - dual boot
  - dualboot
  - refind
  - asahi
tags:
  - os
  - linux
  - macos
  - dual-boot
---
# 🔀 Dual Boot macOS + Linux

#os #linux #macos #dual-boot

> Le dual boot permet de faire cohabiter macOS et Linux sur le même Mac. Au démarrage, je choisis quel système lancer. Chacun a sa propre partition, isolée de l'autre.

---

## Pourquoi le dual boot ?

- Conserver macOS pour ses usages ([[IINA]], Final Cut, compatibilité Apple)
- Avoir Linux pour explorer, programmer, expérimenter dans un vrai environnement Linux
- Ne pas avoir à choisir entre les deux

---

## Compatibilité matérielle

### Mac Intel (avant 2020)
Le dual boot avec Linux est bien supporté. Les distributions majeures (Ubuntu, Fedora) s'installent facilement via le gestionnaire de démarrage **rEFInd** ou GRUB.

### Mac Apple Silicon (M1/M2/M3/M4)
Plus complexe. Le projet **Asahi Linux** est la référence pour Linux sur Apple Silicon :
- [asahilinux.org](https://asahilinux.org)
- Support progressif du matériel (GPU, Wi-Fi, Bluetooth…)
- Distribution propre basée sur Fedora (Fedora Asahi Remix — recommandée)

---

## Installation sur Mac Intel

### Étape 1 : Préparer macOS
1. Sauvegarder avec Time Machine ou [[Veracrypt|volume chiffré]]
2. Dans *Utilitaire de disque* → Partitionner le disque
3. Créer une partition vide pour Linux (minimum 30 Go, recommandé 60+)

### Étape 2 : Créer une clé USB d'installation
```bash
# Télécharger l'ISO de la distribution choisie
# Sur macOS, identifier la clé USB :
diskutil list
# Flasher l'ISO :
sudo dd if=ubuntu.iso of=/dev/rdiskN bs=1m
```
Ou utiliser **balenaEtcher** (interface graphique).

### Étape 3 : Installer rEFInd
rEFInd est un gestionnaire de démarrage qui remplace le bootloader Apple et permet de choisir le système au démarrage.

```bash
# Télécharger rEFInd : rodsbooks.com/refind/
# Désactiver SIP (System Integrity Protection) temporairement :
# Redémarrer en mode recovery → Terminal → csrutil disable
sudo ./refind-install
```

### Étape 4 : Installer Linux
1. Démarrer sur la clé USB (maintenir Option au démarrage)
2. Suivre l'installeur → choisir la partition vide créée à l'étape 1
3. **Ne pas formater la partition EFI** — partagée avec macOS

---

## Installation sur Mac Apple Silicon (Asahi Linux)

```bash
# Depuis macOS, dans le Terminal :
curl https://alx.sh | sh
# Suivre les instructions — processus guidé
```

Asahi Linux installe un bootloader compatible Apple Silicon et partitionne automatiquement.

---

## Gestion des partitions

| Partition | Usage |
|-----------|-------|
| EFI (200 Mo) | Partagée — bootloaders |
| macOS | Système Apple |
| Linux | Système Linux |
| Data partagée (optionnel) | ExFAT accessible des deux côtés |

> [!tip] Une partition ExFAT partagée permet d'échanger des fichiers entre macOS et Linux sans passer par internet.

---

## Au quotidien

- **rEFInd** apparaît au démarrage → flèches pour choisir
- Chaque OS ne voit pas les fichiers de l'autre (sauf partition partagée)
- Les mises à jour macOS ne touchent pas Linux (et vice-versa)

---

## Limites

- Certaines mises à jour macOS peuvent perturber le bootloader → rEFInd à réinstaller
- FileVault (chiffrement macOS) peut compliquer le dual boot
- Sur Apple Silicon : tout le matériel n'est pas encore supporté par Asahi

---

## Voir aussi

- [[Linux - Choisir sa distribution]] — Quelle distro installer
- [[Veracrypt]] — Chiffrer la partition Linux
- [[GrapheneOS]] — Philosophie similaire sur mobile
