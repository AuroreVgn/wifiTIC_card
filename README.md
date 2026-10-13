# 📊 WiFiTIC Lovelace Card

[![GitHub Release](https://img.shields.io/github/v/release/AuroreVgn/wifiTIC_card?style=flat-square)](https://github.com/AuroreVgn/wifiTIC_card/releases)
[![Licence MIT](https://img.shields.io/badge/licence-MIT-4c9a2a?style=flat-square)](LICENSE)
[![Home Assistant](https://img.shields.io/badge/Home%20Assistant-Compatible-41BDF5.svg?style=flat-square&logo=homeassistant)](https://www.home-assistant.io/)
[![HACS Custom](https://img.shields.io/badge/HACS-Custom-41BDF5.svg?style=flat-square)](https://hacs.xyz/)
[![Lovelace](https://img.shields.io/badge/Lovelace-Card-41BDF5?style=flat-square&logo=homeassistant)](https://www.home-assistant.io/dashboards/)
[![Maintainers](https://img.shields.io/badge/maintainers-%40AuroreVgn-007ec6?style=flat-square)](https://github.com/AuroreVgn)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-Support-ff5e5b?style=flat-square&logo=ko-fi)](https://ko-fi.com/aurorevgn)

## 🏠 Mes projets Home Assistant

Retrouvez l'ensemble de mes intégrations et projets Home Assistant sur ma page dédiée :

[**🏠 Découvrir mes projets Home Assistant**](https://erra.me)

## ☕ Soutenir le projet

Si cette carte vous est utile et que vous souhaitez soutenir son développement et sa maintenance :

<p>
  <a href="https://ko-fi.com/aurorevgn">
    <img src="https://storage.ko-fi.com/cdn/kofi4.png?v=3" alt="Soutenir le projet sur Ko-fi" height="45">
  </a>
</p>

## ⚠️ Important

Carte Lovelace personnalisée **Home Assistant** conçue pour l'[intégration WiFiTIC](https://github.com/AuroreVgn/wifiTIC), destinée aux compteurs Linky équipés du module **[WiFiTIC de Cartelectronic](https://cartelectronic.fr/accueil/136-wifitic.html)**.

Elle a pour objectif de rassembler dans une carte les données électriques exposées par l'intégration : soutirage, injection et informations tarifaires.

> [!IMPORTANT]
> Ce projet communautaire est **non officiel**, indépendant de [Cartelectronic](https://cartelectronic.fr/accueil/136-wifitic.html), d'Enedis et de Home Assistant.

## ✨ Fonctionnalités

- Affichage des informations électriques issues de l'intégration WiFiTIC.
- Visualisation de la puissance soutirée et de l'injection vers le réseau.
- Présentation des index de consommation par période tarifaire.
- Affichage des informations de contrat et de période tarifaire lorsqu'elles sont disponibles.
- Présentation adaptée à un tableau de bord Lovelace.
- Deux modes d'affichage : **Détaillé** et **Compact**.
- Graphique local des puissances soutirée et injectée, construit depuis l'ouverture de la carte (jusqu'à une heure).
- Affichage des index tarifaires, mesures, diagnostics et relais disponibles en mode détaillé.
- Éditeur graphique permettant de choisir les entités, le mode, le titre et l'affichage du graphique.
- Résolution automatique des entités WiFiTIC lorsqu'elles peuvent être identifiées sans ambiguïté.
- Compatibilité avec les thèmes clair et sombre.
- Actualisation ciblée du contenu pour limiter les sauts de défilement sur iOS Safari.

## 📸 Aperçus

| Mode sombre | Mode clair |
| :---: | :---: |
| <img src="assets/dark.png" alt="WiFiTIC Card — aperçu en mode sombre" width="340"> | <img src="assets/light.png" alt="WiFiTIC Card — aperçu en mode clair" width="340"> |

Les captures montrent les thèmes clair et sombre de la carte.

## 📋 Prérequis

La carte est conçue pour fonctionner avec l'intégration **[WiFiTIC pour Home Assistant](https://github.com/AuroreVgn/wifiTIC)**.

L'intégration récupère les informations du module via **MQTT** et l'**API REST locale**. Elle doit être installée et configurée avant d'utiliser la carte.

La carte propose des correspondances automatiques avec les capteurs WiFiTIC ; les entités peuvent aussi être sélectionnées manuellement dans l'éditeur graphique.

## 🛡️ Compatibilité

- **Home Assistant** avec un tableau de bord Lovelace.
- **Intégration WiFiTIC** : [AuroreVgn/wifiTIC](https://github.com/AuroreVgn/wifiTIC).
- Données disponibles selon le contrat Linky et les informations remontées par le module.

Aucune version minimale de Home Assistant n'est annoncée tant que la carte n'a pas été testée et publiée.

## 📦 Installation

### Option A — HACS

1. Ouvrir **HACS** dans Home Assistant.
2. Dans les **dépôts personnalisés**, ajouter `https://github.com/AuroreVgn/wifiTIC_card`.
3. Choisir le type **Dashboard / Plugin** selon la version de HACS.
4. Installer **WiFiTIC Card** et recharger le navigateur.

> [!NOTE]
> Le dépôt contient le fichier `hacs.json` et le composant installable dans `dist/`, selon la structure attendue pour un plugin Lovelace HACS.

### Option B — Installation manuelle

1. Télécharger [`wifitic-energy-card.js`](dist/wifitic-energy-card.js).
2. Copier le fichier dans `/config/www/wifitic-energy-card.js`.
3. Dans **Paramètres → Tableaux de bord → ⋮ → Ressources**, ajouter :

```text
/local/wifitic-energy-card.js
```

Type : **Module JavaScript**.

4. Recharger complètement le navigateur (`Ctrl+F5` ou `Cmd+Shift+R`).

## ⚙️ Configuration minimale

Ajouter une carte manuelle :

```yaml
type: custom:wifitic-energy-card
```

Le titre par défaut est **WiFiTIC — Électricité**. Le mode initial est **Détaillé** et le graphique est activé.

## ⚙️ Exemple de configuration complète

```yaml
type: custom:wifitic-energy-card
title: WiFiTIC — Électricité
mode: detailed
show_graph: true

# Facultatif : personnaliser les entités si nécessaire
# import_power: sensor.votre_puissance_soutiree
# export_power: sensor.votre_puissance_injectee
# tariff_period: sensor.votre_periode_tarifaire
```

| Option | Valeur par défaut | Description |
| --- | --- | --- |
| `title` | `WiFiTIC — Électricité` | Titre de la carte |
| `mode` | `detailed` | `detailed` ou `compact` |
| `show_graph` | `true` | Afficher le graphique en mode détaillé |
| `import_power`, `export_power`, etc. | Automatique | Surcharge des entités détectées |

Les entités peuvent être renseignées dans le YAML ou sélectionnées depuis l'éditeur graphique.

## 📊 Entités utilisées

La carte exploitera les données fournies par l'intégration WiFiTIC. Parmi les entités disponibles côté intégration :

| Information | Entité exposée par l'intégration |
| --- | --- |
| Puissance apparente soutirée | Puissance apparente soutirée |
| Puissance soutirée estimée | Puissance soutirée du réseau (estimée) |
| Puissance injectée | Puissance injectée sur le réseau |
| Index d'injection | Index énergie injectée au réseau |
| Index de soutirage | Index énergie soutirée – *nom de période* |
| Période en cours | Période tarifaire |
| Contrat | Contrat électrique |

Les identifiants `sensor.*` exacts peuvent dépendre des noms attribués par Home Assistant. **Ce tableau décrit l'intégration, pas encore une liste d'entités obligatoires pour la carte.**

## 🎛️ Modes d'affichage

### Détaillé

Affiche les quatre indicateurs principaux (puissances et énergies du jour), le graphique des puissances si activé, les index tarifaires, les mesures et diagnostics, ainsi que les relais disponibles.

Le graphique est construit **localement**, à partir des mesures reçues pendant que la carte est ouverte : il ne recharge pas l'historique Recorder.

### Compact

Affiche les quatre indicateurs principaux sans les sections supplémentaires. Ce mode convient aux tableaux de bord plus denses.

## 🎨 Éditeur graphique

L'éditeur permet de configurer :

- le titre ;
- le mode **Détaillé / Compact** ;
- l'affichage du graphique ;
- les entités de puissance, énergie, période tarifaire, index, contrat, diagnostics et relais.

Les entités renseignées manuellement sont prioritaires sur les correspondances automatiques.

## 📱 Responsive / mobile

La carte utilise une grille de deux colonnes et adapte la taille des valeurs aux petits écrans. La version v0.0.1 limite les remplacements du contenu lors des mises à jour afin de préserver autant que possible le **défilement et le focus sur Safari iOS**.

> [!NOTE]
> Ce correctif est intégré au JavaScript, mais son comportement doit encore être confirmé sur les différentes versions de Safari iOS et de Home Assistant.

## 🛠️ Dépannage

### La carte n'apparaît pas

Vérifier que `/local/wifitic-energy-card.js` est enregistrée comme **Module JavaScript**, puis forcer l'actualisation du navigateur.

### Les données ne s'affichent pas

Dans **Outils de développement → États**, vérifier que les capteurs WiFiTIC existent et reçoivent des valeurs. Si les identifiants ont été personnalisés, sélectionner explicitement les bonnes entités dans l'éditeur.

### Le graphique est vide

Il se construit progressivement **depuis l'ouverture de la carte**. Il faut au moins deux échantillons pour tracer les courbes.

### Les changements ne sont pas visibles

Après avoir remplacé le JavaScript, forcer l'actualisation du navigateur pour éviter de conserver l'ancienne version en cache.

## 🤝 Contributions et problèmes

Les retours, corrections et propositions d'amélioration sont les bienvenus dans les [issues du dépôt WiFiTIC Card](https://github.com/AuroreVgn/wifiTIC_card/issues).

Pour faciliter l'analyse, indiquer la version de Home Assistant, celle de l'intégration WiFiTIC, le navigateur utilisé et les étapes permettant de reproduire le problème. Ne pas publier de données personnelles ni d'identifiants.

## 📄 Licence

Projet distribué sous licence [MIT](LICENSE).
