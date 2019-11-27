# Activité 5

### Erreur provoquée

On vient d'ajouter une erreur entre l'insertion de la ligne dans action_log et de la mise à jour du status_id de l'utilisateur. L'update n'est donc pas exécuté contrairement à l'insertion dans la table action_log, on se retrouve donc avec d'un côté un utilisateur ayant lance une action "askDeletion", et de l'autre un utilisateur dont le status-id n'a pas bougé. Les données ne sont donc pas très cohérentes.

Une fois les deux opérations SQL encapsulées dans une même transaction, l'insertion dans la table et l'update de l'utilisateur se passe sans problème. Lorsqu'on rajoute l'erreur, celle-ci est levée, la transaction n'est donc pas commitée, et non seulement le status_id de l'utilisateur n'est pas update, mais en plus l'insertion dans la table action_log n'est pas faite. Contrairement à l'activité précédente, on retrouve ici des données cohérentes.