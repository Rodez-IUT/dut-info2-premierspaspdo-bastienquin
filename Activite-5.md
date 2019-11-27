# Activité 5

### Erreur provoquée

On vient d'ajouter une erreur entre l'insertion de la ligne dans action_log et de la mise à jour du status_id de l'utilisateur. L'update n'est donc pas exécuté contrairement à l'insertion dans la table action_log, on se retrouve donc avec d'un côté un utilisateur ayant lance une action "askDeletion", et de l'autre un utilisateur dont le status-id n'a pas bougé. Les données ne sont donc pas très cohérentes.