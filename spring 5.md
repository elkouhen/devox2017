# Spring Framework 5.0 (Stéphane Nicoll)

## Performances
- reecriture du ant path matcher
- support de zero copy (publication de ressources statiques sans utiliser le CPU)
- Utilisation des automatiques modules de Jigsaw

## JDK 9 - HTTP/2
- Support de HTTP/2 en version "beta"
- Support de Servlet 4 en cours

## Reactive Spring
- More for scalability and stability than for speed

pulic interface XXRepository {
  Mono<Person> findOne();

  Flux<Person> findAll()
}

xxxRepository.findById().map(this::handle).subscribe();

Remarque : Pas de driver reactif JDBC

## Functional APIs

Spring Data, Spring Web (@Controller, RestTemplate) deviennent reactifs & fonctionnels

Nouvelle API pour créer le contexte Spring de manière programmatique

Nouvelle API pour définir le routage programmatiquement

## Kotlin

Langage supporté par Spring 

custom DSL pour le routage par exemple 
