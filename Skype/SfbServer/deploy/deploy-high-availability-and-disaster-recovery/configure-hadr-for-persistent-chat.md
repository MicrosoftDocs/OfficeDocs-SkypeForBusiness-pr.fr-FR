---
title: Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Résumé : cette rubrique vous explique comment configurer la haute disponibilité et la récupération après sinistre pour le serveur de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: a1589dbb22b3737cab1957637b98477502445958
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798261"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="8a9c7-103">Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="8a9c7-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8a9c7-104">**Résumé :** Pour plus d’informations sur la configuration d’une haute disponibilité et d’une reprise après sinistre pour le serveur Chat permanent, voir Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8a9c7-105">Skype entreprise Server prend en charge plusieurs modes de haute disponibilité pour votre serveur principal, y compris la mise en miroir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="8a9c7-106">Pour plus d'informations, reportez-vous à la rubrique [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="8a9c7-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a9c7-107">Les groupes de disponibilité AlwaysOn ne sont pas pris en charge par les serveurs de chat permanents.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="8a9c7-108">Avant de configurer votre déploiement de chat permanent pour une haute disponibilité et une reprise après sinistre, assurez-vous que vous connaissez les concepts de la [planification de la haute disponibilité et de la reprise après sinistre pour le serveur de chat permanent dans Skype entreprise server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="8a9c7-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="8a9c7-109">La solution de reprise après sinistre pour serveur de chat permanent décrite dans ces rubriques est basée sur un pool de serveurs de chat permanent étiré.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="8a9c7-110">Le contenu de la planification décrit les exigences en ressources et la topologie de pool étiré qui permet une disponibilité élevée et une reprise après sinistre pour le serveur de chat permanent, y compris l’utilisation de la mise en miroir SQL Server pour la haute disponibilité et l’envoi du journal SQL Server pour reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="8a9c7-111">Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="8a9c7-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="8a9c7-112">Dans le générateur de topologie, effectuez les étapes suivantes pour configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="8a9c7-113">Ajoutez les bases de données miroir et les magasins de données secondaires SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="8a9c7-114">Modifiez les propriétés du service de chat permanent serveur pour :</span><span class="sxs-lookup"><span data-stu-id="8a9c7-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="8a9c7-115">a.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-115">a.</span></span> <span data-ttu-id="8a9c7-116">activer la mise en miroir pour la base de données primaire ;</span><span class="sxs-lookup"><span data-stu-id="8a9c7-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="8a9c7-117">b.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-117">b.</span></span> <span data-ttu-id="8a9c7-118">Ajoutez le magasin SQL Server en miroir principal.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="8a9c7-119">c.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-119">c.</span></span> <span data-ttu-id="8a9c7-120">Activez la base de données d’envoi de journaux de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="8a9c7-121">d.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-121">d.</span></span> <span data-ttu-id="8a9c7-122">Ajoutez la banque SQL Server secondaire pour l’envoi du journal SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="8a9c7-123">e.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-123">e.</span></span> <span data-ttu-id="8a9c7-124">Ajoutez le miroir SQL Server Store pour la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="8a9c7-125">touche.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-125">f.</span></span> <span data-ttu-id="8a9c7-126">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="8a9c7-127">Configuration de la copie des journaux de transaction SQL Server pour la base de données principale du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="8a9c7-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="8a9c7-128">À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données d’envoi de journaux secondaires du serveur Chat permanent et assurez-vous que l’agent SQL Server est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="8a9c7-129">Ensuite, connectez-vous à l’instance de base de données principale de chat permanent et effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="8a9c7-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="8a9c7-130">Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="8a9c7-131">Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="8a9c7-132">Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="8a9c7-133">Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="8a9c7-134">Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès vers le partage que vous avez créé pour le dossier de sauvegarde des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="8a9c7-p110">Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local vers le dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier (exemple : c:\sauvegarde)**. (Dans le cas contraire, laissez cette zone vide.)</span><span class="sxs-lookup"><span data-stu-id="8a9c7-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8a9c7-137">Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer votre dossier de sauvegarde sur le serveur principal et spécifier un chemin local vers ce dossier.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="8a9c7-138">Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="8a9c7-139">Examinez la planification des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="8a9c7-140">Pour personnaliser le planning de votre installation, cliquez sur **Planning**, puis ajustez la planification de l’agent SQL Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="8a9c7-141">Sous **Compression**, sélectionnez **Utiliser le paramètre du serveur par défaut**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="8a9c7-142">Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="8a9c7-143">Cliquez sur **se connecter** , puis connectez-vous à l’instance de SQL Server que vous avez configurée en tant que serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="8a9c7-144">Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="8a9c7-145">Sous l’onglet **Initialiser la base de données secondaire**, sélectionnez l’option **Oui, générer une sauvegarde complète de la base de données primaire et la restaurer dans la base de données secondaire (créer la base de données secondaire si elle n’existe pas)**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="8a9c7-p112">Sous l’onglet **Copier les fichiers**, dans la zone **Dossier de destination des fichiers copiés**, tapez le chemin d’accès au dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées. Ce dossier se trouve souvent sur le serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="8a9c7-148">Examinez la planification des copies dans la zone **Planification** sous **Copier le travail**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="8a9c7-149">Pour personnaliser le planning de votre installation, cliquez sur **Planning**, puis ajustez la planification de l’agent SQL Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="8a9c7-150">Cette planification doit être approximativement la même que celle des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="8a9c7-151">Sous l’onglet **Restaurer**, sous **État de la base de données lors de la restauration des sauvegardes**, choisissez l’option **Mode sans récupération**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="8a9c7-152">Sous **Retarder la restauration des sauvegardes d’au moins :**, sélectionnez **0 minutes**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="8a9c7-153">Choisissez un seuil d’alerte sous **Envoyer une alerte si aucune restauration ne se produit en l’espace de**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="8a9c7-154">Examinez la planification des restaurations dans la zone **Planification** sous **Restaurer le travail**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="8a9c7-155">Pour personnaliser le planning de votre installation, cliquez sur **Planning**, ajustez la planification de l’agent SQL Server selon les besoins, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="8a9c7-156">Cette planification doit être approximativement la même que celle des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="8a9c7-157">Dans la boîte de dialogue **Propriétés de la base de données**, cliquez sur **OK** pour lancer le processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="8a9c7-158">Définition de la copie des journaux de transaction SQL Server entre la base de données miroir principale et la base de données secondaire</span><span class="sxs-lookup"><span data-stu-id="8a9c7-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="8a9c7-159">Pour continuer, procédez comme suit pour l’envoi de journaux dans le cas où la base de données de chat persistante principale a basculé vers sa base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="8a9c7-160">Basculez manuellement vers le miroir sur la base de données de conversation persistante principale.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="8a9c7-161">Pour ce faire, utilisez Skype entreprise Server Management Shell et l’applet **de passe Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="8a9c7-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="8a9c7-162">À l’aide de SQL Server Management Studio, connectez-vous à l’instance de miroir du serveur de chat permanent principal.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="8a9c7-163">Assurez-vous que l’agent SQL Server est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="8a9c7-164">Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="8a9c7-165">Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="8a9c7-166">Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="8a9c7-167">Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="8a9c7-168">Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès réseau du partage que vous avez créé pour le dossier de sauvegarde du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="8a9c7-p116">Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local au dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier**. (Si le dossier de sauvegarde ne figure pas sur le serveur principal, vous pouvez laisser cette case à cocher vide.)</span><span class="sxs-lookup"><span data-stu-id="8a9c7-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8a9c7-171">Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer votre dossier de sauvegarde sur le serveur principal et spécifier un chemin local vers ce dossier.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="8a9c7-172">Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="8a9c7-173">Examinez la planification des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="8a9c7-174">Pour personnaliser le planning de votre installation, cliquez sur **Planning**, puis ajustez la planification de l’agent SQL Server, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8a9c7-175">Utilisez les mêmes paramètres que ceux de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="8a9c7-176">Sous **Compression**, sélectionnez **Utiliser le paramètre du serveur par défaut**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="8a9c7-177">Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="8a9c7-178">Cliquez sur **Connexion**, puis connectez-vous à l’instance de SQL Server que vous avez configurée en tant que serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="8a9c7-179">Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="8a9c7-180">Sous l’onglet **Initialiser la base de données secondaire**, sélectionnez l’option **Non, la base de données secondaire est initialisée**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="8a9c7-p118">Sous l’onglet **Copier les fichiers**, dans **Dossier de destination des fichiers copiés**, tapez le chemin d’accès du dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées, puis cliquez sur **OK**. Ce dossier est souvent situé sur le serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="8a9c7-183">Ouvrez la liste déroulante **Créer un script de configuration**, puis sélectionnez **Créer un script de configuration dans une nouvelle fenêtre de requête**.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="8a9c7-184">Dans la nouvelle fenêtre de requête, dans **Propriétés de la base de données**, cliquez sur **OK** pour commencer le processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="8a9c7-185">Sélectionnez et exécutez la première moitié de la requête (Voir l’étape 18) jusqu’à la ligne :- \* \* \* \* \* \* -end : script à exécuter sur le principal \* \* \* \* \* \*:.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8a9c7-186">L’exécution manuelle de ce script est nécessaire car SQL Server Management Studio ne prend pas en charge plusieurs bases de données principales dans une configuration d’envoi du journal SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="8a9c7-187">Sélectionnez **Annuler** pour fermer le panneau de configuration de copie des journaux de transaction et établir une configuration de travail qui implémente correctement la copie des journaux de transaction pour la base de données primaire et la base de données en miroir (en cas de basculement). </span><span class="sxs-lookup"><span data-stu-id="8a9c7-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="8a9c7-188">Restaurez manuellement la base de données de conversation persistante principale sur le serveur principal.</span><span class="sxs-lookup"><span data-stu-id="8a9c7-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="8a9c7-189">Pour ce faire, utilisez Skype entreprise Server Management Shell et l’applet de passe **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="8a9c7-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

