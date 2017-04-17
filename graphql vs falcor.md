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
- GraphQL impose un nouveau langage - Syntaxe JSON pour Falcor
- Typage statique en graphql - Typage dynamique Falcor
- Introspection vs Batching / Caching (fusion de n requêtes)
- N implémentations pour GraphQL vs 1 implémentation pour Falcor
- Bonne adoption pour GraphQL vs Faible adoption pour Falcor
