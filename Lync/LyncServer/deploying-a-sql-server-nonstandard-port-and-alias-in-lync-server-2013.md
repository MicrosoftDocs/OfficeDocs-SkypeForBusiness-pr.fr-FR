---
title: Déploiement d’un port non standard et d’un alias SQL Server dans Lync Server 2013
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
ms.openlocfilehash: fffa3502b04a9d05387cd94e157ed183e1fe32ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>Déploiement d’un port non standard et d’un alias SQL Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-09-16_

Microsoft Lync Server 2013 prend en charge l’utilisation d’un port et d’un alias non standard dans SQL Server. L’utilisation d’un port SQL Server non standard et d’un alias augmente la sécurité et crée un environnement plus flexible pour le déploiement Lync. Ces étapes ne constituent qu’une seule étape de sécurisation correcte de votre environnement Lync Server 2013. Des étapes supplémentaires sont nécessaires pour réduire la surface d’attaque d’une implémentation 2013 de Lync Server.

L’article suivant décrit les étapes nécessaires pour configurer un port et un alias SQL Server non standard dans Lync Server 2013.

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>Déploiement d’un port et d’un alias SQL Server non standard dans Lync Server 2013

Le générateur de topologie de Lync Server 2013 prend en charge l’utilisation d’un alias SQL Server comme nom de domaine complet au lieu du nom de domaine complet SQL Server réel lors de la configuration de Lync Server 2013. Cela permet de masquer le nom de domaine complet SQL Server réel auprès d’un attaquant malveillant. De plus, l’utilisation d’un port non standard masque le port réel de n’importe quel attaquant tentant d’attaquer la base de données sur le port 1433 standard, comme illustré dans la figure ci-dessous.

