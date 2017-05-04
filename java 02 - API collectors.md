# L'API Collector dans tous ses états (José Paumard)

## Streams

- Un stream est un pipeline d'opérations
- Certaines operations sont intermédiaires d'autres terminales
- Certains opérations terminales sont des collectors

### Rappel - Opération sur les streams

2 categories d'opérations

- Sans buffer
  - map
  - filter
  - flatMap
- Avec buffer
  - sort
  - distinct

### Opérations terminales

1 stream a besoin d'une operation terminale pour consommer les elements de la source.
- anyMatch, findFirst, etc.

Exemple :
````
.count()
.collect(Collectors.counting())

.min(Comparator.naturalOrder())
.collect(Collectors.minBy(Comparator.naturalOrder())
````

## Collectors
- Permet d'eviter de mapper systématiquement
- Pas de grouping by dans les stream

groupingBy(String::length, Collectors.counting())
