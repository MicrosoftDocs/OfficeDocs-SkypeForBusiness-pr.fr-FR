---
title: "Dépl. d’un port non standard et d’un alias SQL Server dans Lync Server 2013"
TOCtitle: "Dépl. d’un port non standard et d’un alias SQL Server dans Lync Server 2013"
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62633775
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement d’un port non standard et d’un alias SQL Server dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Microsoft Lync Server 2013 prend en charge l’utilisation d’un port non standard et d’un alias dans SQL Server. L’utilisation d’un port non standard et d’un alias SQL Servet permet de renforcer la sécurité et offre un environnement plus flexible pour le déploiement Lync. Ces étapes ne constituent qu’une partie de la sécurisation appropriée de votre environnement Lync Server 2013. D’autres étapes sont nécessaires afin de réduire la surface d’attaque d’une implémentation Lync Server 2013.

L’article ci-dessous décrit les étapes nécessaires à la configuration d’un port non standard et d’un alias SQL Server dans Lync Server 2013.

## Déploiement d’un port non standard et d’un alias SQL Server dans Lync Server 2013

Lync Server 2013Générateur de topologie prend en charge un alias SQL Server comme nom de domaine complet (FQDN) au lieu du nom de domaine complet SQL Server réel lors de la configuration de Lync Server 2013. Il est ainsi possible de masquer le nom de domaine complet SQL Server pour le protéger d’une attaque malveillante. Enfin, l’utilisation d’un port non standard masque le port réel pour le protéger d’une attaque visant la base de données sur le port standard 1433, comme indiqué sur la figure suivante.

