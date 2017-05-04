# Kit d'orchestration avec docker swarm mode (by Vincent Demeester)

Fonctionnalités
- Modele de service declaratif
 - Docker swarm gère la reconciliation
- Service Discovery
- Load balancing
- Rolling Updates

Vocabulaire :
- Cluster : au moins un noeud
- Node : instance docker engine (worker ou master)
- Service : Groupe de Taks
- Task : 1 conteneur
- Stack : groupe de services