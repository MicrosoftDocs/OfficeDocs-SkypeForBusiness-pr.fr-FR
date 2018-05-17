---
title: Déployer un groupe de disponibilité toujours actif sur un serveur principal dans Skype pour Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Déployer le déploiement (installation) un toujours sur groupe de disponibilité dans votre Skype pour Business Server.
ms.openlocfilehash: ed6155ca1d3c7b24450bd8ca5099c2f6fc75e8a4
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2018
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="81ca6-103">Déployer un groupe de disponibilité toujours actif sur un serveur principal dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="81ca6-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="81ca6-104">Déployer le déploiement (installation) un toujours sur disponibilité Group (AG) dans votre Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="81ca6-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="81ca6-105">Comment déployer une AG dépend de si vous déployez il dans un nouveau pool, un pool existant qui utilise la mise en miroir ou un pool existant qui est actuellement pas de haute disponibilité pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="81ca6-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="81ca6-106">À l’aide d’un AG avec un rôle de serveur de conversation permanente n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="81ca6-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="81ca6-107">Déployer un toujours sur groupe de disponibilité dans un nouveau pool frontal</span><span class="sxs-lookup"><span data-stu-id="81ca6-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="81ca6-108">Déployer un toujours sur groupe de disponibilité sur un pool existant qui utilise la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="81ca6-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="81ca6-109">Déployer un toujours sur groupe de disponibilité sur un pool existant qui n’utilise pas la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="81ca6-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="81ca6-110">Déployer un toujours sur groupe de disponibilité dans un nouveau pool frontal</span><span class="sxs-lookup"><span data-stu-id="81ca6-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="81ca6-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca6-111"></span></span>

