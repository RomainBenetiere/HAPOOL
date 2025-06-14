# HAPOOL

## Installation

1. Clonez ce dépôt ou copiez son contenu dans votre répertoire de configuration Home Assistant.
2. Conservez les dossiers `packages/` et `custom_components/` à la racine de la configuration.
3. Vérifiez que `configuration.yaml` inclut les packages :
   ```yaml
   homeassistant:
     packages: !include_dir_named packages
   ```
4. Renseignez vos paramètres personnels dans `secrets.yaml`.

## Structure du dossier `packages/`

La configuration est organisée en modules sous `packages/raspipool`. Chaque fichier YAML correspond à une fonctionnalité :

- `temp.yaml` : mesure de la température de l'eau
- `ph.yaml` et `orp.yaml` : suivis des sondes pH et ORP
- `pump.yaml` : contrôle de la pompe et des cycles
- `fc.yaml`, `bleach.yaml`, `muriatic.yaml` : gestion des produits chimiques
- `notifications.yaml` : envoi d'alertes
- `switches.yaml`, `exterior.yaml`, `system.yaml`, etc.

Tous ces fichiers sont chargés automatiquement par Home Assistant grâce à l'instruction `packages` ci‑dessus. Vous pouvez les adapter en fonction de votre installation.

## Composants personnalisés

Deux composants personnalisés sont fournis dans `custom_components/` :

- **atlas_scientific** : intégration des modules EZO d'Atlas Scientific (pH, ORP, température...). Exemple minimal :
  ```yaml
  sensor:
    - platform: atlas_scientific
      port: 0x66  # adresse I2C ou port série
      scan_interval: 60
  ```
  Il crée des entités `sensor.ezo_*` utilisées dans les packages.

- **rpi_gpio** : gestion des broches GPIO du Raspberry Pi pour les `binary_sensor`, `switch` ou `cover`.

Placez ces dossiers dans `custom_components/` et redémarrez Home Assistant pour activer les intégrations.
