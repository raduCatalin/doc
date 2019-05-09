# Postgresql

```
/etc/postgresql/10/main/→ config file 
service postgresql 	→ savoir les service disponibles
```
---------------
Ajouter un « user »:
```bash
CREATE USER radu WITH PASSWORD 'test123';
```

Ajouter des attributs à un « user »:
```bash
ALTER USER radu WITH SUPERUSER;
```

Changement MDP pour un « user »:
```bash
ALTER USER nom_user WITH PASSWORD 'nouveau_mdp';
```

Creation d'une BDD (par défaut le propriétaire est « postgres ») :
```bash
CREATE DATABASE <nom_db>;	
```

Creation d'une BDD avec un propriétaire :
```bash
CREATE DATABASE <nom_db> OWNER user_name;	
```

Changement du propriétaire de la BDD:
```bash
GRANT ALL PRIVILEGES ON DATABASE <nom_db> TO <nom_admin_user>;
```




```
sudo su postgres	→ se connecter sur le user « postgres » 
psql		        → se connecter à une bdd (accéder a la console psql) par défaut c'est« postgres »
psql nom_database	→ se connecter à une bdd spécifique ; 
\q			→ quitter console psql (exit the psql client )
ctrl + d 		→ déconnexion 
sudo service postgresql stop → stop the server pslq 
```

<!-- Tableaux -->

| Commande | Description         |
| -------- | -------------- |
| \?    | liste des commandes disponibles |
| \list  | obtenir la liste des bases de données du serveur |
| \du  | obtenir les « rôle name » (users) et leurs « Attributs » |
| \d nom_table  | voir la structure d'une table |
| \d  | visualiser les tables de la bdd sur laquelle on est connecté |
| \dn  | obtenir la liste des schémas |
| \c nom_database  | se connecter à une base |
| select * from ma_table  | obtenir le contenu |

<!-- Lignes horizontales -->
___
