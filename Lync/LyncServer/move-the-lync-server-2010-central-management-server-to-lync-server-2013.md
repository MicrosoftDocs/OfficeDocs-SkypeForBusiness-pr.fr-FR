---
title: Déplacer le serveur de gestion centralisée Lync Server 2010 vers Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90af32fce28d87b211a0829c5c863c9277129c86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>Déplacer le serveur de gestion centralisée Lync Server 2010 vers Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-25_

Après avoir effectué une migration de Lync Server 2010 vers Lync Server 2013, vous devez déplacer le serveur de gestion centralisée Lync Server 2010 vers le serveur ou pool frontal Lync Server 2013, avant de pouvoir supprimer le serveur Lync Server 2010 hérité.

Le serveur de gestion centralisée est un système de réplication maître/multiple unique, dans lequel la copie en lecture/écriture de la base de données est conservée par le serveur frontal qui contient le serveur de gestion centralisée. Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion centralisée, dispose d’une copie en lecture seule des données du magasin central de gestion dans la base de données SQL Server (nommée RTCLOCAL par défaut) installée sur l’ordinateur lors de l’installation et déploiement. La base de données locale reçoit les mises à jour de réplica par le biais de l’agent réplicateur de réplicas de Lync Server qui s’exécute en tant que service sur tous les ordinateurs. Le nom de la base de données réelle sur le serveur de gestion centralisée et le réplica local est XDS, composé des fichiers XDS. mdf et XDS. ldf. L’emplacement de la base de données maître est référencé par un point de contrôle de service (SCP) dans les services de domaine Active Directory. Tous les outils qui utilisent le serveur de gestion centralisée pour gérer et configurer Lync Server utilisent le SCP pour localiser le magasin central de gestion.

Une fois que vous avez réussi à déplacer le serveur de gestion centralisée, vous devez supprimer les bases de données du serveur de gestion centralisée à partir du serveur frontal d’origine. Pour plus d’informations sur la suppression des bases de données du serveur de gestion centralisée, consultez [la rubrique Remove the SQL Server Database for a front end pool](remove-the-sql-server-database-for-a-front-end-pool.md).

Vous utilisez l’applet de commande Windows PowerShell **Move-CsManagementServer** dans Lync Server Management Shell pour déplacer la base de données de la base de données SQL Server de lync Server 2010 vers la base de données SQL Server de lync Server 2013, puis mettre à jour le point de gestion de la mise à niveau vers l’emplacement du serveur de gestion centralisée lync Server 2013.

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>Préparation des serveurs frontaux Lync Server 2013 avant le transfert du serveur de gestion centralisée

Utilisez les procédures de cette section pour préparer les serveurs frontaux Lync Server 2013 avant de déplacer le serveur de gestion centralisée Lync Server 2010.

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Pour préparer un pool frontal Enterprise Edition

1.  Sur le pool frontal Lync Server 2013 Enterprise Edition où vous voulez déplacer le serveur de gestion centralisée : Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez également disposer des droits et des autorisations d’utilisateur sysadmin de la base de données SQL Server sur la base de données où vous souhaitez installer le magasin central de gestion.

2.  Ouvrez Lync Server Management Shell.

3.  Pour créer le nouveau magasin central de gestion dans la base de données SQL Server de Lync Server 2013, dans Lync Server Management Shell, tapez :
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  Confirmez que le statut du service du **Serveur principal Lync Server** est **Démarré**.

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>Pour préparer un serveur frontal Standard Edition

1.  Sur le serveur frontal Lync Server 2013 Standard Edition où vous voulez déplacer le serveur de gestion centralisée : Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .

2.  Ouvrez l’Assistant Déploiement Lync Server.

3.  Dans l’Assistant Déploiement Lync Server, cliquez sur **préparer d’abord le serveur Standard Edition**.

