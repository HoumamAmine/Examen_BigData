# Examen_BigData
## Nom & Prénom :HOUMAM AMINE
## Filière :II-BDCC

# Exercice 1: Manipuler le système de fichiers HDFS  
## Tapez les commandes pour répondre aux questions suivantes : 
1. Vérifiez la version Hadoop. 
2. Démarrez HDFS et vérifiez qu’il est en cours d’exécution. 
![11](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/b0527b49-08db-4744-a390-fc82ea043f63)
![1](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/9968d092-74b3-40d9-8906-440d2c0da59f)
3. Créez deux nouveaux répertoires nommés /enset/bddc et /enset/glsid sur HDFS.
![22](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/35de3019-941f-40cb-8ce8-17083ba3d189)
![2](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/452cf486-fbd8-4126-ba48-c28464011cbd)
 4. Créez un nouveau fichier java.txt contenant 10 lignes et cpp.txt contenant 10 lignes sur  votre système local. 
![33](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/8511ae30-2453-4ba5-a7ba-3e81f6931ff7)
5. Charger le fichier java.txt dans /enset/bddc et cpp.txt dans /enset/glsid sur HDFS.
![44](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/6ab4a5dc-e4c2-4d69-8474-2f7f607f48c4)
![3](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/ac43fb79-423c-470f-9de5-9cc8d8447192)
![4](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/93276492-e2d8-4b1e-9799-435eb35b2fb3)
6. Afficher le contenu du répertoire /enset/bddc et /enset/glsid.
![55](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/794b76e1-aaa5-4284-909f-891ccc34d998)
![66](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/f4f1cbb8-c21a-4cbf-9cec-8cef174d04e6)
7. Affichez le contenu du fichier java.txt qui se trouve dans HDFS.
![77](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/105644d4-f657-471a-b636-282488a6b566)
8. Déterminez la taille du fichier cpp.txt qui se trouve dans HDFS. 
![88](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/1cffb7df-4b93-4948-8cac-e1c662ada873)
9. Déplacez le fichier cpp.txt vers /enset/bddc et vérifier si le fichier est bien déplacé.
![99](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/37577364-0553-434d-9554-6be9d51fe0dc)
10. Supprimez les fichiers java.txt et cpp.txt dans HDFS.
![100](https://github.com/Aboufariss-saad/Examen_BigData/assets/96661067/5a3489c2-341a-4cd5-b69d-073392796c66)
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

