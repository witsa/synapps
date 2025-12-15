### orientation
- **Type** : `String`
- **Description** : Définit l'orientation du dessin de la chaudière sur l'interface.

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`.

### Autonome?
- **Type** : `Boolean`
- **Description** : Indique si l'acteur fonctionne de manière autonome, sans nécessiter d'acteur requêteur.

> ⚡Chemin d’accès depuis l’acteur `properties.isAutonomous`.

### Requêteur
- **Type** : `String`
- **Description** : La clé de l'acteur requêteur responsable de la communication avec le REDY. Nécessaire si `isAutonomous` est désactivé (`false`).

> ⚡Chemin d’accès depuis l’acteur `properties.requesterKey`.

### Auto raffraichi?
- **Type** : `Boolean`
- **Description** : Indique si l'acteur doit automatiquement rafraîchir les données du reflet à intervalles réguliers.

> ⚡Chemin d’accès depuis l’acteur `properties.autoRefresh`.

### Délai
- **Type** : `Number`
- **Description** : Le délai en secondes entre chaque rafraîchissement automatique des données du reflet.

> ⚡Chemin d’accès depuis l’acteur `properties.autoRefreshDelay`.

### Reflet
- **Type** : `String`
- **Description** : Le chemin vers le reflet REDY que cet acteur doit afficher.

> ⚡Chemin d’accès depuis l’acteur `properties.reflectPath`.

### Détails de reflet au click
- **Type** : `Boolean`
- **Description** : Permet d'ouvrir une modale avec le détail du reflet lorsque l'utilisateur clique sur l'acteur, si le reflet est commandable la modale proposera sa commande.

> ⚡Chemin d’accès depuis l’acteur `properties.withDetails`.
