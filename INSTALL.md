# Guide d'installion Mumble

Sommaire
<li><a href="#Prérequis techniques">Prérequis techniques</a></li>
<li><a href="#Installation et configuration">Installation et configuration</a></li>
<li><a href="#F.A.Q">F.A.Q</a></li>

<h2 id="Prérequis techniques">Prérequis techniques</h2>  


| Serveur           | Debian 12        |  
|-------------------|------------------|  
| Nom               | SRVLX01          |  
| Compte            | root             |  
| Mot de passe      | Azerty1*         |  
| Adresse IP fixe   | 172.16.10.10/24  |  


<h2 id="Installation et configuration">Installation et configuration</h2>  

⚠️ **Attention :** *Toutes les commandes sont à exécuter en tant que root !*  
##### ( Pour passer root voir la <a href="#F.A.Q">F.A.Q</a> )  

Pour l'installation du serveur mumble voici les étapes à suivre :  

### _1 ) Installation :_  

Avant l'installation, il est conseillé de mettre à jour votre système :

**root@SRVLX01:~#** apt-get update && apt-get upgrade

Pour installer Murmur, c'est extrêmement facile puisque le paquet est présent dans les dépôts officiels de Debian. Vous n'avez qu'à procéder à un simple apt :

**root@SRVLX01:~#** apt-get install mumble-server

Répondez oui lorsque le shell vous demande confirmation pour l'installation.  

Mumble est installé !

Mais avant de le configuré, pensez au pare-feu.
Si votre serveur est équipé d'un pare-feu, il faut autoriser le trafic Mumble à travers celui-ci. Voici donc les commandes à saisir pour le pare-feu iptables (pensez à adapter le port si vous n'utilisez pas celui par défaut) :

**root@SRVLX01:~#** iptables -I INPUT -p tcp --dport 64738 -j ACCEPT  
**root@SRVLX01:~#** iptables -I INPUT -p udp --dport 64738 -j ACCEPT  

### _2 ) Configuration initiale :_ 

Après l’installation, exécutez la configuration initiale :

**root@SRVLX01:~#** dpkg-reconfigure mumble-server

La première question posée est de savoir si vous souhaitez que le serveur s'exécute au démarrage. Sélectionnez cette option, **Yes** sauf si vous préférez démarrer Mumble manuellement après un redémarrage du serveur.

![install_img_001](https://github.com/WildCodeSchool/TSSR-BDX-0924-P1-G2/blob/main/Img_SRC/SRVLX/install_img_001.jpg?raw=true)

Mumble vous demandera alors si vous souhaitez réduire la latence en définissant une priorité CPU et réseau plus élevée.

![install_img_002](https://github.com/WildCodeSchool/TSSR-BDX-0924-P1-G2/blob/main/Img_SRC/SRVLX/install_img_002.jpg?raw=true)

Si vous souhaitez que Murmur ait la priorité sur les autres applications sur le serveur, vous pouvez répondre Oui à cette question.

Ensuite, il vous sera demandé de définir un mot de passe SuperUser . Murmur dispose d'un compte SuperUser qui vous permet de modifier les paramètres du serveur à partir du client Mumble. Vous pouvez le définir avec le mot de passe de votre choix.

![install_img_003](https://github.com/WildCodeSchool/TSSR-BDX-0924-P1-G2/blob/main/Img_SRC/SRVLX/install_img_003.jpg?raw=true)

Vous disposez désormais d'un serveur Mumble fonctionnel. 

Il est temps de le configurer davantage.

### _3 ) Configuration des paramètres du serveur:_ 









<h2 id="F.A.Q">F.A.Q</h2>  