![Un pirate ne connaît pas le numéro de port à attaquer.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Un pirate ne connaît pas le numéro de port à attaquer.")

Pour réussir à déterminer le port que Lync Server 2013 utilise pour communiquer avec SQL Server, l’attaquant doit analyser tous les ports pour obtenir les informations de port. Une analyse de port par un attaquant augmente le risque que la sécurité puisse détecter et arrêter l’instruction. Outre l’ajout d’une sécurité accrue avec un port non standard, vous pouvez également utiliser un alias SQL Server pour offrir une souplesse au déploiement. Cela est utile pour réduire les changements de configuration dans les situations dans lesquelles un changement de nom SQL Server est requis.

<div>


> [!NOTE]  
> SQL Server fournit deux méthodes de tolérance de panne (mise en miroir et mise en miroir). Les méthodes de tolérance de panne SQL Server sont prises en charge à l’aide d’un port et d’un alias SQL Server non standard avec Lync Server 2013. Si le serveur principal SQL Server utilisé par le pool est dans une configuration en miroir, le service de navigateur SQL sur les serveurs principaux SQL Server doit être en cours d’exécution pour les serveurs frontaux pour la connexion à la base de données en miroir lorsque les bases de données sont basculées vers le SQL en miroir Serveurs.



</div>

Lors de la configuration de la connectivité de base de données SQL Server à partir du générateur de topologie ou lors de l’utilisation de l’applet de connexion install-CsDatabase, il n’est pas possible de définir explicitement un numéro de port SQL Server non standard et de l’associer à une instance SQL. Pour définir un port non standard, vous devez utiliser les utilitaires SQL Server et Windows Server.

Pour configurer un port et un alias SQL Server non standard pour une utilisation avec Lync Server 2013, vous devez effectuer trois étapes principales. Ces étapes sont les suivantes :

  - Vérifiez que Lync Server 2013 dispose des dernières mises à jour.

  - Configurez le port et l’alias SQL Server non standard.

  - Configurer Lync Server 2013 avec l’alias SQL Server à l’aide du générateur de topologie.

  - Publiez la topologie et vérifiez la base de données.

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>Vérifiez que Lync Server 2013 a installé les dernières mises à jour.

Il est important de tenir à jour Lync Server 2013. Pour rechercher les mises à jour les plus récentes et obtenir des informations sur la façon de les appliquer, voir [mises à jour de Lync Server 2013](http://support.microsoft.com/kb/2809243).

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>Configurer le port et l’alias SQL Server non standard

Le port et l’alias SQL Server non standard doivent être définis sur l’instance de base de données avant d’être référencés à partir du générateur de topologie Lync Server 2013. Pour configurer un port et un alias SQL Server non standard, vous devez effectuer trois étapes principales. Ces étapes sont les suivantes :

  - Changer les valeurs par défaut du protocole TCP/IP.

  - Créez et configurez un alias SQL Server.

  - Créer un enregistrement de ressource de nom canonique DNS (Domain Name System) (CNAMe).

**Modifier les valeurs par défaut du protocole TCP/IP**

1.  Sélectionnez **Démarrer**, puis sélectionnez **Gestionnaire de configuration SQL Server**, comme illustré dans la figure ci-dessous.
    
    ![Icône SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icône SQL Server Management Studio")

2.  Dans le volet de navigation, sélectionnez l' **instance SQL Server**, choisissez de développer **configuration du réseau SQL Server**, puis sélectionnez **protocoles pour \<nom\>d’instance**, comme illustré dans la figure ci-dessous.
    
    ![Naviguer dans les propriétés TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Naviguer dans les propriétés TCP/IP")

3.  Dans le volet droit, cliquez avec le bouton droit sur **TCP/IP**, puis sélectionnez **Propriétés**. La boîte de dialogue Propriétés TCP/IP s’affiche.

4.  Sélectionnez l’onglet **adresses IP** . L’onglet adresses IP affiche toutes les adresses IP actives du serveur. Celles-ci sont au format IP1, IP2, jusqu’à IPAll, comme illustré dans la figure ci-dessous.
    
    ![Ouvrir les propriétés TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Ouvrir les propriétés TCP/IP.")

5.  Effacez le champ **TCP Dynamic ports** pour toutes les adresses IP. Si le champ contient un caractère zéro, cela signifie que SQL Server écoute sur les ports dynamiques. Assurez-vous que ces champs sont effacés et ne contiennent pas de zéro.

6.  Pour l’adresse IP que Lync Server utilisera pour la connexion à la base de données, assurez-vous que l' **option activé** est définie sur **Oui**, comme illustré dans la figure ci-dessous.
    
    ![Définir Activé sur Oui pour l’adresse IP correcte.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Définir Activé sur Oui pour l’adresse IP correcte.")

7.  Dans la section **IPAll** en bas de la boîte de dialogue, entrez le port souhaité dans le champ **port TCP** , comme illustré dans la figure ci-dessous. Dans cet exemple, nous utilisons le port 50062, mais vous pouvez utiliser n’importe quel port entre 49152 et 65535. Il s’agit des ports attribués à une utilisation dynamique et privée, ce qui évite tout conflit avec d’autres ports utilisés dans le déploiement de Lync Server 2013.
    
    ![Définir le port dans la section IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Définir le port dans la section IPAll.")

8.  Cliquez sur **OK** pour quitter la boîte de dialogue Propriétés TCP/IP.

9.  Redémarrez l’instance SQL Server en sélectionnant **services SQL Server** dans le volet gauche de la fenêtre Gestionnaire de configuration SQL Server. Ensuite, cliquez avec le bouton droit sur **nom \<\> de l’instance SQL Server** dans le volet droit, puis sélectionnez **redémarrer**, comme illustré dans la figure ci-dessous.
    
    ![Réinitialiser le service SQL Server service pour l’instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Réinitialiser le service SQL Server service pour l’instance.")

<div>


> [!IMPORTANT]  
> Veillez à mettre à jour les paramètres de votre pare-feu pour qu’il s’adapte au nouveau port SQL Server.



</div>

**Créer et configurer un alias SQL Server**

1.  Sélectionnez **Démarrer**, puis sélectionnez **Gestionnaire de configuration SQL Server**, comme illustré dans la figure ci-dessous.
    
    ![Icône SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icône SQL Server Management Studio")

2.  Dans le volet gauche, sélectionnez l' **instance de SQL Server**, puis, dans la figure ci-dessous **, choisissez d'** augmenter la configuration de la **version \<\> du client natif SQL**.
    
    ![Alias dans le gestionnaire de configuration SQL Server.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias dans le gestionnaire de configuration SQL Server.")

3.  Cliquez avec le bouton droit sur **alias**, puis sélectionnez **nouveau pseudonyme..**..

4.  Entrez le **nom**de l’alias, le **numéro de port**, le **protocole**et le **serveur**, comme illustré dans la figure ci-dessous.
    
    ![Création d’un alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Création d’un alias")
    
    <div>
    

    > [!CAUTION]  
    > Assurez-vous d’entrer le même port non standard utilisé lors de l’étape précédente, car il s’agit du port sur lequel SQL Server sera écouté. S’il s’agit d’un alias configuré qui se connecte à un nom de domaine complet (FQDN) SQL Server incorrect, désactivez puis réactivez le protocole réseau associé. Cette opération a pour effet d’effacer toutes les informations de connexion mises en cache et de permettre au client de se connecter correctement.

    
    </div>

**Créer un enregistrement de ressource CNAMe DNS**

1.  Connectez-vous à l’ordinateur gestion du DNS.

2.  Cliquez sur **Démarrer**, puis sélectionnez **Gestionnaire de serveur**, comme illustré dans la figure ci-dessous.
    
    ![Ouverture du gestionnaire de serveur](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Ouverture du gestionnaire de serveur")

3.  Sélectionnez la liste déroulante **Outils** et sélectionnez **DNS**, comme illustré dans la figure ci-dessous.
    
    ![Ouverture du DNS à partir du gestionnaire de serveur.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Ouverture du DNS à partir du gestionnaire de serveur.")

4.  Dans le volet gauche, développez le nœud nom du serveur, développez le nœud zones de recherche directes, puis sélectionnez le domaine approprié.

5.  Cliquez avec le bouton droit sur le domaine, puis sélectionnez **nouveau pseudonyme (CNAME)...**, comme illustré dans la figure ci-dessous.
    
    ![Sélection de l’option de création d’un alias CNAMe](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Sélection de l’option de création d’un alias CNAMe")

6.  Entrez le **nom** de l’alias et le nom **de domaine complet (FQDN) de SQL Server**, comme illustré dans la figure ci-dessous.
    
    ![Remplissage de la boîte de dialogue nouveau pseudonyme CNAMe.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Remplissage de la boîte de dialogue nouveau pseudonyme CNAMe.")

7.  Cliquez sur **OK** pour enregistrer le CNAME et l’afficher dans le Gestionnaire DNS.

</div>

<div>

## <a name="validate-database-connectivity"></a>Valider la connectivité de base de données

Il existe de nombreuses façons de vérifier qu’elle fonctionne. Vous voulez vous assurer que la base de données SQL Server écoute sur le port spécifié à l’aide de l’alias. Une vérification rapide peut être effectuée à l’aide des commandes **netstat** et **Telnet** .

<div>


> [!NOTE]  
> Le client Telnet est une fonctionnalité qui est fournie avec Windows Server, mais qui doit être installée. Une fonctionnalité de serveur Windows peut être installée en ouvrant le gestionnaire de serveur et en sélectionnant Ajouter des rôles et des fonctionnalités dans le menu gérer.



</div>

**Utiliser netstat et Telnet pour vérifier la connectivité de base de données**

1.  Sélectionnez **Démarrer**, puis tapez **cmd** pour ouvrir une invite de commandes.

2.  Tapez **netstat-a-f**, puis vérifiez que SQL Server s’exécute avec le port approprié, comme illustré dans la figure ci-dessous.
    
    ![Utiliser netstat pour vérifier le port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Utiliser netstat pour vérifier le port.")

3.  Tapez **port \< \# de nom\> \<d’alias Telnet** pour confirmer la connexion à l’instance SQL Server. S’il s’agit d’une connexion réussie, Telnet se connecte et aucune erreur ne s’affiche. Cela montre que l’instance SQL Server écoute sur le port approprié avec l’alias approprié. Si vous ne parvenez pas à vous connecter à la base de données SQL Server, Telnet affiche une erreur indiquant que la connexion ne peut pas être effectuée. À présent que vous avez vérifié la connectivité de la base de données sur le serveur de base de données, vous pouvez effectuer la même opération sur Lync Server (sur le réseau) et vous assurer qu’aucun pare-feu ne bloque l’accès.

</div>

<div>

## <a name="conclusion"></a>Conclusion

Une fois l’alias SQL Server configuré, vous pouvez l’utiliser pour créer une topologie Lync Server 2013 dans l’outil générateur de topologie. Pour plus d’informations sur les topologies, reportez-vous à [la rubrique définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[planning pour la sécurité dans Lync Server 2013](lync-server-2013-planning-for-security.md)  
[Définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md)  
[Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

