## Docker 2017: Nouveautés et perspectives (Vincent Demeester)

Docker editions
- mac, windows, aws, azure, GCP ?

Docker 4 desktop (Docker4win)
- pas de virtualbox 
- maj auto 
- swarm cloud federation (switcher de swarm) 
- implem natif windows de conteneurs (> image de base 4 Go) 
- integration avec docker cloud
- restruction des options de la ligne de commande (docker ps > docker container ls)
- build
    optimization via la squash
    multistage build (avec plusieurs from) : permet de récupérer les résultat d'une image intermédiaire
- déploiement d'une stack via compose
  - docker stack deploy --compose-file=foo
- ajout de contraintes sur le déploiement (noeud avec label) 
