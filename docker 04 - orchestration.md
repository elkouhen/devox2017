#Orchestration de conteneurs

- Présentation de Kubernetes, Swarm, Mesos

- Organisation paris-container-day.fr

## Conteneur ?

Basé sur noyau linux, Isolation de processus, Plusieurs Impléms ...

On ne livre plus des applications mais des images

App -> Container Manager -> Host OS -> Machine

## Micro Services

Intérêt : mieux gérer la granularité pour pouvoir scaler

Conséquences : on doit gérer une multitude de services et la communication entre les services

## Micro Services & Conteneurs

Uniformisation du déploiement

-> Si trop grand nombre, utilisation d'un orchestrateur

## Orchestrateur ?
- gère un pool de ressources (disque, cpu, etc...)
- connait la topologie du cluster
- connait les applications déployées (où, combien ?)
- connaît l'état de santé des services
- connaît l'état de santé de la plateforme (perte d'un noeud -> redéploiement)

Hyperviseur vs Orchestrateur

1 machine -> n vms isolés
n machines indépendantes -> 1 système logique

## Swarm = Swarm mode de docker

Vocabulaire
- Node : Docker engine membre du cluster (manager ou worker)
- Service : ensemble de taches
- Task : un conteneur & sa commande

Docker gère un DNS interne pour simplifier la communication

- Modèle de service déclaratif : je veux que swarm gère 4 tasks pour un service

Commandes :
- docker node ls (manager : 1 leader les autres sont Reachable)
- docker service ls
- docker service ps MON_SERVICE -> liste des taches
- docker stask ls -> liste des stacks (exemple : 1 stack = 1 envionnement applicatif)
Portainer :
- IHM Web : Affichage des infos du conteneur

## Mesos - Marathon (2 projets)

Vocablaire :
- Mesos Master : connait les ressource et orchestre les taches
- Mesos Agent : exécute les taches demandées par le mastre
- Framework  : permet d'interagir avec le master (exemple : marathon qui travaille avec les conteneurs)
- Task : processus exécuté sur un agent

Il existe d'autres frameworks, Supporte d'eutres conteneurs (Docker + Mesos containerizer)

Archi : Zookeeper -> Master > Marathon -> Mesos Slave -> Tasks

Mesos a une IHM de management

## Kubernetes

Géré par Cloud Native ...

Vocabulaire :
- APiserver : expose l'API de kubernetes
- Kube-controller-manager : contrôle l'état du cluster
- Kube-proxy : configure accès aux service
- Kubelet : présent sur chaque noeud, exécute les pods
- Master : ensemble des composants nécessaires à la gestion du cluster
- Node : exécute les pods
- Pod :
   - ensemble de conteneurs colocalisés partageant des ressources
   - accessible via une adresse IP dédiée, routable au sein du cluster

Commandes :
- kubectl get pods -n kube-system (pods du namespace kube-system)


# Cycle de vie d'une application conteneurisée

- BUILD.
  - Conteneur de build (prend en entrée les sources & contient les outils de dev)
  - Conteneur applicatif : contient l'appli + runtime java + tomcat ..
- Slave à la demande. En utilisant l'API ?
- SHIP. Via un registry et push/pull
- Déploiement via des APIs REST (il faut anticiper les ressources utilisées par application)
  - Stratégie de mises à jour : rolling update, canary release, blue/green
- Résilience : redéploiement, healthcheck, reconciliation

# Usine Logicielle

1 master - n slaves/agent - 1 registry
-> usine logicielle résiliente et scalable

## Swarm mode

Jenkins master + plugin swarm (plugin qui fait auto discovery de slaves)

Docker (Jenkins agent + swarm client)

docker service scale ci_jenkins-slave=10

-> L'agent lance le build dans un contenur de build
-> Utilisation de Docker Compose sur le master swarm

## Mesos

Jenkins master + mesos plugin
Création d'un framework dédié "Jenkins Scheduler"
Configuurer des templates pour les slaves (Slave Info)

## Kubernetes

Jenkins master + kubernetes plugin

1 pod pour le build avec jenkins agent

-> Tous ses outils s'intéègre bien avec le pipeline jenkins

# Communication inter conteneur

## Swarm

Création d'un Overlay network
S'appuie sur le DNS interne

-> on accède aux service directement via leur nom (exemple : redis:6547)

## Mesos

Basé sur Marathon LB : conteneur HAProxy
Mesos envoi des événements à chaque màj. Marathon LB ecoute ces événements

## Kubernetes

Calico : Routage BGP -> Pas de traduction d'adresses

Service : Routage L4 -> repartit la charge sur les services sous jacents

Namespace & KubeDNS : les services disposent d'un entrée relative au namespace

Ingress : Routage applicatif L7 comme HAProxy

# Gestion de la persistance

Se fait via l'utilisation de volumes.

Les volumes loceux ne garantissent pas la persistence

Associer les volumes docker avec système de stockage reseau (REX Ray, Kubernetes Persistent Volume)

# Scalabilité

## SWARM

docker service scale =10

## MESOS

Idem via une API REST ou IHM

Pas d'auto scaling

## Kube

kubectl scale --replicas=5

# Resilience

## SWARM

## MESOS

## KUBERNETES

# S03 : Exploitation
