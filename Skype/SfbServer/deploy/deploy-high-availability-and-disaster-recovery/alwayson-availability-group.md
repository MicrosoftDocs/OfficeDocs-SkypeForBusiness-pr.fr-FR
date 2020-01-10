---
title: Déploiement d’un groupe toujours disponible sur un serveur principal dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Déploiement (installation) d’un groupe toujours disponible dans le déploiement de Skype entreprise Server.
ms.openlocfilehash: eadf3c67f5d2618d7070c2a3540c2a9ad08b5942
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002914"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="bd256-103">Déploiement d’un groupe toujours disponible sur un serveur principal dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bd256-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="bd256-104">Déploiement (installation) d’un groupe toujours disponible sur le déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="bd256-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="bd256-105">Le mode de déploiement d’un programme AG dépend du mode de déploiement dans un nouveau pool, d’un pool existant qui utilise la mise en miroir ou d’un pool existant qui n’est actuellement pas disponible pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="bd256-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd256-106">L’utilisation de la fonction AG avec un rôle serveur de chat permanent n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="bd256-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="bd256-107">Déploiement d’un groupe toujours disponible sur une nouvelle liste frontale</span><span class="sxs-lookup"><span data-stu-id="bd256-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="bd256-108">Déployer un groupe toujours disponible sur un pool existant qui utilise la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="bd256-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="bd256-109">Déployer un groupe toujours disponible sur un pool existant qui n’utilise pas la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="bd256-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="bd256-110">Déploiement d’un groupe toujours disponible sur une nouvelle liste frontale</span><span class="sxs-lookup"><span data-stu-id="bd256-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="bd256-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="bd256-111"></span></span>

1. <span data-ttu-id="bd256-112">Activez la fonctionnalité de mise en cluster de basculement sur tous les serveurs de base de données qui feront partie de la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="bd256-113">Sur chaque serveur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bd256-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="bd256-114">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="bd256-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="bd256-p102">Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="bd256-117">Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="bd256-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="bd256-118">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="bd256-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="bd256-119">Validez la configuration de cluster.</span><span class="sxs-lookup"><span data-stu-id="bd256-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="bd256-120">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.</span><span class="sxs-lookup"><span data-stu-id="bd256-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="bd256-121">Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.</span><span class="sxs-lookup"><span data-stu-id="bd256-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="bd256-122">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-123">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.</span><span class="sxs-lookup"><span data-stu-id="bd256-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="bd256-p103">Dans la boîte **Résumé**, vérifiez les erreurs signalées par l’Assistant, puis cliquez sur **Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="bd256-p103">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="bd256-p104">L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="bd256-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="bd256-129">Créez le cluster de basculement de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="bd256-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="bd256-130">Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.</span><span class="sxs-lookup"><span data-stu-id="bd256-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="bd256-131">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-p105">Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-134">Dans la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-135">Après la création du cluster, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="bd256-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="bd256-p106">Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bd256-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="bd256-138">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.</span><span class="sxs-lookup"><span data-stu-id="bd256-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="bd256-139">Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.</span><span class="sxs-lookup"><span data-stu-id="bd256-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="bd256-140">Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.</span><span class="sxs-lookup"><span data-stu-id="bd256-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="bd256-141">Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-142">Dans la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="bd256-143">Sur chaque serveur dans le cluster, activez la fonction AG dans le gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd256-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="bd256-p107">Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server. </span><span class="sxs-lookup"><span data-stu-id="bd256-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="bd256-p108">Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="bd256-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="bd256-148">Utilisez le générateur de topologie pour créer le pool frontal, comme décrit dans la rubrique [créer et publier une nouvelle topologie dans Skype entreprise Server](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="bd256-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="bd256-149">Le cas échéant, spécifiez la AG comme magasin SQL pour le pool.</span><span class="sxs-lookup"><span data-stu-id="bd256-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="bd256-150">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bd256-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="bd256-151">Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd256-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="bd256-152">Dans l’Explorateur d’objets, développez le dossier **toujours à haute disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="bd256-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="bd256-153">Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="bd256-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="bd256-154">Si la page **Présentation** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-155">Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-156">Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous voulez inclure dans le groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bd256-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="bd256-157">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="bd256-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="bd256-158">N’incluez pas les bases de données de chat **reportserver**, **ReportServerTempDB**ou persistante dans le groupe disponibilité AlwaysOn, car ces informations ne sont pas prises en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="bd256-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="bd256-159">Vous pouvez inclure les autres bases de données Skype entreprise Server dans le groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bd256-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="bd256-160">Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.</span><span class="sxs-lookup"><span data-stu-id="bd256-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="bd256-p113">Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p113">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="bd256-163">Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.</span><span class="sxs-lookup"><span data-stu-id="bd256-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="bd256-p114">Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="bd256-p114">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="bd256-166">Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd256-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="bd256-p115">Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p115">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="bd256-p116">Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="bd256-p116">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="bd256-171">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-172">Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="bd256-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="bd256-173">Après le déploiement du pool et de la AG, réalisez quelques étapes finales pour vous assurer que les connexions SQL se trouvent sur chacun des réplicas du groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bd256-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="bd256-174">Ouvrez le générateur de topologie, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd256-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="bd256-175">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bd256-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="bd256-176">Cliquez avec le bouton droit sur le magasin SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="bd256-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="bd256-177">En bas de la page, dans la zone **FQDN SQL Server** , remplacez la valeur par le nom de domaine complet (FQDN) de l’écouteur de la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="bd256-p118">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="bd256-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="bd256-182">Ouvrez SQL Server Management Studio, puis accédez à la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="bd256-183">Faites-le basculer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="bd256-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="bd256-184">Ouvrez Skype entreprise Server Management Shell et tapez l’applet de commande suivante pour créer les connexions SQL sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="bd256-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="bd256-185">Répétez les deux étapes précédentes (basculez le groupe vers un réplica secondaire, puis `Install-CsDatabase -Update`utilisez) pour chaque réplica du groupe.</span><span class="sxs-lookup"><span data-stu-id="bd256-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="bd256-186">Déployer un groupe toujours disponible sur un pool existant qui utilise la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="bd256-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="bd256-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="bd256-187"></span></span>

