---
title: Gérer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Résumé : Découvrez comment gérer la haute disponibilité et la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 4fb3a38fadf2a8a063715e389718859dcc7ddbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122408"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="8e42b-103">Gérer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="8e42b-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8e42b-104">**Résumé :** Découvrez comment gérer la haute disponibilité et la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8e42b-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8e42b-105">Cette rubrique décrit comment faire échouer et faire échouer le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="8e42b-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="8e42b-106">Avant de lire cette rubrique, veillez à lire Planifier la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise [Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) et à configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise [Server 2015.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)</span><span class="sxs-lookup"><span data-stu-id="8e42b-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8e42b-107">La conversation permanente est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8e42b-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="8e42b-108">Les mêmes fonctionnalités sont disponibles dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8e42b-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="8e42b-109">Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="8e42b-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="8e42b-110">Si vous devez utiliser la conversation permanente, vous pouvez migrer les utilisateurs nécessitant cette fonctionnalité vers Teams ou continuer à utiliser Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8e42b-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="8e42b-111">Faire échouer le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="8e42b-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="8e42b-112">Le failover pour le serveur de conversation permanente est conçu pour être principalement un processus manuel.</span><span class="sxs-lookup"><span data-stu-id="8e42b-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="8e42b-113">La procédure de failover repose sur l’hypothèse que le centre de données secondaire est opérationnel, mais les services du serveur de conversation permanente où se trouve la base de données de conversation permanente principale sont complètement indisponibles, notamment :</span><span class="sxs-lookup"><span data-stu-id="8e42b-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="8e42b-114">La base de données principale du serveur de conversation permanente et la base de données miroir du serveur de conversation permanente sont en panne.</span><span class="sxs-lookup"><span data-stu-id="8e42b-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="8e42b-115">Le serveur frontal Skype Entreprise Server est en panne.</span><span class="sxs-lookup"><span data-stu-id="8e42b-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="8e42b-116">La procédure consiste en deux étapes de base :</span><span class="sxs-lookup"><span data-stu-id="8e42b-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="8e42b-117">Récupérez la base de données de conversation permanente principale (mgc).</span><span class="sxs-lookup"><span data-stu-id="8e42b-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="8e42b-118">Établir la mise en miroir pour la nouvelle base de données principale.</span><span class="sxs-lookup"><span data-stu-id="8e42b-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="8e42b-119">La base de données de conformité de conversation permanente (mgccomp) n’est pas recalculée.</span><span class="sxs-lookup"><span data-stu-id="8e42b-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="8e42b-120">Le contenu de cette base de données est temporaire et purgé au fur et à mesure que l’adaptateur de conformité traite les données.</span><span class="sxs-lookup"><span data-stu-id="8e42b-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="8e42b-121">Il est de votre responsabilité, en tant qu’administrateur de conversation permanente, de gérer correctement la sortie de la carte afin d’éviter la perte de données.</span><span class="sxs-lookup"><span data-stu-id="8e42b-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="8e42b-122">Pour faire échouer le serveur de conversation permanente :</span><span class="sxs-lookup"><span data-stu-id="8e42b-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="8e42b-123">Supprimez la copie des journaux de livraison de la base de données de copie des journaux de sauvegarde du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="8e42b-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="8e42b-124">À l SQL Server Management Studio, connectez-vous à l’instance de base de données où se trouve la base de données mgc de sauvegarde du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="8e42b-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="8e42b-125">Ouvrez une fenêtre de requête pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="8e42b-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="8e42b-126">Utilisez la commande suivante pour annuler la copie des journaux de transaction :</span><span class="sxs-lookup"><span data-stu-id="8e42b-126">Use the following command to drop log shipping:</span></span>
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="8e42b-127">Copiez tous les fichiers de sauvegarde non copiés se trouvant sur le partage de sauvegarde vers le dossier de destination de la copie du serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8e42b-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="8e42b-128">Appliquez dans l’ordre toutes les sauvegardes du journal des transactions non appliquées à la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="8e42b-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="8e42b-129">Pour plus d’informations, [voir How to: Apply a Transaction Log Backup (Transact-SQL).](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="8e42b-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105)).</span></span>
    
