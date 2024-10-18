## Mise en place du serveur vocal Mumble

[![https://www.mumble.info/](https://www.mumble.info/css/mumble.svg)](https://www.mumble.info)



Sommaire
<li><a href="#Présentation du projet et objectifs finaux">Présentation du projet et objectifs finaux</a></li>
<li><a href="#Introduction et mise en contexte">Introduction et mise en contexte</a></li>
<li><a href="#Membres du groupe de projet">Membres du groupe de projet</a></li>
<li><a href="#Choix techniques">Choix techniques</a></li>
<li><a href="#Difficultés rencontrées">Difficultés rencontrées : problèmes techniques rencontrés</a></li>
<li><a href="#Solutions trouvées">Solutions et alternatives trouvées</a></li>
<li><a href="#Améliorations possibles">Améliorations possibles : suggestions d’améliorations futures</a></li>



<h2 id="Présentation du projet et objectifs finaux">Présentation du projet et objectifs finaux</h2>

Le 7 Octobre, nous avons rencontré notre client, représentant de la société Ignetic. Lors de cet entretien, nous avons évoqué les besoins pour cette société. La demande du client est de mettre en place un serveur vocal privé, afin de pouvoir échanger avec ses collaborateurs et ses clients.

Le besoin est d'incrémenter 2 canaux publics: un pour chacune des équipes de travail, ainsi qu'un troisième privé, géré uniquement par l'administrateur. Sur ce canal l'administrateur devra avoir accès à chacune de ses connexions aux historiques de connexion, qui incluent la date et la durée des connexions. 

Cet historique devra pouvoir être accessible sur simple demande de l'administrateur.

La deadline pour la mise en place est le 18 Octobre.

<h2 id="Introduction et mise en contexte">Introduction et mise en contexte</h2>

Du fait des données sensibles manipulées par la société, le client requiert d'avoir son propre serveur vocal à l'instar de Google, mais sur un modèle privé et gratuit. L'avantage d'avoir son propre serveur est que la gestion est locale, les accès sont controlés uniquement par des personnes autorisées. Le logiciel retenu est Mumble.

<h2 id="Membres du groupe de projet">Membres du groupe de projet</h2>

Le projet Mumble est composé d'Anthony Vidal et Mindy Sétham qui partagent à deux les attributions de Scrum Master et de Project Owner. 

Pour rappel, voici les responsabilités et roles de ces deux postes: 

Le **Product Owner** veille à la satisfaction des demandes du client, c'est un chef de projet en mode agile, c'est à dire qu'il va chercher à changer et améliorer continuellement le projet jusqu'a satisfaction finale du client. Il fait la liaison entre les différentes parties qui composent le projet.  
Le **Scrum Master** lui veille, aux bonnes applications de méthode de travail. Il va superviser l'équipe de travail et l'aider grâce à ses enseignements et conseils.  
Pour la première semaine, Mindy prendra le rôle de Product Owner, et la semaine suivante, ce sera le rôle d'Anthony.

<h2 id="Choix techniques">Choix techniques</h2>

Dans le cadre de la sélection du serveur et afin de répondre aux exigences du client, nous avons examiné deux types de systèmes d'exploitation : Debian et Windows.

Nous présentons ci-après les avantages et les inconvénients de chacun.

|  OS SERVEUR  |  Avantages  |  Inconvénients  |  
|---  |:-:  |:-:  |
|  DEBIAN  | **Stabilité :** système très stable et fiable, idéal pour des serveurs à long terme</br> **Performances :** meilleur performances que Windows</br> **Contrôle :** contrôle total du serveur (optimisation, gestion des permissions…)</br> **Sécurité :** sécurité excellente et mise à jour souvent rapide et faciles</br> **Coût :** Gratuit et open-source | **Connaissance de Linux :** ligne de commande, gestions de services etc.. |  
|  WINDOWS |  **Facilité d’installation :** utilise un installateurs graphiques, pas besoin de ligne de commande</br> **Compatibilité :** sous windows le logicielle peut être compatible avec d’autres applications (jeux, logiciel de gestion etc..)</br>**Interface graphique :** gestion du serveur plus facile pour un utilisateur non techniques   |  **Performance :** Windows et plus gourmand en ressources qu’un serveur Linux</br> **Coût :** nécessite l’achat d’une licence Windows</br> **Optimisation :** moins optimisé pour les services de fond (mumble est un service de fond)</br> **Sécurité :** moins sûr qu’un serveur Linux pour un hébergement à long terme  |
  
En prenant en considération les avantages et les inconvénients, tout en respectant les exigences du client, nous avons décidé de choisir Debian comme système d'exploitation pour notre serveur. En effet, malgré un inconvénient majeur, Debian présente tous les atouts nécessaires à la réussite du projet.  

En utilisant Mumble comme application et Debian comme système d'exploitation serveur pour répondre à la demande du client, nous avons constaté que peu de prérequis étaient nécessaires. Vous trouverez ces prérequis détaillés dans la documentation d'administration (INSTALL.md).  


<h2 id="Difficultés rencontrées">Difficultés rencontrées : problèmes techniques rencontrés</h2>

Sur ce projet, nous avons rencontré des difficultés, principalement liées à la compréhension globale des tâches à effectuer. En effet, bien que nous ayons compris qu'il s'agissait de livrer de la documentation, nous souhaitions absolument tester les installations pour être sûrs de ce dont nous parlions. Cependant, cela nous a fait perdre beaucoup de temps en raison de problèmes techniques, notamment l'installation de machines virtuelles avec une connexion.



<h2 id="Solutions trouvées">Solutions et alternatives trouvées</h2>




<h2 id="Améliorations possibles">Améliorations possibles : suggestions d’améliorations futures</h2>

Avec du temps en plus sur ce projet, nous aurions pu vous proposer la mise en place d'une journalisation et d'une surveillance des sessions.

1) Comment configurer les journaux (logs).
2) Quels outils de surveillance utiliser.
3) Comment automatiser la surveillance.
4) Établir des vérifications régulières des journaux.