4.  Sur la page **exécution de commandes** , SQL Server Express est installé en tant que serveur de gestion centralisée. Les règles de pare-feu nécessaires sont créées. Lorsque l’installation de la base de données et des logiciels prérequis est terminée, cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]  
    > L’installation initiale peut durer un certain temps sans que les mises à jour ne soient visibles sur l’écran récapitulatif des résultats de la commande. Ceci est dû à l’installation de SQL Server Express. Pour surveiller l’installation de la base de données, utilisez le Gestionnaire des tâches.

    
    </div>

5.  Pour créer le nouveau magasin central de gestion sur le serveur frontal Lync Server 2013 Standard Edition, dans Lync Server Management Shell, tapez :
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  Confirmez que le statut du service du **Serveur principal Lync Server** est **Démarré**.

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>Pour déplacer le serveur de gestion centralisée Lync Server 2010 vers Lync Server 2013

1.  Sur le serveur Lync Server 2013 qui sera le serveur de gestion centralisée : Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez aussi disposer des droits et autorisation d’administrateur système sur la base de données SQL.

2.  Ouvrez Lync Server Management Shell.

3.  Dans Lync Server Management Shell, tapez :
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > Si <CODE>Enable-CsTopology</CODE> ce n’est pas le cas, résolvez le problème en empêchant la commande de se terminer avant de continuer. Si <STRONG>Enable-CsTopology</STRONG> ne réussit pas, le déplacement échoue et il peut laisser votre topologie dans un État où il n’existe pas de magasin central de gestion.

    
    </div>

4.  Sur le serveur frontal ou le pool frontal Lync Server 2013, dans Lync Server Management Shell, tapez :
    
        Move-CsManagementServer

5.  Lync Server Management Shell affiche les serveurs, les magasins de fichiers, les magasins de bases de données et les points de connexion de service de l’état actuel et de l’État proposé. Lisez soigneusement les informations et confirmez qu’il s’agit de la source et de la destination prévues. Tapez **Y** pour continuer, ou **N** pour cesser le déplacement.

6.  Examinez l’ensemble des erreurs et des avertissements générés par la commande **Move-CsManagementServer** et corrigez-les.

7.  Sur le serveur Lync Server 2013, ouvrez l’Assistant Déploiement de Lync Server.

8.  Dans l’Assistant Déploiement de Lync Server, cliquez sur **installer ou mettre à jour le système Lync Server**, cliquez sur **étape 2 : installer ou supprimer des composants Lync Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**.

9.  Sur le serveur Lync Server 2010, ouvrez l’Assistant Déploiement de Lync Server.

10. Dans l’Assistant Déploiement de Lync Server, cliquez sur **installer ou mettre à jour le système Lync Server**, cliquez sur **étape 2 : installer ou supprimer des composants Lync Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**.

11. Redémarrez le serveur Lync Server 2013. Ceci est nécessaire en raison d’une modification de l’appartenance au groupe vers la base de données du serveur de gestion centralisée.

12. Pour confirmer que la réplication avec le nouveau magasin central de gestion est en cours, dans Lync Server Management Shell, tapez :
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > La réplication peut prendre un certain temps pour mettre à jour tous les réplicas.

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>Pour supprimer les fichiers du magasin central de gestion Lync Server 2010 après un déplacement

1.  Sur le serveur Lync Server 2010 : Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez aussi disposer des droits et autorisation d’administrateur système sur la base de données SQL.

2.  Ouvrir Lync Server Management Shell
    
    <div>
    

    > [!WARNING]  
    > Ne procédez pas à la suppression des fichiers de base de données précédents avant que la réplication ne soit terminée et stable. Si vous supprimez les fichiers avant de terminer la réplication, vous interrompez le processus de réplication et laissez le nouveau serveur de gestion centrale déplacé dans un état inconnu. Utilisez l’applet de commande <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> pour confirmer le statut de réplication.

    
    </div>

3.  Pour supprimer les fichiers de base de données du magasin central de gestion du serveur de gestion centralisée Lync Server 2010, tapez :
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    Par exemple :
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    Où le \<nom de domaine complet\> de SQL Server est le serveur principal Lync Server 2010 dans un déploiement Enterprise Edition ou le nom de domaine complet (FQDN) du serveur Standard Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

