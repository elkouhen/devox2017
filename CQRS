Pattern d'Architecture

Capturer tous les evenements de changement d'état d'une application
-> Etat actuel obtenu par aggregation des evenements

Avantages
- Audit
- Analyse/debug
- Reprise de données / Rejeu de données
- "Performance" ??? Implem sur des composants qui scalent bien

Evenement -> Fonction d'evolution pour mettre à jour l'état
-> Publication des effets de bord vers les partenaires (uniquement quand l'application est dans un état stable)

Queue de commande -> event loop -> BUS

CQRS : Command Query Responsibility Segregation
-> Performances des letures
-> Maintenabilité
-> Integration avec Event Sourcing

Contexte :
-> Monitoring métier
-> contrôles basiques par client, produit, etc.

Stockage Evenement -> Agregation des evenements ⁻> WS -> Console Web