> [!NOTE]
> <span data-ttu-id="bd256-188">Si le pool sur lequel vous effectuez la mise à niveau vers un serveur AG héberge le magasin de gestion central de votre organisation, vous devez d’abord déplacer le MCG vers un autre pool avant de mettre à niveau ce pool.</span><span class="sxs-lookup"><span data-stu-id="bd256-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="bd256-189">Utilisez l’applet de commande Move-CsManagementServer pour déplacer le pool.</span><span class="sxs-lookup"><span data-stu-id="bd256-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="bd256-190">Si vous n’avez pas d’autre liste au sein de votre organisation, vous pouvez déployer temporairement un serveur Standard Edition et déplacer le CMS vers ce serveur avant de mettre à niveau votre groupe vers la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="bd256-191">Basculez toutes les données du miroir vers le nœud principal en ouvrant Skype entreprise Server Management Shell et en tapant l’applet de commande suivante.</span><span class="sxs-lookup"><span data-stu-id="bd256-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="bd256-p121">Répétez cette applet de commande pour chaque type de base de données dans le pool. Vous pouvez utiliser l’applet de commande ci-dessous pour trouver tous les types de bases de données stockées dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="bd256-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="bd256-194">Utilisez le générateur de topologie pour supprimer la mise en miroir de la base de données du pool.</span><span class="sxs-lookup"><span data-stu-id="bd256-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="bd256-195">Ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="bd256-195">Open Topology Builder.</span></span> <span data-ttu-id="bd256-196">Dans votre topologie, développez **Pools frontaux Entreprise Edition**, cliquez avec le bouton droit sur le nom du pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="bd256-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="bd256-197">Pour chaque type de magasin SQL dans le pool, désactivez la case à cocher **Activer la mise en miroir du magasin SQL**.</span><span class="sxs-lookup"><span data-stu-id="bd256-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="bd256-p123">Publiez la topologie modifiée. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="bd256-201">Utilisez SQL Server Management Studio afin de rompre la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="bd256-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="bd256-p124">Ouvrez SQL Server Management Studio, accédez à vos bases de données, cliquez avec le bouton droit sur **Tâches** et cliquez sur **Miroir**. Cliquez ensuite sur **Supprimer la mise en miroir** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="bd256-204">Répétez cette opération pour toutes les bases de données de la liste de ressources partagées qui seront converties en AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="bd256-205">Configurez la fonctionnalité de clustering de basculement sur tous les serveurs de base de données qui feront partie de la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="bd256-206">Sur chaque serveur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bd256-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="bd256-207">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="bd256-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="bd256-p126">Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="bd256-210">Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="bd256-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="bd256-211">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="bd256-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="bd256-212">Validez la configuration de cluster.</span><span class="sxs-lookup"><span data-stu-id="bd256-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="bd256-213">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.</span><span class="sxs-lookup"><span data-stu-id="bd256-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="bd256-214">Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.</span><span class="sxs-lookup"><span data-stu-id="bd256-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="bd256-215">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-216">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.</span><span class="sxs-lookup"><span data-stu-id="bd256-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="bd256-p127">Dans la boîte **Résumé**, vérifiez les erreurs signalées par l’Assistant, puis cliquez sur **Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="bd256-p127">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="bd256-p128">L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="bd256-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="bd256-222">Créez le cluster Windows Server Failover.</span><span class="sxs-lookup"><span data-stu-id="bd256-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="bd256-223">Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.</span><span class="sxs-lookup"><span data-stu-id="bd256-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="bd256-224">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-p129">Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-227">Dans la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-228">Après la création du cluster, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="bd256-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="bd256-p130">Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bd256-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="bd256-231">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.</span><span class="sxs-lookup"><span data-stu-id="bd256-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="bd256-232">Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.</span><span class="sxs-lookup"><span data-stu-id="bd256-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="bd256-233">Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.</span><span class="sxs-lookup"><span data-stu-id="bd256-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="bd256-234">Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-235">Dans la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="bd256-236">Sur chaque serveur dans le cluster, activez la fonction AG dans le gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd256-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="bd256-p131">Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server. </span><span class="sxs-lookup"><span data-stu-id="bd256-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="bd256-p132">Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="bd256-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="bd256-241">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bd256-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="bd256-242">Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd256-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="bd256-243">Dans l’Explorateur d’objets, développez le dossier **toujours à haute disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="bd256-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="bd256-244">Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="bd256-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="bd256-245">Si la page **Présentation** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="bd256-246">Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="bd256-247">Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous voulez inclure dans le groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bd256-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="bd256-248">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="bd256-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="bd256-249">N’incluez pas les bases de données de chat **reportserver**, **ReportServerTempDB**ou persistante dans le groupe disponibilité AlwaysOn, car ces informations ne sont pas prises en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="bd256-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="bd256-250">Vous pouvez inclure les autres bases de données Skype entreprise Server dans le groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bd256-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="bd256-251">Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.</span><span class="sxs-lookup"><span data-stu-id="bd256-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="bd256-p136">Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="bd256-254">Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.</span><span class="sxs-lookup"><span data-stu-id="bd256-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="bd256-p137">Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="bd256-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="bd256-257">Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd256-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="bd256-p138">Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="bd256-p139">Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="bd256-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="bd256-262">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="bd256-263">Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="bd256-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="bd256-264">Créez une nouvelle banque spécifiant l’écouteur AG et spécifiez le principal de l’ancien miroir en tant que nœud principal de la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="bd256-265">Ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="bd256-265">Open Topology Builder.</span></span> <span data-ttu-id="bd256-266">Dans votre topologie, développez **Composants partagés**, cliquez avec le bouton droit sur **Magasins SQL Server**, puis cliquez sur **Nouveau magasin SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bd256-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="bd256-267">Dans la page **Définir un nouveau magasin SQL**, activez tout d’abord la case à cocher **Paramètres de la haute disponibilité**, puis assurez-vous que Groupes de disponibilité SQL AlwaysOn s’affiche dans la zone déroulante.</span><span class="sxs-lookup"><span data-stu-id="bd256-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="bd256-268">Dans la zone **Nom de domaine complet de disponibilité SQL Server**, tapez le nom de domaine complet du port d’écoute que vous avez défini lors de la création du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bd256-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="bd256-269">Dans la zone **FQDN SQL Server** , entrez le nom de domaine complet (FQDN) du nœud principal de la AG, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd256-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="bd256-270">Il doit s’agir du principal de l’ancien miroir pour ce magasin.</span><span class="sxs-lookup"><span data-stu-id="bd256-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="bd256-271">Associez le nouveau AG au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="bd256-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="bd256-272">Dans le générateur de topologie, cliquez avec le bouton droit sur le pool à associer à la AG, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="bd256-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="bd256-273">Sous **associations**, dans la zone **SQL Server Store** , sélectionnez AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="bd256-274">Sélectionnez le même groupe pour toutes les autres bases de données de la liste que vous voulez déplacer vers la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="bd256-275">Lorsque vous êtes certain que toutes les bases de données nécessaires sont définies sur AG, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd256-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="bd256-276">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="bd256-276">Publish the topology.</span></span> <span data-ttu-id="bd256-277">Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="bd256-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="bd256-278">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="bd256-279">Effectuez quelques étapes finales pour vous assurer que les connexions SQL se trouvent sur chacun des réplicas du groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bd256-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="bd256-280">Ouvrez le générateur de topologie, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd256-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="bd256-281">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bd256-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="bd256-282">Cliquez avec le bouton droit sur le magasin SQL du nouveau AG, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="bd256-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="bd256-283">En bas de la page, dans la zone **FQDN SQL Server** , remplacez la valeur par le nom de domaine complet (FQDN) de l’écouteur de la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="bd256-p145">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="bd256-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="bd256-288">Ouvrez SQL Server Management Studio, puis accédez à la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="bd256-289">Faites-le basculer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="bd256-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="bd256-290">Ouvrez Skype entreprise Server Management Shell et tapez l’applet de commande suivante pour créer les connexions SQL sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="bd256-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="bd256-291">Répétez les deux étapes précédentes (basculez le groupe vers un réplica secondaire, puis `Install-CsDatabase -Update`utilisez) pour chaque réplica du groupe.</span><span class="sxs-lookup"><span data-stu-id="bd256-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="bd256-292">Déployer un groupe toujours disponible sur un pool existant qui n’utilise pas la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="bd256-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="bd256-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="bd256-293"></span></span>

