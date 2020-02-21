---
title: 'Lync Server 2013 : configuration de la copie des journaux de transaction SQL Server pour la base de données principale du serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 492d4be1865bdb022736a62a2507c115c892b47b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>Configuration de la copie des journaux de transaction SQL Server dans Lync Server 2013 pour la base de données principale du serveur de conversation permanente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-12_

À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données de copie de journaux secondaires du serveur de conversation permanente et assurez-vous que l’agent SQL Server est en cours d’exécution.

À l’aide de SQL Server Management Studio connecté à l’instance de base de données principale de conversation permanente, procédez comme suit :

1.  Assurez-vous que l’agent SQL Server est en cours d’exécution.

2.  Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.

3.  Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.

4.  Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.

5.  Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.

6.  Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès vers le partage que vous avez créé pour le dossier de sauvegarde des journaux de transactions.

7.  Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local au dossier de sauvegarde dans la zone **si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au\\dossier (exemple : c : sauvegarde)** . (Si le dossier de sauvegarde ne figure pas sur le serveur principal, vous pouvez laisser cette case à cocher vide.)
    
    <div>
    

    > [!IMPORTANT]  
    > Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer votre dossier de sauvegarde sur le serveur principal et spécifier un chemin d’accès local à ce dossier.

    
    </div>

8.  Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.

9.  Examinez l’échéancier des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**. Pour personnaliser la planification de votre installation, cliquez sur **planifier**et ajustez la planification de l’agent SQL Server comme il se doit.

10. Sous **Compression**, sélectionnez **Utiliser le paramètre du serveur par défaut**, puis cliquez sur **OK**.

11. Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.

12. Cliquez sur **connecter** , puis connectez-vous à l’instance de SQL Server que vous avez configurée en tant que serveur secondaire.

13. Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.

14. Sous l’onglet **initialiser la base de données secondaire** , sélectionnez l’option **Oui, générer une sauvegarde complète de la base de données principale et la restaurer dans la base de données secondaire (et créer la base de données secondaire si elle n’existe pas)**.

15. Sous l’onglet **Copier les fichiers**, dans la zone **Dossier de destination des fichiers copiés**, tapez le chemin d’accès au dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées. Ce dossier se trouve souvent sur le serveur secondaire.

16. Examinez la planification des copies dans la zone **Planification** sous **Copier le travail**. Pour personnaliser la planification de votre installation, cliquez sur **planifier**et ajustez la planification de l’agent SQL Server comme il se doit. Cette planification doit être approximativement la même que celle des sauvegardes.

17. Sous l’onglet **Restaurer**, sous **État de la base de données lors de la restauration des sauvegardes**, choisissez l’option **Mode sans récupération**.

18. Sous **Retarder la restauration des sauvegardes d’au moins :**, sélectionnez **0 minutes**.

19. Choisissez un seuil d’alerte sous **Envoyer une alerte si aucune restauration ne se produit en l’espace de**.

20. Examinez la planification des restaurations dans la zone **Planification** sous **Restaurer le travail**. Pour personnaliser la planification de votre installation, cliquez sur **planification**, ajustez la planification de l’agent SQL Server, puis cliquez sur **OK**. Cette planification doit être approximativement la même que celle des sauvegardes.

21. Dans la boîte de dialogue **Propriétés de la base de données**, cliquez sur **OK** pour lancer le processus de configuration.

</div>

<span> </span>

</div>

</div>

</div>

