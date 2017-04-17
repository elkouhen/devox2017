# GraphQL vs Falcor (Antoine Cellier, Hugo Wood)

REST
- identifier les ressources via URL, bien utiliser les verbes

Graphql
- langage de requetage
- développé par Facebook
- langage de description des requêtes
- lib serveur

Falcor :
- syntaxe JSON
- développé par netflix
- lib client + serveur

Similarités
- C'est le client qui choisit les champs et relations
- 1 requête par écran

Différences
- GraphQL impose un nouveau langage
- Typage statique en graphql (vs typage dynamique Falcor)
- Introspection vs Batching / Caching (fusion de n requêtes)
- N implémentations vs 1 implémentation
- Bonne adoption (exemple API Github) vs Faible adoption
