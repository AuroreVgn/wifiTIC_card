# 🧩 WiFiTIC Card

[![Release](https://img.shields.io/github/v/release/AuroreVgn/wifiTIC_card?label=release&style=flat-square)](https://github.com/AuroreVgn/wifiTIC_card/releases)
[![Home Assistant](https://img.shields.io/badge/Home%20Assistant-Compatible-41BDF5?style=flat-square&logo=homeassistant)](https://www.home-assistant.io/)
[![HACS](https://img.shields.io/badge/HACS-Dépôt%20personnalisé-41BDF5?style=flat-square)](https://www.hacs.xyz/)
[![Mainteneur](https://img.shields.io/badge/mainteneur-%40AuroreVgn-0078D7?style=flat-square)](https://github.com/AuroreVgn)
[![Ko--fi](https://img.shields.io/badge/Ko--fi-Soutenir-FF5E5B?logo=kofi&logoColor=white&style=flat-square)](https://ko-fi.com/aurorevgn)

Carte **Lovelace** dédiée aux compteurs **Linky** équipés d’un module **WiFiTIC CARTELECTRONIC**, pour visualiser les informations électriques directement dans un tableau de bord Home Assistant.

> [!IMPORTANT]
> Projet communautaire non officiel, indépendant de CARTELECTRONIC, d’Enedis et de Home Assistant.

## 🏠 Mes projets Home Assistant

[Découvrir mes projets Home Assistant](https://erra.me)

## ☕ Soutenir le projet

Si ce projet vous est utile, vous pouvez [soutenir son développement sur Ko-fi](https://ko-fi.com/aurorevgn).

## ✨ Fonctionnalités prévues

La carte a pour objectif de présenter, dans une interface dédiée :

- La **puissance instantanée** du compteur.
- La **consommation électrique** et les index tarifaires.
- L'**injection vers le réseau**.
- Les **périodes tarifaires** disponibles dans l'intégration.

> [!NOTE]
> Les fonctionnalités définitives, les options d'affichage et les entités requises seront documentées à partir du code JavaScript publié. Cette liste décrit l'objectif du projet, pas une version déjà distribuée.

## 🛡️ Compatibilité

La carte est destinée à être utilisée avec l'[intégration WiFiTIC](https://github.com/AuroreVgn/wifiTIC) dans un tableau de bord Lovelace Home Assistant.

## 📦 Installation

> [!WARNING]
> **Publication en cours :** le code JavaScript de la carte n'est pas encore présent dans ce dépôt. L'installation HACS n'est pas disponible à ce stade.

Une fois le code publié, cette section détaillera l'installation HACS et manuelle selon la structure réelle des fichiers.

## ⚙️ Configuration

La configuration YAML et les éventuelles options de l'éditeur visuel seront documentées après publication du composant Lovelace.

## 📊 Affichage

La carte vise à regrouper les informations électriques issues de WiFiTIC : puissance, soutirage, injection et périodes tarifaires.

## 🔌 Intégration Home Assistant

L'intégration correspondante est disponible dans le dépôt [WiFiTIC](https://github.com/AuroreVgn/wifiTIC).

## ℹ️ Fonctionnement et limites

- Les données affichées dépendront des entités réellement disponibles dans Home Assistant.
- La carte ne remplace pas les statistiques du tableau de bord Énergie.
- Aucun fichier JavaScript installable n'est encore publié dans ce dépôt.

## 🤝 Signaler un problème

Ouvrir une [issue GitHub](https://github.com/AuroreVgn/wifiTIC_card/issues) en précisant la version de Home Assistant, le navigateur et les étapes de reproduction.

## 📄 Licence

Licence à définir avant publication du code. Aucun fichier LICENSE n'est actuellement publié.
