# 📊 WiFiTIC Card — dépôt historique

> [!IMPORTANT]
> **WiFiTIC Card est désormais intégrée directement à l'intégration [WiFiTIC](https://github.com/AuroreVgn/wifiTIC).**
> Ce dépôt séparé n'est plus destiné à recevoir de nouvelles versions de la carte. Il est conservé pour l'historique du projet, les anciennes versions et les captures d'écran.

## Installer la carte

Installez ou mettez à jour l'intégration **[AuroreVgn/wifiTIC](https://github.com/AuroreVgn/wifiTIC)** via HACS / Marketplace ou manuellement, puis redémarrez Home Assistant.

La ressource JavaScript est fournie par l'intégration :

```text
/wifitic/wifitic-energy-card.js
```

L'intégration tente de l'enregistrer automatiquement. Si nécessaire, ajoutez-la dans **Paramètres → Tableaux de bord → Ressources** en tant que **Module JavaScript**.

Ajoutez ensuite une carte manuelle :

```yaml
type: custom:wifitic-energy-card
```

L'éditeur graphique, les modes détaillé/compact, les tuiles et jauges avec maxima indépendants, les graphiques et les optimisations mobiles sont conservés.

## Migration depuis l'installation séparée

1. Mettez à jour l'intégration WiFiTIC vers une version incluant la carte intégrée (la prochaine version prévue est **0.0.3**, non publiée à ce jour).
2. Vérifiez que la ressource `/wifitic/wifitic-energy-card.js` est accessible et enregistrée dans Lovelace.
3. Désinstallez l'ancienne carte `wifiTIC_card` installée séparément via HACS, si elle existe.
4. Supprimez uniquement son ancienne ressource JavaScript (par exemple `/hacsfiles/wifiTIC_card/wifitic-energy-card.js` ou `/local/wifitic-energy-card.js`), **pas** `/wifitic/wifitic-energy-card.js`.
5. Actualisez le navigateur. Vos configurations `type: custom:wifitic-energy-card` restent valides.

Ne chargez pas simultanément les anciennes et nouvelles ressources : elles déclarent le même type de carte.

## Documentation et support

- [README complet, configuration et dépannage](https://github.com/AuroreVgn/wifiTIC#readme)
- [Instructions de migration](https://github.com/AuroreVgn/wifiTIC#toc-section-7)
- [Signaler un problème](https://github.com/AuroreVgn/wifiTIC/issues)
- [Captures d'écran historiques](assets/)

Merci aux utilisateurs et contributeurs de WiFiTIC Card !