![Un pirate ne connaît pas le numéro de port à attaquer.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Un pirate ne connaît pas le numéro de port à attaquer.")

Pour parvenir à déterminer le port utilisé par Lync Server 2013 pour communiquer avec SQL Server, l’intrus devrait analyser tous les ports pour obtenir les informations du port. L’analyse d’un port par une personne malveillante augmente les chances de détection et de blocage de l’instruction par la sécurité. Outre l’amélioration de la sécurité résultant de l’utilisation d’un port non standard, vous pouvez également recourir à un alias SQL Server pour simplifier le déploiement. Cette considération est précieuse afin de réduire les changements de configuration dans les situations où il est nécessaire de modifier le nom d’un serveur SQL.

> [!NOTE]  
> SQL Server prend en charge deux méthodes de tolérance de pannes (Clustering de basculement et Miroir). Ces trois méthodes de tolérance de pannes SQL Server sont prises en charge à l’aide d'un port non standard et d’un alias SQL Server avec Lync Server 2013.

Lorsque vous configurez la connectivité de la base de données SQL Server à partir de Générateur de topologie ou avec l’applet de commande Install-CsDatabase, il n’est pas possible de définir explicitement un numéro de port non standard SQL Server et de l’associer à une instance SQL. Pour définir un port non standard, vous devez utiliser les utilitaires SQL Server et Windows Server.

Pour configurer un port non standard et un alias SQL Server avec Lync Server 2013, vous devez effectuer trois étapes principales, à savoir :

  - Vérifiez que Lync Server 2013 contient les dernières mises à jour appliquées.

  - Configurez le port non standard et l’alias SQL Server.

  - Configurez Lync Server 2013 avec l’alias SQL Server à l’aide de Générateur de topologie.

  - Publiez la topologie et vérifiez la base de données.

## Vérifiez que Lync Server 2013 contient les dernières mises à jour appliquées

Il est important de s’assurer que Lync Server 2013 est à jour. Pour rechercher les dernières mises à jour et les informations concernant leur application, reportez-vous à la rubrique [Mises à jour pour Lync Server 2013](http://support.microsoft.com/kb/2809243).

## Configuration du port non standard et de l’alias SQL Server

Le port non standard et l’alias SQL Server doivent être configurés dans l’instance de la base de données avant de pouvoir être référencé à partir de Lync Server 2013Générateur de topologie. Pour configurer un port non standard et un alias SQL Server, vous devez effectuer trois étapes principales, à savoir :

  - Modifiez les valeurs par défaut du protocole TCP/IP.

  - Créez et configurez un alias SQL Server.

  - Créez un enregistrement de ressource DNS et nom canonique (CNAME).

**Modification des valeurs par défaut du protocole TCP/IP**

1.  Cliquez sur **Démarrer**, puis sélectionnez **Gestionnaire de configuration SQL Server**, comme indiqué sur la figure suivante.
    
    ![Icône SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icône SQL Server Management Studio")

2.  Dans le volet de navigation, développez **Instance SQL Server**, puis **Configuration du réseau SQL Server** et **Protocoles pour « nom de l’instance »**, comme indiqué sur la figure suivante.
    
    ![Naviguer dans les propriétés TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Naviguer dans les propriétés TCP/IP")

3.  Dans le volet de droite, cliquez sur **TCP/IP** avec le bouton droit de la souris et cliquez sur **Propriétés**. La boîte de dialogue Propriétés TCP/IP s’affiche.

4.  Cliquez sur l’onglet **Adresses IP**. Cet onglet affiche toutes les adresses IP actives sur le serveur. Elles sont au format IP1, IP2 et IPAll, comme indiqué sur la figure suivante.
    
    ![Ouvrir les propriétés TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Ouvrir les propriétés TCP/IP.")

5.  Désactivez le champ **Ports TCP dynamiques** pour toutes les adresses IP. Si le champ contient un caractère zéro, le serveur SQL Server écoute des ports dynamiques. Vérifiez que ces champs sont désactivés et ne contiennent pas de zéro.

6.  Pour l’adresse IP utilisée par Lync Server afin de se connecter à la base de données, vérifiez que **Activé** a la valeur **Oui**, comme indiqué sur la figure suivante.
    
    ![Définir Activé sur Oui pour l’adresse IP correcte.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Définir Activé sur Oui pour l’adresse IP correcte.")

7.  Dans la section **IPAll** dans la partie inférieure de la boîte de dialogue, saisissez le port de votre choix dans le champ **Port TCP**, comme indiqué sur la figure suivante. Dans cet exemple, nous utilisons le port 50062, mais il est possible d’utiliser un port compris entre 49 152 et 65 535. Il s’agit des ports affectés à un usage dynamique et privé afin d’éviter tout usage conflictuel avec les autres ports utilisés lors du déploiement Lync Server 2013.
    
    ![Définir le port dans la section IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Définir le port dans la section IPAll.")

8.  Cliquez sur **OK** pour quitter la boîte de dialogue Propriétés TCP/IP.

9.  Redémarrez l’instance de SQL Server en sélectionnant **Services SQL Server** dans le volet de gauche du Gestionnaire de configuration SQL Server. Puis cliquez sur **« nom de l’instance » SQL Server** avec le bouton droit de la souris dans le volet de droite, puis cliquez sur **Redémarrer**, comme indiqué sur la figure suivante.
    
    ![Réinitialiser le service SQL Server service pour l’instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Réinitialiser le service SQL Server service pour l’instance.")

> [!IMPORTANT]  
> Vérifiez que vos paramètres de pare-feu sont à jour pour prendre en compte le nouveau port SQL Server.

**Création et configuration d’un alias SQL Server**

1.  Cliquez sur **Démarrer**, puis sur **Gestionnaire de configuration SQL Server**, comme indiqué sur la figure suivante.
    
    ![Icône SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icône SQL Server Management Studio")

2.  Dans le volet de gauche, développez **Instance SQL Server**, puis **Configuration de SQL Native Client « version »**, puis **Alias**, comme indiqué sur la figure suivante.
    
    ![Alias dans le Gestionnaire de configuration SQL Server](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias dans le Gestionnaire de configuration SQL Server")

3.  Cliquez sur **Alias** avec le bouton droit de la souris, puis cliquez sur **Nouvel alias…**.

4.  Renseignez les champs **Nom de l’alias**, **Numéro de port**, **Protocole** et **Serveur**, comme indiqué sur la figure suivante.
    
    ![Création d’un alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Création d’un alias")
    
    > [!CAUTION]  
    > Veillez à saisir le port non standard utilisé lors de l’étape précédente, car il s’agit du port écouté par SQL Server. Si un alias configuré se connecte à l’instance ou au nom de domaine complet incorrect, désactivez puis réactivez le protocole réseau associé. Cette opération efface les informations de connexion dans la mémoire cache et permet au client de se connecter correctement.

**Création d’un enregistrement de ressource CNAME DNS**

1.  Connectez-vous à l’ordinateur qui gère le DNS.

2.  Cliquez sur **Démarrer**, puis sur **Gestionnaire de serveur**, comme indiqué sur la figure suivante.
    
    ![Ouverture du Gestionnaire de serveur](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Ouverture du Gestionnaire de serveur")

3.  Cliquez sur la liste déroulante **Outils**, puis sur **DNS**, comme indiqué sur la figure suivante.
    
    ![Ouverture du DNS à partir du gestionnaire de serveur](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Ouverture du DNS à partir du gestionnaire de serveur")

4.  Dans le volet de gauche, développez le nœud du nom de serveur, puis le nœud Zones de recherche directes et sélectionnez le domaine de votre choix.

5.  Cliquez sur le domaine avec le bouton droit de la souris et sélectionnez **Nouvel alias (CNAME)…**, comme indiqué sur la figure suivante.
    
    ![Sélection de l’option permettant de créer un alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Sélection de l’option permettant de créer un alias CNAME")

6.  Renseignez les champs **Nom de l’alias** et **Nom de domaine complet du serveur SQL Server**, comme indiqué sur la figure suivante.
    
    ![Renseignement de la boîte de dialogue Nouvelle alias CNAME](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Renseignement de la boîte de dialogue Nouvelle alias CNAME")

7.  Cliquez sur **OK** pour enregistrer le CNAME et l’afficher dans le Gestionnaire DNS.

## Validation de la connectivité de la base de données

Vous pouvez procéder de différentes façons pour vérifier son bon fonctionnement. Vérifiez que la base de données SQL Server écoute le port spécifié à l’aide de l’alias. Les commandes **netstat** et **telnet** permettent d’effectuer une vérification rapide.

> [!NOTE]  
> Le client Telnet est une fonctionnalité intégrée à Windows Server, mais qu’il faut installer. Vous pouvez installer une fonctionnalité Windows Server en ouvrant le Gestionnaire de serveur et en sélectionnant la fonctionnalité Ajouter des rôles dans le menu Gérer.

**Utilisation des commandes netstat et telnet pour vérifier la connectivité de la base de données**

1.  Cliquez sur **Démarrer** et tapez **cmd** pour afficher une invite de commandes.

2.  Tapez **netstat -a -f** et confirmez que SQL Server s’exécute avec le port correct, comme indiqué sur la figure suivante.
    
    ![Utilisation de netstat pour vérifier le port](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Utilisation de netstat pour vérifier le port")

3.  Tapez **telnet « nom d’alias» « port »** pour confirmer la connexion à l’instance SQL Server. Si la connexion est établie, telnet se connecte et aucune erreur ne doit s’afficher. Cela indique que l’instance SQL Server écoute le port approprié avec l’alias correct. En cas de problème de connexion à la base de données SQL Server, telnet affiche une erreur indiquant que la connexion ne peut pas être établie. Maintenant que vous venez de vérifier la connectivité de la base de données sur le serveur de base de données, vous pouvez répéter cette opération à partir de Lync Server (sur le réseau) en vous assurant qu’aucun pare-feu ne bloque l’accès.

## Conclusion

Une fois l’alias SQL Server configuré, il vous permet de créer une topologie Lync Server 2013 dans l’outil Générateur de topologie. Pour plus d’informations sur les topologies, reportez-vous à la rubrique [Définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

## Voir aussi

#### Concepts

[Microsoft Lync Server 2013](microsoft-lync-server-2013.md)  

#### Autres ressources

[Planification de la sécurité dans Lync Server 2013](lync-server-2013-planning-for-security.md)  
[Définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md)  
[Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md)

