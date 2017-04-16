Docker editions 
- mac, windows, aws, azure, GCP ?


Docker 4 desktop (Docker4win)
- pas de virtualbox 
- maj auto 
- swarm cloud federation (switcher de swarm) 
- implem natif windows de conteneurs (> image de base 4 Go) 
- integration avec docker cloud 
- docker-init tue les processus zombie
- restruction des options de la ligne de commande (docker ps > docker container ls)
- un client 1.11 peut communiquer avec des clients plus anciens 
- utilisation de plugins (exemple: volumes)
- system 
    docker system df
    docker system prune
    docker image prune
- build 
    optimization via la squash
    multistage build (avec plusieurs from) 
        permet de récupérer les résultat d'une image intermédiaire
        le cache est bieb géré 
    incremental context sending 
- docker stack deploy --compose-file=foo // compose to swarm 
- ajout de contraintes sur le déploiement (noeud avec label) 
