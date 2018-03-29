---
title: Gestion de la haute disponibilité et de la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Résumé : Apprenez à gérer persistant Chat Server haute disponibilité et reprise après sinistre dans Skype pour Business Server 2015.'
ms.openlocfilehash: 8bc80ff6a38238b81b658a7f4d9620dc3a56b9be
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="52c2a-103">Gestion de la haute disponibilité et de la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="52c2a-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="52c2a-104">**Résumé :** Découvrez comment gérer persistant Chat Server haute disponibilité et reprise après sinistre dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="52c2a-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="52c2a-105">Cette rubrique décrit comment basculer et serveur de conversation précédent persistant.</span><span class="sxs-lookup"><span data-stu-id="52c2a-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="52c2a-106">Avant de lire cette rubrique, veillez à lire le [Plan pour la haute disponibilité et reprise après sinistre pour serveur Chat persistant dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) et [configuration haute disponibilité et reprise après sinistre pour serveur Chat persistant dans Skype pour Entreprise 2015 de serveur](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="52c2a-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="52c2a-107">Basculer sur le serveur de conversation permanent</span><span class="sxs-lookup"><span data-stu-id="52c2a-107">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="52c2a-108">Basculement de serveur de conversation persistant est conçu pour être principalement un processus manuel.</span><span class="sxs-lookup"><span data-stu-id="52c2a-108">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="52c2a-109">La procédure de basculement est basé sur l’hypothèse que le centre de données secondaire est en cours d’exécution, mais les services de serveur de conversation permanents où se trouve la base de données primaire de conversation permanents sont totalement indisponibles, y compris les suivantes :</span><span class="sxs-lookup"><span data-stu-id="52c2a-109">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="52c2a-110">Persistant Chat Server principal de base de données et base de données miroir de serveur de conversation persistant sont arrêtés.</span><span class="sxs-lookup"><span data-stu-id="52c2a-110">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="52c2a-111">Skype pour Business Server serveur frontal est en panne.</span><span class="sxs-lookup"><span data-stu-id="52c2a-111">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="52c2a-112">La procédure consiste en deux étapes de base :</span><span class="sxs-lookup"><span data-stu-id="52c2a-112">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="52c2a-113">Récupérer le Chat persistant base de données primaire (mgc).</span><span class="sxs-lookup"><span data-stu-id="52c2a-113">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="52c2a-114">Établir la mise en miroir pour la nouvelle base de données principale.</span><span class="sxs-lookup"><span data-stu-id="52c2a-114">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="52c2a-115">La conversation permanents conformité base de données (mgccomp) n’est pas basculé.</span><span class="sxs-lookup"><span data-stu-id="52c2a-115">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="52c2a-116">Le contenu de cette base de données est temporaire et purgé au fur et à mesure que l’adaptateur de conformité traite les données.</span><span class="sxs-lookup"><span data-stu-id="52c2a-116">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="52c2a-117">Il est de votre responsabilité, en tant qu’administrateur de Chat permanents, à gérer correctement la sortie de l’adaptateur pour éviter la perte de données.</span><span class="sxs-lookup"><span data-stu-id="52c2a-117">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="52c2a-118">Basculer vers un serveur de conversation permanente :</span><span class="sxs-lookup"><span data-stu-id="52c2a-118">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="52c2a-119">Supprimer l’envoi de journaux à partir de la base de données persistante Chat Server sauvegarde l’envoi de journaux.</span><span class="sxs-lookup"><span data-stu-id="52c2a-119">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
  - <span data-ttu-id="52c2a-120">À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données où se trouve la base de données de sauvegarde mgc persistant Chat Server.</span><span class="sxs-lookup"><span data-stu-id="52c2a-120">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
  - <span data-ttu-id="52c2a-121">Ouvrez une fenêtre de requête pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="52c2a-121">Open a query window to the master database.</span></span>
    
  - <span data-ttu-id="52c2a-122">Utilisez la commande suivante pour annuler la copie des journaux de transaction :</span><span class="sxs-lookup"><span data-stu-id="52c2a-122">Use the following command to drop log shipping:</span></span>
    
  ```
  exec sp_delete_log_shipping_secondary_database mgc
  ```

