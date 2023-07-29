# Examen_BigData
## Nom & Prénom :HOUMAM AMINE
## Filière :II-BDCC

# Exercice 1: Manipuler le système de fichiers HDFS  
## Tapez les commandes pour répondre aux questions suivantes : 
1. Vérifiez la version Hadoop. 
2. Démarrez HDFS et vérifiez qu’il est en cours d’exécution. 

3. Créez deux nouveaux répertoires nommés /enset/bddc et /enset/glsid sur HDFS.

 4. Créez un nouveau fichier java.txt contenant 10 lignes et cpp.txt contenant 10 lignes sur  votre système local. 

5. Charger le fichier java.txt dans /enset/bddc et cpp.txt dans /enset/glsid sur HDFS.

6. Afficher le contenu du répertoire /enset/bddc et /enset/glsid.

7. Affichez le contenu du fichier java.txt qui se trouve dans HDFS.

8. Déterminez la taille du fichier cpp.txt qui se trouve dans HDFS. 

9. Déplacez le fichier cpp.txt vers /enset/bddc et vérifier si le fichier est bien déplacé.
    
10. Supprimez les fichiers java.txt et cpp.txt dans HDFS.
    
 ![1](https://github.com/HoumamAmine/Examen_BigData/assets/117035681/da5218b4-13a9-42eb-b5d7-0d49c659926d)
![2](https://github.com/HoumamAmine/Examen_BigData/assets/117035681/012ebcc5-043e-4c1e-8499-c08f0b6104c4)
![3](https://github.com/HoumamAmine/Examen_BigData/assets/117035681/f85b6a60-33b6-4d6f-b91b-e5e7951571ce)
![4](https://github.com/HoumamAmine/Examen_BigData/assets/117035681/f357626e-ce0b-4527-8639-7309caff5b05)
![5](https://github.com/HoumamAmine/Examen_BigData/assets/117035681/05ce1847-63d4-4cb5-b84d-458cb633763f)
![6](https://github.com/HoumamAmine/Examen_BigData/assets/117035681/414a50ab-c85b-46ae-9ee4-5edb555b73b8)
![7](https://github.com/HoumamAmine/Examen_BigData/assets/117035681/bb67de98-31ed-4ab7-a5df-a552af30341b)
![8](https://github.com/HoumamAmine/Examen_BigData/assets/117035681/db327241-f484-471b-bf72-53225f1b8d43)
![9](https://github.com/HoumamAmine/Examen_BigData/assets/117035681/98a6b7ca-c6dc-4cdb-a9a2-d6d640f39587)

    
# Exercice 2 : 
On souhaite traiter des données des vols d’une société aérienne au moyen d’une application Spark  d’une manière parallèle est distribuée. L’entreprise possède des données stockées dans une base de  données relationnel et des fichiers CSV. L’objectif est de traiter ces données en utilisant Spark SQL  et SPARK Structured Streaming à travers les APIs DataFrame et Dataset pour extraire des  informations utiles afin de prendre des décisions.
## Partie 1 : Spark SQL 
La société possède une application web pour gérer les réservations des vols, les données sont  stockées dans une base de données MYSQL nommée DB_AEROPORT, qui contient trois tables  VOLS et PASSAGERS et RESERVATIONS (Voir les figures 1, 2 et 3). 

![11](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/4e5e35cc-585e-4295-8e2d-0a4c26eba9d0)

Figure 1: Table Vols

![1](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/4137a86d-7eff-4a63-b7f0-01a4aa6e9568)
Figure 2: Table Passagers 

![2](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/57eefc6c-3d4c-4ae7-960b-ecd07744ad7d)
Figure 3: Table RESERVATIONS

Travail à faire : 
Vous créez la base de données et les tables et vous répondez aux questions suivantes :
1. Afficher pour charque vol, le nombre de passagers selon le format d’affichage suivant : ID_VOL |DATE DEPART| NOMBRE
![22](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/71c8ab86-89f9-484a-90a0-9dfbe4b43c38)

2. Afficher la liste des vols en cours selon le format d’affichage suivant : 
ID_VOL |DATE DEPART| DATE ARRIVE
![33](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/e7f97661-4c86-410d-ae66-3ecad039e038)

## Partie 2 : Importer et exporter des données avec SQOOP 
On souhaite à travers cet exercice d’importer et exporter des données entre une base de données sur  MySQL et HDFS. 
- On considère la base de données DB_AEROPORT dans MySQL contenant une table VOLS.
- Importez les données de la table VOLS dans HDFS en utilisant SQOOP.
  ### sqoop import --connect "jdbc:mysql://localhost:3306/db_aer" --username "root" --password "" --table vols --target-dir /vols
- Créez un fichier nommé vols.txt, ajouter 3 vols, puis charger le fichier dans HDFS puis  l’exportez vers la table VOLS avec scoop. 
   ### sqoop export --connect "jdbc:mysql://localhost:3306/db_aer" --username "root" --password "" --table vols --export-dir /enset/vols.txt   input-fields-terminated-by ',' --input-lines-terminated-by '\n'

## Partie 3: Traitement de données en streaming 
La société reçoit d’une manière contenu des fichiers CSV qui contient les incidents dans les avions,  les fichiers sont stockés directement sur HDFS.  
 Le format de données dans les fichiers csv et la suivante :  
 id, description, no_avion, date 
 Travail à faire : 
1. Afficher d’une manière continue l’avion ayant plus d’incidents.
![img1](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/7692739b-c20e-4c0a-a0a3-19e5c6673c62)
2. Afficher d’une manière continue les deux mois de l’année en cours où il a y avait moins d’incidents.
![img2](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/71994804-2e0f-4290-8b9a-6bdd22a21171)

