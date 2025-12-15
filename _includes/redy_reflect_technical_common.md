## Propriétés spécifiques

### orientation
- **Type** : `String`
- **Description** : Définit l'orientation du dessin de la chaudière sur l'interface. Les valeurs possibles sont `up`, `down`, `right` (droite), ou `left` (gauche).

### Autonome? `isAutonomous`
- **Type** : `Boolean`
- **Description** : Indique si l'acteur fonctionne de manière autonome, sans nécessiter d'acteur requêteur.

### Requêteur `requesterKey`
- **Type** : `String`
- **Description** : La clé de l'acteur requêteur responsable de la communication avec le REDY. Nécessaire si `isAutonomous` est désactivé (`false`).

### Auto raffraichi? `autoRefresh`
- **Type** : `Boolean`
- **Description** : Indique si l'acteur doit automatiquement rafraîchir les données du reflet à intervalles réguliers.

### Délai `autoRefreshDelay`
- **Type** : `Number`
- **Description** : Le délai en secondes entre chaque rafraîchissement automatique des données du reflet.

### Reflet `reflectPath`
- **Type** : `String`
- **Description** : Le chemin vers le reflet REDY que cet acteur doit afficher.

### Détails de reflet au click `withDetails`
- **Type** : `Boolean`
- **Description** : Permet d'ouvrir une modale avec le détail du reflet lorsque l'utilisateur clique sur l'acteur, si le reflet est commandable la modale proposera ces commandes.