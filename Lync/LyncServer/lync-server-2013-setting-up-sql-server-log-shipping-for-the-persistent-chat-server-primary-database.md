---
title: 'Lync Server 2013 : configuration de la copie des journaux de transaction SQL Server pour la base de données principale du serveur de conversation permanente'
description: 'Lync Server 2013 : configuration de la copie des journaux de transaction SQL Server pour la base de données principale du serveur de conversation permanente.'
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
ms.openlocfilehash: 72b7e68bd0cb7b9f544b86a15204d3e832692ec1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554260"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="ff80d-103">Configuration de la copie des journaux de transaction SQL Server dans Lync Server 2013 pour la base de données principale du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ff80d-103">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff80d-104">_**Dernière modification de la rubrique :** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="ff80d-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="ff80d-105">À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données de copie de journaux secondaires du serveur de conversation permanente et assurez-vous que l’agent SQL Server est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="ff80d-105">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="ff80d-106">À l’aide de SQL Server Management Studio connecté à l’instance de base de données principale de conversation permanente, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff80d-106">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="ff80d-107">Assurez-vous que l’agent SQL Server est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="ff80d-107">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="ff80d-108">Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-108">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="ff80d-109">Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-109">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="ff80d-110">Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-110">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="ff80d-111">Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-111">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="ff80d-112">Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès vers le partage que vous avez créé pour le dossier de sauvegarde des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="ff80d-112">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="ff80d-113">Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local au dossier de sauvegarde dans la zone **si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier (exemple : c : \\ sauvegarde)** .</span><span class="sxs-lookup"><span data-stu-id="ff80d-113">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="ff80d-114">(Si le dossier de sauvegarde ne figure pas sur le serveur principal, vous pouvez laisser cette case à cocher vide.)</span><span class="sxs-lookup"><span data-stu-id="ff80d-114">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ff80d-115">Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer votre dossier de sauvegarde sur le serveur principal et spécifier un chemin d’accès local à ce dossier.</span><span class="sxs-lookup"><span data-stu-id="ff80d-115">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="ff80d-116">Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-116">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="ff80d-117">Examinez l’échéancier des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-117">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="ff80d-118">Pour personnaliser la planification de votre installation, cliquez sur **planifier**et ajustez la planification de l’agent SQL Server comme il se doit.</span><span class="sxs-lookup"><span data-stu-id="ff80d-118">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="ff80d-119">Sous **Compression**, sélectionnez **Utiliser le paramètre du serveur par défaut**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-119">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="ff80d-120">Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-120">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="ff80d-121">Cliquez sur **connecter** , puis connectez-vous à l’instance de SQL Server que vous avez configurée en tant que serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="ff80d-121">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="ff80d-122">Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ff80d-122">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="ff80d-123">Sous l’onglet **initialiser la base de données secondaire** , sélectionnez l’option **Oui, générer une sauvegarde complète de la base de données principale et la restaurer dans la base de données secondaire (et créer la base de données secondaire si elle n’existe pas)**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-123">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="ff80d-p103">Sous l’onglet **Copier les fichiers**, dans la zone **Dossier de destination des fichiers copiés**, tapez le chemin d’accès au dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées. Ce dossier se trouve souvent sur le serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="ff80d-p103">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="ff80d-126">Examinez la planification des copies dans la zone **Planification** sous **Copier le travail**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-126">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="ff80d-127">Pour personnaliser la planification de votre installation, cliquez sur **planifier**et ajustez la planification de l’agent SQL Server comme il se doit.</span><span class="sxs-lookup"><span data-stu-id="ff80d-127">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="ff80d-128">Cette planification doit être approximativement la même que celle des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="ff80d-128">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="ff80d-129">Sous l’onglet **Restaurer**, sous **État de la base de données lors de la restauration des sauvegardes**, choisissez l’option **Mode sans récupération**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-129">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="ff80d-130">Sous **Retarder la restauration des sauvegardes d’au moins :**, sélectionnez **0 minutes**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-130">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="ff80d-131">Choisissez un seuil d’alerte sous **Envoyer une alerte si aucune restauration ne se produit en l’espace de**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-131">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="ff80d-132">Examinez la planification des restaurations dans la zone **Planification** sous **Restaurer le travail**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-132">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="ff80d-133">Pour personnaliser la planification de votre installation, cliquez sur **planification**, ajustez la planification de l’agent SQL Server, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff80d-133">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="ff80d-134">Cette planification doit être approximativement la même que celle des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="ff80d-134">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="ff80d-135">Dans la boîte de dialogue **Propriétés de la base de données**, cliquez sur **OK** pour lancer le processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="ff80d-135">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

