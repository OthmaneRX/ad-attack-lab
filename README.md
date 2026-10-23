# AD Attack Lab — GOAD-Light

Étude de sécurité Active Directory sur lab personnel **GOAD-Light** (Game of Active Directory, Orange Cyberdefense).
Environnement volontairement vulnérable, monté et attaqué **sur ma machine personnelle**, à des fins d'apprentissage et de documentation.

> ⚠️ **Périmètre strict.** Tout le contenu de ce dépôt provient d'un lab isolé sur mon poste personnel.
> Rien ici ne concerne un réseau, un système ou des données d'une entreprise.

---

## 🎯 Objectifs

- Cartographier un domaine Active Directory et comprendre les chemins vers l'administrateur du domaine.
- Pratiquer la chaîne d'attaque AD de bout en bout dans un cadre maîtrisé.
- Pour **chaque** technique : documenter la **détection** (événements Windows) et la **remédiation**.
- Ajouter un volet **AD CS** (sécurité de la PKI Windows) — pont direct avec mes autres travaux PKI.

## 🖥️ Schéma du lab

```
                 GOAD-Light (3 VM)
  ┌───────────────────────────────────────────────┐
  │                                               │
  │   [DC01]  Contrôleur de domaine                │
  │     │        (+ AD CS / rôle PKI)              │
  │     │                                          │
  │   [SRV02] Serveur membre                       │
  │     │                                          │
  │   [WS01]  Poste de travail                      │
  │                                               │
  │   Attaquant : VM Kali/ParrotOS sur le même     │
  │   réseau interne isolé (host-only)             │
  └───────────────────────────────────────────────┘
```
> À adapter selon le déploiement réel (noms de machines, domaine, IP). Captures et schéma final dans `00-setup/`.

## 🔗 Résumé de la chaîne d'attaque

| # | Phase | Dossier | Statut |
|---|-------|---------|--------|
| 0 | Mise en place du lab | [`00-setup/`](00-setup/) | ⬜ À faire |
| 1 | Énumération / cartographie | [`01-enumeration/`](01-enumeration/) | ⬜ À faire |
| 2 | Attaques sur les identifiants | [`02-credential-attacks/`](02-credential-attacks/) | ⬜ À faire |
| 3 | Mouvement latéral | [`03-lateral-movement/`](03-lateral-movement/) | ⬜ À faire |
| 4 | Exploitation AD CS (PKI) | [`04-adcs-exploitation/`](04-adcs-exploitation/) | ⬜ À faire |
| 5 | Compromission du domaine | [`05-domain-compromise/`](05-domain-compromise/) | ⬜ À faire |
| — | Détection & remédiation (transverse) | [`detection-remediation.md`](detection-remediation.md) | ⬜ À faire |

Mettre à jour le statut (⬜ → 🟨 en cours → ✅ fait) au fur et à mesure. Publier chaque étape dès qu'elle est terminée.

## 🧰 Environnement

- **Lab :** GOAD-Light — https://github.com/Orange-Cyberdefense/GOAD
- **Hyperviseur :** _(à compléter : VirtualBox / VMware / Proxmox…)_
- **Machine hôte :** 32 Go RAM — _(CPU, disque dispo à compléter)_
- **OS attaquant :** _(Kali / ParrotOS…)_

## 📅 Suivi

Projet mené en parallèle de l'alternance. Durée cible : 6–8 semaines.
Journal d'avancement dans [`00-setup/README.md`](00-setup/README.md).
