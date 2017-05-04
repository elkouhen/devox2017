#Orchestration de conteneurs : le choix des armes ! (by Jonathan Raffre , Jean-Louis Rigau , Thomas Auffredou, Yannick lorenzati)

- Présentation de Kubernetes, Swarm, Mesos

## Conteneur ?

- Basé sur noyau linux
- Permet une isolation de processus
- Il existe plusieurs implémentations (docker, rkt, etc.)

=> On ne livre plus des applications mais des images

## Micro Services

Intérêt : mieux gérer la granularité des services pour faciliter le scaling

Conséquences : on doit gérer une multitude de services et la communication entre les services

## Micro Services & Conteneurs

Uniformisation du déploiement

-> Si trop grand nombre de services, il est nécessaire d'utiliser un orchestrateur de conteneurs

## Orchestrateur ?

- gère un pool de ressources (disque, cpu, etc...)
- connait la topologie du cluster
- connait les applications déployées (où, combien ?)
- connaît l'état de santé des services
- connaît l'état de santé de la plateforme (perte d'un noeud -> redéploiement)

## Hyperviseur vs Orchestrateur

Hyperviseur : Sur 1 machine on déploie n vms isolés
Orchestrateur : Permet d'aggréger n machines indépendantes en un 1 système logique

## Swarm = Swarm mode de docker

Vocabulaire
- Node : Docker engine membre du cluster (manager ou worker)
- Service : ensemble de Tasks
- Task : un conteneur & sa commande

Docker gère un DNS interne pour simplifier la communication entre les conteneurs

Swarm gère un modèle de service déclaratif
- exemple : je veux que swarm gère 4 tasks pour un service

## Mesos - Marathon (2 projets)

Vocabulaire :
- Mesos Master : connait les ressource et orchestre les taches
- Mesos Agent : exécute les taches demandées par le master
- Framework  : permet d'interagir avec le master (exemple : marathon qui travaille avec les conteneurs)
- Task : processus exécuté sur un agent

Supporte d'autres conteneurs (Docker + Mesos containerizer)

## Kubernetes

Vocabulaire :
- APiserver : expose l'API de kubernetes
- Kube-controller-manager : contrôle l'état du cluster
- Kube-proxy : configure l'accès aux service
- Kubelet : présent sur chaque noeud, exécute les pods
- Master : ensemble des composants nécessaires à la gestion du cluster
- Node : exécute les pods
- Pod :
   - ensemble de conteneurs colocalisés partageant des ressources
   - accessible via une adresse IP dédiée, routable au sein du cluster

# Cycle de vie d'une application conteneurisée

- BUILD.
  - Conteneur de build (prend en entrée les sources & contient les outils de dev)
  - Conteneur applicatif : contient l'appli + runtime java + tomcat ..
- Slave à la demande. En utilisant l'API ?
- SHIP
  - Via un registry et push/pull
- DEPLOY
  - il faut anticiper les ressources utilisées par les applications
  - Stratégie de mises à jour : rolling update, canary release, blue/green
  - Gestion de la Résilience : redéploiement, healthcheck, reconciliation

# Usine Logicielle Scalable avec un Orchetsrateur

## Swarm mode

1 Jenkins master + plugin swarm (plugin qui fait auto discovery de slaves)

N Jenkins Slave : Conteneur Docker (Jenkins agent + swarm client)

=> L'agent lance le build dans un contenur de build

## Mesos

1 Jenkins master + mesos plugin

Création d'un framework dédié "Jenkins Scheduler"

Configuration de templates pour les slaves (Slave Info)

## Kubernetes

1 Jenkins master + kubernetes plugin

1 pod pour le build avec jenkins agent

=> Tous ses outils s'intéègre bien avec le pipeline jenkins

# Communication inter conteneur

## Swarm

Création d'un Overlay network
S'appuie sur le DNS interne

-> on accède aux service directement via leur nom (exemple : redis:6547)

## Mesos

Basé sur Marathon LB : conteneur HAProxy
Mesos envoi des événements à chaque màj. Marathon LB ecoute ces événements

## Kubernetes

Différentes solutions : 
- Calico : Routage BGP -> Pas de traduction d'adresses
- Service : Routage L4 -> repartit la charge sur les services sous jacents
- Namespace & KubeDNS : les services disposent d'un entrée relative au namespace
- Ingress : Routage L7 comme HAProxy

# Gestion de la persistance

Se fait via l'utilisation de volumes.

=> Les volumes loceux ne garantissent pas la persistence

Il faut associer les volumes docker avec des systèmes de stockage reseau 
- Solutions : REX Ray, Kubernetes Persistent Volume

# Gestion de la Scalabilité

## SWARM

docker service scale =10

## MESOS

Idem via une API REST ou IHM

Pas d'auto scaling

## Kube

kubectl scale --replicas=5
