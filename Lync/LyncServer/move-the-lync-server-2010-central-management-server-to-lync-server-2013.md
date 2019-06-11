---
title: Déplacer le serveur de gestion central de Lync Server 2010 vers Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abcb361beb82b98cd765b3797b63b22c280fdf70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>Déplacer le serveur de gestion central de Lync Server 2010 vers Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-25_

Après la migration de Lync Server 2010 vers Lync Server 2013, vous devez déplacer le serveur de gestion central de Lync Server 2010 vers le pool ou le serveur frontal de Lync Server 2013, avant de pouvoir supprimer l’ancien serveur Lync Server 2010.

Le serveur de gestion central est un système de réplication maître/multiple unique, où la copie en lecture/écriture de la base de données est stockée par le serveur frontal qui contient le serveur de gestion central. Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion central, dispose d’une copie en lecture seule de la base de données centrale de gestion de la base de données SQL Server (nommée RTCLOCAL par défaut) installée sur l’ordinateur lors de l’installation et développement. La base de données locale reçoit les mises à jour de réplica par le biais de l’agent réplicateur de réplicas de Lync Server exécuté en tant que service sur tous les ordinateurs. Le nom de la base de données réelle du serveur de gestion central et du réplica local est XDS, qui est constitué des fichiers XDS. mdf et XDS. ldf. L’emplacement de la base de données maître est référencé par un point de contrôle de service (SCP) dans les services de domaine Active Directory (AD DS). Tous les outils qui utilisent le serveur de gestion central pour gérer et configurer Lync Server utilisent le SCP pour trouver le magasin de gestion central.

Après avoir déplacé le serveur de gestion central, vous devez supprimer les bases de données du serveur principal de gestion du serveur frontal initial. Pour plus d’informations sur la suppression de la base de données de serveur de gestion centrale, voir [Supprimer la base de données SQL Server d’un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md).

Pour déplacer la base de données **** de la base de données sql Server 2010 vers lync Server 2013 SQL Server à l’aide de la cmdlet Windows PowerShell, procédez comme s’il s’agit de la base de données sql Server SQL Server, puis mettez à jour le SCP pour qu’il pointe vers Lync. Emplacement du serveur de gestion central de Server 2013.

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>Préparation des serveurs frontaux Lync Server 2013 avant le déplacement du serveur de gestion central

Suivez les procédures décrites dans cette section pour préparer les serveurs frontaux Lync Server 2013 avant de déplacer le serveur de gestion central de Lync Server 2010.

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Pour préparer un pool frontal Enterprise Edition

1.  Sur le pool frontal de Lync Server 2013 Enterprise Edition dans lequel vous souhaitez relocaliser le serveur de gestion central: Connectez-vous à l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez également disposer des droits d’utilisateur sysadmin et des autorisations de la base de données SQL Server sur la base de données dans laquelle vous voulez installer le centre de gestion central.

2.  Ouvrez Lync Server Management Shell.

3.  Pour créer la nouvelle Banque centrale de gestion dans la base de données SQL Server 2013 de Lync Server, dans Lync Server Management Shell, tapez:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  Vérifiez que l’état du service **frontal de Lync Server** est **démarré**.

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>Pour préparer un serveur frontal Standard Edition

1.  Sur le serveur frontal de Lync Server 2013 Standard Edition sur lequel vous voulez déplacer le serveur de gestion centralisée: Connectez-vous à l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .

2.  Ouvrez l’Assistant Déploiement de Lync Server.

3.  Dans l’Assistant Déploiement de Lync Server, cliquez sur **préparer le premier serveur Standard Edition**.

4.  Sur la page **exécution des commandes** , SQL Server Express est installé en tant que serveur de gestion central. Des règles de pare-feu nécessaires sont créées. Lorsque l’installation de la base de données et du logiciel requis est terminée, cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]  
    > L’installation initiale risque de prendre un certain temps sans qu’aucune mise à jour ne s’affiche à l’écran de synthèse de la sortie de commande. Le problème est dû à l’installation de SQL Server Express. Si vous avez besoin de surveiller l’installation de la base de données, utilisez le gestionnaire des tâches pour contrôler la configuration.

    
    </div>

