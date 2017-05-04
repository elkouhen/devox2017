#HTTP/2 du point de vue développeur (Sebastien Augereau)


## Historique : 
- HTTP 1.1 -> 97
- HTTP 2 -> 2015 Développé par IETF

## Différences

HTTP/1 : Clean Text
HTTP/2 : Binary Frame (moins lisible, plus compacte)

## Grosse Feature : multiplexing
- HTTP 1.1 => 1 connexion TCP par ressource, gestion du keep alive, entre 8 et 12 connexions max ouvertes par navigateur
- HTTP 2 => 1 connexion TCP bidirectionnelle et persistente (gestion de priorités sur les ressources)

## Compression des headers

Format Hpack (30 et 80% de compression, suppression des headers redondants via des diff)

## Navigateur

Géré par tous les navigateurs sauf Opera mini

# Pourquoi migrer ?

Temps de chargement réduit de 25 à 50 %
SEO  : Google se base sur la latence de la page + SSL

## Pratiques obsoletes
- Concaténer les fichiers
- Inline
- Sprite
- Domaine sharding