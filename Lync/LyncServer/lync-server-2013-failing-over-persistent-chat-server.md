---
title: 'Lync Server 2013 : Basculement vers un serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 021b34cafd91397cc36da1dbc22f91b8665aea96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ff560-102">Basculement vers un serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff560-102">Failing over Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff560-103">_**Dernière modification de la rubrique:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="ff560-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="ff560-104">Le basculement pour le serveur de chat permanent est conçu pour être essentiellement un processus manuel.</span><span class="sxs-lookup"><span data-stu-id="ff560-104">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="ff560-105">La procédure de basculement repose sur l’hypothèse que le centre de données secondaire est opérationnel et qu’il est en cours d’exécution, mais les services serveur de chat permanent dans lesquels réside la base de données de chat permanent principal sont entièrement indisponibles, y compris les suivantes:</span><span class="sxs-lookup"><span data-stu-id="ff560-105">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="ff560-106">La base de données principale de chat serveur et la base de données miroir du serveur de chat permanent sont inversées.</span><span class="sxs-lookup"><span data-stu-id="ff560-106">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="ff560-107">Le serveur frontal de Lync Server est arrêté.</span><span class="sxs-lookup"><span data-stu-id="ff560-107">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="ff560-108">La procédure consiste en deux étapes de base :</span><span class="sxs-lookup"><span data-stu-id="ff560-108">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="ff560-109">Récupérez la base de données de chat persistante principale (MGC).</span><span class="sxs-lookup"><span data-stu-id="ff560-109">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="ff560-110">Établir la mise en miroir pour la nouvelle base de données principale.</span><span class="sxs-lookup"><span data-stu-id="ff560-110">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="ff560-111">La base de données de compatibilité des conversations permanentes (mgccomp) n’a pas pu être lancée.</span><span class="sxs-lookup"><span data-stu-id="ff560-111">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="ff560-112">Le contenu de cette base de données est temporaire et purgé au fur et à mesure que l’adaptateur de conformité traite les données.</span><span class="sxs-lookup"><span data-stu-id="ff560-112">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="ff560-113">Il est de votre responsabilité, en tant qu’administrateur de chat permanent, de gérer correctement la sortie de la carte pour éviter la perte de données.</span><span class="sxs-lookup"><span data-stu-id="ff560-113">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="ff560-114">Pour basculer vers un serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="ff560-114">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="ff560-115">Supprimez l’envoi de journaux de la base de données d’envoi de journaux de sauvegarde du serveur Chat permanent.</span><span class="sxs-lookup"><span data-stu-id="ff560-115">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="ff560-116">À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données dans laquelle réside la base de données de sauvegarde serveur de chat MGC.</span><span class="sxs-lookup"><span data-stu-id="ff560-116">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="ff560-117">Ouvrez une fenêtre de requête pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="ff560-117">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="ff560-118">Utilisez la commande suivante pour annuler la copie des journaux de transaction :</span><span class="sxs-lookup"><span data-stu-id="ff560-118">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="ff560-119">Copiez tous les fichiers de sauvegarde non copiés se trouvant sur le partage de sauvegarde vers le dossier de destination de la copie du serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ff560-119">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="ff560-120">Appliquez dans l’ordre toutes les sauvegardes du journal des transactions non appliquées à la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="ff560-120">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="ff560-121">Pour plus d’informations, consultez la section «Procédure: appliquer une sauvegarde du journal des transactions (Transact http://go.microsoft.com/fwlink/p/?linkid=247428-SQL)» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="ff560-121">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at http://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="ff560-p103">Mettez en ligne la base de données mgc de sauvegarde. Dans la fenêtre de requête ouverte à l’étape 1b, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff560-p103">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="ff560-124">Mettez fin à toutes les connexions à la base de données mgc, le cas échéant :</span><span class="sxs-lookup"><span data-stu-id="ff560-124">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="ff560-125">**Exec SP\_WHO2** identifiant les connexions de la base de données MGC.</span><span class="sxs-lookup"><span data-stu-id="ff560-125">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="ff560-126">**Arrêtez \<le\> SPID** pour terminer ces connexions.</span><span class="sxs-lookup"><span data-stu-id="ff560-126">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="ff560-127">Mettez en ligne la base de données :</span><span class="sxs-lookup"><span data-stu-id="ff560-127">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="ff560-128">**restaurer la base de données mgc avec récupération**.</span><span class="sxs-lookup"><span data-stu-id="ff560-128">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="ff560-129">Dans Lync Server Management Shell, utilisez la commande **Set-CsPersistentChatState-Identity «service: ATL-CS-001.litwareinc.com» – PoolState FailedOver** pour basculer vers la base de données de sauvegarde MGC.</span><span class="sxs-lookup"><span data-stu-id="ff560-129">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="ff560-130">Veillez à remplacer le nom de domaine complet de votre pool de conversation permanente par atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ff560-130">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="ff560-131">La base de données mgc de sauvegarde est désormais la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="ff560-131">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="ff560-132">Dans Lync Server Management Shell, vous pouvez utiliser l’applet de passe **install-CsMirrorDatabase** pour établir un miroir haute disponibilité pour la base de données de sauvegarde, qui sert désormais de base de données principale.</span><span class="sxs-lookup"><span data-stu-id="ff560-132">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="ff560-133">Utilisez l’instance de la base de données de sauvegarde en tant que base de données principale et l’instance de la base de données miroir de sauvegarde en tant qu’instance miroir.</span><span class="sxs-lookup"><span data-stu-id="ff560-133">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="ff560-134">Il ne s’agit pas du même miroir que celui qui a été initialement configuré pour la base de données principale pendant la configuration.</span><span class="sxs-lookup"><span data-stu-id="ff560-134">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="ff560-135">Pour plus d’informations, reportez-vous à la section «utilisation des cmdlets Lync Server Management Shell» du [déploiement de la mise en miroir SQL pour la haute disponibilité du serveur principal dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="ff560-135">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="ff560-136">Définissez les serveurs actifs de chat permanent serveur.</span><span class="sxs-lookup"><span data-stu-id="ff560-136">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="ff560-137">À partir de l’interpréteur de commandes de Lync Server, utilisez l’applet de commande **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.</span><span class="sxs-lookup"><span data-stu-id="ff560-137">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ff560-138">Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="ff560-138">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="ff560-139">À ce stade, le basculement de la base de données principale du serveur Chat permanent vers la base de données de sauvegarde du serveur Chat permanent s’effectue correctement.</span><span class="sxs-lookup"><span data-stu-id="ff560-139">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

