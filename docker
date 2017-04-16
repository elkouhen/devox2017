docker

Modele de service declaratif
  - tel appli, tel port
=> Docker swarm gère la reconciliation
Service Discovery
Load balancing
Rolling Updates

Vocabulaire :

Cluster : au moins un noeud
Node : instace docker engine
  workers ou master (dont 1 leader élu par RAFT)


Service :
Task : 1 conteneur
Secrets, Reseaux, Noeuds, Volumes
Stack : groupe de services

docker swarm init
docker join-swarm token
docker node ls
docker update --role-manager
docker service rm foo
docker service create
docker network create --driver overlay 

visualizer pour voir l'état d'un cluster dockeer swarm
