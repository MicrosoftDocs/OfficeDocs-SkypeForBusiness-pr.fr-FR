---
title: Basculement ou restauration d’un pool
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: f2a1970df43aa2fb7becb03319ee6ff5934afe0a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991799"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Échec et reprise d’un regroupement dans Skype entreprise Server 

Appliquez les procédures suivantes si un pool frontal unique a échoué et qu’il doit être en échec, ou si le pool ayant rencontré le désastre est en ligne et que vous devez rétablir le fonctionnement normal de votre déploiement. Apprenez-en plus sur le basculement et le basculement du pool Edge utilisé pour la Fédération Skype entreprise ou XMPP, ou changez le pool de périphériques associés à un pool frontal.

- [Basculer sur un pool frontal](#fail-over-a-front-end-pool)
- [Restauration d’un pool](#fail-back-a-pool)
- [Basculer vers le pool Edge utilisé pour la Fédération de Skype entreprise Server](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Basculer vers le pool Edge utilisé pour la Fédération XMPP dans Skype entreprise Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Restauration de la liste détourée utilisée pour Skype entreprise Server Federation ou XMPP Federation](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Changer le pool de frontière associé à un pool frontal](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Basculer sur un pool frontal

Dans cette procédure, Datacenter1 contient Pool1 et Pool1 a échoué. Vous basculez vers Pool2 situé dans Datacenter2.

La majeure partie du fonctionnement du basculement de pool implique un échec du magasin de gestion central, si nécessaire. C’est important, car le magasin de gestion centralisée doit être opérationnel lorsque les utilisateurs du pool ont échoué.

De plus, si un pool frontal tombe en panne mais que le pool Edge sur ce site est toujours en cours d’exécution, vous devez savoir si le pool d’applications de périmètre utilise le pool en échec en tant que pool de prochains tronçons. Si tel est le cas, vous devez modifier le pool Edge pour utiliser un autre pool frontal avant de basculer sur le pool frontal défectueux. La façon dont vous modifiez le paramètre de saut suivant dépend de la façon dont le bord utilise un pool sur le même site que le pool de périphérie ou un site différent.

**Pour définir un pool de bords pour utiliser un pool de sauts suivant sur le même site**

1.  Ouvrez le générateur de topologie, cliquez avec le bouton droit sur le pool de bords qui doit être modifié, puis cliquez sur **modifier les propriétés**.

2.  Cliquez sur **tronçon suivant**. À partir de la liste **pool de prochains tronçons :** , sélectionnez le pool qui fera désormais Office de réserve de prochains tronçon.

3.  Cliquez sur **OK**, puis publiez les modifications.

**Pour définir un pool de bords pour utiliser un pool de sauts suivant sur un autre site**

1.  Ouvrez une fenêtre Skype entreprise Server Management Shell et tapez l’applet de commande suivante :
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Pour basculer sur un pool en cas de sinistre**

1.  Recherchez quel pool est l’hôte du serveur de gestion central en tapant l’applet de commande suivante sur un serveur frontal dans Pool2 :
    
        Invoke-CsManagementServerFailover -Whatif
    
    Les résultats de cette applet de requête indiquent le pool qui héberge actuellement le serveur de gestion central. Dans le reste de cette procédure, ce pool est appelé pool CMS\_.

2.  Utilisez le générateur de topologie pour rechercher la version de Skype entreprise Server en cours d’exécution\_sur le pool CMS. S’il s’agit de Skype entreprise Server, utilisez l’applet de commande suivante pour trouver le pool de sauvegarde du pool 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Laissez le\_pool de sauvegarde être le pool de sauvegarde.

3.  Vérifiez l’état du magasin central de gestion avec l’applet de commande suivante :
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Cette applet de cmdlet doit indiquer que ActiveMasterFQDN et ActiveFileTransferAgents sont dirigés vers le nom\_de domaine complet du pool CMS. S’il est vide, le serveur de gestion central n’est pas disponible et vous devez le basculer.

4.  Si le magasin de gestion central n’est pas disponible ou si la Banque de gestion centrale s’exécutait sur Pool1 (autrement dit, le pool ayant échoué), vous devez faire basculer le serveur de gestion central avant de basculer sur le pool. Si vous avez besoin de basculer sur le serveur de gestion central hébergé sur un pool exécutant Skype entreprise Server, utilisez l’applet de demande à l’étape 5 de cette procédure. Si vous n’avez pas besoin de basculer sur le serveur de gestion central, passez à l’étape 7 de cette procédure.

5.  Pour faire basculer le magasin de gestion central sur un pool exécutant Skype entreprise Server, procédez comme suit :
    
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

7.  Basculez les utilisateurs de Pool1 à Pool2 en exécutant l’applet de commande suivante dans une fenêtre Skype entreprise Server Management Shell :
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Dans la mesure où les étapes décrites dans les parties précédentes de cette procédure permettent de vérifier que l’état du magasin de gestion central n’est pas universel, il est possible que cette applet de connexion échoue, car le magasin central de gestion n’a pas encore été complètement en échec. Dans ce cas, vous devez résoudre le magasin de gestion central en fonction des messages d’erreur qui s’affichent, puis réexécuter cette cmdlet.
    
    Si vous voyez le message d’erreur suivant, vous devez modifier le pool de périphérie sur ce site pour utiliser un autre pool comme tronçon suivant avant d’avoir basculé sur le pool. Pour plus d’informations, reportez-vous aux procédures au début de cette rubrique.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Restauration d’un pool

Une fois que le regroupement qui a expérimenté le désastre est en ligne (à savoir Pool1 dans cet exemple), procédez comme suit pour restaurer le statut de travail normal de votre déploiement.

Notez que le processus de restauration automatique prend quelques minutes.À titre de référence, il devrait prendre jusqu’à 60 minutes pour un pool de 20 000 utilisateurs.

Restaurez les utilisateurs qui ont été initialement hébergés dans Pool1 et qui ont échoué sur Pool2 en tapant l’applet de commande suivante :
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Aucune autre étape n’est nécessaire. Si vous avez échoué sur le serveur de gestion central, vous pouvez le laisser dans Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Basculer vers le pool Edge utilisé pour la Fédération de Skype entreprise Server 

Si le pool de périphériques sur lequel vous avez configuré la Fédération de Skype entreprise Server s’affiche, vous devez modifier la Fédération de manière à utiliser un pool de périphérie différent pour que la Fédération fonctionne.

1.  Sur un serveur frontal, ouvrez le générateur de topologie. Développez **pools de bords**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la Fédération. Sélectionnez **modifier les propriétés**.

2.  Dans **modifier les propriétés** sous **général**, décochez **la case Activer la Fédération pour ce pool de périphériques (port 5061)**. Cliquez sur **OK**.

3.  Développez **pools de bords**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge que vous voulez utiliser pour la Fédération. Sélectionnez **modifier les propriétés**.

4.  Dans **modifier les propriétés** sous **général**, sélectionnez **activer la Fédération pour ce pool Edge (port 5061)**. Cliquez sur **OK**.

5.  Cliquez sur **action**, sélectionnez **topologie**, puis **publier**. Lorsque le système vous **le**demande, cliquez sur **suivant**. Lorsque la publication est terminée, cliquez sur **Terminer**.

6.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Skype entreprise Server. Cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, puis cliquez sur **configurer ou supprimer les composants Skype entreprise Server**. Cliquez de **nouveau sur exécuter**.

7.  Cliquez sur **Suivant**. L’écran de synthèse indique les actions à mesure qu’elles sont exécutées. Lorsque le déploiement est effectué, cliquez sur **afficher le journal** pour afficher les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.
    
    Si le site contenant le pool de périphériques en échec contient des serveurs frontaux qui sont toujours en cours d’exécution, vous devez mettre à jour les services de conférence Web et de conférence A/V sur ces pools frontal pour qu’ils utilisent un pool de bords sur un site distant qui est toujours en cours d’exécution. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Basculer vers le pool Edge utilisé pour la Fédération XMPP dans Skype entreprise Server 

Dans votre organisation, il existe un pool Edge désigné comme pool à utiliser pour la Fédération XMPP. Si ce pool est vers le bas, vous devez le faire basculer sur la Fédération XMPP pour utiliser un pool Edge différent avant que la Fédération XMPP puisse fonctionner de nouveau.

Lorsque vous installez les pools de périphérie et activez la Fédération XMPP, vous pouvez simplifier le processus de reprise après sinistre en configurant des enregistrements SRV DNS externes pour tous vos pools de périphérie pour la Fédération XMPP, au lieu d’une seule. Chacun de ces enregistrements SRV doit avoir un ensemble de priorités différent. Tout le trafic de Fédération XMPP traverse le pool avec l’enregistrement SRV dont la priorité est la plus élevée. 

Dans la procédure ci-dessous, EdgePool1 est le pool qui a hébergé la Fédération XMPP et EdgePool2 est le pool qui héberge désormais la Fédération de XMPP.


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Pour faire basculer le pool Edge utilisé pour la Fédération XMPP

1.  Si vous n’avez pas encore déployé un pool Edge (en plus de celui qui est actuellement disponible), vous devez déployer ce pool. 

2.  Sur chaque serveur Edge du nouveau pool de périphériques Edge qui hébergera maintenant la Fédération de XMPP (EdgePool2), exécutez l’applet de commande suivante :
    
        Stop-CsWindowsService

3.  Exécutez l’applet de commande suivante pour rediriger l’itinéraire de Fédération XMPP vers EdgePool2 :
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    Dans cet exemple, site2 est le site contenant le pool de bords qui héberge désormais l’itinéraire de Fédération XMPP et EdgeServer2.contoso.com est le nom de domaine complet d’un serveur Edge dans ce pool.

4.  Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la Fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.

5.  Si vous ne disposez pas encore d’un enregistrement DNS SRV pour la Fédération XMPP qui se résout au pool de périphérie qui hébergera maintenant la Fédération de XMPP, vous devez l’ajouter, comme dans l’exemple ci-dessous. Cet enregistrement SRV doit avoir une valeur de port de 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Assurez-vous que le pool de bords qui hébergera désormais la Fédération XMPP dispose d’une ouverture externe du port 5269.

7.  Démarrez les services sur tous les serveurs Edge du pool Edge qui hébergeront désormais la Fédération XMPP :
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Restauration de la liste détourée utilisée pour Skype entreprise Server Federation ou XMPP Federation 

Après le rétablissement d’un pool de périphériques inactif utilisé pour la Fédération d’hébergement en ligne, procédez comme suit pour restaurer le routage de la Fédération Skype entreprise Server et/ou l’itinéraire de Fédération XMPP pour qu’il utilise de nouveau ce pool de périphériques restaurés.

1.  Sur le pool Edge qui est désormais disponible, démarrez les services Edge.

2.  Si vous souhaitez remettre en échec l’itinéraire de la Fédération Skype entreprise Server afin qu’il utilise le serveur Edge restauré, procédez comme suit :
    
      - Sur un serveur frontal, ouvrez le générateur de topologie. Développez **pools de bords**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la Fédération. Sélectionnez **modifier les propriétés**.
    
      - Dans **modifier les propriétés** sous **général**, décochez **la case Activer la Fédération pour ce pool de périphériques (port 5061)**. Cliquez sur **OK**.
    
      - Développez **pools de bords**, puis cliquez avec le bouton droit sur le serveur Edge d’origine ou sur le pool de serveurs Edge que vous souhaitez utiliser pour la Fédération. Sélectionnez **modifier les propriétés**.
    
      - Dans **modifier les propriétés** sous **général**, sélectionnez **activer la Fédération pour ce pool Edge (port 5061)**. Cliquez sur **OK**.
    
      - Cliquez sur **action**, sélectionnez **topologie**, puis **publier**. Lorsque le système vous **le**demande, cliquez sur **suivant**. Lorsque la publication est terminée, cliquez sur **Terminer**.
    
      - Sur le serveur Edge, ouvrez l’Assistant Déploiement de Skype entreprise Server. Cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, puis cliquez sur **configurer ou supprimer les composants Skype entreprise Server**. Cliquez de **nouveau sur exécuter**.
    
      - Cliquez sur **Suivant**. L’écran de synthèse indique les actions à mesure qu’elles sont exécutées. Lorsque le déploiement est effectué, cliquez sur **afficher le journal** pour afficher les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.

3.  Si vous souhaitez restaurer l’itinéraire de la Fédération XMPP de manière à utiliser le serveur de périphérie de restauration, procédez comme suit :
    
      - Exécutez l’applet de commande suivante pour rediriger l’itinéraire de Fédération XMPP vers le pool Edge qui hébergera maintenant la Fédération de XMPP (dans cet exemple, EdgeServer1) :
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        Dans cet exemple, site1 est le site contenant le pool de bords qui héberge désormais l’itinéraire de Fédération XMPP et EdgeServer1.contoso.com est le nom de domaine complet d’un serveur Edge dans ce pool.
    
      - Si vous ne disposez pas encore d’un enregistrement DNS SRV pour la Fédération XMPP qui se résout au pool de périphérie qui hébergera maintenant la Fédération de XMPP, vous devez l’ajouter, comme dans l’exemple ci-dessous. Cet enregistrement SRV doit avoir une valeur de port de 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la Fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.
    
      - Assurez-vous que le pool de bords qui hébergera désormais la Fédération XMPP dispose d’une ouverture externe du port 5269.

4.  Si le pool frontal restait en cours d’exécution sur le site contenant le pool de périphériques ayant échoué et a été restauré, vous devez mettre à jour les services de conférence Web et de service de conférence A/V sur ces pools frontal pour pouvoir utiliser les pools de périphérie sur leur site local.

5.  Si le pool frontal sur le même site que le pool d’échecs en panne ne fonctionne pas, vous pouvez désormais utiliser Invoke-CsPoolFailback pour restaurer le pool frontal.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Changer le pool de frontière associé à un pool frontal

Si un pool de bords est en panne alors que le pool frontal sur le même site est toujours en cours d’exécution, vous devez définir le pool frontal pour qu’il utilise un pool de bords sur un autre site jusqu’à ce que le pool de frontière en panne soit restauré.

1.  Dans le générateur de topologie, accédez au nom de la réserve frontale que vous devez modifier.

2.  Cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.

3.  Dans la section **associations** , sous **associer le pool de bords (pour les composants multimédias)**, utilisez la zone de liste déroulante pour sélectionner le pool de bords avec lequel vous voulez associer ce pool frontal.

4.  Cliquez sur **OK**.
