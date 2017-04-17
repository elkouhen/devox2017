# CQRS/EventSourcing par la pratique (Clément Heliou)

## Event Sourcing

Consiste à capturer tous les evenements de changement d'état d'une application.

L'état de l'application est obtenu par aggrégation des événements.

Avantages
- Audit
- Analyse/debug
- Reprise de données / Rejeu de données
- "Performance" Impleméntation basé sur l'utilisation de composants qui scalent bien

## CQRS : Command Query Responsibility Segregation

Séparation, au sein d’une application, des composants de traitement métier de l’information ("command" / écriture) et de restitution de l’information ("query" / lecture).

Avantages
- Performances des lectures
- Bonne Integration avec Event Sourcing
- Maintenabilité
