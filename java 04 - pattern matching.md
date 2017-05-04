# Pattern Matching en Java (10 ?) (by Remi Forax)

## Projet Valhalla

=> 2 features : value types, generic sur primitive et value types

Ce qui ne va pas avec les objets
- Chaque objet a un header de 64 bits
- Les tableaux d'objets sont des tableaux de reference
- On crée trop de références
- Le rapport du cout d'accès la mémoire / CPU est très cher aujourd'hui

Intérêt des Value Type
- idem struct C
- pas d'identité (pas d'adresse mémoire)
- List<complex> implémenté comme un tableau de complex et pas un tableau de pointeurs de commple

## Projet Panama
- Appel de C a partir de java
- Accéder aux opérateurs SIMD (exemple : int sur 512 bits)

## Java 10

### Roadmap 
- Intègrer les fonctionnalités des projets Panama et Valhalle

### Projet Amber
- étendre l'inférence de type
  - classes anonymes
  - lambda : var lambda = x -> x + 2
- Enums avec Generics

### Grosse Feature de java 10 : Pattern Matching

Switch sur les types demandé depuis 97
- switch case sur les types des objets
- switch retourne une valeur

Implique d'intégrer dans java les hiérachies fermées (typage algébrique)
