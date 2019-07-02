---
title: Gestion de la haute disponibilité et de la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Résumé: Découvrez comment gérer l’utilisation du serveur Chat permanent et de la reprise après sinistre dans Skype entreprise Server 2015.'
ms.openlocfilehash: ff30bcdd99a4c92bd8fbd8f0a5c4bcedd8aa63b0
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418704"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="875ea-103">Gestion de la haute disponibilité et de la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="875ea-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="875ea-104">**Résumé:** Découvrez comment gérer la haute disponibilité et la reprise après sinistre du serveur Chat permanent dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="875ea-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="875ea-105">Cette rubrique décrit la procédure de basculement et de basculement du serveur de conversation permanent.</span><span class="sxs-lookup"><span data-stu-id="875ea-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="875ea-106">Avant de lire ce sujet, veillez à lire [plan pour une haute disponibilité et une reprise après sinistre pour le serveur de chat permanent dans Skype entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) et à [configurer une haute disponibilité et une reprise après sinistre pour le serveur de chat permanent dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="875ea-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="875ea-107">La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="875ea-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="875ea-108">La même fonctionnalité est disponible dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="875ea-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="875ea-109">Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="875ea-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="875ea-110">Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="875ea-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="875ea-111">Basculement du serveur de conversation permanent</span><span class="sxs-lookup"><span data-stu-id="875ea-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="875ea-112">Le basculement pour le serveur de chat permanent est conçu pour être essentiellement un processus manuel.</span><span class="sxs-lookup"><span data-stu-id="875ea-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="875ea-113">La procédure de basculement repose sur l’hypothèse que le centre de données secondaire est opérationnel et qu’il est en cours d’exécution, mais les services serveur de chat permanent dans lesquels réside la base de données de chat permanent principal sont entièrement indisponibles, y compris les suivantes:</span><span class="sxs-lookup"><span data-stu-id="875ea-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="875ea-114">La base de données principale de chat serveur et la base de données miroir du serveur de chat permanent sont inversées.</span><span class="sxs-lookup"><span data-stu-id="875ea-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="875ea-115">Le serveur frontal de Skype entreprise Server est arrêté.</span><span class="sxs-lookup"><span data-stu-id="875ea-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="875ea-116">La procédure consiste en deux étapes de base :</span><span class="sxs-lookup"><span data-stu-id="875ea-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="875ea-117">Récupérez la base de données de chat persistante principale (MGC).</span><span class="sxs-lookup"><span data-stu-id="875ea-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="875ea-118">Établir la mise en miroir pour la nouvelle base de données principale.</span><span class="sxs-lookup"><span data-stu-id="875ea-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="875ea-119">La base de données de compatibilité des conversations permanentes (mgccomp) n’a pas pu être lancée.</span><span class="sxs-lookup"><span data-stu-id="875ea-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="875ea-120">Le contenu de cette base de données est temporaire et purgé au fur et à mesure que l’adaptateur de conformité traite les données.</span><span class="sxs-lookup"><span data-stu-id="875ea-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="875ea-121">Il est de votre responsabilité, en tant qu’administrateur de chat permanent, de gérer correctement la sortie de la carte pour éviter la perte de données.</span><span class="sxs-lookup"><span data-stu-id="875ea-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="875ea-122">Basculer vers un serveur de conversation permanente :</span><span class="sxs-lookup"><span data-stu-id="875ea-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="875ea-123">Supprimez l’envoi de journaux de la base de données d’envoi de journaux de sauvegarde du serveur Chat permanent.</span><span class="sxs-lookup"><span data-stu-id="875ea-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="875ea-124">À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données dans laquelle réside la base de données de sauvegarde serveur de chat MGC.</span><span class="sxs-lookup"><span data-stu-id="875ea-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="875ea-125">Ouvrez une fenêtre de requête pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="875ea-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="875ea-126">Utilisez la commande suivante pour annuler la copie des journaux de transaction :</span><span class="sxs-lookup"><span data-stu-id="875ea-126">Use the following command to drop log shipping:</span></span>
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="875ea-127">Copiez tous les fichiers de sauvegarde non copiés se trouvant sur le partage de sauvegarde vers le dossier de destination de la copie du serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="875ea-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="875ea-128">Appliquez dans l’ordre toutes les sauvegardes du journal des transactions non appliquées à la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="875ea-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="875ea-129">Pour plus d’informations, reportez-vous [à la rubrique Procédure: appliquer une sauvegarde du journal des transactions (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span><span class="sxs-lookup"><span data-stu-id="875ea-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="875ea-p105">Mettez en ligne la base de données mgc de sauvegarde. Dans la fenêtre de requête ouverte à l’étape 1b, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="875ea-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="875ea-132">Mettez fin à toutes les connexions à la base de données mgc, le cas échéant :</span><span class="sxs-lookup"><span data-stu-id="875ea-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="875ea-133">**exec sp_who2** pour identifier les connexions à la base de données mgc.</span><span class="sxs-lookup"><span data-stu-id="875ea-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="875ea-134">**Arrêtez \<le\> SPID** pour terminer ces connexions.</span><span class="sxs-lookup"><span data-stu-id="875ea-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="875ea-135">Mettez en ligne la base de données :</span><span class="sxs-lookup"><span data-stu-id="875ea-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="875ea-136">**restaurer la base de données mgc avec récupération**.</span><span class="sxs-lookup"><span data-stu-id="875ea-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="875ea-137">Dans Skype entreprise Server Management Shell, utilisez la commande **Set-CsPersistentChatState-Identity "service: ATL-CS-001.litwareinc.com"-PoolState FailedOver** pour basculer vers la base de données de sauvegarde MGC.</span><span class="sxs-lookup"><span data-stu-id="875ea-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="875ea-138">Veillez à remplacer le nom de domaine complet de votre pool de conversation permanente par atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="875ea-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="875ea-139">La base de données mgc de sauvegarde est désormais la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="875ea-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="875ea-140">Dans Skype entreprise Server Management Shell, vous pouvez utiliser l’applet de passe **install-CsMirrorDatabase** pour établir un miroir haute disponibilité pour la base de données de sauvegarde qui sert désormais de base de données principale.</span><span class="sxs-lookup"><span data-stu-id="875ea-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="875ea-141">Utilisez l’instance de la base de données de sauvegarde en tant que base de données principale et l’instance de la base de données miroir de sauvegarde en tant qu’instance miroir.</span><span class="sxs-lookup"><span data-stu-id="875ea-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="875ea-142">Il ne s’agit pas du même miroir que celui qui a été initialement configuré pour la base de données principale pendant la configuration.</span><span class="sxs-lookup"><span data-stu-id="875ea-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="875ea-143">Définissez les serveurs actifs de chat permanent serveur.</span><span class="sxs-lookup"><span data-stu-id="875ea-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="875ea-144">À partir de Skype entreprise Server Management Shell, utilisez l’applet de contrôle **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.</span><span class="sxs-lookup"><span data-stu-id="875ea-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="875ea-145">Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="875ea-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="875ea-146">À ce stade, le basculement de la base de données principale du serveur Chat permanent vers la base de données de sauvegarde du serveur Chat permanent s’effectue correctement.</span><span class="sxs-lookup"><span data-stu-id="875ea-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="875ea-147">Échec du serveur de conversation persistante</span><span class="sxs-lookup"><span data-stu-id="875ea-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="875ea-148">Cette procédure décrit les étapes nécessaires à la récupération d’une défaillance du serveur de chat permanent et à la restauration d’opérations à partir du centre de données principal.</span><span class="sxs-lookup"><span data-stu-id="875ea-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="875ea-149">Lors de l’échec du serveur Chat permanent, le centre de données principal est en panne, et les bases de données principales et miroirs deviennent indisponibles.</span><span class="sxs-lookup"><span data-stu-id="875ea-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="875ea-150">Le centre de données principal bascule vers le serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="875ea-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="875ea-151">La procédure suivante rétablit le fonctionnement normal une fois le centre de données principal sauvegardé et les serveurs reconstruits.</span><span class="sxs-lookup"><span data-stu-id="875ea-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="875ea-152">Cette procédure part du principe que le centre de données principal a été restauré à partir d’une panne totale et que la base de données MGC et la base de données mgccomp ont été recréées puis réinstallées à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="875ea-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="875ea-153">La procédure s’appuie aussi sur le fait qu’aucun nouveau serveur (miroir et de sauvegarde) n’a été déployé au cours de la période de basculement, et que le seul serveur déployé est le serveur de sauvegarde et son serveur miroir, conformément à la définition donnée dans Basculement vers un serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="875ea-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="875ea-154">Ces étapes visent à récupérer la configuration telle qu’elle existait avant la défaillance, cette dernière ayant provoqué le basculement du serveur principal vers le serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="875ea-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="875ea-155">Effacez tous les serveurs de la liste de serveurs actifs de chat permanent du serveur à l’aide de l’applet de contrôle **Set-CsPersistentChatActiveServer** de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="875ea-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="875ea-156">Cela a pour fin la connexion à la base de données MGC et de la base de données mgccomp lors du retour arrière.</span><span class="sxs-lookup"><span data-stu-id="875ea-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="875ea-157">L’agent SQL Server sur le serveur principal de chat permanent du serveur principal doit être en cours d’exécution sous un compte privilégié.</span><span class="sxs-lookup"><span data-stu-id="875ea-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="875ea-158">Plus précisément, le compte doit disposer des droits suivants :</span><span class="sxs-lookup"><span data-stu-id="875ea-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="875ea-159">Accès en lecture au partage réseau dans lequel les sauvegardes sont placées</span><span class="sxs-lookup"><span data-stu-id="875ea-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="875ea-160">Accès en écriture au répertoire local spécifique vers lequel les sauvegardes sont copiées</span><span class="sxs-lookup"><span data-stu-id="875ea-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="875ea-161">Désactivez la mise en miroir sur la base de données mgc de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="875ea-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="875ea-162">À l’aide de SQL Server Management Studio, connectez-vous à l’instance Backup MGC.</span><span class="sxs-lookup"><span data-stu-id="875ea-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="875ea-163">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Miroir**.</span><span class="sxs-lookup"><span data-stu-id="875ea-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="875ea-164">Cliquez sur **Supprimer la mise en miroir**.</span><span class="sxs-lookup"><span data-stu-id="875ea-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="875ea-165">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="875ea-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="875ea-166">Procédez de la même façon avec la base de données mgccomp.</span><span class="sxs-lookup"><span data-stu-id="875ea-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="875ea-167">Sauvegardez la base de données mgc afin qu’elle puisse être restaurée vers la nouvelle base de données primaire :</span><span class="sxs-lookup"><span data-stu-id="875ea-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="875ea-168">À l’aide de SQL Server Management Studio, connectez-vous à l’instance Backup MGC.</span><span class="sxs-lookup"><span data-stu-id="875ea-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="875ea-p113">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**. La boîte de dialogue **Sauvegarder la base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="875ea-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="875ea-171">Dans **Type de sauvegarde**, sélectionnez **Complète**.</span><span class="sxs-lookup"><span data-stu-id="875ea-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="875ea-172">Pour **Composant de sauvegarde**, cliquez sur **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="875ea-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="875ea-173">Acceptez le nom du jeu de sauvegarde par défaut suggéré dans **Nom** ou entrez un autre nom pour le jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="875ea-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="875ea-174">\* \<Facultatif\> \*  Dans **Description**, entrez une description du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="875ea-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="875ea-175">Supprimez l’emplacement de sauvegarde par défaut de la liste de destination.</span><span class="sxs-lookup"><span data-stu-id="875ea-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="875ea-p114">Ajoutez un fichier à la liste en utilisant le chemin d’accès à l’emplacement de partage que vous avez établi pour l’envoi de journaux. Ce chemin d’accès est accessible à la base de données primaire et à la base de données de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="875ea-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="875ea-178">Cliquez sur **OK** pour fermer la boîte de dialogue et lancer le processus de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="875ea-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="875ea-179">Restaurez la base de données primaire à l’aide de la base de données de sauvegarde créée à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="875ea-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="875ea-180">À l’aide de SQL Server Management Studio, connectez-vous à l’instance MGC principale.</span><span class="sxs-lookup"><span data-stu-id="875ea-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="875ea-p115">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, sur **Restaurer**, puis cliquez sur **Base de données**. La boîte de dialogue **Restaurer la base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="875ea-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="875ea-183">Sélectionnez **À partir du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="875ea-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="875ea-p116">Cliquez sur le bouton Parcourir pour ouvrir la boîte de dialogue **Spécifier la sauvegarde**. Dans **Support de sauvegarde**, sélectionnez **Fichier**. Cliquez sur **Ajouter**, sélectionnez le fichier de sauvegarde que vous avez créé à l’étape 3, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="875ea-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="875ea-187">Dans **Sélectionnez les jeux de sauvegarde à restaurer**, sélectionnez la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="875ea-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="875ea-188">Dans le volet **Sélectionner une page**, cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="875ea-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="875ea-189">Dans **Options de restauration**, sélectionnez uniquement **Remplacer la base de données existante**.</span><span class="sxs-lookup"><span data-stu-id="875ea-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="875ea-190">Dans **État de récupération**, sélectionnez **Laisser la base de données opérationnelle**.</span><span class="sxs-lookup"><span data-stu-id="875ea-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="875ea-191">Cliquez sur **OK** pour lancer le processus de restauration.</span><span class="sxs-lookup"><span data-stu-id="875ea-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="875ea-192">Configurer l’envoi du journal SQL Server pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="875ea-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="875ea-193">Suivez les procédures de [configuration de haute disponibilité et de récupération d’urgence pour le serveur de chat permanent dans Skype entreprise server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) de manière à établir une expédition du journal pour la base de données MGC principale.</span><span class="sxs-lookup"><span data-stu-id="875ea-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="875ea-194">Définissez les serveurs actifs de chat permanent serveur.</span><span class="sxs-lookup"><span data-stu-id="875ea-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="875ea-195">À partir de Skype entreprise Server Management Shell, utilisez l’applet de contrôle **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.</span><span class="sxs-lookup"><span data-stu-id="875ea-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="875ea-196">Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="875ea-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="875ea-197">Pour restaurer le pool à son état normal, exécutez la commande Windows PowerShell suivante:</span><span class="sxs-lookup"><span data-stu-id="875ea-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="875ea-198">Pour plus d’informations, voir la rubrique d’aide sur l’applet de commande [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="875ea-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

