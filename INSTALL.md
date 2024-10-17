# Guide d'installation Mumble

Sommaire
<li><a href="#Prérequis techniques serveur">Prérequis techniques serveur</a></li>
<li><a href="#Installation et configuration">Installation et configuration</a></li>
<li><a href="#Prérequis techniques client">Prérequis techniques client</a></li>
<li><a href="#F.A.Q">F.A.Q</a></li>

<h2 id="Prérequis techniques serveur">Prérequis techniques serveur</h2>  


| Serveur           | Debian 12        |  
|-------------------|------------------|  
| Nom               | SRVLX01          |  
| Compte            | root             |  
| Mot de passe      | Azerty1*         |  
| Adresse IP fixe   | 172.16.10.10/24  |  



<h2 id="Installation et configuration">Installation et configuration</h2>  

⚠️ **Attention :** _Toutes les commandes doivent être exécuteées en tant que root !_  
##### ( Pour passer root, voir la <a href="#F.A.Q">F.A.Q</a> )  

Pour l'installation du serveur Mumble, voici les étapes à suivre :  

### _1 ) Installation :_  

Avant l'installation, il est conseillé de mettre à jour votre système :

`root@SRVLX01:~# apt-get update && apt-get upgrade`

Pour installer Mumble, c'est extrêmement facile puisque le paquet est présent dans les dépôts officiels de Debian. Ilsuffit d'exécuter une simple commande apt :

`root@SRVLX01:~# apt-get install mumble-server`

Répondez "oui" lorsque le shell vous demande de confirmer l'installation.  

Mumble est maintenant installé !

Avant de le configurer, pensez à vérifier votre pare-feu.
Si votre serveur est équipé d'un pare-feu, il faut autoriser le trafic Mumble. Voici les commandes pour le pare-feu iptables (adaptez le port si nécessaire) :

`root@SRVLX01:~# iptables -I INPUT -p tcp --dport 64738 -j ACCEPT`  
`root@SRVLX01:~# iptables -I INPUT -p udp --dport 64738 -j ACCEPT`  

### _2 ) Configuration initiale :_ 

Après l’installation, lancez la configuration initiale avec:

`root@SRVLX01:~# dpkg-reconfigure mumble-server`  

La première question posée est de savoir si vous souhaitez que le serveur s'exécute au démarrage. Sélectionnez cette option, **Oui** sauf si vous préférez démarrer Mumble manuellement après un redémarrage du serveur.

##### Vous pouvez également modifier ce parametre (voir la <a href="#F.A.Q">F.A.Q</a>)  