2. <span data-ttu-id="52c2a-123">Copiez tous les fichiers de sauvegarde non copiés se trouvant sur le partage de sauvegarde vers le dossier de destination de la copie du serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="52c2a-123">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="52c2a-124">Appliquez dans l’ordre toutes les sauvegardes du journal des transactions non appliquées à la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="52c2a-124">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="52c2a-125">Pour plus d’informations, consultez [Comment : appliquer une sauvegarde du journal des transactions (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span><span class="sxs-lookup"><span data-stu-id="52c2a-125">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="52c2a-p104">Mettez en ligne la base de données mgc de sauvegarde. Dans la fenêtre de requête ouverte à l’étape 1b, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="52c2a-p104">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
  - <span data-ttu-id="52c2a-128">Mettez fin à toutes les connexions à la base de données mgc, le cas échéant :</span><span class="sxs-lookup"><span data-stu-id="52c2a-128">End all connections to the mgc database, if there are any:</span></span>
    
  - <span data-ttu-id="52c2a-129">**exec sp_who2** pour identifier les connexions à la base de données mgc.</span><span class="sxs-lookup"><span data-stu-id="52c2a-129">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
  - <span data-ttu-id="52c2a-130">**kill \<spid\> ** pour mettre fin à ces connexions.</span><span class="sxs-lookup"><span data-stu-id="52c2a-130">**kill \<spid\>** to end these connections.</span></span>
    
  - <span data-ttu-id="52c2a-131">Mettez en ligne la base de données :</span><span class="sxs-lookup"><span data-stu-id="52c2a-131">Bring the database online:</span></span>
    
  - <span data-ttu-id="52c2a-132">**restaurer la base de données mgc avec récupération**.</span><span class="sxs-lookup"><span data-stu-id="52c2a-132">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="52c2a-133">Dans Skype pour Business Server Management Shell, utilisez la commande **Set-CsPersistentChatState-Identity « service : atl-cs-001.litwareinc.com » - PoolState FailedOver** basculer sur la base de données de sauvegarde de mgc.</span><span class="sxs-lookup"><span data-stu-id="52c2a-133">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="52c2a-134">Veillez à remplacer le nom de domaine complet de votre pool de conversation permanente par atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="52c2a-134">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="52c2a-135">La base de données mgc de sauvegarde est désormais la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="52c2a-135">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="52c2a-136">Dans Skype pour Business Server Management Shell, utilisez l’applet de commande **Install-CsMirrorDatabase** d’établir une mise en miroir haute disponibilité pour la sauvegarde de base de données qui sert désormais de la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="52c2a-136">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="52c2a-137">Utilisez l’instance de la base de données de sauvegarde en tant que base de données principale et l’instance de la base de données miroir de sauvegarde en tant qu’instance miroir.</span><span class="sxs-lookup"><span data-stu-id="52c2a-137">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="52c2a-138">Il ne s’agit pas du même miroir que celui qui a été initialement configuré pour la base de données principale pendant la configuration.</span><span class="sxs-lookup"><span data-stu-id="52c2a-138">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="52c2a-139">Définir les serveurs actifs du serveur de conversation persistant.</span><span class="sxs-lookup"><span data-stu-id="52c2a-139">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="52c2a-140">À partir de la Skype pour Business Server Management Shell, utilisez l’applet de commande **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.</span><span class="sxs-lookup"><span data-stu-id="52c2a-140">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="52c2a-141">Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="52c2a-141">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="52c2a-142">À ce stade, le basculement à partir de la base de données primaire du serveur de Chat persistant à la base de données de sauvegarde de serveur persistant de Chat se termine correctement.</span><span class="sxs-lookup"><span data-stu-id="52c2a-142">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="52c2a-143">Échec du serveur de conversation précédent persistant</span><span class="sxs-lookup"><span data-stu-id="52c2a-143">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="52c2a-144">Cette procédure décrit les étapes nécessaires pour récupérer d’une défaillance du serveur de conversation persistant et rétablir des opérations à partir du centre de données principal.</span><span class="sxs-lookup"><span data-stu-id="52c2a-144">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="52c2a-145">Lors de la défaillance du serveur de conversation permanents, le centre de données principal subit une panne complète et le serveur principal et de mise en miroir de bases de données ne sont plus disponibles.</span><span class="sxs-lookup"><span data-stu-id="52c2a-145">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="52c2a-146">Le centre de données principal bascule vers le serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="52c2a-146">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="52c2a-147">La procédure suivante rétablit le fonctionnement normal une fois le centre de données principal sauvegardé et les serveurs reconstruits.</span><span class="sxs-lookup"><span data-stu-id="52c2a-147">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="52c2a-148">La procédure suppose que le centre de données principal a été récupéré à partir de la panne totale et que la base de données mgc et la base de données mgccomp ont été reconstruits et réinstallés à l’aide du Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="52c2a-148">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="52c2a-149">La procédure s’appuie aussi sur le fait qu’aucun nouveau serveur (miroir et de sauvegarde) n’a été déployé au cours de la période de basculement, et que le seul serveur déployé est le serveur de sauvegarde et son serveur miroir, conformément à la définition donnée dans Basculement vers un serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="52c2a-149">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="52c2a-150">Ces étapes visent à récupérer la configuration telle qu’elle existait avant la défaillance, cette dernière ayant provoqué le basculement du serveur principal vers le serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="52c2a-150">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="52c2a-151">Effacer tous les serveurs de la liste permanente Chat Server Active Server à l’aide de l’applet de commande **Set-CsPersistentChatActiveServer** à partir de la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="52c2a-151">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="52c2a-152">Tous les serveurs Chat persistants à partir de la connexion à la base de données mgc et la base de données mgccomp au cours de la restauration s’arrête.</span><span class="sxs-lookup"><span data-stu-id="52c2a-152">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="52c2a-153">L’agent SQL Server sur le serveur secondaire persistant Chat Server serveur principal doit être en cours d’exécution sous un compte privilégié.</span><span class="sxs-lookup"><span data-stu-id="52c2a-153">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="52c2a-154">Plus précisément, le compte doit disposer des droits suivants :</span><span class="sxs-lookup"><span data-stu-id="52c2a-154">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="52c2a-155">Accès en lecture au partage réseau dans lequel les sauvegardes sont placées</span><span class="sxs-lookup"><span data-stu-id="52c2a-155">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="52c2a-156">Accès en écriture au répertoire local spécifique vers lequel les sauvegardes sont copiées</span><span class="sxs-lookup"><span data-stu-id="52c2a-156">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="52c2a-157">Désactivez la mise en miroir sur la base de données mgc de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="52c2a-157">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="52c2a-158">À l’aide de SQL Server Management Studio, connectez-vous à l’instance de sauvegarde mgc.</span><span class="sxs-lookup"><span data-stu-id="52c2a-158">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="52c2a-159">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Miroir**.</span><span class="sxs-lookup"><span data-stu-id="52c2a-159">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="52c2a-160">Cliquez sur **Supprimer la mise en miroir**.</span><span class="sxs-lookup"><span data-stu-id="52c2a-160">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="52c2a-161">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="52c2a-161">Click **OK**.</span></span>
    
   - <span data-ttu-id="52c2a-162">Procédez de la même façon avec la base de données mgccomp.</span><span class="sxs-lookup"><span data-stu-id="52c2a-162">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="52c2a-163">Sauvegardez la base de données mgc afin qu’elle puisse être restaurée vers la nouvelle base de données primaire :</span><span class="sxs-lookup"><span data-stu-id="52c2a-163">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="52c2a-164">À l’aide de SQL Server Management Studio, connectez-vous à l’instance de sauvegarde mgc.</span><span class="sxs-lookup"><span data-stu-id="52c2a-164">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="52c2a-p112">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**. La boîte de dialogue **Sauvegarder la base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="52c2a-p112">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="52c2a-167">Dans **Type de sauvegarde**, sélectionnez **Complète**.</span><span class="sxs-lookup"><span data-stu-id="52c2a-167">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="52c2a-168">Pour **Composant de sauvegarde**, cliquez sur **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="52c2a-168">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="52c2a-169">Acceptez le nom du jeu de sauvegarde par défaut suggéré dans **Nom** ou entrez un autre nom pour le jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="52c2a-169">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="52c2a-170">* \<Facultatif\> *  Dans la zone **Description**, entrez une description du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="52c2a-170">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="52c2a-171">Supprimez l’emplacement de sauvegarde par défaut de la liste de destination.</span><span class="sxs-lookup"><span data-stu-id="52c2a-171">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="52c2a-p113">Ajoutez un fichier à la liste en utilisant le chemin d’accès à l’emplacement de partage que vous avez établi pour l’envoi de journaux. Ce chemin d’accès est accessible à la base de données primaire et à la base de données de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="52c2a-p113">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="52c2a-174">Cliquez sur **OK** pour fermer la boîte de dialogue et lancer le processus de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="52c2a-174">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="52c2a-175">Restaurez la base de données primaire à l’aide de la base de données de sauvegarde créée à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="52c2a-175">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="52c2a-176">À l’aide de SQL Server Management Studio, de se connecter à l’instance principale mgc.</span><span class="sxs-lookup"><span data-stu-id="52c2a-176">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="52c2a-p114">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, sur **Restaurer**, puis cliquez sur **Base de données**. La boîte de dialogue **Restaurer la base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="52c2a-p114">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="52c2a-179">Sélectionnez **À partir du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="52c2a-179">Select **From Device**.</span></span>
    
   - <span data-ttu-id="52c2a-p115">Cliquez sur le bouton Parcourir pour ouvrir la boîte de dialogue **Spécifier la sauvegarde**. Dans **Support de sauvegarde**, sélectionnez **Fichier**. Cliquez sur **Ajouter**, sélectionnez le fichier de sauvegarde que vous avez créé à l’étape 3, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="52c2a-p115">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="52c2a-183">Dans **Sélectionnez les jeux de sauvegarde à restaurer**, sélectionnez la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="52c2a-183">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="52c2a-184">Dans le volet **Sélectionner une page**, cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="52c2a-184">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="52c2a-185">Dans **Options de restauration**, sélectionnez uniquement **Remplacer la base de données existante**.</span><span class="sxs-lookup"><span data-stu-id="52c2a-185">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="52c2a-186">Dans **État de récupération**, sélectionnez **Laisser la base de données opérationnelle**.</span><span class="sxs-lookup"><span data-stu-id="52c2a-186">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="52c2a-187">Cliquez sur **OK** pour lancer le processus de restauration.</span><span class="sxs-lookup"><span data-stu-id="52c2a-187">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="52c2a-188">Configurer l’envoi de journaux SQL Server pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="52c2a-188">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="52c2a-189">Suivez les procédures [configuration de haute disponibilité et reprise après sinistre pour serveur Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) pour établir l’envoi de journaux pour la base de données primaire mgc.</span><span class="sxs-lookup"><span data-stu-id="52c2a-189">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="52c2a-190">Définir les serveurs actifs du serveur de conversation persistant.</span><span class="sxs-lookup"><span data-stu-id="52c2a-190">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="52c2a-191">À partir de la Skype pour Business Server Management Shell, utilisez l’applet de commande **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.</span><span class="sxs-lookup"><span data-stu-id="52c2a-191">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="52c2a-192">Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="52c2a-192">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="52c2a-193">Pour restaurer le pool à son état normal, exécutez la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="52c2a-193">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="52c2a-194">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="52c2a-194">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

