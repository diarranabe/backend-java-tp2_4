# backend-java-tp2_4

L’objectif de ce projet est de construire une application type réseau social permettant de comparer sa consommation électrique avec ses amis et ses voisins.(#version Api)

## Getting Started

### Design
La conception est dans le fichier "Design.md"
### Prerequisites

```
 Java  -
 Maven -
 Apache tomcat -
 Hibernate -
 Javax servlet -
 jersey -  
 Postman -

```

### Installation

1: Configuration du server 


 Dans le ficher persistence.xml (src/java/resources/META-INF) 
Utiliser les informations de votre server 'nom' 'password' et nom de la BD  "jpaservelet" dans notre cas

            <property name="hibernate.connection.password" value="yourPassword"/>
            <property name="hibernate.connection.url" value="jdbc:mysql://localhost/jpaservelet"/>
            <property name="hibernate.connection.username" value="Name"/>

2: Demarer votre server (Wamp : http://www.wampserver.com/en/ dans notre cas)

3: Lancer l'application JpaTest(Java)
```
il créaion des tables dans la BD
```

4: Lancer Maven avec:
```
Goal : tomcat7:run
```
5: Faite vos requetes avec Postman https://www.getpostman.com/ ou autre outil pour les interactions avec les données.
Il donc possible de manipuler:
* Les personnes (/person)
* Les résidences (/home)
* Les chauffages (/heater)
* Les équipements électroniques (/electro)

Exemple:
http://localhost:8080/rest/person/3/home/3/heater/14

Cette url retourne en GET les informations du Chauffage avec l'id 14 dans la Résidence avec l'id 3 de la Personne ayant l'id 3

A cela s'ajoute interface (front) réalisée avec les Servlet pour un affichage avec Bootstrap ( n'offre pas encore toutes les fonctionalités ci-dessus)

## Auteurs

* **Nabé N. Diarrassouba** (https://github.com/diarranabe)
* **Nada Ez Zirray** (https://github.com/nadaez)
* **Charles Oliviers Maud** (https://github.com/maudmcok)

## License

This project is licensed under the GNU License.
