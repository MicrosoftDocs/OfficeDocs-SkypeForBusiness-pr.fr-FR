---
title: 'Lync Server 2013 : Basculement vers un pool'
TOCTitle: Basculement vers un pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204678(v=OCS.15)
ms:contentKeyID: 49296281
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Basculement vers un pool dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-10-10_

Si un seul pool frontal a échoué et doit être basculé, utilisez la procédure ci-après. Dans cette procédure, Datacenter1 contient Pool1 et Pool1 a échoué. Vous effectuez le basculement vers Pool2 qui se trouve dans Datacenter2.

Le basculement du pool consiste principalement à faire basculer vers le magasin central de gestion, si cela est nécessaire. C’est important, car le magasin central de gestion doit être fonctionnel au moment où les utilisateurs du pool sont basculés.

En outre, si un pool frontal échoue mais que le pool de serveurs Edge sur ce site est toujours en cours d’exécution, vous devez savoir si le pool de serveurs Edge utilise le pool qui a échoué comme pool du tronçon suivant. Si tel est le cas, vous devez modifier le pool de serveurs Edge de manière à utiliser un pool frontal différent avant de faire basculer le pool frontal qui a connu un échec. La manière dont vous pouvez modifier le paramètre du tronçon suivant varie selon que le serveur Edge va utiliser un pool sur le même site comme pool de serveurs Edge ou sur un site différent.

**Pour configurer un pool de serveurs Edge de manière à utiliser un pool du tronçon suivant sur le même site**

1.  Ouvrez le Générateur de topologie, cliquez avec le bouton droit de la souris sur le pool de serveurs Edge devant être modifié, puis cliquez sur **Modifier les propriétés** .

2.  Cliquez sur **Tronçon suivant** . Dans la liste **Pool du tronçon suivant :** , sélectionnez le pool qui servira désormais de pool du tronçon suivant.

3.  Cliquez sur **OK** , puis publiez les modifications.

**Pour configurer un pool de serveurs Edge de manière à utiliser un pool du tronçon suivant sur un site différent**

1.  Ouvrez une fenêtre Lync Server Management Shell et tapez l’applet de commande suivante :
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Pour faire basculer un pool en cas d’urgence**

1.  Identifiez le pool qui sert d’hôte au serveur de gestion centralisée en saisissant l’applet de commande suivante sur un serveur frontal dans Pool2 :
    
        Invoke-CsManagementServerFailover -Whatif
    
    Les résultats de cette applet de commande montrent le pool qui héberge actuellement le serveur de gestion centralisée. Dans le reste de cette procédure, ce pool porte le nom de CMS\_Pool.

2.  Utilisez le générateur de topologie pour connaître la version de Lync Server qui s’exécute sur CMS\_Pool. Si le pool exécute Lync Server 2013, utilisez l’applet de commande suivante pour trouver le pool de sauvegarde de Pool1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Définissez Backup\_Pool comme pool de sauvegarde.

3.  Vérifiez le statut du magasin central de gestion à l’aide de l’applet de commande suivante :
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Cette applet de commande doit montrer que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet de CMS\_Pool. S’ils sont vides, le serveur de gestion centralisée n’est pas disponible et vous devez le faire basculer.

4.  Si le magasin central de gestion n’est pas disponible ou si le magasin central de gestion s’exécutait sur Pool1 (c’est-à-dire le pool qui a échoué), vous devez faire basculer le serveur de gestion centralisée avant de faire basculer le pool. Si vous devez faire basculer le serveur de gestion centralisée qui était hébergé sur un pool exécutant Lync Server 2013, utilisez l’applet de commande de l’étape 5 de cette procédure. Si vous devez faire basculer le serveur de gestion centralisée qui était hébergé sur un pool exécutant Lync Server 2010, utilisez l’applet de commande de l’étape 6 de cette procédure. Si vous n’avez pas besoin de faire basculer le serveur de gestion centralisée, passez à l’étape 7 de cette procédure.

5.  Pour faire basculer le magasin central de gestion vers un pool exécutant Lync Server 2013, procédez comme suit :
    
      - Vérifiez d’abord quel serveur principal sur Backup\_Pool exécute l’instance principale du magasin central de gestion en tapant ce qui suit :
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Si le serveur principal primaire sur Backup\_Pool est le principal, tapez :
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Si le serveur principal miroir sur Backup\_Pool est le principal, tapez :
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Vérifiez que le basculement du serveur de gestion centralisée est terminé. Tapez ce qui suit :
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Assurez-vous que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet de Backup\_Pool.
    
      - Enfin, vérifiez le statut des réplicas de tous les serveurs frontaux en tapant ce qui suit :
        
            Get-CsManagementStoreReplicationStatus 
        
        Assurez-vous que tous les réplicas sont définis sur True.
        
        Passez à l’étape 7 de cette procédure.

6.  Installez le magasin central de gestion sur le serveur principal de Backup\_Pool.
    
      - Exécutez d’abord cette commande :
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Exécutez la commande suivante sur un des serveurs frontaux de Backup\_Pool pour forcer le déplacement du magasin central de gestion :
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Vérifiez que le déplacement est terminé :
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Assurez-vous que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet de Backup\_Pool.
    
      - Vérifiez le statut des réplicas de tous les serveurs frontaux en tapant ce qui suit :
        
            Get-CsManagementStoreReplicationStatus 
        
        Assurez-vous que tous les réplicas sont définis sur True.
    
      - Installez le service du serveur de gestion centralisée sur le reste des serveurs frontaux dans Backup\_Pool. Pour ce faire, exécutez la commande suivante sur tous les serveurs frontaux, à l’exception de celui que vous avez utilisé pour forcer le déplacement du magasin central de gestion précédemment au cours cette procédure :
        
            Bootstrapper /Setup 

7.  Faites basculer les utilisateurs de Pool1 vers Pool2 en exécutant l’applet de commande suivante dans une fenêtre Lync Server Management Shell :
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Comme les étapes décrites dans les sections précédentes de cette procédure afin de vérifier le statut du magasin central de gestion ne sont pas universelles, il est toujours possible que cette applet de commande échoue, car le magasin central de gestion n’est pas encore entièrement basculé. Dans ce cas, vous devez corriger le magasin central de gestion en fonction des messages d’erreur qui s’affichent avant de réexécuter cette applet de commande.
    
    Si le message d’erreur suivant s’affiche, vous devez modifier le pool de serveurs Edge sur ce site afin d’utiliser un pool différent comme tronçon suivant avant de faire basculer le pool. Pour plus d’informations, reportez-vous aux procédures indiquées au début de cette rubrique.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

