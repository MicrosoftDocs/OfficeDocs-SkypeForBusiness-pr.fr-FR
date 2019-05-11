---
title: Gestion de la haute disponibilité et de la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Résumé : Découvrez comment gérer les serveurs de conversation permanente haute disponibilité et récupération d’urgence dans Skype pour Business Server 2015.'
ms.openlocfilehash: 8e2b9cecef2a3598c318ab8a758c99eb2caf40e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910346"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="7058d-103">Gestion de la haute disponibilité et de la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7058d-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7058d-104">**Résumé :** Découvrez comment gérer des serveurs de conversation permanente haute disponibilité et récupération d’urgence dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7058d-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7058d-105">Cette rubrique décrit comment basculer et restaurer le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7058d-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="7058d-106">Avant de lire cette rubrique, vous devez avoir lu [planifier la haute disponibilité et de récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) et [Configure une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Entreprise 2015 Server](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="7058d-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7058d-107">Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7058d-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7058d-108">La même fonctionnalité est disponible dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="7058d-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="7058d-109">Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="7058d-109">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="7058d-110">Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7058d-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="7058d-111">Faire basculer le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="7058d-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="7058d-112">Le basculement de serveur de conversation permanente est conçu pour être principalement un processus manuel.</span><span class="sxs-lookup"><span data-stu-id="7058d-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="7058d-113">La procédure de basculement se base sur l’hypothèse que le centre de données secondaire est actif et en cours d’exécution, mais les services de serveur de conversation permanente où se trouve la base de données primaire conversation permanente sont totalement indisponibles, y compris les suivantes :</span><span class="sxs-lookup"><span data-stu-id="7058d-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="7058d-114">Base de données primaire persistent Chat Server et la base de données miroir Persistent Chat Server sont inactives.</span><span class="sxs-lookup"><span data-stu-id="7058d-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="7058d-115">Skype pour Business Server serveur frontal est inactif.</span><span class="sxs-lookup"><span data-stu-id="7058d-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="7058d-116">La procédure consiste en deux étapes de base :</span><span class="sxs-lookup"><span data-stu-id="7058d-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="7058d-117">Récupérer la conversation permanente base de données principale (mgc).</span><span class="sxs-lookup"><span data-stu-id="7058d-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="7058d-118">Établir la mise en miroir pour la nouvelle base de données principale.</span><span class="sxs-lookup"><span data-stu-id="7058d-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="7058d-119">La base de données de conformité conversation permanente (mgccomp) n’est pas basculé.</span><span class="sxs-lookup"><span data-stu-id="7058d-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="7058d-120">Le contenu de cette base de données est temporaire et purgé au fur et à mesure que l’adaptateur de conformité traite les données.</span><span class="sxs-lookup"><span data-stu-id="7058d-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="7058d-121">Il vous incombe, en tant qu’administrateur de conversation permanente, pour gérer correctement la sortie de la carte pour éviter toute perte de données.</span><span class="sxs-lookup"><span data-stu-id="7058d-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="7058d-122">Basculer vers un serveur de conversation permanente :</span><span class="sxs-lookup"><span data-stu-id="7058d-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="7058d-123">Supprimer des journaux de transaction de la base de données Persistent Chat Server sauvegarde l’envoi de journaux.</span><span class="sxs-lookup"><span data-stu-id="7058d-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="7058d-124">À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données où se trouve la base de données mgc de sauvegarde Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="7058d-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="7058d-125">Ouvrez une fenêtre de requête pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="7058d-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="7058d-126">Utilisez la commande suivante pour annuler la copie des journaux de transaction :</span><span class="sxs-lookup"><span data-stu-id="7058d-126">Use the following command to drop log shipping:</span></span>
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="7058d-127">Copiez tous les fichiers de sauvegarde non copiés se trouvant sur le partage de sauvegarde vers le dossier de destination de la copie du serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7058d-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="7058d-128">Appliquez dans l’ordre toutes les sauvegardes du journal des transactions non appliquées à la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="7058d-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="7058d-129">Pour plus d’informations, voir [procédure : appliquer une sauvegarde du journal des transactions (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span><span class="sxs-lookup"><span data-stu-id="7058d-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="7058d-p105">Mettez en ligne la base de données mgc de sauvegarde. Dans la fenêtre de requête ouverte à l’étape 1b, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7058d-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="7058d-132">Mettez fin à toutes les connexions à la base de données mgc, le cas échéant :</span><span class="sxs-lookup"><span data-stu-id="7058d-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="7058d-133">**exec sp_who2** pour identifier les connexions à la base de données mgc.</span><span class="sxs-lookup"><span data-stu-id="7058d-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="7058d-134">\*\*kill \<spid\> \*\* pour mettre fin à ces connexions.</span><span class="sxs-lookup"><span data-stu-id="7058d-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="7058d-135">Mettez en ligne la base de données :</span><span class="sxs-lookup"><span data-stu-id="7058d-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="7058d-136">**restaurer la base de données mgc avec récupération**.</span><span class="sxs-lookup"><span data-stu-id="7058d-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="7058d-137">Dans Skype pour Business Server Management Shell, utilisez la commande **Set-CsPersistentChatState-Identity « service : atl-cs-001.litwareinc.com » - PoolState FailedOver** pour faire basculer la base de données mgc sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7058d-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="7058d-138">Veillez à remplacer le nom de domaine complet de votre pool de conversation permanente par atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="7058d-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="7058d-139">La base de données mgc de sauvegarde est désormais la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="7058d-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="7058d-140">Dans Skype pour Business Server Management Shell, utilisez l’applet de commande **Install-CsMirrorDatabase** pour établir une mise en miroir haute disponibilité pour la base de données de sauvegarde qui sert désormais la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="7058d-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="7058d-141">Utilisez l’instance de la base de données de sauvegarde en tant que base de données principale et l’instance de la base de données miroir de sauvegarde en tant qu’instance miroir.</span><span class="sxs-lookup"><span data-stu-id="7058d-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="7058d-142">Il ne s’agit pas du même miroir que celui qui a été initialement configuré pour la base de données principale pendant la configuration.</span><span class="sxs-lookup"><span data-stu-id="7058d-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="7058d-143">Définir les serveurs actifs du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7058d-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="7058d-144">À partir de Skype pour Business Server Management Shell, utilisez l’applet de commande **Set-cspersistentchatactiveserver ne** pour définir la liste de serveurs actives.</span><span class="sxs-lookup"><span data-stu-id="7058d-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7058d-145">Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="7058d-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="7058d-146">À ce stade, le basculement de la base de données principale du serveur de conversation permanente à la base de données Persistent Chat Server sauvegarde se termine correctement.</span><span class="sxs-lookup"><span data-stu-id="7058d-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="7058d-147">Échec du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="7058d-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="7058d-148">Cette procédure décrit les étapes nécessaires pour récupérer d’une défaillance du serveur de conversation permanente et pour rétablir les opérations à partir du centre de données principal.</span><span class="sxs-lookup"><span data-stu-id="7058d-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="7058d-149">Défaillance d’un serveur de conversation permanente, le centre de données principal subit une panne complète et le serveur principal et miroir de bases de données ne sont plus disponibles.</span><span class="sxs-lookup"><span data-stu-id="7058d-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="7058d-150">Le centre de données principal bascule vers le serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7058d-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="7058d-151">La procédure suivante rétablit le fonctionnement normal une fois le centre de données principal sauvegardé et les serveurs reconstruits.</span><span class="sxs-lookup"><span data-stu-id="7058d-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="7058d-152">La procédure suppose que le centre de données principal a été récupéré à partir d’une panne totale et que la base de données mgc et la base de données mgccomp ont été régénérés et réinstallés à l’aide du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="7058d-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="7058d-153">La procédure s’appuie aussi sur le fait qu’aucun nouveau serveur (miroir et de sauvegarde) n’a été déployé au cours de la période de basculement, et que le seul serveur déployé est le serveur de sauvegarde et son serveur miroir, conformément à la définition donnée dans Basculement vers un serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7058d-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="7058d-154">Ces étapes visent à récupérer la configuration telle qu’elle existait avant la défaillance, cette dernière ayant provoqué le basculement du serveur principal vers le serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7058d-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="7058d-155">Désactivez tous les serveurs de la liste Persistent Chat Server Active Server à l’aide de l’applet de commande **Set-cspersistentchatactiveserver ne** le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7058d-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="7058d-156">Cela arrête tous les serveurs de conversation permanente de se connecter à la base de données mgc et la base de données mgccomp durant la restauration.</span><span class="sxs-lookup"><span data-stu-id="7058d-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7058d-157">L’agent SQL Server sur le serveur secondaire Persistent Chat Server le serveur principal doit être en cours d’exécution sous un compte privilégié.</span><span class="sxs-lookup"><span data-stu-id="7058d-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="7058d-158">Plus précisément, le compte doit disposer des droits suivants :</span><span class="sxs-lookup"><span data-stu-id="7058d-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="7058d-159">Accès en lecture au partage réseau dans lequel les sauvegardes sont placées</span><span class="sxs-lookup"><span data-stu-id="7058d-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="7058d-160">Accès en écriture au répertoire local spécifique vers lequel les sauvegardes sont copiées</span><span class="sxs-lookup"><span data-stu-id="7058d-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="7058d-161">Désactivez la mise en miroir sur la base de données mgc de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="7058d-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="7058d-162">À l’aide de SQL Server Management Studio, connectez-vous à l’instance mgc de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7058d-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="7058d-163">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Miroir**.</span><span class="sxs-lookup"><span data-stu-id="7058d-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="7058d-164">Cliquez sur **Supprimer la mise en miroir**.</span><span class="sxs-lookup"><span data-stu-id="7058d-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="7058d-165">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7058d-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="7058d-166">Procédez de la même façon avec la base de données mgccomp.</span><span class="sxs-lookup"><span data-stu-id="7058d-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="7058d-167">Sauvegardez la base de données mgc afin qu’elle puisse être restaurée vers la nouvelle base de données primaire :</span><span class="sxs-lookup"><span data-stu-id="7058d-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="7058d-168">À l’aide de SQL Server Management Studio, connectez-vous à l’instance mgc de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7058d-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="7058d-p113">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**. La boîte de dialogue **Sauvegarder la base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="7058d-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="7058d-171">Dans **Type de sauvegarde**, sélectionnez **Complète**.</span><span class="sxs-lookup"><span data-stu-id="7058d-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="7058d-172">Pour **Composant de sauvegarde**, cliquez sur **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="7058d-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="7058d-173">Acceptez le nom du jeu de sauvegarde par défaut suggéré dans **Nom** ou entrez un autre nom pour le jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7058d-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="7058d-174">\* \<Facultatif\> \*  Dans la zone **Description**, entrez une description du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7058d-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="7058d-175">Supprimez l’emplacement de sauvegarde par défaut de la liste de destination.</span><span class="sxs-lookup"><span data-stu-id="7058d-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="7058d-p114">Ajoutez un fichier à la liste en utilisant le chemin d’accès à l’emplacement de partage que vous avez établi pour l’envoi de journaux. Ce chemin d’accès est accessible à la base de données primaire et à la base de données de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7058d-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="7058d-178">Cliquez sur **OK** pour fermer la boîte de dialogue et lancer le processus de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7058d-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="7058d-179">Restaurez la base de données primaire à l’aide de la base de données de sauvegarde créée à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="7058d-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="7058d-180">À l’aide de SQL Server Management Studio, connectez-vous à l’instance mgc primaire.</span><span class="sxs-lookup"><span data-stu-id="7058d-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="7058d-p115">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, sur **Restaurer**, puis cliquez sur **Base de données**. La boîte de dialogue **Restaurer la base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="7058d-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="7058d-183">Sélectionnez **À partir du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="7058d-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="7058d-p116">Cliquez sur le bouton Parcourir pour ouvrir la boîte de dialogue **Spécifier la sauvegarde**. Dans **Support de sauvegarde**, sélectionnez **Fichier**. Cliquez sur **Ajouter**, sélectionnez le fichier de sauvegarde que vous avez créé à l’étape 3, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7058d-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="7058d-187">Dans **Sélectionnez les jeux de sauvegarde à restaurer**, sélectionnez la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7058d-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="7058d-188">Dans le volet **Sélectionner une page**, cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="7058d-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="7058d-189">Dans **Options de restauration**, sélectionnez uniquement **Remplacer la base de données existante**.</span><span class="sxs-lookup"><span data-stu-id="7058d-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="7058d-190">Dans **État de récupération**, sélectionnez **Laisser la base de données opérationnelle**.</span><span class="sxs-lookup"><span data-stu-id="7058d-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="7058d-191">Cliquez sur **OK** pour lancer le processus de restauration.</span><span class="sxs-lookup"><span data-stu-id="7058d-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="7058d-192">Configurer les journaux SQL Server pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="7058d-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="7058d-193">Suivez les procédures [configuration de haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) pour établir l’envoi de journaux pour la base de données mgc primaire.</span><span class="sxs-lookup"><span data-stu-id="7058d-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="7058d-194">Définir les serveurs actifs du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7058d-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="7058d-195">À partir de Skype pour Business Server Management Shell, utilisez l’applet de commande **Set-cspersistentchatactiveserver ne** pour définir la liste de serveurs actives.</span><span class="sxs-lookup"><span data-stu-id="7058d-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7058d-196">Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="7058d-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="7058d-197">Pour restaurer le pool à son état normal, exécutez la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="7058d-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="7058d-198">Pour plus d’informations, voir la rubrique d’aide sur l’applet de commande [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7058d-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

