HTTP/2 du point de vue développeur


HTTP 1.1 -> 97
HTTP 2 -> 2015
Développé par IETF

Différences

HTTP/1 : Clean Text
HTTP/2 : Binary Frame (moins lisible, plus compacte)

## Grosse Feature : multiplexing
- 1 connexion TCP par ressources, gestion du keep alive, entre 8 et 12 connexion ouverts par navigateur
- 1 connexion TCP bidirectionnelle et persistente (gestion de prioriétés sur les ressources)

## Compression des headers

Format Hpack (30 et 80% de compression , suppression des headers redondants via des diff)

## Navigateur

Tous sauf Opera mini

## Noms de domaines : 150 à 200 000, très forte augmentation en dec 2015 (bascule d'un CDN)

## Outils

Chrome developper tools
curl  (ajouter module nghttp2)

# Pourquoi migrer ?

Temps de chargement réduit de 25 à 50 %
SEO  : Google se base sur la latence de la page + SSL

# Ou agir

1 page = 2Mo
1 image = 1.5 Mo

Back End
-> Java Servlet 4 (Fin 2017)
-> existe deja chez tomcat 8.5, jetty, undertow

Front End : prendre les ressources d'un CDN HTTP/2

Pratiques inutiesl
- Concaténer les fichiers
- Inline
- Sprite
- Domaine sharding