1. <span data-ttu-id="81ca6-112">Activer la fonctionnalité Clustering avec basculement sur tous les serveurs de base de données qui feront partie de l’AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="81ca6-113">Sur chaque serveur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="81ca6-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="81ca6-114">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="81ca6-p102">Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="81ca6-117">Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="81ca6-118">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="81ca6-119">Validez la configuration de cluster.</span><span class="sxs-lookup"><span data-stu-id="81ca6-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="81ca6-120">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="81ca6-121">Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="81ca6-122">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-123">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="81ca6-124">Dans la zone**Résumé** , vérifiez les erreurs de rapports de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="81ca6-124">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="81ca6-125">Cliquez sur **Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="81ca6-125">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="81ca6-p104">L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="81ca6-129">Créer un Cluster de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="81ca6-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="81ca6-130">Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="81ca6-131">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-p105">Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-134">Dans la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-135">Après la création du cluster, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="81ca6-p106">Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="81ca6-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="81ca6-138">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="81ca6-139">Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="81ca6-140">Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="81ca6-141">Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-142">Dans la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="81ca6-143">Sur chaque serveur du cluster, activez la fonctionnalité AG dans le Gestionnaire de Configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="81ca6-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="81ca6-p107">Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server. </span><span class="sxs-lookup"><span data-stu-id="81ca6-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="81ca6-p108">Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="81ca6-148">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="81ca6-148">Create the availability group.</span></span>
    
   - <span data-ttu-id="81ca6-149">Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="81ca6-149">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="81ca6-150">Dans l’Explorateur d’objets, développez le dossier **Toujours sur une haute disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="81ca6-150">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="81ca6-151">Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-151">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="81ca6-152">Si la page **Présentation** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-152">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-153">Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-153">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-154">Dans la page Sélectionner les bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="81ca6-154">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="81ca6-155">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-155">Then click **Next**.</span></span>
    
    <span data-ttu-id="81ca6-156">N’incluez pas le **ReportServer**, **ReportServerTempDB**ou bases de données de conversation permanente dans le groupe de disponibilité AlwaysOn, comme ils ne sont pas pris en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="81ca6-156">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="81ca6-157">Vous pouvez inclure tous les autres Skype pour les bases de données Business Server dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="81ca6-157">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="81ca6-158">Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.</span><span class="sxs-lookup"><span data-stu-id="81ca6-158">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="81ca6-p112">Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="81ca6-161">Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.</span><span class="sxs-lookup"><span data-stu-id="81ca6-161">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="81ca6-p113">Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="81ca6-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="81ca6-164">Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-164">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="81ca6-p114">Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="81ca6-p115">Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="81ca6-169">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-169">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-170">Dans la page**Résumé** , vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="81ca6-170">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="81ca6-171">Utilisez le Générateur de topologie pour créer le pool frontal, comme expliqué dans [créer et publier la nouvelle topologie dans Skype pour Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="81ca6-171">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="81ca6-172">Lorsque vous le faites, spécifiez le AG comme le magasin SQL pour le pool.</span><span class="sxs-lookup"><span data-stu-id="81ca6-172">When you do, specify the AG as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="81ca6-173">Une fois le pool et l’AG sont déployés, effectuer certaines étapes finales pour vous assurer que les connexions SQL sur chacun des réplicas dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="81ca6-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="81ca6-174">Ouvrez le Générateur de topologie, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="81ca6-175">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="81ca6-176">Cliquez sur le magasin SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur ** Propriétés ** Modifier.</span><span class="sxs-lookup"><span data-stu-id="81ca6-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="81ca6-177">En bas de la page, dans la zone **Nom de domaine complet de SQL Server** , modifiez la valeur pour le nom de domaine complet de l’écouteur de l’AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="81ca6-p118">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="81ca6-182">Ouvrez SQL Server Management Studio et accédez à la AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="81ca6-183">Faites-le basculer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="81ca6-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="81ca6-184">Ouvrez Skype pour Business Server Management Shell et entrez l’applet de commande suivante pour créer les connexions SQL sur le réplica :</span><span class="sxs-lookup"><span data-stu-id="81ca6-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="81ca6-185">Répétez les deux étapes précédentes (bascule vers le groupe à un réplica secondaire, puis utilisez `Install-CsDatabase -Update`) pour chaque réplica dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="81ca6-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="81ca6-186">Déployer un toujours sur groupe de disponibilité sur un pool existant qui utilise la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="81ca6-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="81ca6-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca6-187"></span></span>

> [!NOTE]
> <span data-ttu-id="81ca6-188">Si le pool que vous mettez à niveau vers un AG héberge le magasin Central de gestion pour votre organisation, vous devez déplacer le CMS vers un autre pool avant de mettre à niveau de ce pool.</span><span class="sxs-lookup"><span data-stu-id="81ca6-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="81ca6-189">Utilisez l’applet de commande Move-CsManagementServer pour déplacer le pool.</span><span class="sxs-lookup"><span data-stu-id="81ca6-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="81ca6-190">Si vous ne disposez pas d’un autre pool dans votre organisation, vous pouvez déployer un serveur Standard Edition server temporairement et déplacer le CMS sur ce serveur de mise à niveau de votre pool à la AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="81ca6-191">Faire basculer toutes les données à partir de la mise en miroir au nœud principal en ouvrant Skype pour Business Server Management Shell et en tapant l’applet de commande suivante.</span><span class="sxs-lookup"><span data-stu-id="81ca6-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="81ca6-p121">Répétez cette applet de commande pour chaque type de base de données dans le pool. Vous pouvez utiliser l’applet de commande ci-dessous pour trouver tous les types de bases de données stockées dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="81ca6-194">Utilisation du Générateur de topologie pour supprimer la mise en miroir de base de données à partir du pool</span><span class="sxs-lookup"><span data-stu-id="81ca6-194">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="81ca6-195">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="81ca6-195">Open Topology Builder.</span></span> <span data-ttu-id="81ca6-196">Dans votre topologie, développez **Pools frontaux Entreprise Edition**, cliquez avec le bouton droit sur le nom du pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="81ca6-197">Pour chaque type de magasin SQL dans le pool, désactivez la case à cocher **Activer la mise en miroir du magasin SQL**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="81ca6-p123">Publiez la topologie modifiée. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="81ca6-201">Utilisez SQL Server Management Studio afin de rompre la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="81ca6-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="81ca6-p124">Ouvrez SQL Server Management Studio, accédez à vos bases de données, cliquez avec le bouton droit sur **Tâches** et cliquez sur **Miroir**. Cliquez ensuite sur **Supprimer la mise en miroir** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="81ca6-204">Répétez cette procédure pour toutes les bases de données du pool qui sera converti en un AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="81ca6-205">Configurer la fonctionnalité Clustering avec basculement sur tous les serveurs de base de données qui feront partie de l’AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="81ca6-206">Sur chaque serveur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="81ca6-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="81ca6-207">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="81ca6-p126">Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="81ca6-210">Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="81ca6-211">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="81ca6-212">Validez la configuration de cluster.</span><span class="sxs-lookup"><span data-stu-id="81ca6-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="81ca6-213">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="81ca6-214">Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="81ca6-215">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-216">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="81ca6-217">Dans la zone**Résumé** , vérifiez les erreurs de rapports de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="81ca6-217">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="81ca6-218">Cliquez sur **Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="81ca6-218">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="81ca6-p128">L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="81ca6-222">Créer un Cluster de basculement Windows Server.</span><span class="sxs-lookup"><span data-stu-id="81ca6-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="81ca6-223">Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="81ca6-224">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-p129">Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-227">Dans la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-228">Après la création du cluster, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="81ca6-p130">Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="81ca6-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="81ca6-231">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="81ca6-232">Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="81ca6-233">Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="81ca6-234">Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-235">Dans la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="81ca6-236">Sur chaque serveur du cluster, activez la fonctionnalité AG dans le Gestionnaire de Configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="81ca6-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="81ca6-p131">Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server. </span><span class="sxs-lookup"><span data-stu-id="81ca6-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="81ca6-p132">Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="81ca6-241">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="81ca6-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="81ca6-242">Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="81ca6-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="81ca6-243">Dans l’Explorateur d’objets, développez le dossier **Toujours sur une haute disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="81ca6-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="81ca6-244">Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="81ca6-245">Si la page **Présentation** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="81ca6-246">Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="81ca6-247">Dans la page Sélectionner les bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="81ca6-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="81ca6-248">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="81ca6-249">N’incluez pas le **ReportServer**, **ReportServerTempDB**ou bases de données de conversation permanente dans le groupe de disponibilité AlwaysOn, comme ils ne sont pas pris en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="81ca6-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="81ca6-250">Vous pouvez inclure tous les autres Skype pour les bases de données Business Server dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="81ca6-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="81ca6-251">Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.</span><span class="sxs-lookup"><span data-stu-id="81ca6-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="81ca6-p136">Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="81ca6-254">Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.</span><span class="sxs-lookup"><span data-stu-id="81ca6-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
     - <span data-ttu-id="81ca6-p137">Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="81ca6-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="81ca6-257">Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="81ca6-p138">Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="81ca6-p139">Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="81ca6-262">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="81ca6-263">Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="81ca6-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="81ca6-264">Créer un nouveau magasin spécifiant le port d’écoute AG et en spécifiant le principal du miroir ancien comme nœud principal de l’AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="81ca6-265">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="81ca6-265">Open Topology Builder.</span></span> <span data-ttu-id="81ca6-266">Dans votre topologie, développez **Composants partagés**, cliquez avec le bouton droit sur **Magasins SQL Server**, puis cliquez sur **Nouveau magasin SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="81ca6-267">Dans la page **Définir un nouveau magasin SQL**, activez tout d’abord la case à cocher **Paramètres de la haute disponibilité**, puis assurez-vous que Groupes de disponibilité SQL AlwaysOn s’affiche dans la zone déroulante.</span><span class="sxs-lookup"><span data-stu-id="81ca6-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="81ca6-268">Dans la zone **Nom de domaine complet de disponibilité SQL Server**, tapez le nom de domaine complet du port d’écoute que vous avez défini lors de la création du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="81ca6-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="81ca6-269">Dans la zone **Nom de domaine complet de SQL Server** , tapez le nom de domaine complet du nœud principal de l’AG, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="81ca6-270">Il doit s’agir du principal de l’ancien miroir pour ce magasin.</span><span class="sxs-lookup"><span data-stu-id="81ca6-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="81ca6-271">Associez le nouveau AG le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="81ca6-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="81ca6-272">Dans le Générateur de topologie, cliquez sur le pool à associer avec AG, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="81ca6-273">Sous **Associations**, dans la zone **Magasin SQL Server** , sélectionnez le AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="81ca6-274">Sélectionnez le groupe même pour les autres bases de données dans le pool auquel vous souhaitez déplacer vers le AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="81ca6-275">Lorsque vous êtes certain que toutes les bases de données nécessaires sont définies à l’AG, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="81ca6-p143">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="81ca6-279">Effectuer certaines étapes finales pour vous assurer que les connexions SQL sur chacun des réplicas dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="81ca6-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="81ca6-280">Ouvrez le Générateur de topologie, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="81ca6-281">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="81ca6-282">Avec le bouton droit de la nouvel AG magasin SQL, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="81ca6-283">En bas de la page, dans la zone **Nom de domaine complet de SQL Server** , modifiez la valeur pour le nom de domaine complet de l’écouteur de l’AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="81ca6-p145">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="81ca6-288">Ouvrez SQL Server Management Studio et accédez à la AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="81ca6-289">Faites-le basculer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="81ca6-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="81ca6-290">Ouvrez Skype pour Business Server Management Shell et entrez l’applet de commande suivante pour créer les connexions SQL sur le réplica :</span><span class="sxs-lookup"><span data-stu-id="81ca6-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="81ca6-291">Répétez les deux étapes précédentes (bascule vers le groupe à un réplica secondaire, puis utilisez `Install-CsDatabase -Update`) pour chaque réplica dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="81ca6-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="81ca6-292">Déployer un toujours sur groupe de disponibilité sur un pool existant qui n’utilise pas la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="81ca6-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="81ca6-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca6-293"></span></span>

> [!NOTE]
> <span data-ttu-id="81ca6-294">Si le pool que vous mettez à niveau vers un AG héberge le magasin Central de gestion pour votre organisation, vous devez déplacer le CMS vers un autre pool avant de mettre à niveau de ce pool.</span><span class="sxs-lookup"><span data-stu-id="81ca6-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="81ca6-295">Utilisez l’applet de commande Move-CsManagementServer pour déplacer le pool.</span><span class="sxs-lookup"><span data-stu-id="81ca6-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="81ca6-296">Si vous ne disposez pas d’un autre pool dans votre organisation, vous pouvez déployer un serveur Standard Edition server temporairement et déplacer le CMS sur ce serveur de mise à niveau de votre pool à la AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="81ca6-297">Configurer la fonctionnalité Clustering avec basculement sur tous les serveurs de base de données qui feront partie de l’AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="81ca6-298">Sur chaque serveur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="81ca6-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="81ca6-299">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="81ca6-p149">Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="81ca6-302">Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="81ca6-303">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="81ca6-304">Validez la configuration de cluster.</span><span class="sxs-lookup"><span data-stu-id="81ca6-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="81ca6-305">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="81ca6-306">Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="81ca6-307">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-308">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="81ca6-309">Dans la zone**Résumé** , vérifiez les erreurs de rapports de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="81ca6-309">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="81ca6-310">Cliquez sur **Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="81ca6-310">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="81ca6-p151">L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="81ca6-314">Créer un Cluster de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="81ca6-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="81ca6-315">Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="81ca6-316">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-p152">Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-319">Dans la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-320">Après la création du cluster, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="81ca6-p153">Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="81ca6-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="81ca6-323">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="81ca6-324">Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="81ca6-325">Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="81ca6-326">Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-327">Dans la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="81ca6-328">Sur chaque serveur du cluster, activer AG dans le Gestionnaire de Configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="81ca6-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="81ca6-p154">Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server. </span><span class="sxs-lookup"><span data-stu-id="81ca6-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="81ca6-p155">Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="81ca6-333">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="81ca6-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="81ca6-334">Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="81ca6-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="81ca6-335">Dans l’Explorateur d’objets, développez le dossier **Toujours sur une haute disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="81ca6-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="81ca6-336">Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="81ca6-337">Si la page **Présentation** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-338">Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-339">Dans la page Sélectionner les bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="81ca6-340">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-340">Then click **Next**.</span></span>
    
    <span data-ttu-id="81ca6-341">N’incluez pas le **ReportServer**, **ReportServerTempDB**ou bases de données de conversation permanente du groupe AG, comme ils ne sont pas pris en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="81ca6-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="81ca6-342">Vous pouvez inclure tous les autres Skype pour les bases de données Business Server du groupe AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="81ca6-343">Dans la page **Spécifier les réplicas** , cliquez sur l’onglet **réplicas** . Cliquez sur le bouton **Ajouter les réplicas** , puis se connecter à d’autres instances SQL que vous avez rejoint sous forme de nœuds de la WSFC.</span><span class="sxs-lookup"><span data-stu-id="81ca6-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="81ca6-p159">Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="81ca6-346">Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.</span><span class="sxs-lookup"><span data-stu-id="81ca6-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="81ca6-p160">Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="81ca6-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="81ca6-349">Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="81ca6-p161">Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="81ca6-p162">Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="81ca6-354">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="81ca6-355">Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="81ca6-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="81ca6-356">Créer un nouveau magasin spécifiant le port d’écoute AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="81ca6-357">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="81ca6-357">Open Topology Builder.</span></span> <span data-ttu-id="81ca6-358">Dans votre topologie, développez **Composants partagés**, cliquez avec le bouton droit sur **Magasins SQL Server**, puis cliquez sur **Nouveau magasin SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="81ca6-359">Dans la page **Définir un nouveau magasin SQL**, activez tout d’abord la case à cocher **Paramètres de la haute disponibilité**, puis assurez-vous que Groupes de disponibilité SQL AlwaysOn s’affiche dans la zone déroulante.</span><span class="sxs-lookup"><span data-stu-id="81ca6-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="81ca6-360">Dans la zone **Nom de domaine complet de disponibilité SQL Server**, tapez le nom de domaine complet du port d’écoute que vous avez défini lors de la création du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="81ca6-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="81ca6-361">Dans la zone **Nom de domaine complet de SQL Server** , tapez le nom de domaine complet du nœud principal de l’AG, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="81ca6-362">Associez le nouveau toujours sur groupe de disponibilité avec le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="81ca6-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="81ca6-363">Dans le Générateur de topologie, cliquez sur le pool à associer avec AG, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="81ca6-364">Sous **Associations**, dans la zone **Magasin SQL Server** , sélectionnez le AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="81ca6-365">Sélectionnez le groupe même pour les autres bases de données dans le pool auquel vous souhaitez déplacer vers le AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="81ca6-366">Lorsque vous êtes certain que toutes les bases de données nécessaires sont définies à l’AG, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="81ca6-p165">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="81ca6-370">Effectuer certaines étapes pour vous assurer que les connexions SQL sur tous les réplicas du groupe AG finales.</span><span class="sxs-lookup"><span data-stu-id="81ca6-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="81ca6-371">Ouvrez le Générateur de topologie, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="81ca6-372">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="81ca6-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="81ca6-373">Avec le bouton droit de la nouvel AG magasin SQL, puis cliquez sur ** Propriétés ** Modifier.</span><span class="sxs-lookup"><span data-stu-id="81ca6-373">Right-click the SQL store of the new AG, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="81ca6-374">En bas de la page, dans la zone **Nom de domaine complet de SQL Server** , modifiez la valeur pour le nom de domaine complet de l’écouteur de l’AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="81ca6-p167">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="81ca6-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="81ca6-379">Ouvrez SQL Server Management Studio et accédez à la AG.</span><span class="sxs-lookup"><span data-stu-id="81ca6-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="81ca6-380">Faites-le basculer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="81ca6-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="81ca6-381">Ouvrez Skype pour Business Server Management Shell et entrez l’applet de commande suivante pour créer les connexions SQL sur le réplica :</span><span class="sxs-lookup"><span data-stu-id="81ca6-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
     ```
     Install-CsDatabase -Update
     ```

     - <span data-ttu-id="81ca6-382">Répétez les deux étapes précédentes (bascule vers le groupe à un réplica secondaire, puis utilisez `Install-CsDatabase -Update`) pour chaque réplica dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="81ca6-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    

