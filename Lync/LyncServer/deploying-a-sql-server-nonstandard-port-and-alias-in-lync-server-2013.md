---
title: Déploiement d’un port et d’un alias SQL Server non standard dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1134422c8c55a60858a9fd8c28be2e6ff159d48
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>Déploiement d’un port et d’un alias SQL Server non standard dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-09-16_

Microsoft Lync Server 2013 prend en charge l’utilisation d’un alias et d’un port non standard dans SQL Server. L’utilisation d’un port SQL Server non standard et d’un alias augmente la sécurité et crée un environnement plus flexible pour le déploiement Lync. Ces étapes ne constituent qu’une seule étape de sécurisation de votre environnement Lync Server 2013. Des étapes supplémentaires doivent être prises pour réduire la surface d’attaque d’une implémentation Lync Server 2013.

L’article suivant décrit les étapes à suivre pour configurer un alias et un port non standard SQL Server dans Lync Server 2013.

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>Déploiement d’un port et d’un alias SQL Server non standard dans Lync Server 2013

Le générateur de topologies Lync Server 2013 prend en charge l’utilisation d’un alias SQL Server comme nom de domaine complet (FQDN) au lieu du nom de domaine complet SQL Server réel lors de la configuration de Lync Server 2013. Cela permet de masquer le nom de domaine complet SQL Server réel à un utilisateur malveillant. En outre, l’utilisation d’un port non standard masque le port réel de tout agresseur tentant d’attaquer la base de données sur le port 1433 standard, comme illustré dans la figure suivante.

