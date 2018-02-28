Objectif

L’objectif de ce projet est de construire une application type réseau social permettant de comparer sa consommation électrique avec ses amis, ses voisins,.. 

@Entity
Ca permet de créer une table coté hibernate


But
 
Un template de projet pour la construction d’application autonome utilisant JPA, hibernate et hsqldb. 
Ona travaillé au début avec hsqldb et  ensuite mysql pour la base de données.
 
Le but c’est de se familiariser avec hibernate , l’héritage en hibernante, 
Schéma
Ayant a respecter le modèle métier qui nous a été donné en énonce :


![](/mcd.png?raw=true)



Objects (persistence)


Person

Une personne a une liste d’amis en ajoutant la relation (@manytomany)


Home

Résidence dans la philosophie du code on a compris d'aprés le schéma que le propriétaire de cette résidence est une seule personne  ce qu'on a exprimé par la relation (@onetomany) coté home 

Heater

Un chauffage est lié a une seule résidence , alors que dans une résidence on peut trouver plusieurs chauffages ( @onetomany)



	 Pour l’héritage  nous avons choisi la « SingleTable » stratégie , une seule table (classe mére) est utilisée pour stocker toutes les instances de la hiérarchie d’héritage entiére.

	ElectronicDevice
	la classe qui va être créer en disant « phone» est une sous-classe de Device en ajoutant l’annotation @DiscriminatorValue pour déterminer quelle classe une ligne particulière fait partie dans le tableau de classe mére dans notre ças on veut la distinguer de la classe « Heater » en fmettant @DiscriminatorValue("phone") 

	Device

	c’est la clase mére ,sa table aura les attributs de toutes les classe de la hiérarchie , si une ligne n’as pas les attributs qu'une autre car ils ne sont pas lié elle met null .

On a définie deux packages :

dao : pour la gestion de  la base de données , tpour faire les liasons entre les tables tout ce qui est lié aux requêtes avec .merge pour la modification , .persisit pour l’ajout , .delete pour la supression a partir de la classe EntityManager .

domain : la ou on définit les classes précedentes ( la partie Objects)
