---
title: 'Lync Server 2013 : Basculement vers un pool'
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
ms.openlocfilehash: ea66ae4a224d78e40a9fdb9de867d4738a5e3714
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>Basculement vers un pool dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-10-10_

Si un pool frontal unique a échoué et qu’il doit être basculé, utilisez la procédure suivante. Dans cette procédure, Datacenter1 contient Pool1 et Pool1 a échoué. Vous basculez vers Pool2 situé dans Datacenter2.

La majeure partie du fonctionnement du basculement de pool implique un échec du magasin de gestion central, si nécessaire. C’est important, car le magasin de gestion centralisée doit être opérationnel lorsque les utilisateurs du pool ont échoué.

De plus, si un pool frontal tombe en panne mais que le pool Edge sur ce site est toujours en cours d’exécution, vous devez savoir si le pool d’applications de périmètre utilise le pool en échec en tant que pool de prochains tronçons. Si tel est le cas, vous devez modifier le pool Edge pour utiliser un autre pool frontal avant de basculer sur le pool frontal défectueux. La façon dont vous modifiez le paramètre de saut suivant dépend de la façon dont le bord utilise un pool sur le même site que le pool de périphérie ou un site différent.

**Pour définir un pool de bords pour utiliser un pool de sauts suivant sur le même site**

1.  Ouvrez le générateur de topologie, cliquez avec le bouton droit sur le pool de bords qui doit être modifié, puis cliquez sur **modifier les propriétés**.

2.  Cliquez sur **tronçon suivant**. À partir de la liste **pool de prochains tronçons :** , sélectionnez le pool qui fera désormais Office de réserve de prochains tronçon.

3.  Cliquez sur **OK**, puis publiez les modifications.

**Pour définir un pool de bords pour utiliser un pool de sauts suivant sur un autre site**

1.  Ouvrez une fenêtre Lync Server Management Shell et tapez l’applet de commande suivante :
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Pour basculer sur un pool en cas de sinistre**

1.  Recherchez quel pool est l’hôte du serveur de gestion central en tapant l’applet de commande suivante sur un serveur frontal dans Pool2 :
    
        Invoke-CsManagementServerFailover -Whatif
    
    Les résultats de cette applet de requête indiquent le pool qui héberge actuellement le serveur de gestion central. Dans le reste de cette procédure, ce pool est appelé pool CMS\_.

2.  Utilisez le générateur de topologie pour rechercher la version de Lync Server exécutée sur\_le pool CMS. S’il exécute Lync Server 2013, utilisez l’applet de commande suivante pour trouver le pool de sauvegarde du pool 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Laissez le\_pool de sauvegarde être le pool de sauvegarde.

3.  Vérifiez l’état du magasin central de gestion avec l’applet de commande suivante :
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Cette applet de cmdlet doit indiquer que ActiveMasterFQDN et ActiveFileTransferAgents sont dirigés vers le nom\_de domaine complet du pool CMS. S’il est vide, le serveur de gestion central n’est pas disponible et vous devez le basculer.

4.  Si le magasin de gestion central n’est pas disponible ou si la Banque de gestion centrale s’exécutait sur Pool1 (autrement dit, le pool ayant échoué), vous devez faire basculer le serveur de gestion central avant de basculer sur le pool. Si vous devez basculer sur le serveur de gestion central hébergé sur un pool exécutant Lync Server 2013, utilisez l’applet de demande à l’étape 5 de cette procédure. Si vous devez basculer sur le serveur de gestion central hébergé sur un pool exécutant Lync Server 2010, utilisez l’applet de contrôle à l’étape 6 de cette procédure. Si vous n’avez pas besoin de basculer sur le serveur de gestion central, passez à l’étape 7 de cette procédure.

5.  Pour faire basculer le magasin de gestion central sur un pool exécutant Lync Server 2013, procédez comme suit :
    
      - Tout d’abord, vérifiez quel serveur principal du\_pool de sauvegarde exécute l’instance principale du magasin central de gestion en entrant la commande suivante :
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Si le serveur principal principal du pool de\_sauvegarde est le principal, tapez :
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Si le serveur principal miroir du pool de\_sauvegarde est le principal, tapez :
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Vérifiez que le basculement du serveur central de gestion est terminé. Tapez les informations suivantes :
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Vérifiez que les ActiveMasterFQDN et ActiveFileTransferAgents pointent sur le nom de domaine\_complet (FQDN) du pool de sauvegarde.
    
      - Enfin, vérifiez l’état de réplica de tous les serveurs front-end en entrant la commande suivante :
        
            Get-CsManagementStoreReplicationStatus 
        
        Vérifiez que tous les réplicas ont la valeur true.
        
        Passez à l’étape 7 de cette procédure.

6.  Installez le centre de gestion central sur le serveur principal du pool\_de sauvegarde.
    
      - Tout d’abord, exécutez la commande suivante :
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Exécutez la commande suivante sur l’un des serveurs front-end du\_pool de sauvegarde pour forcer le déplacement du magasin de gestion central :
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Valider le déplacement est terminé :
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Vérifiez que les ActiveMasterFQDN et ActiveFileTransferAgents pointent sur le nom de domaine\_complet (FQDN) du pool de sauvegarde.
    
      - Vérifiez l’état du réplica pour tous les serveurs frontaux en entrant la commande suivante :
        
            Get-CsManagementStoreReplicationStatus 
        
        Vérifiez que tous les réplicas ont la valeur true.
    
      - Installez le service central de gestion sur le reste des serveurs frontaux dans le pool\_de sauvegarde. Pour cela, exécutez la commande suivante sur tous les serveurs frontaux, à l’exception de celle que vous avez utilisée lorsque vous forcez le déplacement du magasin de gestion central plus haut dans cette procédure :
        
            Bootstrapper /Setup 

7.  Basculez les utilisateurs de Pool1 à Pool2 en exécutant l’applet de commande suivante dans une fenêtre Lync Server Management Shell :
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Dans la mesure où les étapes décrites dans les parties précédentes de cette procédure permettent de vérifier que l’état du magasin de gestion central n’est pas universel, il est possible que cette applet de connexion échoue, car le magasin central de gestion n’a pas encore été complètement en échec. Dans ce cas, vous devez résoudre le magasin de gestion central en fonction des messages d’erreur qui s’affichent, puis réexécuter cette cmdlet.
    
    Si vous voyez le message d’erreur suivant, vous devez modifier le pool de périphérie sur ce site pour utiliser un autre pool comme tronçon suivant avant d’avoir basculé sur le pool. Pour plus d’informations, reportez-vous aux procédures au début de cette rubrique.
    
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