5.  Pour créer la nouvelle Banque centrale de gestion sur le serveur frontal Lync Server 2013 Standard Edition, dans Lync Server Management Shell, tapez:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  Vérifiez que l’état du service **frontal de Lync Server** est **démarré**.

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>Pour déplacer le serveur de gestion centralisée de Lync Server 2010 vers Lync Server 2013

1.  Sur le serveur Lync Server 2013 qui sera le serveur de gestion central: Connectez-vous à l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez également avoir les autorisations et les droits d’utilisateur de l’administrateur de base de données SQL Server.

2.  Ouvrez Lync Server Management Shell.

3.  Dans Lync Server Management Shell, tapez:
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > Si <CODE>Enable-CsTopology</CODE> ce n’est pas le cas, résolvez le problème empêchant l’exécution de la commande avant de poursuivre. Si <STRONG>Enable-CsTopology</STRONG> ne fonctionne pas, le déplacement échoue et il peut arriver que votre topologie soit dans un État où il n’y a aucune banque centrale de gestion.

    
    </div>

4.  Sur le serveur frontal ou le pool frontal Lync Server 2013, dans Lync Server Management Shell, tapez:
    
        Move-CsManagementServer

5.  Lync Server Management Shell affiche les serveurs, les magasins de fichiers, les magasins de bases de données et les points de connexion de service de l’état actuel et de l’État proposé. Lisez attentivement les informations et confirmez qu’il s’agit de la source et de la destination attendues. Tapez **Y** pour continuer ou **N** pour arrêter le déplacement.

6.  Examinez les avertissements ou erreurs générés par la commande **Move-CsManagementServer** et résolvez-les.

7.  Sur le serveur Lync Server 2013, ouvrez l’Assistant Déploiement de Lync Server.

8.  Dans l’Assistant Déploiement de Lync Server, cliquez sur **installer ou mettre à jour le système de serveur Lync**, cliquez sur **étape 2: installer ou supprimer des composants Lync Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**.

9.  Sur le serveur Lync Server 2010, ouvrez l’Assistant Déploiement de Lync Server.

10. Dans l’Assistant Déploiement de Lync Server, cliquez sur **installer ou mettre à jour le système de serveur Lync**, cliquez sur **étape 2: installer ou supprimer des composants Lync Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**.

11. Redémarrez le serveur Lync Server 2013. Ceci est requis en raison d’une modification d’appartenance de groupe à une base de données du serveur de gestion centralisée.

12. Pour vérifier que la réplication avec le nouveau magasin central de gestion est en cours, dans Lync Server Management Shell, tapez:
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > La réplication risque de prendre un certain temps pour mettre à jour tous les réplicas actuels.

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>Pour supprimer les fichiers du store de la gestion centrale de Lync Server 2010 après un déplacement

1.  Sur Lync Server 2010 Server: Connectez-vous à l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez également avoir les autorisations et les droits d’utilisateur de l’administrateur de base de données SQL Server.

2.  Ouvrez Lync Server Management Shell
    
    <div>
    

    > [!WARNING]  
    > Ne continuez pas la suppression des fichiers de base de données précédents tant que la réplication n’est pas terminée et qu’elle est stable. Si vous supprimez les fichiers avant de procéder à la réplication, vous désactiverez le processus de réplication et laissons le serveur de gestion central nouvellement déplacé dans un état inconnu. Utilisez l’applet de connexion <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> pour vérifier l’état de la réplication.

    
    </div>

3.  Pour supprimer les fichiers de base de données du magasin de gestion centrale du serveur de gestion central de Lync Server 2010, tapez:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    Par exemple :
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    Où le \<FQDN de SQL Server\> est le serveur principal Lync Server 2010 dans un déploiement Enterprise Edition ou le nom de domaine complet (FQDN) du serveur Standard Edition Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

