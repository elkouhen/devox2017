L'API Collector dans tout ses etats

2 depots GitHub streams-util et collectors-util

-> partie de l'API stream
-> simplifier les traitements

# Streams

Objet qui se connecte à une source (et les regarde passer). Ne contient pas de données
- pipeline d'opérations
-> operations intermédiaires/terminales
Certains terminales peuvent être des collectors

Rappel - Opération sur les streams

2 categories
sans buffer
  - map
  - filter
  - flatMap
avec buffer
  - sort
  - distinct
avec compteur, sans buffer
  - limit
  - skip

Operations terminales : 1 stream a besoin d'une operation terminale pour consommer les elements de la source.
- anyMatch, findFirst, etc.


Exemple :
.count()
.collect(Collectors.counting())

.min(Comparator.natralOrder())
.collect(Collectors.minBy(Comparator.natralOrder())

-> Permet d'eviter de mapper systématiquement
-> pas de grouping by dans les stream

groupingBy(String::length, Collectors.counting())

Opérations sur les collectors
- supplier : construction de la liste
- accumulator : ajout d'un élément à la liste
- combiner :
- finisher qui peut etre la fonction identité (cf. Collectors .collectingAndThen)

-> Interface Collector
