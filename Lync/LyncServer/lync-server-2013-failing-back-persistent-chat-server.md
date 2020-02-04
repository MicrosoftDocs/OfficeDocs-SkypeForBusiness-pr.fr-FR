---
title: 'Lync Server 2013 : Restauration d’un serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca00a71c88b917b9e59f2e9039e7960b51f64157
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>Restauration d’un serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-05_

Cette procédure décrit les étapes nécessaires à la récupération d’une défaillance du serveur de chat permanent et à la restauration d’opérations à partir du centre de données principal.

Lors de l’échec du serveur Chat permanent, le centre de données principal est en panne, et les bases de données principales et miroirs deviennent indisponibles. Le centre de données principal bascule vers le serveur de sauvegarde.

La procédure suivante rétablit le fonctionnement normal une fois le centre de données principal sauvegardé et les serveurs reconstruits. Cette procédure part du principe que le centre de données principal a été restauré à partir d’une panne totale et que la base de données MGC et la base de données mgccomp ont été recréées puis réinstallées à l’aide du générateur de topologie.

Cette procédure part du principe qu’aucun nouveau serveur miroir et de sauvegarde n’a été déployé pendant la période de basculement, et que le seul serveur déployé est le serveur de sauvegarde et son serveur miroir, comme cela a été défini dans [échec du serveur de conversation permanent dans Lync server 2013](lync-server-2013-failing-over-persistent-chat-server.md).

Ces étapes visent à récupérer la configuration telle qu’elle existait avant la défaillance, cette dernière ayant provoqué le basculement du serveur principal vers le serveur de sauvegarde.

<div>

## <a name="to-fail-back-persistent-chat-server"></a>Pour restaurer le serveur de conversation persistante

1.  Effacez tous les serveurs de la liste de serveurs actifs de chat permanent `Set-CsPersistentChatActiveServer` du serveur à l’aide de l’applet de contrôle de Lync Server Management Shell. Cela a pour fin la connexion à la base de données MGC et de la base de données mgccomp lors du retour arrière.
    
    <div>
    

    > [!IMPORTANT]  
    > L’agent SQL Server sur le serveur principal de chat permanent du serveur principal doit être en cours d’exécution sous un compte privilégié. Plus précisément, le compte doit disposer des droits suivants : 
    > <UL>
    > <LI>
    > <P>Accès en lecture au partage réseau dans lequel les sauvegardes sont placées</P>
    > <LI>
    > <P>Accès en écriture au répertoire local spécifique vers lequel les sauvegardes sont copiées</P></LI></UL>

    
    </div>

2.  Désactivez la mise en miroir sur la base de données mgc de sauvegarde :
    
    1.  À l’aide de SQL Server Management Studio, connectez-vous à l’instance Backup MGC.
    
    2.  Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Miroir**.
    
    3.  Cliquez sur **Supprimer la mise en miroir**.
    
    4.  Cliquez sur **OK**.
    
    5.  Procédez de la même façon avec la base de données mgccomp.

3.  Sauvegardez la base de données mgc afin qu’elle puisse être restaurée vers la nouvelle base de données primaire :
    
    1.  À l’aide de SQL Server Management Studio, connectez-vous à l’instance Backup MGC.
    
    2.  Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**. La boîte de dialogue **Sauvegarder la base de données** s’affiche.
    
    3.  Dans **Type de sauvegarde**, sélectionnez **Complète**.
    
    4.  Pour **Composant de sauvegarde**, cliquez sur **Base de données**.
    
    5.  Acceptez le nom du jeu de sauvegarde par défaut suggéré dans **Nom** ou entrez un autre nom pour le jeu de sauvegarde.
    
    6.  * \<Facultatif\> * Dans **Description**, entrez une description du jeu de sauvegarde.
    
    7.  Supprimez l’emplacement de sauvegarde par défaut de la liste de destination.
    
    8.  Ajoutez un fichier à la liste en utilisant le chemin d’accès à l’emplacement de partage que vous avez établi pour l’envoi de journaux. Ce chemin d’accès est accessible à la base de données primaire et à la base de données de sauvegarde.
    
    9.  Cliquez sur **OK** pour fermer la boîte de dialogue et lancer le processus de sauvegarde.

4.  Restaurez la base de données primaire à l’aide de la base de données de sauvegarde créée à l’étape précédente.
    
    1.  À l’aide de SQL Server Management Studio, connectez-vous à l’instance MGC principale.
    
    2.  Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, sur **Restaurer**, puis cliquez sur **Base de données**. La boîte de dialogue **Restaurer la base de données** s’affiche.
    
    3.  Sélectionnez **À partir du périphérique**.
    
    4.  Cliquez sur le bouton Parcourir pour ouvrir la boîte de dialogue **Spécifier la sauvegarde**. Dans **Support de sauvegarde**, sélectionnez **Fichier**. Cliquez sur **Ajouter**, sélectionnez le fichier de sauvegarde que vous avez créé à l’étape 3, puis cliquez sur **OK**.
    
    5.  Dans **Sélectionnez les jeux de sauvegarde à restaurer**, sélectionnez la sauvegarde.
    
    6.  Dans le volet **Sélectionner une page**, cliquez sur **Options**.
    
    7.  Dans **Options de restauration**, sélectionnez uniquement **Remplacer la base de données existante**.
    
    8.  Dans **État de récupération**, sélectionnez **Laisser la base de données opérationnelle**.
    
    9.  Cliquez sur **OK** pour lancer le processus de restauration.

5.  Configurer l’envoi du journal SQL Server pour la base de données principale. Suivez les procédures de [configuration du serveur de chat permanent pour une haute disponibilité et une reprise après sinistre dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) pour établir l’envoi de journaux pour la base de données MGC principale.

6.  Définissez les serveurs actifs de chat permanent serveur. À partir de Lync Server Management Shell, utilisez l’applet de contrôle **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.
    
    <div>
    

    > [!IMPORTANT]  
    > Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.

    
    </div>

Lorsque le pool est restauré à son état normal, exécutez la commande Windows PowerShell suivante :

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

Pour plus d’informations, consultez la rubrique d’aide sur l’applet de [CsPersistentChatState Set-](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

