---
aliases:
  - protonvpn
  - proton vpn
tags:
  - réseau
  - vpn
  - vie-privée
---
#  ProtonVPN

#réseau #vpn #vie-privée

> ProtonVPN est le VPN de l'écosystème Proton. Je l'utilise comme alternative à Mullvad, notamment pour sa version gratuite robuste et son intégration avec ProtonMail.

---

## Qui est ProtonVPN ?

ProtonVPN est développé par **Proton AG**, la même entreprise que [[ProtonMail]], basée en Suisse. C'est l'un des rares VPN à proposer une version **gratuite sans publicité et sans limite de données**.

### Points forts
- **Open source** : code client entièrement public et auditable
- **Suisse** : hors juridiction UE/US pour la rétention de données
- **No-logs** : vérifié par audits indépendants
- Plan gratuit : **illimité en données**, 3 pays disponibles, 1 appareil
- Plan payant : serveurs très rapides, plus pays, Tor-over-VPN, NetShield

### NetShield
Fonctionnalité intégrée dans les plans payants : bloque les **publicités, trackers et malwares** au niveau DNS directement dans le VPN. Similaire à [[NextDNS]] mais intégré.

---

## Différences avec Mullvad

| Critère | [[MullvadVPN\|Mullvad]] | ProtonVPN |
|---------|---------|-----------|
| Anonymat inscription | ✅ (numéro seul) | ❌ (email requis) |
| Plan gratuit | ❌ | ✅ |
| Open source | ✅ | ✅ |
| Paiement anonyme | ✅ (cash, Monero) | Partiel (crypto) |
| Intégration écosystème | ❌ | ✅ Proton |
| Tor-over-VPN | ❌ | ✅ (payant) |

**Mon choix** : Mullvad pour la confidentialité maximale, ProtonVPN comme fallback ou pour accéder au plan gratuit depuis un second appareil.

---

## Tor-over-VPN

ProtonVPN (plan payant) propose des **serveurs Tor** : le trafic passe par le VPN puis entre dans le réseau [[Tor]]. Avantage : on n'a pas besoin du Tor Browser, n'importe quelle application bénéficie de Tor. Inconvénient : encore plus lent.

---

## Configuration

1. Créer un compte sur [proton.me](https://proton.me)
2. Télécharger le client ProtonVPN
3. Choisir le protocole **WireGuard** ou **Stealth** (obfusqué, pour contourner les blocages)
4. Activer le kill switch

---

## Voir aussi

- [[MullvadVPN]] — VPN principal
- [[Tor]] — Anonymat renforcé
- [[ProtonMail]] — Même écosystème
- [[NextDNS]] — DNS filtrant
