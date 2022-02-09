---
title: Basculement ou restauration d’un pool
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: .
ms.openlocfilehash: e9dd797c9db1a42b692376712dd4515751912be5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410837"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Faire échouer et faire échouer un pool dans Skype Entreprise Server

Utilisez les procédures suivantes si un pool de Front-End unique a échoué et doit être retenté, ou si le pool qui a connu le sinistre est de nouveau en ligne et que vous devez rétablir l’état de travail normal de votre déploiement. Découvrez comment faire échouer et faire échouer le pool edge utilisé pour la fédération Skype Entreprise ou XMPP, ou comment modifier le pool edge associé à un pool Front-End pool.

- [Faire échouer un pool frontal](#fail-over-a-front-end-pool)
- [Faire échouer un pool](#fail-back-a-pool)
- [Faire échouer le pool edge utilisé pour la fédération Skype Entreprise Server’équipe](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Faire échouer le pool edge utilisé pour la fédération XMPP dans Skype Entreprise Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Faire échouer le pool edge utilisé pour la fédération Skype Entreprise Server ou XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Modifier le pool edge associé à un pool frontal](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Faire échouer un pool Front-End'équipe

Datacenter1 contient Pool1 et Pool1 a échoué. Vous faites le pas vers Pool2 situé dans Datacenter2.

La majeure partie du travail du pool consiste à faire échouer le magasin central de gestion, si nécessaire. Le magasin central de gestion doit être fonctionnel lorsque les utilisateurs du pool sont retentés.

Si un pool Front-End tombe en panne, mais que le pool edge de ce site est toujours en cours d’exécution, vous devez savoir si le pool edge utilise le pool défaille comme pool du saut suivant. Si c’est le cas, vous devez modifier le pool edge pour qu’il utilise un pool de Front-End différent avant de faire échouer le pool Front-End échoué. La manière dont vous pouvez modifier le paramètre du tronçon suivant varie selon que le serveur Edge va utiliser un pool sur le même site comme pool de serveurs Edge ou sur un site différent.

**Pour définir un pool edge pour utiliser un pool de saut suivant sur le même site**

1. Ouvrez le Générateur de topologie, cliquez avec le bouton droit sur le pool edge qui doit être modifié, puis **sélectionnez Modifier les propriétés**.

2. Sélectionnez **Saut suivant**. Dans la **liste Pool du saut suivant** : sélectionnez le pool qui servira désormais de pool du saut suivant.

3. **Sélectionnez OK**, puis publiez les modifications.

**Pour définir un pool edge pour utiliser un pool de saut suivant sur un autre site**

1. Ouvrez une Skype Entreprise Server Management Shell et tapez l’cmdlet suivante :

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**Pour faire échouer un pool en cas d’urgence**

1. Recherchez le pool d’hôtes pour le serveur central de gestion en tapant l’cmdlet suivante sur un serveur Front-End dans Pool2 :

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    Les résultats de cette cmdlet indiquent quel pool héberge actuellement le serveur central de gestion. Dans le reste de cette procédure, ce pool est appelé CMSPool\_.

2. Utilisez le Générateur de topologie pour trouver la version de Skype Entreprise Server en cours d’exécution sur CMSPool\_. Si elle est en cours d’Skype Entreprise Server, utilisez l’cmdlet suivante pour trouver le pool de sauvegarde du pool 1.

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    Que BackupPool\_ soit le pool de sauvegarde.

3. Vérifiez l’état du magasin central de gestion avec l’cmdlet suivante :

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    Cette cmdlet doit montrer que activeMasterFQDN et ActiveFileTransferAgents pointent vers le FQDN de CMSPool\_. S’ils sont vides, le serveur central de gestion n’est pas disponible et vous devez le faire échouer.

4.  Si le magasin central de gestion n’est pas disponible ou si le magasin central de gestion était en cours d’exécution sur Pool1 (autrement dit, le pool qui a échoué), vous devez faire échouer le serveur central de gestion avant de faire échouer le pool. Si vous devez faire échouer le serveur central de gestion hébergé sur un pool exécutant Skype Entreprise Server, utilisez la cmdlet à l’étape 5 de cette procédure. Si vous n’avez pas besoin de faire échouer le serveur central de gestion, passez à l’étape 7 de cette procédure.

5.  Pour faire échouer le magasin central de gestion sur un pool exécutant Skype Entreprise Server, exécutez les conseils suivants :

    1. Tout d’abord, vérifiez Back-End Server dans BackupPool\_ exécute l’instance principale du magasin central de gestion en tapant ce qui suit :

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. Si le serveur Back-End principal dans BackupPool\_ est le principal, tapez :

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. Si le serveur Back-End miroir dans BackupPool\_ est le principal, tapez :
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. Vérifier que le serveur central de gestion est terminé. Tapez la commande suivante :
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Vérifiez que activeMasterFQDN et ActiveFileTransferAgents pointent vers le FQDN de BackupPool\_.
    
    1. Enfin, vérifiez l’état du réplica pour tous Front-End serveurs en tapant ce qui suit :
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        Assurez-vous que tous les réplicas sont définis sur True.
        
        Passez à l’étape 7 de cette procédure.

6.  Installez le magasin central de gestion sur le serveur principal de BackupPool\_.
    
    1. Exécutez d’abord cette commande :

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. Exécutez la commande suivante sur l’un des serveurs frontux de BackupPool\_ pour forcer le déplacement du magasin central de gestion :

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. Vérifiez que le déplacement est terminé :

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Vérifiez que activeMasterFQDN et ActiveFileTransferAgents pointent vers le FQDN de BackupPool\_.
    
    1. Vérifiez le statut des réplicas de tous les serveurs frontaux en tapant ce qui suit :

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        Assurez-vous que tous les réplicas sont définis sur True.
    
    1. Installez le service Serveur central de gestion sur le reste des serveurs frontux dans BackupPool\_. Pour ce faire, exécutez la commande suivante sur tous les serveurs frontux, à l’exception de celle que vous avez utilisée pour forcer le déplacement du magasin central de gestion précédemment dans cette procédure :

        ```console
        Bootstrapper /Setup
        ```

7.  Pour faire échouer les utilisateurs de Pool1 à Pool2, exécutez l’cmdlet suivante dans une fenêtre Skype Entreprise Server Management Shell :

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    Étant donné que les étapes des étapes précédentes de cette procédure pour vérifier l’état du magasin central de gestion ne sont pas universelles, il est toujours possible que cette cmdlet échoue, car le magasin central de gestion n’est pas encore entièrement bas. Dans ce cas, vous devez corriger le magasin central de gestion en fonction des messages d’erreur que vous voyez, puis ré-exécuter cette cmdlet.
    
    Si le message d’erreur suivant apparaît, vous devez modifier le pool de serveurs Edge sur ce site afin d’utiliser un pool différent comme tronçon suivant avant de faire basculer le pool. Pour plus d’informations, voir les procédures indiquées au début de cette rubrique.
    
    ```console
    Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
    topology as the next hop for the Edge server. Failing over this pool may cause External
    access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
    change the Edge internal next hop setting to point to a different Front-end pool,  before you
    proceed.
    ```


## <a name="fail-back-a-pool"></a>Faire échouer un pool

Une fois que le pool ayant subi une défaillance est à nouveau en ligne (Pool1 dans cet exemple), procédez comme suit pour rétablir votre déploiement à un état de fonctionnement normal.

Le processus de récupération de l’échec prend plusieurs minutes. À référence, un pool de 20 000 utilisateurs devrait prendre jusqu’à 60 minutes.

Restaurez les utilisateurs qui étaient initialement hébergés dans Pool1 et qui ont été basculés vers Pool2 en tapant l’applet de commande suivante :

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

Aucune autre étape n’est nécessaire. Si vous avez échoué sur le serveur central de gestion, vous pouvez le laisser dans Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Faire échouer le pool edge utilisé pour la fédération Skype Entreprise Server’équipe 

Si le pool edge sur lequel la fédération Skype Entreprise Server configurée est en panne, vous devez modifier la fédération pour utiliser un autre pool edge pour que la fédération fonctionne.

1.  Sur le serveur frontal, ouvrez le Générateur de topologie. **Développez les pools** de serveurs Edge, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la fédération. Sélectionnez **Modifier les propriétés**.

2.  Dans **Modifier les propriétés**, sous **Général**, désactivez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**. Sélectionnez **OK**.

3.  **Développez les pools** de serveurs Edge, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge que vous souhaitez maintenant utiliser pour la fédération. Sélectionnez **Modifier les propriétés**.

4.  Dans **Modifier les propriétés**, sous **Général**, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**. Sélectionnez **OK**.

5.  Select **Action**, select **Topology**, select **Publish**. Lorsque vous y sont **invités sur Publier la topologie**, sélectionnez **Suivant**. Lorsque la publication est terminée, sélectionnez **Terminer**.

6.  Sur le serveur Edge, ouvrez l’Assistant Skype Entreprise Server déploiement. **Sélectionnez Installer ou mettre à Skype Entreprise Server système**, puis installer ou supprimer **Skype Entreprise Server composants**. **Sélectionnez Exécuter à nouveau**.

7.  Sélectionnez **Suivant**. L’écran récapitulatif affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, sélectionnez **Afficher le journal** pour afficher les fichiers journaux disponibles. **Sélectionnez Terminer** pour terminer le déploiement.
    
    Si le site contenant le pool edge défactuant contient des serveurs frontux qui sont toujours en cours d’exécution, vous devez mettre à jour le service de conférence Web et le service de conférence A/V sur ces pools Front-End pour utiliser un pool edge dans un site distant en cours d’exécution. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Faire échouer le pool edge utilisé pour la fédération XMPP dans Skype Entreprise Server 

Dans votre organisation, il existe un pool de serveurs Edge désigné en tant que pool à utiliser pour la fédération XMPP. Si ce pool tombe en panne, vous devez effectuer un basculement de la fédération XMPP et utiliser un autre pool de serveurs Edge pour permettre à la fédération XMPP de fonctionner à nouveau.

Quand vous installez des pools de serveurs Edge et que vous activez la fédération XMPP, vous pouvez simplifier le processus de récupération d’urgence en configurant des enregistrements SRV DNS externes pour tous les pools de serveurs Edge (au lieu d’un seul) de la fédération XMPP. Chacun de ces enregistrements SRV doit avoir une priorité distincte. Tout le trafic de la fédération XMPP passe par le pool dont l’enregistrement SRV a la priorité la plus élevée. 

Dans la procédure suivante, EdgePool1 est le pool, qui hébergeait à l’origine la fédération XMPP, et EdgePool2 le pool qui hébergera désormais la fédération XMPP.
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Pour faire échouer le pool edge utilisé pour la fédération XMPP

1.  Si vous n’avez pas encore déployé un autre pool edge (en plus de celui actuellement en panne), déployez ce pool. 

2.  Sur chaque serveur Edge du nouveau pool de serveurs Edge qui va héberger la fédération XMPP (EdgePool2), exécutez l’applet de commande suivante :

    ```powershell
    Stop-CsWindowsService
    ```

3.  Exécutez l’applet de commande suivante pour faire pointer à nouveau l’itinéraire de fédération XMPP vers EdgePool2 :

    ```powershell
    Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    ```
    
    Dans cet exemple, Site2 est le site contenant le pool de serveurs Edge qui va héberger l’itinéraire de fédération XMPP. EdgeServer2.contoso.com est le nom de domaine complet d’un serveur Edge de ce pool.

4.  Sur le serveur DNS externe, modifiez l’enregistrement DNS A afin que la fédération XMPP pointe vers EdgeServer2.contoso.com.

5.  Si vous n’avez pas encore d’enregistrement DNS SRV pour la fédération XMPP correspondant au pool de serveurs Edge qui va héberger la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant. La valeur du port de cet enregistrement SRV doit être 5269.

    ```console
    _xmpp-server._tcp.contoso.com
    ```

6.  Assurez-vous que le port externe 5269 du pool de serveurs Edge qui va héberger la fédération XMPP est ouvert.

7.  Démarrez les services de tous les serveurs Edge du pool de serveurs Edge qui va héberger la fédération XMPP :

    ```powershell
    Start-CsWindowsService
    ```

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Faire échouer le pool edge utilisé pour la fédération Skype Entreprise Server ou XMPP 

Après la restauration en ligne d’un pool Edge qui hébergeait la fédération, utilisez cette procédure pour restaurer l’itinéraire de fédération Skype Entreprise Server et/ou l’itinéraire de fédération XMPP pour utiliser à nouveau ce pool Edge restauré.

1.  Sur le pool Edge de nouveau disponible, lancez les Services Edge.

2.  Si vous souhaitez restaurer l’itinéraire Skype Entreprise Server de fédération pour utiliser le serveur Edge restauré, faites les choses suivantes :
    
    1. Sur le serveur frontal, ouvrez le Générateur de topologie. **Développez les pools de serveurs Edge**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la fédération. Sélectionnez **Modifier les propriétés**.
    
    1. Dans **Modifier les propriétés**, sous **Général**, désactivez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**. Sélectionnez **OK**.
    
    1. **Développez les pools de serveurs Edge**, puis cliquez avec le bouton droit sur le serveur Edge d’origine ou le pool de serveurs Edge que vous souhaitez à nouveau utiliser pour la fédération. Sélectionnez **Modifier les propriétés**.
    
    1. Dans **Modifier les propriétés**, sous **Général**, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**. Sélectionnez **OK**.
    
    1. Select **Action**, select **Topology**, select **Publish**. Lorsque vous y sont **invités sur Publier la topologie**, sélectionnez **Suivant**. Lorsque la publication est terminée, sélectionnez **Terminer**.
    
    1. Sur le serveur Edge, ouvrez l’Assistant Skype Entreprise Server déploiement. **Sélectionnez Installer ou mettre à jour Skype Entreprise Server système**, puis installer ou **supprimer Skype Entreprise Server composants**. **Sélectionnez Exécuter à nouveau**.
    
    1. Sélectionnez **Suivant**. L’écran récapitulatif affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, sélectionnez **Afficher le journal** pour afficher les fichiers journaux disponibles. **Sélectionnez Terminer** pour terminer le déploiement.

3.  Si vous voulez restaurer l’itinéraire de fédération XMPP pour utiliser le serveur Edge restauré, procédez comme suit :
    
    1. Exécutez la cmdlet suivante pour pointer de nouveau l’itinéraire de fédération XMPP sur le pool Edge qui héberge désormais la fédération XMPP (dans cet exemple, EdgeServer1) :
  
        ```powershell
        Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        ```
        
        Dans cet exemple, Site1 représente le site qui contient le pool Edge qui hébergera désormais l’itinéraire de fédération XMPP, et EdgeServer1.contoso.com représente le nom de domaine complet (FQDN) d’un serveur Edge de ce pool.
    
    1. Si vous n’avez pas encore d’enregistrement DNS SRV pour la fédération XMPP qui aboutit au pool Edge qui héberge désormais la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant. Cet enregistrement SRV doit avoir une valeur de port de 5269.

        ```console
        _xmpp-server._tcp.contoso.com
        ```
    
    1. Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.
    
    1. Vérifiez que le port 5269 du pool Edge qui héberge désormais la fédération XMPP est ouvert de façon externe.

4.  Si les pools frontaux ont continué à s’exécuter sur le site contenant le pool Edge qui a échoué et a été restauré, vous devez mettre à jour les services de conférence web et de conférence A/V sur ces pools frontaux pour réutiliser les pools Edge sur leur site local.

5.  Si le pool frontal du site où le pool Edge a échoué échoue également, vous pouvez désormais utiliser Invoke–CsPoolFailback pour restaurer le pool frontal.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Modifier le pool edge associé à un pool frontal

Si un pool de serveurs Edge est défaillant mais que le pool de serveurs frontaux du même site fonctionne encore, vous devrez définir le pool de serveurs frontaux pour qu’il utilise le pool de serveurs Edge d’un autre site jusqu’à ce que le pool de serveurs Edge défaillant soit restauré.

1.  Dans le Générateur de topologie, accédez au nom du pool de serveurs frontaux que vous devez changer.

2.  Cliquez avec le bouton droit sur le pool, puis sélectionnez **Modifier les propriétés**.

3.  Dans la section **Associations**, sous **Associer le pool de serveurs Edge (pour les composants multimédias)**, utilisez la zone de liste déroulante pour sélectionner le pool de serveurs Edge que vous voulez associer à ce pool de serveurs frontaux.

4.  Sélectionnez **OK**.