4. <span data-ttu-id="8e42b-p105">Mettez en ligne la base de données mgc de sauvegarde. Dans la fenêtre de requête ouverte à l’étape 1b, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8e42b-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="8e42b-132">Mettez fin à toutes les connexions à la base de données mgc, le cas échéant :</span><span class="sxs-lookup"><span data-stu-id="8e42b-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="8e42b-133">**exec sp_who2** pour identifier les connexions à la base de données mgc.</span><span class="sxs-lookup"><span data-stu-id="8e42b-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="8e42b-134">**kill \<spid\>** pour mettre fin à ces connexions.</span><span class="sxs-lookup"><span data-stu-id="8e42b-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="8e42b-135">Mettez en ligne la base de données :</span><span class="sxs-lookup"><span data-stu-id="8e42b-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="8e42b-136">**restaurer la base de données mgc avec récupération.**</span><span class="sxs-lookup"><span data-stu-id="8e42b-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="8e42b-137">Dans Skype Entreprise Server Management Shell, utilisez la commande **Set-CsPersistentChatState -Identity « service:atl-cs-001.litwareinc.com » -PoolState FailedOver** pour faire échouer la base de données de sauvegarde mgc.</span><span class="sxs-lookup"><span data-stu-id="8e42b-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="8e42b-138">N’oubliez pas de remplacer le nom de domaine complet de votre pool de conversation permanente par atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="8e42b-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="8e42b-139">La base de données mgc de sauvegarde est désormais la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="8e42b-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="8e42b-140">Dans Skype Entreprise Server Management Shell, utilisez l’cmdlet **Install-CsMirrorDatabase** pour établir un miroir de haute disponibilité pour la base de données de sauvegarde qui sert désormais de base de données principale.</span><span class="sxs-lookup"><span data-stu-id="8e42b-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="8e42b-141">Utilisez l’instance de la base de données de sauvegarde en tant que base de données principale et l’instance de la base de données miroir de sauvegarde en tant qu’instance miroir.</span><span class="sxs-lookup"><span data-stu-id="8e42b-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="8e42b-142">Il ne s’agit pas du même miroir que celui qui a été initialement configuré pour la base de données principale pendant la configuration.</span><span class="sxs-lookup"><span data-stu-id="8e42b-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="8e42b-143">Définissez les serveurs actifs du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="8e42b-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="8e42b-144">À partir de Skype Entreprise Server Management Shell, utilisez l’applet de commandes **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.</span><span class="sxs-lookup"><span data-stu-id="8e42b-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8e42b-145">Tous les serveurs actifs doivent être situés dans le même centre de données que celui de la nouvelle base de données principale, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="8e42b-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="8e42b-146">À ce stade, le passage de la base de données principale du serveur de conversation permanente à la base de données de sauvegarde du serveur de conversation permanente se termine correctement.</span><span class="sxs-lookup"><span data-stu-id="8e42b-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="8e42b-147">Faire échouer le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="8e42b-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="8e42b-148">Cette procédure décrit les étapes nécessaires à la récupération après une défaillance du serveur de conversation permanente et à la reprise des opérations à partir du centre de données principal.</span><span class="sxs-lookup"><span data-stu-id="8e42b-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="8e42b-149">En cas de défaillance du serveur de conversation permanente, le centre de données principal subit une panne complète et les bases de données principale et miroir deviennent indisponibles.</span><span class="sxs-lookup"><span data-stu-id="8e42b-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="8e42b-150">Le centre de données principal bascule vers le serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8e42b-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="8e42b-151">La procédure suivante rétablit le fonctionnement normal une fois le centre de données principal sauvegardé et les serveurs reconstruits.</span><span class="sxs-lookup"><span data-stu-id="8e42b-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="8e42b-152">La procédure suppose que le centre de données principal a été récupéré après une panne totale et que la base de données mgc et la base de données mgccomp ont été reconstruites et réinstallées à l’aide du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="8e42b-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="8e42b-153">La procédure suppose également qu’aucun nouveau serveur miroir et serveur de sauvegarde n’a été déployé pendant la période de failover, et que le seul serveur déployé est le serveur de sauvegarde et son serveur miroir, comme défini précédemment dans Le serveur de conversation permanente fail over Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="8e42b-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="8e42b-154">Ces étapes visent à récupérer la configuration telle qu’elle existait avant la défaillance, cette dernière ayant provoqué le basculement du serveur principal vers le serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8e42b-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="8e42b-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8e42b-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="8e42b-156">Cela empêche tous les serveurs de conversation permanente de se connecter à la base de données mgc et à la base de données mgccomp pendant la récupération.</span><span class="sxs-lookup"><span data-stu-id="8e42b-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8e42b-157">L’agent SQL Server sur le serveur principal du serveur de conversation permanente secondaire doit être en cours d’exécution sous un compte privilégié.</span><span class="sxs-lookup"><span data-stu-id="8e42b-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="8e42b-158">Plus précisément, le compte doit disposer des droits suivants :</span><span class="sxs-lookup"><span data-stu-id="8e42b-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="8e42b-159">Accès en lecture au partage réseau dans lequel les sauvegardes sont placées</span><span class="sxs-lookup"><span data-stu-id="8e42b-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="8e42b-160">Accès en écriture au répertoire local spécifique vers lequel les sauvegardes sont copiées</span><span class="sxs-lookup"><span data-stu-id="8e42b-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="8e42b-161">Désactivez la mise en miroir sur la base de données mgc de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="8e42b-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="8e42b-162">À l SQL Server Management Studio, connectez-vous à l’instance mgc de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8e42b-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="8e42b-163">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Miroir**.</span><span class="sxs-lookup"><span data-stu-id="8e42b-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="8e42b-164">Cliquez sur **Supprimer la mise en miroir**.</span><span class="sxs-lookup"><span data-stu-id="8e42b-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="8e42b-165">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e42b-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="8e42b-166">Procédez de la même façon avec la base de données mgccomp.</span><span class="sxs-lookup"><span data-stu-id="8e42b-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="8e42b-167">Sauvegardez la base de données mgc afin qu’elle puisse être restaurée vers la nouvelle base de données primaire :</span><span class="sxs-lookup"><span data-stu-id="8e42b-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="8e42b-168">À l SQL Server Management Studio, connectez-vous à l’instance mgc de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8e42b-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="8e42b-p113">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**. La boîte de dialogue **Sauvegarder la base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="8e42b-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="8e42b-171">Dans **Type de sauvegarde**, sélectionnez **Complète**.</span><span class="sxs-lookup"><span data-stu-id="8e42b-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="8e42b-172">Pour **Composant de sauvegarde**, cliquez sur **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="8e42b-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="8e42b-173">Acceptez le nom du jeu de sauvegarde par défaut suggéré dans **Nom** ou entrez un autre nom pour le jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8e42b-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="8e42b-174">*\<Optional\>*  Dans **Description,** entrez une description du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8e42b-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="8e42b-175">Supprimez l’emplacement de sauvegarde par défaut de la liste de destination.</span><span class="sxs-lookup"><span data-stu-id="8e42b-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="8e42b-p114">Ajoutez un fichier à la liste en utilisant le chemin d’accès à l’emplacement de partage que vous avez établi pour l’envoi de journaux. Ce chemin d’accès est accessible à la base de données primaire et à la base de données de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8e42b-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="8e42b-178">Cliquez sur **OK** pour fermer la boîte de dialogue et lancer le processus de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8e42b-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="8e42b-179">Restaurez la base de données primaire à l’aide de la base de données de sauvegarde créée à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="8e42b-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="8e42b-180">À l SQL Server Management Studio, connectez-vous à l’instance mgc principale.</span><span class="sxs-lookup"><span data-stu-id="8e42b-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="8e42b-p115">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, sur **Restaurer**, puis cliquez sur **Base de données**. La boîte de dialogue **Restaurer la base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="8e42b-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="8e42b-183">Sélectionnez **À partir du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="8e42b-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="8e42b-p116">Cliquez sur le bouton Parcourir pour ouvrir la boîte de dialogue **Spécifier la sauvegarde**. Dans **Support de sauvegarde**, sélectionnez **Fichier**. Cliquez sur **Ajouter**, sélectionnez le fichier de sauvegarde que vous avez créé à l’étape 3, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e42b-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="8e42b-187">Dans **Sélectionnez les jeux de sauvegarde à restaurer**, sélectionnez la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8e42b-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="8e42b-188">Dans le volet **Sélectionner une page**, cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="8e42b-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="8e42b-189">Dans **Options de restauration**, sélectionnez uniquement **Remplacer la base de données existante**.</span><span class="sxs-lookup"><span data-stu-id="8e42b-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="8e42b-190">Dans **État de récupération**, sélectionnez **Laisser la base de données opérationnelle**.</span><span class="sxs-lookup"><span data-stu-id="8e42b-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="8e42b-191">Cliquez sur **OK** pour lancer le processus de restauration.</span><span class="sxs-lookup"><span data-stu-id="8e42b-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="8e42b-192">Configurez la SQL Server des journaux de livraison pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="8e42b-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="8e42b-193">Suivez les procédures de [configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span><span class="sxs-lookup"><span data-stu-id="8e42b-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="8e42b-194">Définissez les serveurs actifs du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="8e42b-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="8e42b-195">À partir de Skype Entreprise Server Management Shell, utilisez l’applet de commandes **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.</span><span class="sxs-lookup"><span data-stu-id="8e42b-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8e42b-196">Tous les serveurs actifs doivent être situés dans le même centre de données que celui de la nouvelle base de données principale, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="8e42b-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="8e42b-197">Pour restaurer l’état normal du pool, exécutez la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="8e42b-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="8e42b-198">Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Set-CsPersistentChatState.](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8e42b-198">For more information, see the help topic for the [Set-CsPersistentChatState](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