![install_img_001](https://github.com/WildCodeSchool/TSSR-BDX-0924-P1-G2/blob/main/Img_SRC/SRVLX/install_img_001.jpg?raw=true)

Mumble vous demandera alors si vous souhaitez réduire la latence en définissant une priorité CPU et réseau plus élevée.

![install_img_002](https://github.com/WildCodeSchool/TSSR-BDX-0924-P1-G2/blob/main/Img_SRC/SRVLX/install_img_002.jpg?raw=true)

Si vous souhaitez que Mumble ait la priorité sur les autres applications sur le serveur, vous pouvez répondre Oui à cette question.

Ensuite, il vous sera demandé de définir un mot de passe SuperUser . Mumble dispose d'un compte SuperUser qui vous permet de modifier les paramètres du serveur à partir du client Mumble. Vous pouvez le définir avec le mot de passe de votre choix.

![install_img_003](https://github.com/WildCodeSchool/TSSR-BDX-0924-P1-G2/blob/main/Img_SRC/SRVLX/install_img_003.jpg?raw=true)

Vous disposez désormais d'un serveur Mumble fonctionnel. 

Il est temps de le configurer davantage.

### _3 ) Configuration des paramètres du serveur:_ 

Passons à la configuration avancée en éditant le fichier de configuration Murmur situé à l'adresse suivante : `/etc/mumble-server.ini`.  

Ouvrez le fichier avec votre éditeur de texte préféré. Ici, nous utiliserons **vi**.

`root@SRVLX01:~# vi /etc/mumble-server.ini`  

Vous pouvez maintenant personnaliser les paramètres du serveur.

Pour afficher un message de bienvenue :

`_welcometext_ = "Bienvenue sur le Mumble de la société Ignetic."`

Choix du port (par défaut 64738) :

`_port_ = 64738`

Définir l'adresse IP spécifique :

`_host_ = 172.16.10.10`

Définir le mot de passe d'accès au serveur (exemple: Azerty1*) :

`_serverpassword_ =Azerty1*` 

Nombre maximum d'utilisateurs simultanés (nombre de slots) :

`_users_=25`

![install_img_004](https://github.com/WildCodeSchool/TSSR-BDX-0924-P1-G2/blob/main/Img_SRC/SRVLX/install_img_004.jpg?raw=true)

##### Vous trouverez d'autre paramètres dans la <a href="#F.A.Q">F.A.Q</a>

### _4) Ajouter plusieurs salons:_

Vous pouvez créer un salon à l'intérieur d'un autre salon existant. Faites un clic droit sur le salon parent et cliquez sur **Ajouter**.

![install_img_005](https://github.com/WildCodeSchool/TSSR-BDX-0924-P1-G2/blob/main/Img_SRC/SRVLX/install_img_005.jpg?raw=true)

Vous pouvez également ajouter un mot de passe à un salon.

![install_img_006](https://github.com/WildCodeSchool/TSSR-BDX-0924-P1-G2/blob/main/Img_SRC/SRVLX/install_img_006.jpg?raw=true)



<h2 id="Prérequis techniques client">Prérequis techniques client</h2> 


| Client            | Ubuntu 24.04     |  
|-------------------|------------------|  
| Nom               | CLILIN01         |  
| Compte            | wilder           |  
| Mot de passe      | Azerty1*         |  
| Adresse IP fixe   | 172.16.10.20/24  | 

| Client            | Windows 10       |  
|-------------------|------------------|  
| Nom               | CLIWIN01         |  
| Compte            | wilder           |  
| Mot de passe      | Azerty1*         |  
| Adresse IP fixe   | 172.16.10.30/24  | 


<h2 id="F.A.Q">F.A.Q</h2>  

### _1) Comment passer root ?_

Dans le terminal, exécutez la commande suivante :  
`$ su root`  
`Mot de passe : (inscrire le mot de passe de root)`  

### _2) Désactiver le démarrage du serveur au démarrage_

Pour désactiver le démarrage automatique du serveur, utilisez la commande suivante :

`root@SRVLX01:~# systemctl disable mumble-server`


### _3) Autres paramètres de modification :_

Dans le fichier mumble-server.ini :

| Paramètre         | Description                                                                                              |
|-------------------|----------------------------------------------------------------------------------------------------------|
| `autobanAttempts`  | Définissez le nombre de fois qu'une personne peut ne pas parvenir à se connecter au serveur dans un délai donné. |
| `autobanTimeframe` | Définissez le délai donné pour les tentatives de connexion au serveur.                                    |
| `autobanTime`      | Définissez la durée de l'interdiction de connexion.                                                       |
| `logfile`          | Définissez l’emplacement du fichier journal, si vous souhaitez qu’il réside dans un emplacement différent. |
| `welcometext`      | Définissez le texte qui s'affiche dans le journal de discussion textuelle lorsque vous vous connectez.     |
| `port`             | Définissez le port auquel vous souhaitez vous connecter et auquel vos utilisateurs souhaitent se connecter.|
| `serverpassword`   | Définissez un mot de passe que les utilisateurs devront utiliser pour se connecter. Il doit être différent du mot de passe SuperUser. |
| `bandwidth`        | Définissez la bande passante maximale (en bits par seconde) que chaque utilisateur peut utiliser.          |
| `users`            | Définissez le nombre maximal d'utilisateurs pouvant se connecter simultanément au serveur.                 |

