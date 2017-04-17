Project Valhalla
- 2 features : value types, generic sur primitive et value types

Ce qui ne va pas avec les objets

- Chaque objet a un header de 64 bits
- Les tableaux d'objets sont des tableaux de reference
- On crée trop de références

Le rapport du cout d'accès la mémoire / CPU est très cher aujourd'hui

Value Type
- idem struct C
- pas d'identité (pas d'adresse mémoire)
- immutable -> trop compliqué

List<complex> -> tableau de complex et pas un tableau de pointeurs

Valuetype + Generics -> Bytecode non pret

List<?> vs List<int> vs List<Integer>

Project Panama
- Appel de C a partir de java
- Accéder aux opérateurs SIMD (exemple : int sur 512 bits)

Java 10
- Panama
- Valhalla : Value Types

Java 11 :
- Value Type + Generique spécialisées

Project Amber
- inférence de type
  - classique
  - classes anonymes
  - lambda : var lambda = x -> x + 2
- Enums avec Generics
- Lambda
  - _ unused parameters
  - améliorer l'inférence

Grosse Feature de java 10 : Pattern Matching

Switch sur les types demandé depuis 97

- switch case sur les types des objets
- switch retourne une valeur

-> Nouveau concept : Les hiérachies fermées -> typage algébrique
