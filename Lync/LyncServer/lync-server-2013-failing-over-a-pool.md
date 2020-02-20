---
title: 'Lync Server 2013 : basculement d’un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5771d21479cf4dd63a3fa1e1e141b566fdbe6899
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>Basculement d’un pool dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-10-10_

Si un seul pool frontal a échoué et doit être basculé, utilisez la procédure ci-après. Dans cette procédure, Datacenter1 contient Pool1 et Pool1 a échoué. Vous effectuez le basculement vers Pool2 qui se trouve dans Datacenter2.

La plupart du travail pour le basculement de pool implique le basculement du magasin central de gestion, si nécessaire. Ceci est important, car le magasin central de gestion doit être fonctionnel lorsque les utilisateurs du pool ont basculé.

En outre, si un pool frontal échoue mais que le pool de serveurs Edge sur ce site est toujours en cours d’exécution, vous devez savoir si le pool de serveurs Edge utilise le pool qui a échoué comme pool du tronçon suivant. Si tel est le cas, vous devez modifier le pool de serveurs Edge de manière à utiliser un pool frontal différent avant de faire basculer le pool frontal qui a connu un échec. La manière dont vous pouvez modifier le paramètre du tronçon suivant varie selon que le serveur Edge va utiliser un pool sur le même site comme pool de serveurs Edge ou sur un site différent.

**Pour configurer un pool de serveurs Edge de manière à utiliser un pool du tronçon suivant sur le même site**

1.  Ouvrez le générateur de topologies, cliquez avec le bouton droit sur le pool de serveurs Edge à modifier, puis cliquez sur **modifier les propriétés**.

2.  Cliquez sur **Tronçon suivant**. Dans la liste **Pool du tronçon suivant :**, sélectionnez le pool qui servira désormais de pool du tronçon suivant.

3.  Cliquez sur **OK**, puis publiez les modifications.

**Pour configurer un pool de serveurs Edge de manière à utiliser un pool du tronçon suivant sur un site différent**

1.  Ouvrez une fenêtre Lync Server Management Shell et tapez l’applet de commande suivante :
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Pour faire basculer un pool en cas d’urgence**

1.  Recherchez le pool qui héberge le serveur de gestion centralisée en tapant l’applet de commande suivante sur un serveur frontal dans Pool2 :
    
        Invoke-CsManagementServerFailover -Whatif
    
    Les résultats de cette cmdlet indiquent le pool qui héberge actuellement le serveur de gestion centralisée. Dans le reste de cette procédure, ce pool est appelé pool CMS\_.

2.  Utilisez le générateur de topologies pour rechercher la version de Lync Server exécutée\_sur le pool CMS. S’il exécute Lync Server 2013, utilisez l’applet de commande suivante pour rechercher le pool de sauvegarde du pool 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Laissez le\_pool de sauvegardes être le pool de sauvegarde.

3.  Vérifiez l’état du magasin central de gestion à l’aide de l’applet de commande suivante :
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Cette applet de commande doit indiquer que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de\_domaine complet du pool CMS. S’ils sont vides, le serveur de gestion centralisée n’est pas disponible et vous devez le faire basculer.

4.  Si le magasin central de gestion n’est pas disponible ou si le magasin central de gestion était en cours d’exécution sur Pool1 (autrement dit, sur le pool ayant échoué), vous devez basculer le serveur de gestion centralisée avant de basculer sur le pool. Si vous avez besoin de basculer le serveur de gestion centralisée hébergé sur un pool exécutant Lync Server 2013, utilisez l’applet de commande à l’étape 5 de cette procédure. Si vous avez besoin de basculer le serveur de gestion centralisée hébergé sur un pool exécutant Lync Server 2010, utilisez l’applet de commande à l’étape 6 de cette procédure. Si vous n’avez pas besoin de basculer le serveur de gestion centralisée, passez à l’étape 7 de cette procédure.

5.  Pour faire basculer le magasin central de gestion sur un pool exécutant Lync Server 2013, procédez comme suit :
    
      - Tout d’abord, vérifiez le serveur principal dans\_le pool de sauvegarde qui exécute l’instance principale du magasin central de gestion en tapant ce qui suit :
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Si le principal serveur principal dans le pool\_de sauvegarde est le principal, tapez :
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Si le serveur principal miroir dans le pool\_de sauvegarde est le principal, tapez :
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Vérifiez que le basculement du serveur de gestion centralisée est terminé. Tapez ensuite :
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Vérifiez que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet\_du pool de sauvegarde.
    
      - Enfin, vérifiez l’état du réplica de tous les serveurs frontaux en tapant ce qui suit :
        
            Get-CsManagementStoreReplicationStatus 
        
        Assurez-vous que tous les réplicas sont définis sur True.
        
        Passez à l’étape 7 de cette procédure.

6.  Installez le magasin central de gestion sur le serveur principal du pool\_de sauvegarde.
    
      - Exécutez d’abord cette commande :
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Exécutez la commande suivante sur l’un des serveurs frontaux du pool\_de sauvegarde pour forcer le déplacement du magasin central de gestion :
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Vérifiez que le déplacement est terminé :
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Vérifiez que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet\_du pool de sauvegarde.
    
      - Vérifiez le statut des réplicas de tous les serveurs frontaux en tapant ce qui suit :
        
            Get-CsManagementStoreReplicationStatus 
        
        Assurez-vous que tous les réplicas sont définis sur True.
    
      - Installez le service de gestion centralisée sur le reste des serveurs frontaux dans le\_pool de sauvegarde. Pour ce faire, exécutez la commande suivante sur tous les serveurs frontaux, à l’exception de celle que vous avez utilisée lors de l’activation forcée du déplacement du magasin central de gestion plus haut dans cette procédure :
        
            Bootstrapper /Setup 

7.  Basculez les utilisateurs de Pool1 vers Pool2 en exécutant l’applet de commande suivante dans une fenêtre Lync Server Management Shell :
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Étant donné que les étapes décrites dans les parties précédentes de cette procédure pour vérifier que l’état du magasin central de gestion ne sont pas universelles, il est possible que cette cmdlet échoue car le magasin central de gestion n’est pas encore totalement basculé. Dans ce cas, vous devez corriger le magasin central de gestion en fonction des messages d’erreur qui s’affichent, puis réexécuter cette applet de commande.
    
    Si le message d’erreur suivant apparaît, vous devez modifier le pool de serveurs Edge sur ce site afin d’utiliser un pool différent comme tronçon suivant avant de faire basculer le pool. Pour plus d’informations, voir les procédures indiquées au début de cette rubrique.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

