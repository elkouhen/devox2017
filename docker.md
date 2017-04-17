# Kit d'orchestration avec docker swarm mode (Vincent Demeester)

Modele de service declaratif
- Docker swarm gère la reconciliation
Service Discovery
Load balancing
Rolling Updates

Vocabulaire :

Cluster : au moins un noeud
Node : instace docker engine, workers ou master (dont 1 leader élu par RAFT)
Service :
Task : 1 conteneur
Stack : groupe de services