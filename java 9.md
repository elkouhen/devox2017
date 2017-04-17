Java 9

Changements mineurs
- try with resources try (fis) { }
- opérateur diamant sur classes anonymes
- @SafeVarargs (sur méthodes privées)
- Méthodes provées dans les interfaces private void methode()
- Fini l'identifiant _ (sera utilisé dans les lambda java 10)
- StackWalking API : parcourir et filtrer info des stacktraces (interface StackWalker.StackFrame)
- Desktop : Intégrtion Bureau, Barres de taches, Evenements (JEP - 272)
- Flow API -> mise en oeuvre des reactive streams : publication/souscription asynchrone
  - Flow.Subscriber
  - Flow.Processor (entre un producteur et consommateur) -> mise en place back pressure
- API Process : Interface ProcessHandle (-> processu courant, liste des processus, déclencher des traiements à la fin d'un processus)
- Collections
  - immutables :
    - 12 surcharges de la méthode of pour 0, 1 ou plusieurs éléments
    - pas d'interface qui indique l'immutabilité
- Optional
  - stream renvoie la valeur
  - or
- Stream
  - takeWhile(Predicate)
  - dropWhile(Predicate)
  - ofNullable (pet prendre null en paramètre)
  - iterate avec Predicate
- Outils JDK
  - plus de distinction JDK/JRE (organisation des repertoires, avant une JDK contenanti unt JRE)
  - Uniformisation des paramètres des CLI ( GNU style) -> Las anciennes options restent
  - Un compilateur ne supporte que la version courante de java et les 3 précédentes (support 7, 8 et 6 avec warnings)
    - option --release
  - Multi Release JAR Files (un jar par version)
    - la version courante à la racine
    - les autres dans META-INFO/versions/N
  - JShell : interpreteur ligne de commande
  - Compact Strings : reduction de l'empreinte mémoire
    tableau de char : un char = 16 bits (java 8)
    tableau de bytes + format  (UTF16 ou Latin)
  - Javadoc : HTML 5 + Recherche
  - SHA-3
  - UTF-8 properties (PorpertyResourceBundle supporte encoding UTF-8)
  - @Deprecated (forRemoval, since)
  - Incubator modules : Client HTTP 2.0


  Reportées :
  - JSON
  - Money

  Release 27 juillet
