---
title: Échec de retour plus, sinon un pool
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 23b70817ba75f3a0a6e73cc42a9df9026e17b2d7
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223506"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Échec de plus, sinon back un pool dans Skype pour Business Server 

Utilisez les procédures suivantes si un pool frontal unique a échoué et doit être basculé ou le pool ayant subi une défaillance est en ligne et que vous avez besoin de restaurer votre déploiement à l’état de fonctionnement normal. Également Découvrez comment réaliser le basculement et la restauration automatique du pool Edge utilisé pour Skype pour la fédération entreprise ou la fédération XMPP ou modifier le pool Edge associé à un pool frontal.

- [Faire basculer un pool frontal](#fail-over-a-front-end-pool)
- [Restauration d’un pool](#fail-back-a-pool)
- [Faire basculer le pool Edge utilisé pour Skype pour la fédération Business Server](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Basculement du pool Edge utilisé pour la fédération XMPP dans Skype pour Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Basculer le pool Edge utilisé pour Skype pour la fédération du serveur d’entreprise ou la fédération XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Changer le pool Edge associé à un pool frontal](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Faire basculer un pool frontal

Dans cette procédure, Datacenter1 contient Pool1 et Pool1 a échoué. Basculement vers Pool2 situé dans Datacenter2.

La plupart du travail pour le basculement de pool implique le basculement du magasin Central de gestion, si cela est nécessaire. Ceci est important parce que le magasin Central de gestion doit être fonctionnel lorsque les utilisateurs du pool sont basculées.

En outre, si un pool frontal échoue mais que le pool Edge sur le site est en cours d’exécution, vous devez savoir si le pool de serveurs Edge utilise le pool ayant échoué comme un pool du tronçon suivant. Si c’est le cas, vous devez modifier le pool Edge pour utiliser un autre pool frontal avant le basculement sur le pool frontal ayant échoué. Comment vous modifiez le paramètre du tronçon suivant dépend de si le bord utilise un pool sur le même site que le pool de serveurs Edge ou un autre site.

**Pour définir un pool de serveurs Edge à utiliser un pool du tronçon suivant sur le même site**

1.  Ouvrez le Générateur de topologie, avec le bouton droit le pool Edge qui doit être modifié, cliquez sur **Modifier les propriétés**.

2.  Cliquez sur le **tronçon suivant**. À partir de la **pool du tronçon suivant :** , sélectionnez le pool qui servira maintenant le pool du tronçon suivant.

3.  Cliquez sur **OK**, puis publiez les modifications.

**Pour définir un pool de serveurs Edge à utiliser un pool du tronçon suivant dans un autre site**

1.  Ouvrez un Skype pour fenêtre Business Server Management Shell et entrez l’applet de commande suivante :
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Pour faire basculer un pool en cas d’urgence**

1.  Recherchez le pool qui sert de l’hôte pour le serveur d’administration centrale en tapant l’applet de commande suivante sur un serveur frontal dans Pool2 :
    
        Invoke-CsManagementServerFailover -Whatif
    
    Les résultats de cette présentation de l’applet de commande quel pool héberge actuellement le serveur d’administration centrale. Dans le reste de cette procédure, ce pool est appelé CMS\_Pool.

2.  Utilisez le Générateur de topologie pour trouver la version de Skype pour Business Server s’exécutant sur le serveur CMS\_Pool. Si elle est en cours d’exécution Skype pour Business Server, utilisez l’applet de commande suivante pour rechercher le pool de sauvegarde du Pool 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Permettre la sauvegarde\_Pool est le pool de sauvegarde.

3.  Vérifier l’état du magasin Central de gestion avec l’applet de commande suivante :
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Cette applet de commande doit s’afficher que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet du serveur CMS\_Pool. S’ils sont vides, le serveur d’administration centrale n’est pas disponible et vous devez le faire basculer.

4.  Si le magasin Central de gestion n’est pas disponible ou si le magasin Central de gestion a été exécuté sur Pool1 (autrement dit, le pool qui a échoué), vous devez basculer sur le serveur de gestion centralisée avant le basculement vers le pool. Si vous avez besoin faire basculer le serveur de gestion centralisée qui était hébergée sur un pool en cours d’exécution Skype pour Business Server, utilisez l’applet de commande à l’étape 5 de cette procédure. Si vous n’avez besoin pas basculer sur le serveur d’administration centrale, passez à l’étape 7 de cette procédure.

5.  Pour faire basculer le magasin Central de gestion sur un pool en cours d’exécution Skype pour Business Server, procédez comme suit :
    
      - Vérifiez d’abord quel serveur principal sauvegarde\_Pool s’exécute l’instance principale du magasin Central de gestion en tapant ce qui suit :
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Si le serveur principal primaire dans sauvegarde\_Pool est le principal, type :
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Si le serveur principal sauvegarde miroir\_Pool est le principal, type :
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Vérifier que le basculement du serveur de gestion centralisée est terminé. Tapez ce qui suit :
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Vérifiez que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet de sauvegarde\_Pool.
    
      - Enfin, vérifiez le statut des réplicas pour tous les serveurs frontaux en tapant ce qui suit :
        
            Get-CsManagementStoreReplicationStatus 
        
        Vérifiez que tous les réplicas ont la valeur True.
        
        Passez à l’étape 7 de cette procédure.

6.  Installer le magasin Central de gestion sur le Back End Server de sauvegarde\_Pool.
    
      - Tout d’abord, exécutez la commande suivante :
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Exécutez la commande suivante sur un de la Front End serveurs de sauvegarde\_Pool pour forcer le déplacement du magasin Central de gestion :
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Valider le déplacement est terminé :
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Vérifiez que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet de sauvegarde\_Pool.
    
      - Vérifiez le statut des réplicas pour tous les serveurs frontaux en tapant ce qui suit :
        
            Get-CsManagementStoreReplicationStatus 
        
        Vérifiez que tous les réplicas ont la valeur True.
    
      - Installez le service de serveur de gestion centralisée sur le reste des serveurs frontaux dans sauvegarde\_Pool. Pour ce faire, exécutez la commande suivante sur tous les serveurs frontaux, sauf celle que vous avez utilisé pour forcer la gestion centralisée magasin déplacer plus haut dans cette procédure :
        
            Bootstrapper /Setup 

7.  Faire basculer les utilisateurs de Pool1 vers Pool2 en exécutant la cmdlet suivante dans un Skype pour fenêtre Business Server Management Shell :
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Les étapes effectuées dans les parties précédentes de cette procédure pour vérifier l’état du magasin Central de gestion n’étant pas universels, il est toujours un risque que cette applet de commande échouera car le magasin Central de gestion pas encore totalement de basculement. Dans ce cas, vous devez corriger le magasin Central de gestion basé sur les messages d’erreur que vous voyez et puis réexécuter cette applet de commande.
    
    Si vous voyez le message d’erreur suivant, vous devez modifier le pool Edge sur ce site à utiliser un autre pool comme son tronçon suivant avant le basculement sur le pool. Pour plus d’informations, voir les procédures au début de cette rubrique.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Restauration d’un pool

Une fois que le pool ayant subi une défaillance est en ligne (Pool1 dans cet exemple), procédez comme suit pour restaurer votre déploiement à l’état de fonctionnement normal.

Notez que le processus de basculement prend plusieurs minutes à effectuer.À titre de référence, il devrait prendre jusqu’à 60 minutes pour un pool de 20 000 utilisateurs.

Restaurez les utilisateurs qui étaient initialement hébergés dans Pool1 et ont été basculés vers Pool2 en tapant l’applet de commande suivante :
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Aucun autres étapes ne sont nécessaires. Si vous n’avez pas sur le serveur d’administration centrale, vous pouvez le laisser dans Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Faire basculer le pool Edge utilisé pour Skype pour la fédération Business Server 

Si le pool Edge où vous avez Skype pour la fédération Business Server configurée tombe en panne, vous devez modifier la fédération pour utiliser un autre pool Edge pour la fédération fonctionne.

1.  Sur un serveur frontal, ouvrez le Générateur de topologie. Développez **pools de serveurs Edge**, puis cliquez sur le serveur Edge ou le pool de serveurs Edge qui est actuellement configuré pour la fédération. Sélectionnez **Modifier les propriétés**.

2.  Dans **Modifier les propriétés** , sous **Général**, désactivez **Activer la fédération pour ce pool Edge (Port 5061)**. Cliquez sur **OK**.

3.  Développez **pools de serveurs Edge**, puis cliquez sur le serveur Edge ou le pool de serveurs Edge que vous souhaitez utiliser pour la fédération. Sélectionnez **Modifier les propriétés**.

4.  Dans **Modifier les propriétés** , sous **Général**, sélectionnez **Activer la fédération pour ce pool Edge (Port 5061)**. Cliquez sur **OK**.

5.  Cliquez sur **Action**, sélectionnez **la topologie**, sélectionnez **Publier**. Lorsque vous y êtes invité sur **publier la topologie**, cliquez sur **suivant**. Lorsque la publication est terminée, cliquez sur **Terminer**.

6.  Sur le serveur de périphérie, ouvrez le Skype pour l’Assistant de déploiement de serveur d’entreprise. Cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**, puis cliquez sur **installer ou supprimer des Skype pour les composants de serveur d’entreprise**. Cliquez sur **réexécuter**.

7.  Cliquez sur **Suivant**. L’écran Résumé affiche les actions quand elles sont exécutées. Une fois le déploiement est terminé, cliquez sur **Afficher le journal** pour afficher les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.
    
    Si le site contenant le pool Edge ayant échoué contient les serveurs frontaux qui sont en cours d’exécution, vous devez mettre à jour le Service de conférence Web et A / V de Service de conférence sur ces pools frontaux à utiliser un pool de serveurs Edge dans un à distance de sites qui est toujours en cours d’exécution. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Basculement du pool Edge utilisé pour la fédération XMPP dans Skype pour Business Server 

Dans votre organisation, il existe un pool de serveurs Edge désigné en tant que le pool à utiliser pour la fédération XMPP. Si ce pool tombe en panne, vous devez basculer vers la fédération XMPP pour utiliser un autre pool Edge avant la fédération XMPP peut fonctionner à nouveau.

Lors de la première installation de pools de serveurs Edge et activer la fédération XMPP, vous pouvez simplifier le processus de récupération d’urgence en configurant les enregistrements SRV DNS externes pour tous vos pools Edge pour la fédération XMPP, au lieu d’un seul. Chacun de ces enregistrements SRV doit avoir une priorité différente défini. Tout le trafic de fédération XMPP accède par le biais du pool dont l’enregistrement SRV avec la priorité la plus élevée. 

Dans la procédure suivante, EdgePool1 est le pool qui hébergeait à l’origine de la fédération XMPP et EdgePool2 est le pool qui va héberger la fédération XMPP.


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Pour faire basculer le pool Edge utilisé pour la fédération XMPP

1.  Si vous ne disposez pas d’un autre pool de serveurs Edge déployé (en plus de celui qui est actuellement vers le bas), déployer ce pool. 

2.  Sur chaque serveur Edge du nouveau pool Edge qui va héberger la fédération XMPP (EdgePool2), exécutez l’applet de commande suivante :
    
        Stop-CsWindowsService

3.  Exécutez la cmdlet suivante pour faire pointer à nouveau l’itinéraire de fédération XMPP vers EdgePool2 :
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    Dans cet exemple, Site2 est le site contenant le pool Edge qui va héberger l’itinéraire de fédération XMPP et EdgeServer2.contoso.com est le nom de domaine complet d’un serveur Edge de ce pool.

4.  Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la fédération XMPP vers EdgeServer2.contoso.com.

5.  Si vous n’avez pas déjà un enregistrement DNS SRV pour la fédération XMPP qui correspond au pool Edge qui va héberger la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant. Cet enregistrement SRV doit avoir la valeur port 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Vérifiez que le pool Edge qui va héberger la fédération XMPP a port 5269 open en externe.

7.  Démarrer les services sur tous les serveurs Edge du pool Edge qui va héberger la fédération XMPP :
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Basculer le pool Edge utilisé pour Skype pour la fédération du serveur d’entreprise ou la fédération XMPP 

Après un échec Edge pool utilisé pour la fédération hôte a été remis en ligne, utilisez cette procédure pour basculer le Skype pour l’itinéraire de fédération Business Server et/ou l’itinéraire de fédération XMPP pour réutiliser ce pool Edge restauré.

1.  Sur le pool Edge qui est maintenant à nouveau disponible, démarrer les Services de périphérie.

2.  Si vous voulez restaurer le Skype pour l’itinéraire de fédération Business Server afin d’utiliser le serveur Edge restauré, procédez comme suit :
    
      - Sur un serveur frontal, ouvrez le Générateur de topologie. Développez **pools de serveurs Edge**, puis avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge qui est actuellement configuré pour la fédération. Sélectionnez **Modifier les propriétés**.
    
      - Dans **Modifier les propriétés** , sous **Général**, désactivez **Activer la fédération pour ce pool Edge (Port 5061)**. Cliquez sur **OK**.
    
      - Développez **pools de serveurs Edge**, puis avec le bouton droit sur le serveur de périphérie d’origine ou d’un pool de serveurs Edge que vous souhaitez à nouveau utiliser pour la fédération. Sélectionnez **Modifier les propriétés**.
    
      - Dans **Modifier les propriétés** , sous **Général**, sélectionnez **Activer la fédération pour ce pool Edge (Port 5061)**. Cliquez sur **OK**.
    
      - Cliquez sur **Action**, sélectionnez **la topologie**, sélectionnez **Publier**. Lorsque vous y êtes invité sur **publier la topologie**, cliquez sur **suivant**. Lorsque la publication est terminée, cliquez sur **Terminer**.
    
      - Sur le serveur de périphérie, ouvrez le Skype pour l’Assistant de déploiement de serveur d’entreprise. Cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**, puis cliquez sur **installer ou supprimer des Skype pour les composants de serveur d’entreprise**. Cliquez sur **réexécuter**.
    
      - Cliquez sur **Suivant**. L’écran Résumé affiche les actions quand elles sont exécutées. Une fois le déploiement est terminé, cliquez sur **Afficher le journal** pour afficher les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.

3.  Si vous voulez restaurer l’itinéraire de fédération XMPP pour utiliser le serveur Edge restauré, procédez comme suit :
    
      - Exécutez la cmdlet suivante pour faire pointer à nouveau l’itinéraire de fédération XMPP vers le pool Edge qui va héberger la fédération XMPP (dans cet exemple, EdgeServer1) :
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        Dans cet exemple, Site1 est le site contenant le pool Edge qui va héberger l’itinéraire de fédération XMPP et EdgeServer1.contoso.com est le nom de domaine complet d’un serveur Edge de ce pool.
    
      - Si vous n’avez pas déjà un enregistrement DNS SRV pour la fédération XMPP qui correspond au pool Edge qui va héberger la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant. Cet enregistrement SRV doit avoir la valeur port 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la fédération XMPP vers EdgeServer2.contoso.com.
    
      - Vérifiez que le pool Edge qui va héberger la fédération XMPP a port 5269 open en externe.

4.  Si les pools frontaux est resté en cours d’exécution dans le site contenant le pool Edge qui a échoué et a été restauré, vous devez mettre à jour le Service de conférence Web et A / V Conferencing Service sur ces Front-End pools à utiliser à nouveau les pools de serveurs Edge sur leur site local.

5.  Si le pool frontal sur le même site en tant que le pool Edge a échoué échoue également, vous pouvez maintenant utiliser Invoke – CsPoolFailback pour basculer le pool frontal.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Changer le pool Edge associé à un pool frontal

Si un pool Edge tombe en panne mais le pool frontal sur le même site est en cours d’exécution, vous devez définir le pool frontal à utiliser un pool de serveurs Edge à un autre site jusqu'à ce que le pool Edge ayant échoué est restauré.

1.  Dans le Générateur de topologie, accédez au nom du pool frontal que vous souhaitez modifier.

2.  Avec le bouton droit de la liste, puis cliquez sur **Modifier les propriétés**.

3.  Dans la section **Associations** , sous **Associer un Pool Edge (pour les composants médias)**, utilisez la liste déroulante pour sélectionner le pool Edge que vous souhaitez associer ce pool frontal avec.

4.  Cliquez sur **OK**.