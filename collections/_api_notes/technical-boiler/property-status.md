---
api_type: technical/boiler
kind: property
name: status
---
Indique l'état de fonctionnement de la chaudière. Les valeurs possibles sont :

| **Nom**            | **Clé**    | **Description**                        | **État du brûleur**                |
| ------------------ | ---------- | -------------------------------------- | ---------------------------------- |
| Arrêté             | `stopped`  | La chaudière est arrêtée               | Éteint                             |
| En marche          | `running`  | La chaudière est en fonctionnement     | Synchronisé avec l'état du brûleur |
| Démarrage en cours | `starting` | La chaudière est en phase de démarrage | Éteint                             |
| Arrêt en cours     | `stopping` | La chaudière est en phase d'arrêt      | Éteint                             |