![Un pirate ne connaît pas le numéro de port à attaquer.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Un pirate ne connaît pas le numéro de port à attaquer.")

Pour réussir à déterminer le port que Lync Server 2013 utilise pour communiquer avec SQL Server, l’agresseur doit analyser tous les ports pour obtenir les informations sur les ports. Une analyse des ports par un agresseur augmente les risques que la sécurité peut détecter et arrêter l’instruction. En plus d’ajouter une sécurité accrue avec un port non standard, vous pouvez également utiliser un alias SQL Server pour assurer la flexibilité du déploiement. Cela est utile afin de réduire les modifications de configuration dans les situations où un changement de nom SQL Server est requis.

<div>


> [!NOTE]  
> SQL Server fournit deux méthodes de tolérance de panne (clustering et mise en miroir de basculement). Les deux méthodes de tolérance de panne SQL Server sont prises en charge à l’aide d’un alias et d’un port non standard SQL Server avec Lync Server 2013. Si le serveur principal SQL Server utilisé par le pool est dans une configuration mise en miroir, le service SQL Browser sur les serveurs principaux SQL Server doit être en cours d’exécution pour que les serveurs frontaux se connectent à la base de données mise en miroir lorsque les bases de données sont basculées vers le SQL en miroir. Serveurs.



</div>

Lors de la configuration de la connectivité de base de données SQL Server dans le générateur de topologie, ou lors de l’utilisation de la cmdlet install-applet csdatabase, il n’est pas possible de définir explicitement un numéro de port non standard SQL Server et de l’associer à une instance SQL. Pour définir un port non standard, vous devez utiliser SQL Server et les utilitaires Windows Server.

Pour configurer un alias et un port non standard SQL Server à utiliser avec Lync Server 2013, vous devez effectuer les trois étapes principales. Voici la procédure à suivre :

  - Vérifiez que les mises à jour les plus récentes sont appliquées à Lync Server 2013.

  - Configurez le port et l’alias non standard de SQL Server.

  - Configurez Lync Server 2013 avec l’alias SQL Server à l’aide du générateur de topologie.

  - Publiez la topologie et vérifiez la base de données.

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>Vérifiez que les mises à jour les plus récentes sont appliquées à Lync Server 2013

Il est important de tenir à jour Lync Server 2013. Pour vérifier les mises à jour les plus récentes et obtenir des informations sur leur application, voir [mises à jour pour Lync Server 2013](https://support.microsoft.com/kb/2809243).

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>Configurer le port et l’alias non standard de SQL Server

Le port et l’alias SQL Server non standard doivent être configurés sur l’instance de base de données pour pouvoir être référencés à partir du générateur de topologies Lync Server 2013. Pour configurer un alias et un port non standard SQL Server, vous devez effectuer les trois étapes principales. Ces étapes sont les suivantes :

  - Modifier les valeurs par défaut du protocole TCP/IP.

  - Créez et configurez un alias SQL Server.

  - Créez un enregistrement de ressource de nom canonique DNS (Domain Name System).

**Modifier les valeurs par défaut du protocole TCP/IP**

1.  Sélectionnez **Démarrer**, puis **Gestionnaire de configuration SQL Server**, comme illustré dans la figure suivante.
    
    ![Icône SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icône SQL Server Management Studio")

2.  Dans le volet de navigation, développez l' **instance SQL Server**, développez **configuration du réseau SQL Server**, puis choisissez **protocoles comme \<\>nom d’instance**, comme illustré dans la figure suivante.
    
    ![Accéder aux propriétés TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Accéder aux propriétés TCP/IP")

3.  Dans le volet droit, cliquez avec le bouton droit sur **TCP/IP**, puis sélectionnez **Propriétés**. La boîte de dialogue Propriétés TCP/IP s’affiche.

4.  Sélectionnez l’onglet **adresses IP** . L’onglet adresses IP affiche toutes les adresses IP actives sur le serveur. Il s’agit du format IP1, IP2, jusqu’à IPAll, comme illustré dans la figure suivante.
    
    ![Ouvrez les propriétés TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Ouvrez les propriétés TCP/IP.")

5.  Effacez le champ **ports dynamiques TCP** pour toutes les adresses IP. Si le champ contient un caractère zéro, cela signifie que SQL Server est à l’écoute sur les ports dynamiques. Assurez-vous que ces champs sont effacés et qu’ils ne contiennent pas de zéro.

6.  Pour l’adresse IP que Lync Server utilisera pour se connecter à la base de données, assurez-vous que l' **option activé** est définie sur **Oui**, comme illustré dans la figure suivante.
    
    ![Définissez l’option activé sur Oui pour l’adresse IP correcte.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Définissez l’option activé sur Oui pour l’adresse IP correcte.")

7.  Dans la section **IPAll** en bas de la boîte de dialogue, entrez le port souhaité dans le champ **port TCP** , comme illustré dans la figure suivante. Dans cet exemple, nous utilisons le port 50062, mais vous pouvez utiliser n’importe quel port entre 49152 et 65535. Il s’agit des ports affectés à une utilisation dynamique et privée, ce qui garantit que vous ne serez pas en conflit avec les autres ports utilisés dans le déploiement Lync Server 2013.
    
    ![Définir le port dans la section IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Définir le port dans la section IPAll.")

8.  Choisissez **OK** pour quitter la boîte de dialogue Propriétés TCP/IP.

9.  Redémarrez l’instance SQL Server en sélectionnant **services SQL Server** dans le volet gauche du gestionnaire de configuration SQL Server. Ensuite, cliquez avec le bouton droit sur **nom \<\> de l’instance SQL Server** dans le volet droit, puis sélectionnez **redémarrer**, comme illustré dans la figure suivante.
    
    ![Réinitialisez le service SQL Server pour l’instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Réinitialisez le service SQL Server pour l’instance.")

<div>


> [!IMPORTANT]  
> Veillez à mettre à jour vos paramètres de pare-feu afin de prendre en compte le nouveau port SQL Server.



</div>

**Créer et configurer un alias SQL Server**

1.  Sélectionnez **Démarrer**, puis **Gestionnaire de configuration SQL Server**, comme illustré dans la figure suivante.
    
    ![Icône SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icône SQL Server Management Studio")

2.  Dans le volet de gauche, choisissez l' **instance SQL Server**, puis développez **configuration de la \<version\> du client natif SQL**, puis sélectionnez **alias**, comme illustré dans la figure suivante.
    
    ![Alias dans le gestionnaire de configuration SQL Server.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias dans le gestionnaire de configuration SQL Server.")

3.  Cliquez avec le bouton droit sur **alias**et sélectionnez **Nouvel alias..**..

4.  Entrez le **nom**de l’alias, le **numéro de port**, le **protocole**et le **serveur**, comme illustré dans la figure suivante.
    
    ![Création d’un alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Création d’un alias")
    
    <div>
    

    > [!CAUTION]  
    > Assurez-vous d’entrer le port non standard que vous avez utilisé à l’étape précédente, car il s’agit du port d’écoute de SQL Server. Si un alias configuré se connecte à un nom de domaine complet ou à une instance incorrects de SQL Server, désactivez puis réactivez le protocole réseau associé. Cette opération efface toutes les informations de connexion mises en cache et autorise le client à se connecter correctement.

    
    </div>

**Créer un enregistrement de ressource CNAMe DNS**

1.  Connectez-vous à l’ordinateur qui gère DNS.

2.  Sélectionnez **Démarrer**, puis **Gestionnaire de serveur**, comme illustré dans la figure suivante.
    
    ![Ouverture du gestionnaire de serveur](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Ouverture du gestionnaire de serveur")

3.  Sélectionnez la liste déroulante **Outils** , puis **DNS**, comme illustré dans la figure suivante.
    
    ![Ouverture du DNS à partir du gestionnaire de serveur.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Ouverture du DNS à partir du gestionnaire de serveur.")

4.  Dans le volet gauche, développez le nœud nom du serveur, développez le nœud zones de recherche directes, puis choisissez le domaine approprié.

5.  Cliquez avec le bouton droit sur le domaine, puis sélectionnez **Nouvel alias (CNAME)...**, comme illustré dans la figure suivante.
    
    ![Sélection de l’option permettant de créer un nouvel alias CNAMe](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Sélection de l’option permettant de créer un nouvel alias CNAMe")

6.  Entrez le **nom d’alias** et le nom **de domaine complet (FQDN) de SQL Server**, comme illustré dans la figure suivante.
    
    ![Renseignement de la boîte de dialogue nouveau pseudonyme CNAMe.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Renseignement de la boîte de dialogue nouveau pseudonyme CNAMe.")

7.  Choisissez **OK** pour enregistrer le CNAME et l’afficher dans le Gestionnaire DNS.

</div>

<div>

## <a name="validate-database-connectivity"></a>Valider la connectivité de la base de données

Il existe plusieurs façons de s’assurer qu’il fonctionne. Vous voulez vous assurer que la base de données SQL Server écoute sur le port spécifié à l’aide de l’alias. Une vérification rapide peut être effectuée à l’aide des commandes **netstat** et **Telnet** .

<div>


> [!NOTE]  
> Le client Telnet est une fonctionnalité qui est fournie avec Windows Server, mais qui doit être installée. Une fonctionnalité Windows Server peut être installée en ouvrant le gestionnaire de serveur et en sélectionnant Ajouter des rôles et des fonctionnalités dans le menu gérer.



</div>

**Utiliser netstat et Telnet pour vérifier la connectivité de la base de données**

1.  Sélectionnez **Démarrer**, puis tapez **cmd** pour ouvrir une invite de commandes.

2.  Tapez **netstat-a-f**et confirmez que SQL Server s’exécute avec le port correct, comme illustré dans la figure suivante.
    
    ![Utilisation de netstat pour vérifier le port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Utilisation de netstat pour vérifier le port.")

3.  Tapez **telnet \<alias name\> \<port \# ** pour confirmer la connexion à l’instance de SQL Server. Si la connexion réussit, Telnet se connecte et vous ne devriez pas voir d’erreur. Cela indique que l’instance de SQL Server écoute sur le port correct avec l’alias correct. Si un problème se présente lors de la connexion à la base de données SQL Server, Telnet affiche une erreur indiquant que la connexion ne peut pas être établie. Maintenant que vous avez vérifié la connectivité de base de données sur le serveur de base de données, vous pouvez effectuer la même chose à partir de Lync Server (sur le réseau) et vous assurer qu’aucun pare-feu ne bloque l’accès en cours.

</div>

<div>

## <a name="conclusion"></a>Conclusion

Une fois que l’alias SQL Server a été configuré, vous pouvez l’utiliser pour créer une topologie Lync Server 2013 dans l’outil générateur de topologies. Pour plus d’informations sur les topologies, reportez-vous à [la rubrique Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[planification de la sécurité dans Lync Server 2013](lync-server-2013-planning-for-security.md)  
[Définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md)  
[Déploiement de Microsoft Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

