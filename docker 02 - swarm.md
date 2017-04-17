# Kit d'orchestration avec docker swarm mode (Vincent Demeester)

Fonctionnalités
- Modele de service declaratif
 - Docker swarm gère la reconciliation
- Service Discovery
- Load balancing
- Rolling Updates

Vocabulaire :
- Cluster : au moins un noeud
- Node : instance docker engine (worker ou master)
- Service :
- Task : 1 conteneur
- Stack : groupe de services