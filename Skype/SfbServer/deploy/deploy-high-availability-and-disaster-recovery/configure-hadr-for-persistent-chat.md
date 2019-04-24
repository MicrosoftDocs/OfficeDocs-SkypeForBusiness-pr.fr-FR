---
title: Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: 5c53652cf5084b5a6c021c38f71f1cccc0322efa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225489"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="b65f0-103">Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b65f0-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b65f0-104">**Résumé :** Lisez cette rubrique pour savoir comment configurer une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b65f0-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b65f0-105">Skype pour Business Server prend en charge plusieurs modes de haute disponibilité pour vos serveurs principaux, y compris la mise en miroir de base de données.</span><span class="sxs-lookup"><span data-stu-id="b65f0-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="b65f0-106">Pour plus d'informations, reportez-vous à la rubrique [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="b65f0-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b65f0-107">Groupes de disponibilité AlwaysOn ne sont pas pris en charge avec les serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b65f0-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="b65f0-108">Avant de configurer votre déploiement de conversation permanente pour la haute disponibilité et de récupération d’urgence, veillez à ce que vous êtes familiarisé avec les concepts présentés dans le [Plan de haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="b65f0-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="b65f0-109">La solution de récupération d’urgence pour les serveurs de conversation permanente décrites dans ces rubriques repose sur un pool de serveurs de conversation permanente étiré.</span><span class="sxs-lookup"><span data-stu-id="b65f0-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="b65f0-110">Décrit les besoins en ressources et la topologie de pool étiré qui permet une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente, notamment à l’aide de la mise en miroir SQL Server pour une haute disponibilité et SQL Server envoi de journaux pour le contenu de planification récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="b65f0-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="b65f0-111">Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="b65f0-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="b65f0-112">Dans le générateur de topologie, effectuez les étapes suivantes pour configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b65f0-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="b65f0-113">Ajoutez les bases de données miroir et le journal d’expédition base de données secondaire que magasins SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b65f0-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="b65f0-114">Modifier les propriétés du service serveur de conversation permanente pour :</span><span class="sxs-lookup"><span data-stu-id="b65f0-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="b65f0-115">a.</span><span class="sxs-lookup"><span data-stu-id="b65f0-115">a.</span></span> <span data-ttu-id="b65f0-116">activer la mise en miroir pour la base de données primaire ;</span><span class="sxs-lookup"><span data-stu-id="b65f0-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="b65f0-117">b.</span><span class="sxs-lookup"><span data-stu-id="b65f0-117">b.</span></span> <span data-ttu-id="b65f0-118">Ajouter le magasin SQL Server miroir principal ;</span><span class="sxs-lookup"><span data-stu-id="b65f0-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="b65f0-119">c.</span><span class="sxs-lookup"><span data-stu-id="b65f0-119">c.</span></span> <span data-ttu-id="b65f0-120">Activer la base de données de journaux SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b65f0-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="b65f0-121">d.</span><span class="sxs-lookup"><span data-stu-id="b65f0-121">d.</span></span> <span data-ttu-id="b65f0-122">Ajoutez l’envoi de journaux SQL Server secondaire du magasin SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b65f0-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="b65f0-123">e.</span><span class="sxs-lookup"><span data-stu-id="b65f0-123">e.</span></span> <span data-ttu-id="b65f0-124">Ajouter le miroir du magasin SQL Server pour la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="b65f0-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="b65f0-125">f.</span><span class="sxs-lookup"><span data-stu-id="b65f0-125">f.</span></span> <span data-ttu-id="b65f0-126">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="b65f0-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="b65f0-127">Configuration de la copie des journaux de transaction SQL Server pour la base de données principale du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="b65f0-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="b65f0-128">À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données Persistent Chat Server secondaire envoi de journaux et assurez-vous que l’Agent SQL Server est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="b65f0-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="b65f0-129">Connectez-vous à l’instance de base de données principale de conversation permanente, puis effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b65f0-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="b65f0-130">Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="b65f0-131">Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="b65f0-132">Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="b65f0-133">Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="b65f0-134">Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès vers le partage que vous avez créé pour le dossier de sauvegarde des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="b65f0-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="b65f0-p110">Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local vers le dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier (exemple : c:\sauvegarde)**. (Dans le cas contraire, laissez cette zone vide.)</span><span class="sxs-lookup"><span data-stu-id="b65f0-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b65f0-137">Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer le dossier de sauvegarde sur le serveur principal et spécifier un chemin d’accès local pour ce dossier.</span><span class="sxs-lookup"><span data-stu-id="b65f0-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="b65f0-138">Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="b65f0-139">Examinez la planification des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="b65f0-140">Pour personnaliser la planification de votre installation, cliquez sur **la planification**et ajustez la planification de l’Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b65f0-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="b65f0-141">Sous **Compression**, sélectionnez **Utiliser le paramètre du serveur par défaut**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="b65f0-142">Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="b65f0-143">Cliquez sur **se connecter** et se connecter à l’instance de SQL Server que vous avez configuré en tant que serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="b65f0-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="b65f0-144">Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="b65f0-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="b65f0-145">Sous l’onglet **Initialiser la base de données secondaire**, sélectionnez l’option **Oui, générer une sauvegarde complète de la base de données primaire et la restaurer dans la base de données secondaire (créer la base de données secondaire si elle n’existe pas)**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="b65f0-p112">Sous l’onglet **Copier les fichiers**, dans la zone **Dossier de destination des fichiers copiés**, tapez le chemin d’accès au dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées. Ce dossier se trouve souvent sur le serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="b65f0-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="b65f0-148">Examinez la planification des copies dans la zone **Planification** sous **Copier le travail**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="b65f0-149">Pour personnaliser la planification de votre installation, cliquez sur **la planification**et ajustez la planification de l’Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b65f0-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="b65f0-150">Cette planification doit être approximativement la même que celle des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="b65f0-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="b65f0-151">Sous l’onglet **Restaurer**, sous **État de la base de données lors de la restauration des sauvegardes**, choisissez l’option **Mode sans récupération**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="b65f0-152">Sous **Retarder la restauration des sauvegardes d’au moins :**, sélectionnez **0 minutes**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="b65f0-153">Choisissez un seuil d’alerte sous **Envoyer une alerte si aucune restauration ne se produit en l’espace de**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="b65f0-154">Examinez la planification des restaurations dans la zone **Planification** sous **Restaurer le travail**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="b65f0-155">Pour personnaliser la planification de votre installation, cliquez sur **la planification**, ajustez la planification de l’Agent SQL Server et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="b65f0-156">Cette planification doit être approximativement la même que celle des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="b65f0-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="b65f0-157">Dans la boîte de dialogue **Propriétés de la base de données**, cliquez sur **OK** pour lancer le processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="b65f0-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="b65f0-158">Définition de la copie des journaux de transaction SQL Server entre la base de données miroir principale et la base de données secondaire</span><span class="sxs-lookup"><span data-stu-id="b65f0-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="b65f0-159">Effectuez les étapes suivantes pour l’envoi de journaux pour continuer si la base de données primaire conversation permanente est basculé vers sa base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="b65f0-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="b65f0-160">Basculer manuellement la base de données de conversation permanente principal vers le serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="b65f0-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="b65f0-161">Cette opération est effectuée à l’aide de la Skype pour Business Server Management Shell et l’applet de commande **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="b65f0-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="b65f0-162">À l’aide de SQL Server Management Studio, connectez-vous à l’instance miroir Persistent Chat Server principal.</span><span class="sxs-lookup"><span data-stu-id="b65f0-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="b65f0-163">N’oubliez pas que l’Agent SQL Server est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="b65f0-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="b65f0-164">Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="b65f0-165">Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="b65f0-166">Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="b65f0-167">Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="b65f0-168">Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès réseau du partage que vous avez créé pour le dossier de sauvegarde du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="b65f0-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="b65f0-p116">Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local au dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier**. (Si le dossier de sauvegarde ne figure pas sur le serveur principal, vous pouvez laisser cette case à cocher vide.)</span><span class="sxs-lookup"><span data-stu-id="b65f0-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b65f0-171">Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer le dossier de sauvegarde sur le serveur principal et spécifier un chemin d’accès local pour ce dossier.</span><span class="sxs-lookup"><span data-stu-id="b65f0-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="b65f0-172">Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="b65f0-173">Examinez la planification des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="b65f0-174">Pour personnaliser la planification de votre installation, cliquez sur **la planification**et ajustez la planification de l’Agent SQL Server, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="b65f0-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b65f0-175">Utilisez les mêmes paramètres que ceux de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="b65f0-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="b65f0-176">Sous **Compression**, sélectionnez **Utiliser le paramètre du serveur par défaut**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="b65f0-177">Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="b65f0-178">Cliquez sur **Connexion**, puis connectez-vous à l’instance de SQL Server que vous avez configurée en tant que serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="b65f0-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="b65f0-179">Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="b65f0-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="b65f0-180">Sous l’onglet **Initialiser la base de données secondaire**, sélectionnez l’option **Non, la base de données secondaire est initialisée**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="b65f0-p118">Sous l’onglet **Copier les fichiers**, dans **Dossier de destination des fichiers copiés**, tapez le chemin d’accès du dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées, puis cliquez sur **OK**. Ce dossier est souvent situé sur le serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="b65f0-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="b65f0-183">Ouvrez la liste déroulante **Créer un script de configuration**, puis sélectionnez **Créer un script de configuration dans une nouvelle fenêtre de requête**.</span><span class="sxs-lookup"><span data-stu-id="b65f0-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="b65f0-184">Dans la nouvelle fenêtre de requête, dans **Propriétés de la base de données**, cliquez sur **OK** pour commencer le processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="b65f0-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="b65f0-185">Sélectionnez et exécutez la première moitié de la requête (voir l’étape 18) up à la ligne :-- \* \* \* \* \* \* fin : Script à exécuter sur le serveur principal : \* \* \* \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="b65f0-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b65f0-186">Exécution manuelle de ce script est nécessaire car SQL Server Management Studio ne prend pas en charge plusieurs bases de données primaires dans une configuration de l’envoi de journaux SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b65f0-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="b65f0-187">Sélectionnez **Annuler** pour fermer le panneau de configuration de copie des journaux de transaction et établir une configuration de travail qui implémente correctement la copie des journaux de transaction pour la base de données primaire et la base de données en miroir (en cas de basculement). </span><span class="sxs-lookup"><span data-stu-id="b65f0-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="b65f0-188">Restaurez manuellement la base de données de conversation permanente principal vers le serveur principal.</span><span class="sxs-lookup"><span data-stu-id="b65f0-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="b65f0-189">Cette opération est effectuée à l’aide de la Skype pour Business Server Management Shell et l’applet de commande **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="b65f0-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

