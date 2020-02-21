---
title: 'Lync Server 2013 : basculement de serveur de conversation permanente'
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
ms.openlocfilehash: 570ed42bb2ff1d5b1f4ab58e9bbd9aad9159bef3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Basculement du serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-05_

Le basculement pour le serveur de conversation permanente est conçu pour être principalement un processus manuel.

La procédure de basculement est basée sur l’hypothèse que le centre de données secondaire est en cours d’exécution, mais que les services de serveur de conversation permanente où se trouve la base de données de conversation permanente principale sont totalement indisponibles, notamment les suivants :

  - La base de données principale du serveur de conversation permanente et la base de données miroir du serveur de conversation permanente sont inactives.

  - Le serveur frontal Lync Server est inactif.

La procédure consiste en deux étapes de base :

  - Récupérez la base de données de conversation permanente principale (MGC).

  - Établir la mise en miroir pour la nouvelle base de données principale.

La base de données de conformité de conversation permanente (mgccomp) n’est pas basculée. Le contenu de cette base de données est temporaire et purgé au fur et à mesure que l’adaptateur de conformité traite les données. Il est de votre responsabilité, en tant qu’administrateur de conversation permanente, de gérer correctement la sortie de l’adaptateur afin d’éviter toute perte de données.

<div>

## <a name="to-fail-over-persistent-chat-server"></a>Pour basculer le serveur de conversation permanente

1.  Supprimez l’envoi de journaux de la base de données de copie des journaux de sauvegarde du serveur de conversation permanente.
    
    1.  À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données où se trouve la base de données MGC de sauvegarde du serveur de conversation permanente.
    
    2.  Ouvrez une fenêtre de requête pour la base de données principale.
    
    3.  Utilisez la commande suivante pour annuler la copie des journaux de transaction :
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Copiez tous les fichiers de sauvegarde non copiés se trouvant sur le partage de sauvegarde vers le dossier de destination de la copie du serveur de sauvegarde.

3.  Appliquez dans l’ordre toutes les sauvegardes du journal des transactions non appliquées à la base de données secondaire. Pour plus d’informations, consultez la rubrique « Procédure : appliquer une sauvegarde du journal des transactions (Transact https://go.microsoft.com/fwlink/p/?linkid=247428-SQL) » à l’adresse.

4.  Mettez en ligne la base de données mgc de sauvegarde. Dans la fenêtre de requête ouverte à l’étape 1b, procédez comme suit :
    
    1.  Mettez fin à toutes les connexions à la base de données mgc, le cas échéant :
        
        1.  **Exec SP\_WHO2** pour identifier les connexions à la base de données MGC.
        
        2.  **Kill \<SPID\> ** pour mettre fin à ces connexions.
    
    2.  Mettez en ligne la base de données :
        
        1.  **restaurer la base de données MGC avec récupération**.

5.  Dans Lync Server Management Shell, utilisez la commande **Set-CsPersistentChatState-Identity "service : ATL-CS-001.litwareinc.com" – PoolState FailedOver** pour basculer vers la base de données de sauvegarde MGC. N’oubliez pas de remplacer le nom de domaine complet de votre pool de conversations permanentes par atl-cs-001.litwareinc.com.
    
    La base de données mgc de sauvegarde est désormais la base de données principale.

6.  Dans Lync Server Management Shell, utilisez l’applet de commande **install-CsMirrorDatabase** pour établir un miroir de haute disponibilité pour la base de données de sauvegarde qui sert désormais de base de données principale. Utilisez l’instance de la base de données de sauvegarde en tant que base de données principale et l’instance de la base de données miroir de sauvegarde en tant qu’instance miroir. Il ne s’agit pas du même miroir que celui qui a été initialement configuré pour la base de données principale pendant la configuration. Pour plus d’informations, reportez-vous à la section « utilisation des applets de commande Lync Server Management Shell » dans [Deploying SQL Mirroring for back end Server High Availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Définissez les serveurs actifs du serveur de conversation permanente. À partir de l’interface de commande de Lync Server, utilisez la cmdlet **Set-applet cspersistentchatactiveserver** pour définir la liste des serveurs actifs.
    
    <div>
    

    > [!IMPORTANT]  
    > Tous les serveurs actifs doivent être situés dans le même centre de données que celui de la nouvelle base de données principale, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.

    
    </div>
    
    À ce stade, le basculement de la base de données principale du serveur de conversation permanente vers la base de données de sauvegarde du serveur de conversation permanente se termine avec succès.

</div>

</div>

<span> </span>

</div>

</div>

</div>