> [!NOTE]
> <span data-ttu-id="bd256-294">Si le pool sur lequel vous effectuez la mise à niveau vers un serveur AG héberge le magasin de gestion central de votre organisation, vous devez d’abord déplacer le MCG vers un autre pool avant de mettre à niveau ce pool.</span><span class="sxs-lookup"><span data-stu-id="bd256-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="bd256-295">Utilisez l’applet de commande Move-CsManagementServer pour déplacer le pool.</span><span class="sxs-lookup"><span data-stu-id="bd256-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="bd256-296">Si vous n’avez pas d’autre liste au sein de votre organisation, vous pouvez déployer temporairement un serveur Standard Edition et déplacer le CMS vers ce serveur avant de mettre à niveau votre groupe vers la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="bd256-297">Configurez la fonctionnalité de clustering de basculement sur tous les serveurs de base de données qui feront partie de la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="bd256-298">Sur chaque serveur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bd256-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="bd256-299">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="bd256-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="bd256-p149">Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="bd256-302">Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="bd256-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="bd256-303">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="bd256-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="bd256-304">Validez la configuration de cluster.</span><span class="sxs-lookup"><span data-stu-id="bd256-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="bd256-305">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.</span><span class="sxs-lookup"><span data-stu-id="bd256-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="bd256-306">Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.</span><span class="sxs-lookup"><span data-stu-id="bd256-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="bd256-307">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-308">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.</span><span class="sxs-lookup"><span data-stu-id="bd256-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="bd256-p150">Dans la boîte **Résumé**, vérifiez les erreurs signalées par l’Assistant, puis cliquez sur **Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="bd256-p150">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="bd256-p151">L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="bd256-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="bd256-314">Créez le cluster de basculement de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="bd256-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="bd256-315">Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.</span><span class="sxs-lookup"><span data-stu-id="bd256-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="bd256-316">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-p152">Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-319">Dans la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-320">Après la création du cluster, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="bd256-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="bd256-p153">Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bd256-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="bd256-323">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.</span><span class="sxs-lookup"><span data-stu-id="bd256-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="bd256-324">Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.</span><span class="sxs-lookup"><span data-stu-id="bd256-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="bd256-325">Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.</span><span class="sxs-lookup"><span data-stu-id="bd256-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="bd256-326">Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-327">Dans la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="bd256-328">Sur chaque serveur du cluster, activez AG dans le gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd256-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="bd256-p154">Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server. </span><span class="sxs-lookup"><span data-stu-id="bd256-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="bd256-p155">Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="bd256-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="bd256-333">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bd256-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="bd256-334">Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd256-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="bd256-335">Dans l’Explorateur d’objets, développez le dossier **toujours à haute disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="bd256-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="bd256-336">Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="bd256-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="bd256-337">Si la page **Présentation** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-338">Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-339">Dans la page Sélectionner une base de données, sélectionnez les bases de données que vous voulez inclure dans le AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="bd256-340">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="bd256-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="bd256-341">N’incluez pas les bases de données de chat **reportserver**, **ReportServerTempDB**ou permanentes dans la AG, car elles ne sont pas prises en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="bd256-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="bd256-342">Vous pouvez inclure toutes les autres bases de données Skype entreprise Server du AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="bd256-343">Dans la page **spécifier des réplicas** , cliquez sur l’onglet **fac-similés** . Cliquez ensuite sur le bouton **Ajouter des réplicas** , puis connectez-vous aux autres instances SQL que vous avez jointes en tant que nœuds du WSFC.</span><span class="sxs-lookup"><span data-stu-id="bd256-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="bd256-p159">Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="bd256-346">Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.</span><span class="sxs-lookup"><span data-stu-id="bd256-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="bd256-p160">Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="bd256-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="bd256-349">Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd256-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="bd256-p161">Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="bd256-p162">Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="bd256-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="bd256-354">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="bd256-355">Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="bd256-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="bd256-356">Créez une nouvelle banque spécifiant l’écouteur AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="bd256-357">Ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="bd256-357">Open Topology Builder.</span></span> <span data-ttu-id="bd256-358">Dans votre topologie, développez **Composants partagés**, cliquez avec le bouton droit sur **Magasins SQL Server**, puis cliquez sur **Nouveau magasin SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bd256-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="bd256-359">Dans la page **Définir un nouveau magasin SQL**, activez tout d’abord la case à cocher **Paramètres de la haute disponibilité**, puis assurez-vous que Groupes de disponibilité SQL AlwaysOn s’affiche dans la zone déroulante.</span><span class="sxs-lookup"><span data-stu-id="bd256-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="bd256-360">Dans la zone **Nom de domaine complet de disponibilité SQL Server**, tapez le nom de domaine complet du port d’écoute que vous avez défini lors de la création du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bd256-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="bd256-361">Dans la zone **FQDN SQL Server** , entrez le nom de domaine complet (FQDN) du nœud principal de la AG, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd256-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="bd256-362">Associez le nouveau groupe toujours disponible au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="bd256-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="bd256-363">Dans le générateur de topologie, cliquez avec le bouton droit sur le pool à associer à la AG, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="bd256-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="bd256-364">Sous **associations**, dans la zone **SQL Server Store** , sélectionnez AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="bd256-365">Sélectionnez le même groupe pour toutes les autres bases de données de la liste que vous voulez déplacer vers la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="bd256-366">Lorsque vous êtes certain que toutes les bases de données nécessaires sont définies sur AG, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd256-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="bd256-367">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="bd256-367">Publish the topology.</span></span> <span data-ttu-id="bd256-368">Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="bd256-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="bd256-369">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd256-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="bd256-370">Effectuez quelques étapes finales pour vous assurer que les connexions SQL se trouvent sur chacun des réplicas du AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="bd256-371">Ouvrez le générateur de topologie, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd256-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="bd256-372">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bd256-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="bd256-373">Cliquez avec le bouton droit sur le magasin SQL du nouveau AG, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="bd256-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="bd256-374">En bas de la page, dans la zone **FQDN SQL Server** , remplacez la valeur par le nom de domaine complet (FQDN) de l’écouteur de la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="bd256-p167">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="bd256-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="bd256-379">Ouvrez SQL Server Management Studio, puis accédez à la AG.</span><span class="sxs-lookup"><span data-stu-id="bd256-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="bd256-380">Faites-le basculer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="bd256-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="bd256-381">Ouvrez Skype entreprise Server Management Shell et tapez l’applet de commande suivante pour créer les connexions SQL sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="bd256-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="bd256-382">Répétez les deux étapes précédentes (basculez le groupe vers un réplica secondaire, puis `Install-CsDatabase -Update`utilisez) pour chaque réplica du groupe.</span><span class="sxs-lookup"><span data-stu-id="bd256-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
