# Java 9 modulo les modules (Jean-Michel Doudoux)

## Changements mineurs

- Simplification du try with resources try (fis) { }

- Opérateur diamant sur classes anonymes

- Méthodes privées dans les interfaces

- Fini l'identifiant _ (underscore)
  - Sera utilisé dans les lambda java 10

- API StackWalking : parcourir et filtrer info des stacktraces (interface StackWalker.StackFrame)

- API Flow -> mise en oeuvre des reactive streams : publication/souscription asynchrone
  - Flow.Subscriber
  - Flow.Processor (entre un producteur et consommateur) -> mise en place back pressure

- API Process
  - Interface ProcessHandle (-> processus courant, liste des processus, déclencher des traitements à la fin d'un processus)

- API Collections
  - immutables :
    - 12 surcharges de la méthode of pour 0, 1 ou plusieurs éléments
    - pas d'interface qui indique l'immutabilité

- API Stream -> ajout de méthodes
  - takeWhile(Predicate)
  - dropWhile(Predicate)
  - ofNullable (pet prendre null en paramètre)
  - iterate avec Predicate

- Outils JDK
  - plus de distinction JDK/JRE (organisation des repertoires, avant une JDK contenant une JRE)
  - Uniformisation des paramètres des CLI ( GNU style) -> Las anciennes options restent
  - Un compilateur ne supporte que la version courante de java et les 3 précédentes (support 7, 8 et 6 avec warnings)
  - Gestion de Multi Release JAR Files (un jar par version)
    - la version courante à la racine
    - les autres dans META-INFO/versions/N
  - JShell : interpreteur ligne de commande
  - Compact Strings => reduction de l'empreinte mémoire
  - Javadoc : HTML 5 + Moteur de Recherche
  - Implémentation de SHA-3
  - Fichiers de propriétés UTF-8

## Modules incubés 
  - Client HTTP 2.0

## Changements Reportées :
  - API JSON
  - API Money

  Release 27 juillet