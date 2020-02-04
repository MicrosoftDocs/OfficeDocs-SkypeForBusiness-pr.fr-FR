---
title: 'Lync Server 2013 : Basculement vers un serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd62d4037ae1795a553d207cb698f88f9b3b8ab8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Basculement vers un serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-05_

Le basculement pour le serveur de chat permanent est conçu pour être essentiellement un processus manuel.

La procédure de basculement repose sur l’hypothèse que le centre de données secondaire est opérationnel et qu’il est en cours d’exécution, mais les services serveur de chat permanent dans lesquels réside la base de données de chat permanent principal sont entièrement indisponibles, y compris les suivantes :

  - La base de données principale de chat serveur et la base de données miroir du serveur de chat permanent sont inversées.

  - Le serveur frontal de Lync Server est arrêté.

La procédure consiste en deux étapes de base :

  - Récupérez la base de données de chat persistante principale (MGC).

  - Établir la mise en miroir pour la nouvelle base de données principale.

La base de données de compatibilité des conversations permanentes (mgccomp) n’a pas pu être lancée. Le contenu de cette base de données est temporaire et purgé au fur et à mesure que l’adaptateur de conformité traite les données. Il est de votre responsabilité, en tant qu’administrateur de chat permanent, de gérer correctement la sortie de la carte pour éviter la perte de données.

<div>

## <a name="to-fail-over-persistent-chat-server"></a>Pour basculer vers un serveur de chat permanent

1.  Supprimez l’envoi de journaux de la base de données d’envoi de journaux de sauvegarde du serveur Chat permanent.
    
    1.  À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données dans laquelle réside la base de données de sauvegarde serveur de chat MGC.
    
    2.  Ouvrez une fenêtre de requête pour la base de données principale.
    
    3.  Utilisez la commande suivante pour annuler la copie des journaux de transaction :
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Copiez tous les fichiers de sauvegarde non copiés se trouvant sur le partage de sauvegarde vers le dossier de destination de la copie du serveur de sauvegarde.

3.  Appliquez dans l’ordre toutes les sauvegardes du journal des transactions non appliquées à la base de données secondaire. Pour plus d’informations, consultez la section « Procédure : appliquer une sauvegarde du journal des transactions (Transact http://go.microsoft.com/fwlink/p/?linkid=247428-SQL) » à l’adresse.

4.  Mettez en ligne la base de données mgc de sauvegarde. Dans la fenêtre de requête ouverte à l’étape 1b, procédez comme suit :
    
    1.  Mettez fin à toutes les connexions à la base de données mgc, le cas échéant :
        
        1.  **Exec SP\_WHO2** identifiant les connexions de la base de données MGC.
        
        2.  **Arrêtez \<le\> SPID** pour terminer ces connexions.
    
    2.  Mettez en ligne la base de données :
        
        1.  **restaurer la base de données mgc avec récupération**.

5.  Dans Lync Server Management Shell, utilisez la commande **Set-CsPersistentChatState-Identity « service : ATL-CS-001.litwareinc.com » – PoolState FailedOver** pour basculer vers la base de données de sauvegarde MGC. Veillez à remplacer le nom de domaine complet de votre pool de conversation permanente par atl-cs-001.litwareinc.com.
    
    La base de données mgc de sauvegarde est désormais la base de données principale.

6.  Dans Lync Server Management Shell, vous pouvez utiliser l’applet de passe **install-CsMirrorDatabase** pour établir un miroir haute disponibilité pour la base de données de sauvegarde, qui sert désormais de base de données principale. Utilisez l’instance de la base de données de sauvegarde en tant que base de données principale et l’instance de la base de données miroir de sauvegarde en tant qu’instance miroir. Il ne s’agit pas du même miroir que celui qui a été initialement configuré pour la base de données principale pendant la configuration. Pour plus d’informations, reportez-vous à la section « utilisation des cmdlets Lync Server Management Shell » du [déploiement de la mise en miroir SQL pour la haute disponibilité du serveur principal dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Définissez les serveurs actifs de chat permanent serveur. À partir de l’interpréteur de commandes de Lync Server, utilisez l’applet de commande **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.
    
    <div>
    

    > [!IMPORTANT]  
    > Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.

    
    </div>
    
    À ce stade, le basculement de la base de données principale du serveur Chat permanent vers la base de données de sauvegarde du serveur Chat permanent s’effectue correctement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

