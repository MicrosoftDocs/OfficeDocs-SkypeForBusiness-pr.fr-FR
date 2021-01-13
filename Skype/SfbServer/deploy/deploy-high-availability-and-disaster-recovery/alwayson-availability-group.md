---
title: Déployer un groupe de disponibilité Always On sur un serveur principal dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Déployez (installez) un groupe de disponibilité Always On dans votre déploiement Skype Entreprise Server.
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830654"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="33592-103">Déployer un groupe de disponibilité Always On sur un serveur principal dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="33592-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="33592-104">Déployez (installez) un groupe de disponibilité Always On (AG) dans votre déploiement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33592-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="33592-105">La façon dont vous déployez une ag ag varie selon que vous la déployez dans un nouveau pool, un pool existant qui utilise la mise en miroir ou un pool existant qui n’a actuellement aucune haute disponibilité pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="33592-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="33592-106">L’utilisation d’une ag ag avec un rôle serveur de conversation permanente n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="33592-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="33592-107">Déployer un groupe de disponibilité Always On sur un nouveau pool frontal</span><span class="sxs-lookup"><span data-stu-id="33592-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="33592-108">Déployer un groupe de disponibilité Always On sur un pool existant qui utilise la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="33592-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="33592-109">Déployer un groupe de disponibilité Always On sur un pool existant qui n’utilise pas la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="33592-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="33592-110">Déployer un groupe de disponibilité Always On sur un nouveau pool frontal</span><span class="sxs-lookup"><span data-stu-id="33592-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="33592-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="33592-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="33592-112">Activez la fonctionnalité clustering de failover sur tous les serveurs de base de données qui feront partie de l’AG.</span><span class="sxs-lookup"><span data-stu-id="33592-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="33592-113">Sur chaque serveur, faites les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="33592-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="33592-114">Ouvrez le Gestionnaire de serveur et cliquez **sur Ajouter des rôles et des fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="33592-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="33592-115">Cliquez **sur Suivant** jusqu’à atteindre la zone Sélectionner les **fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="33592-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="33592-116">Ici, cochez la case **Clustering deover.**</span><span class="sxs-lookup"><span data-stu-id="33592-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="33592-117">Dans la **zone Ajouter des fonctionnalités requises pour** le clustering de failover, cliquez sur Ajouter des **fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="33592-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="33592-118">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="33592-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="33592-119">Validez la configuration du cluster.</span><span class="sxs-lookup"><span data-stu-id="33592-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="33592-120">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils,** puis cliquez sur Gestionnaire **du cluster de failover.**</span><span class="sxs-lookup"><span data-stu-id="33592-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="33592-121">Sous **Actions** sur le côté droit de l’écran, cliquez **sur Valider la configuration.**</span><span class="sxs-lookup"><span data-stu-id="33592-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="33592-122">Sur la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-123">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests.**</span><span class="sxs-lookup"><span data-stu-id="33592-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="33592-124">Dans la **zone Résumé,** vérifiez les erreurs que l’Assistant signale.</span><span class="sxs-lookup"><span data-stu-id="33592-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="33592-125">Cliquez ensuite **sur Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="33592-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="33592-126">L’Assistant signalera probablement plusieurs avertissements, en particulier si vous n’utilisez pas de stockage partagé.</span><span class="sxs-lookup"><span data-stu-id="33592-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="33592-127">Vous n’êtes pas obligé d’utiliser le stockage partagé.</span><span class="sxs-lookup"><span data-stu-id="33592-127">You are not required to use shared storage.</span></span> <span data-ttu-id="33592-128">Toutefois, si  vous voyez des messages d’erreur, vous devez résoudre ces problèmes avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="33592-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="33592-129">Créez le cluster de failover Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="33592-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="33592-130">Dans **l’Assistant Gestion du cluster de failover,** cliquez avec le bouton droit sur Gestion du cluster de **failover,** puis cliquez **sur Créer un cluster.**</span><span class="sxs-lookup"><span data-stu-id="33592-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="33592-131">Sur la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-132">Ajoutez le nom du cluster et l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="33592-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="33592-133">Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-134">Sur la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-135">Une fois le cluster créé, cliquez sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="33592-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="33592-136">Nous vous recommandons de configurer les paramètres de quorum de cluster pour utiliser un témoin de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="33592-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="33592-137">Pour ce faire, utilisez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="33592-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="33592-138">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions,** puis cliquez sur **Configurer les paramètres de quorum du cluster.**</span><span class="sxs-lookup"><span data-stu-id="33592-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="33592-139">Dans la page **Sélectionner l’option de configuration du quorum,** cliquez sur Sélectionner le témoin de **quorum.**</span><span class="sxs-lookup"><span data-stu-id="33592-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="33592-140">Dans la page **Sélectionner un témoin de quorum,** cliquez sur Configurer un témoin de partage de **fichiers.**</span><span class="sxs-lookup"><span data-stu-id="33592-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="33592-141">Dans la page **Configurer le témoin de partage** de fichiers, tapez le chemin d’accès du partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="33592-142">Sur la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="33592-143">Sur chaque serveur du cluster, activez la fonctionnalité AG dans SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="33592-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="33592-144">Ouvrez le Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33592-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="33592-145">Dans l’arborescence sur le côté gauche de l’écran, cliquez sur **SQL Server Services,** puis double-cliquez sur SQL Server service.</span><span class="sxs-lookup"><span data-stu-id="33592-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="33592-146">Dans la **zone Propriétés,** sélectionnez **l’onglet Haute disponibilité AlwaysOn.** Activez la case à cocher Activer les groupes de disponibilité **AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="33592-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="33592-147">Redémarrez le service SQL Server lorsque vous y être invité.</span><span class="sxs-lookup"><span data-stu-id="33592-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="33592-148">Utilisez le Générateur de topologie pour créer le pool frontal, comme expliqué dans Créer et publier une nouvelle [topologie dans Skype Entreprise Server.](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="33592-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="33592-149">Lorsque vous le faites, spécifiez la ag ag comme SQL magasin pour le pool.</span><span class="sxs-lookup"><span data-stu-id="33592-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="33592-150">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="33592-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="33592-151">Ouvrez SQL Server Management Studio et connectez-vous à SQL Server instance.</span><span class="sxs-lookup"><span data-stu-id="33592-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="33592-152">Dans l’Explorateur d’objets, développez **le dossier Haute disponibilité Always On.**</span><span class="sxs-lookup"><span data-stu-id="33592-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="33592-153">Cliquez avec le bouton droit **sur le dossier Groupes de** disponibilité, puis cliquez sur Assistant Nouveau groupe de **disponibilité.**</span><span class="sxs-lookup"><span data-stu-id="33592-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="33592-154">Si la page **Introduction** s’affiche, cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="33592-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-155">Dans la page **Spécifier le nom du** groupe de disponibilité, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="33592-156">Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="33592-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="33592-157">Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="33592-158">N’incluez pas les bases de données **ReportServer,** **ReportServerTempDB** ou Persistent Chat dans le groupe de disponibilité AlwaysOn, car elles ne sont pas pris en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="33592-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="33592-159">Vous pouvez inclure toutes les autres bases de données Skype Entreprise Server dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="33592-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="33592-160">Dans la page **Spécifier les réplicas,** cliquez sur **l’onglet Réplicas.** Cliquez ensuite sur le bouton Ajouter des **réplicas,** puis connectez-vous aux autres instances SQL que vous avez jointes en tant que nodes du cluster de bas niveau Windows Server.</span><span class="sxs-lookup"><span data-stu-id="33592-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="33592-161">Pour chaque instance, sélectionnez les options **Deover automatique et** **Validation synchrone.**</span><span class="sxs-lookup"><span data-stu-id="33592-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="33592-162">Ne sélectionnez pas **l’option Secondaire lisible.**</span><span class="sxs-lookup"><span data-stu-id="33592-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="33592-163">Cliquez sur **l’onglet Points de terminaison** et vérifiez que le **numéro de port** est 5022.</span><span class="sxs-lookup"><span data-stu-id="33592-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="33592-164">Cliquez sur **l’onglet d’écoute,** puis sélectionnez l’option Créer **un listener de** groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="33592-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="33592-165">Sous cette option, tapez un nom pour l’port d’écoute et définissez le **port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="33592-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="33592-166">Cliquez **sur** Ajouter, puis dans la zone **Adresse IPv4,** fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="33592-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="33592-167">Dans la **page** Sélectionner la synchronisation initiale des données, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et pour qui le compte de service SQL Server utilisé par les deux réplicas dispose d’autorisations d’écriture.</span><span class="sxs-lookup"><span data-stu-id="33592-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="33592-168">Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="33592-169">Ce partage de fichiers sera utilisé temporairement lors de l’initialisation des bases de données.</span><span class="sxs-lookup"><span data-stu-id="33592-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="33592-170">Si vous avez affaire à des bases de données de grande taille, nous vous recommandons de les initialiser manuellement si votre bande passante réseau ne peut pas prendre en charge la taille des sauvegardes de base de données.</span><span class="sxs-lookup"><span data-stu-id="33592-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="33592-171">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="33592-172">Dans la page **Résumé,** vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="33592-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="33592-173">Une fois le pool et le groupe de disponibilité de service déployés, effectuez quelques étapes finales pour vous assurer que les connexions SQL sont sur chacun des réplicas du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="33592-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="33592-174">Ouvrez le Générateur de topologie, **sélectionnez Télécharger** la topologie à partir d’un déploiement existant, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="33592-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="33592-175">Développez Skype Entreprise Server, développez votre topologie et **développez SQL Server Stores.**</span><span class="sxs-lookup"><span data-stu-id="33592-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="33592-176">Cliquez avec le bouton droit SQL magasin du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="33592-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="33592-177">En bas de la page, dans la zone **SQL Server FQDN,** modifiez la valeur en nom de nom de groupe de l’écoute de l’ag.</span><span class="sxs-lookup"><span data-stu-id="33592-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="33592-178">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="33592-178">Publish the topology.</span></span> <span data-ttu-id="33592-179">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="33592-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="33592-180">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="33592-181">Patientez ensuite quelques minutes pour que la nouvelle topologie soit répliquée.</span><span class="sxs-lookup"><span data-stu-id="33592-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="33592-182">Ouvrez SQL Server Management Studio, puis accédez à l’AG.</span><span class="sxs-lookup"><span data-stu-id="33592-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="33592-183">Le faire échouer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="33592-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="33592-184">Ouvrez Skype Entreprise Server Management Shell et tapez l’cmdlet suivante pour créer SQL connexions sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="33592-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="33592-185">Répétez les deux étapes précédentes (faire échouer le groupe vers un réplica secondaire, puis  `Install-CsDatabase -Update` utilisez) pour chaque réplica du groupe.</span><span class="sxs-lookup"><span data-stu-id="33592-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="33592-186">Déployer un groupe de disponibilité Always On sur un pool existant qui utilise la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="33592-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="33592-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="33592-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="33592-188">Si le pool que vous misez à niveau vers une ag ag héberge le magasin central de gestion de votre organisation, vous devez d’abord déplacer le cms vers un autre pool avant de mettre à niveau ce pool.</span><span class="sxs-lookup"><span data-stu-id="33592-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="33592-189">Utilisez lMove-CsManagementServer cmdlet pour déplacer le pool.</span><span class="sxs-lookup"><span data-stu-id="33592-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="33592-190">Si vous n’avez pas d’autre pool dans votre organisation, vous pouvez déployer temporairement un serveur Standard Edition Server et déplacer le cmS vers ce serveur avant de mettre à niveau votre pool vers le groupe de sécurité d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="33592-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="33592-191">Pour faire échouer toutes les données du miroir vers le nœud principal, ouvrent Skype Entreprise Server Management Shell et tapent l’cmdlet suivante.</span><span class="sxs-lookup"><span data-stu-id="33592-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="33592-192">Répétez cette cmdlet pour chaque type de base de données dans le pool.</span><span class="sxs-lookup"><span data-stu-id="33592-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="33592-193">Vous pouvez utiliser l’cmdlet suivante pour rechercher tous les types de base de données stockés dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="33592-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="33592-194">Utilisez le Générateur de topologie pour supprimer la mise en miroir de base de données du pool.</span><span class="sxs-lookup"><span data-stu-id="33592-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="33592-195">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="33592-195">Open Topology Builder.</span></span> <span data-ttu-id="33592-196">Dans votre topologie, développez pools frontux **Enterprise Edition,** cliquez avec le bouton droit sur le nom du pool, puis cliquez sur **Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="33592-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="33592-197">Pour chaque type de SQL dans le pool, activez la case à **cocher Activer SQL mise** en miroir du Store.</span><span class="sxs-lookup"><span data-stu-id="33592-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="33592-198">Publiez la topologie modifiée.</span><span class="sxs-lookup"><span data-stu-id="33592-198">Publish the changed topology.</span></span> <span data-ttu-id="33592-199">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="33592-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="33592-200">Ensuite, dans la page de confirmation, cliquez sur **Suivant**</span><span class="sxs-lookup"><span data-stu-id="33592-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="33592-201">Utilisez SQL Server Management Studio pour rompre le miroir.</span><span class="sxs-lookup"><span data-stu-id="33592-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="33592-202">Ouvrez SQL Server Management Studio, accédez à vos bases de données, cliquez avec le bouton droit sur **Tâches** et cliquez sur **Miroir.**</span><span class="sxs-lookup"><span data-stu-id="33592-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="33592-203">Cliquez ensuite **sur Supprimer la mise en** miroir et sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="33592-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="33592-204">Répétez cette phase pour toutes les bases de données du pool qui seront converties en ag.</span><span class="sxs-lookup"><span data-stu-id="33592-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="33592-205">Configurer la fonctionnalité clustering de failover sur tous les serveurs de base de données qui feront partie de l’AG.</span><span class="sxs-lookup"><span data-stu-id="33592-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="33592-206">Sur chaque serveur, faites les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="33592-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="33592-207">Ouvrez le Gestionnaire de serveur et cliquez **sur Ajouter des rôles et des fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="33592-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="33592-208">Cliquez **sur Suivant** jusqu’à atteindre la zone Sélectionner les **fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="33592-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="33592-209">Ici, cochez la case **Clustering deover.**</span><span class="sxs-lookup"><span data-stu-id="33592-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="33592-210">Dans la **zone Ajouter des fonctionnalités requises pour** le clustering de failover, cliquez sur Ajouter des **fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="33592-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="33592-211">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="33592-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="33592-212">Validez la configuration du cluster.</span><span class="sxs-lookup"><span data-stu-id="33592-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="33592-213">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils,** puis cliquez sur Gestionnaire **du cluster de failover.**</span><span class="sxs-lookup"><span data-stu-id="33592-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="33592-214">Sous **Actions** sur le côté droit de l’écran, cliquez **sur Valider la configuration.**</span><span class="sxs-lookup"><span data-stu-id="33592-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="33592-215">Sur la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-216">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests.**</span><span class="sxs-lookup"><span data-stu-id="33592-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="33592-217">Dans la **zone Résumé,** vérifiez les erreurs que l’Assistant signale.</span><span class="sxs-lookup"><span data-stu-id="33592-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="33592-218">Cliquez ensuite **sur Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="33592-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="33592-219">L’Assistant signalera probablement plusieurs avertissements, en particulier si vous n’utilisez pas de stockage partagé.</span><span class="sxs-lookup"><span data-stu-id="33592-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="33592-220">Vous n’êtes pas obligé d’utiliser le stockage partagé.</span><span class="sxs-lookup"><span data-stu-id="33592-220">You are not required to use shared storage.</span></span> <span data-ttu-id="33592-221">Toutefois, si  vous voyez des messages d’erreur, vous devez résoudre ces problèmes avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="33592-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="33592-222">Créez le cluster de failover Windows Server.</span><span class="sxs-lookup"><span data-stu-id="33592-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="33592-223">Dans **l’Assistant Gestion du cluster de failover,** cliquez avec le bouton droit sur Gestion du cluster de **failover,** puis cliquez **sur Créer un cluster.**</span><span class="sxs-lookup"><span data-stu-id="33592-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="33592-224">Sur la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-225">Ajoutez le nom du cluster et l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="33592-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="33592-226">Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-227">Sur la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-228">Une fois le cluster créé, cliquez sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="33592-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="33592-229">Nous vous recommandons de configurer les paramètres de quorum de cluster pour utiliser un témoin de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="33592-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="33592-230">Pour ce faire, utilisez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="33592-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="33592-231">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions,** puis cliquez sur **Configurer les paramètres de quorum du cluster.**</span><span class="sxs-lookup"><span data-stu-id="33592-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="33592-232">Dans la page **Sélectionner l’option de configuration du quorum,** cliquez sur Sélectionner le témoin de **quorum.**</span><span class="sxs-lookup"><span data-stu-id="33592-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="33592-233">Dans la page **Sélectionner un témoin de quorum,** cliquez sur Configurer un témoin de partage de **fichiers.**</span><span class="sxs-lookup"><span data-stu-id="33592-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="33592-234">Dans la page **Configurer le témoin de partage** de fichiers, tapez le chemin d’accès du partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="33592-235">Sur la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="33592-236">Sur chaque serveur du cluster, activez la fonctionnalité AG dans SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="33592-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="33592-237">Ouvrez le Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33592-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="33592-238">Dans l’arborescence sur le côté gauche de l’écran, cliquez sur **SQL Server Services,** puis double-cliquez sur SQL Server service.</span><span class="sxs-lookup"><span data-stu-id="33592-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="33592-239">Dans la **zone Propriétés,** sélectionnez **l’onglet Haute disponibilité AlwaysOn.** Activez la case à cocher Activer les groupes de disponibilité **AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="33592-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="33592-240">Redémarrez le service SQL Server lorsque vous y être invité.</span><span class="sxs-lookup"><span data-stu-id="33592-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="33592-241">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="33592-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="33592-242">Ouvrez SQL Server Management Studio et connectez-vous à SQL Server instance.</span><span class="sxs-lookup"><span data-stu-id="33592-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="33592-243">Dans l’Explorateur d’objets, développez **le dossier Haute disponibilité Always On.**</span><span class="sxs-lookup"><span data-stu-id="33592-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="33592-244">Cliquez avec le bouton droit **sur le dossier Groupes de** disponibilité, puis cliquez sur Assistant Nouveau groupe de **disponibilité.**</span><span class="sxs-lookup"><span data-stu-id="33592-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="33592-245">Si la page **Introduction** s’affiche, cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="33592-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="33592-246">Dans la page **Spécifier le nom du** groupe de disponibilité, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="33592-247">Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="33592-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="33592-248">Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="33592-249">N’incluez pas les bases de données **ReportServer,** **ReportServerTempDB** ou Persistent Chat dans le groupe de disponibilité AlwaysOn, car elles ne sont pas pris en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="33592-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="33592-250">Vous pouvez inclure toutes les autres bases de données Skype Entreprise Server dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="33592-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="33592-251">Dans la page **Spécifier les réplicas,** cliquez sur **l’onglet Réplicas.** Cliquez ensuite sur le bouton Ajouter des **réplicas,** puis connectez-vous aux autres instances SQL que vous avez jointes en tant que nodes du cluster de bas niveau Windows Server.</span><span class="sxs-lookup"><span data-stu-id="33592-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="33592-252">Pour chaque instance, sélectionnez les options **Deover automatique et** **Validation synchrone.**</span><span class="sxs-lookup"><span data-stu-id="33592-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="33592-253">Ne sélectionnez pas **l’option Secondaire lisible.**</span><span class="sxs-lookup"><span data-stu-id="33592-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="33592-254">Cliquez sur **l’onglet Points de terminaison** et vérifiez que le **numéro de port** est 5022.</span><span class="sxs-lookup"><span data-stu-id="33592-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="33592-255">Cliquez sur **l’onglet d’écoute,** puis sélectionnez l’option Créer **un listener de** groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="33592-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="33592-256">Sous cette option, tapez un nom pour l’port d’écoute et définissez le **port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="33592-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="33592-257">Cliquez **sur** Ajouter, puis dans la zone **Adresse IPv4,** fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="33592-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="33592-258">Dans la **page** Sélectionner la synchronisation initiale des données, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et pour qui le compte de service SQL Server utilisé par les deux réplicas dispose d’autorisations d’écriture.</span><span class="sxs-lookup"><span data-stu-id="33592-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="33592-259">Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="33592-260">Ce partage de fichiers sera utilisé temporairement lors de l’initialisation des bases de données.</span><span class="sxs-lookup"><span data-stu-id="33592-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="33592-261">Si vous avez affaire à des bases de données de grande taille, nous vous recommandons de les initialiser manuellement si votre bande passante réseau ne peut pas prendre en charge la taille des sauvegardes de base de données.</span><span class="sxs-lookup"><span data-stu-id="33592-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="33592-262">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="33592-263">Dans la page **Résumé,** vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="33592-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="33592-264">Créez un magasin en spécifiant l’auditeur AG et en spécifiant le principal de l’ancien miroir comme nœud principal de l’AG.</span><span class="sxs-lookup"><span data-stu-id="33592-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="33592-265">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="33592-265">Open Topology Builder.</span></span> <span data-ttu-id="33592-266">Dans votre topologie, développez **Composants partagés,** cliquez avec le bouton droit **sur SQL Server Store,** puis cliquez sur Nouveau **SQL Server Store.**</span><span class="sxs-lookup"><span data-stu-id="33592-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="33592-267">Dans la page Définir un nouveau **magasin SQL,** activez d’abord la case à cocher **Paramètres** de haute disponibilité, puis assurez-vous que les groupes de disponibilité AlwaysOn SQL apparaissent dans la zone de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="33592-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="33592-268">Dans la **SQL Server FQDN** de l’écouteur de disponibilité, tapez le FQDN de l’écoute que vous avez créé lorsque vous avez créé le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="33592-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="33592-269">Dans la **SQL Server FQDN,** tapez le FQDN du nœud principal de l’ag, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="33592-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="33592-270">Il doit s’y prendre comme principal de l’ancien miroir pour ce magasin.</span><span class="sxs-lookup"><span data-stu-id="33592-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="33592-271">Associez la nouvelle AG au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="33592-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="33592-272">Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool à associer à l’AG, puis cliquez **sur Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="33592-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="33592-273">Sous **Associations,** dans la **SQL Server Store,** sélectionnez l’AG.</span><span class="sxs-lookup"><span data-stu-id="33592-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="33592-274">Sélectionnez le même groupe pour toutes les autres bases de données du pool que vous souhaitez déplacer vers l’ag.</span><span class="sxs-lookup"><span data-stu-id="33592-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="33592-275">Lorsque vous êtes sûr que toutes les bases de données nécessaires sont définies sur la ag ag, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="33592-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="33592-276">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="33592-276">Publish the topology.</span></span> <span data-ttu-id="33592-277">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="33592-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="33592-278">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="33592-279">Effectuez quelques étapes finales pour vous assurer que les connexions SQL sont sur chacun des réplicas du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="33592-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="33592-280">Ouvrez le Générateur de topologie, **sélectionnez Télécharger** la topologie à partir d’un déploiement existant, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="33592-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="33592-281">Développez Skype Entreprise Server, développez votre topologie et **développez SQL Server Stores.**</span><span class="sxs-lookup"><span data-stu-id="33592-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="33592-282">Cliquez avec le bouton droit SQL magasin de la nouvelle ag, puis cliquez **sur Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="33592-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="33592-283">En bas de la page, dans la zone **SQL Server FQDN,** modifiez la valeur en nom de nom de groupe de l’écoute de l’ag.</span><span class="sxs-lookup"><span data-stu-id="33592-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="33592-284">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="33592-284">Publish the topology.</span></span> <span data-ttu-id="33592-285">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="33592-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="33592-286">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="33592-287">Patientez ensuite quelques minutes pour que la nouvelle topologie soit répliquée.</span><span class="sxs-lookup"><span data-stu-id="33592-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="33592-288">Ouvrez SQL Server Management Studio, puis accédez à l’AG.</span><span class="sxs-lookup"><span data-stu-id="33592-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="33592-289">Le faire échouer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="33592-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="33592-290">Ouvrez Skype Entreprise Server Management Shell et tapez l’cmdlet suivante pour créer SQL connexions sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="33592-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="33592-291">Répétez les deux étapes précédentes (faire échouer le groupe vers un réplica secondaire, puis  `Install-CsDatabase -Update` utilisez) pour chaque réplica du groupe.</span><span class="sxs-lookup"><span data-stu-id="33592-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="33592-292">Déployer un groupe de disponibilité Always On sur un pool existant qui n’utilise pas la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="33592-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="33592-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="33592-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="33592-294">Si le pool que vous misez à niveau vers une ag ag héberge le magasin central de gestion de votre organisation, vous devez d’abord déplacer le cms vers un autre pool avant de mettre à niveau ce pool.</span><span class="sxs-lookup"><span data-stu-id="33592-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="33592-295">Utilisez lMove-CsManagementServer cmdlet pour déplacer le pool.</span><span class="sxs-lookup"><span data-stu-id="33592-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="33592-296">Si vous n’avez pas d’autre pool dans votre organisation, vous pouvez déployer temporairement un serveur Standard Edition Server et déplacer le cmS vers ce serveur avant de mettre à niveau votre pool vers le groupe de sécurité d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="33592-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="33592-297">Configurer la fonctionnalité clustering de failover sur tous les serveurs de base de données qui feront partie de l’AG.</span><span class="sxs-lookup"><span data-stu-id="33592-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="33592-298">Sur chaque serveur, faites les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="33592-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="33592-299">Ouvrez le Gestionnaire de serveur et cliquez **sur Ajouter des rôles et des fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="33592-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="33592-300">Cliquez **sur Suivant** jusqu’à atteindre la zone Sélectionner les **fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="33592-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="33592-301">Ici, cochez la case **Clustering deover.**</span><span class="sxs-lookup"><span data-stu-id="33592-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="33592-302">Dans la **zone Ajouter des fonctionnalités requises pour** le clustering de failover, cliquez sur Ajouter des **fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="33592-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="33592-303">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="33592-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="33592-304">Validez la configuration du cluster.</span><span class="sxs-lookup"><span data-stu-id="33592-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="33592-305">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils,** puis cliquez sur Gestionnaire **du cluster de failover.**</span><span class="sxs-lookup"><span data-stu-id="33592-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="33592-306">Sous **Actions** sur le côté droit de l’écran, cliquez **sur Valider la configuration.**</span><span class="sxs-lookup"><span data-stu-id="33592-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="33592-307">Sur la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-308">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests.**</span><span class="sxs-lookup"><span data-stu-id="33592-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="33592-309">Dans la **zone Résumé,** vérifiez les erreurs que l’Assistant signale.</span><span class="sxs-lookup"><span data-stu-id="33592-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="33592-310">Cliquez ensuite **sur Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="33592-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="33592-311">L’Assistant signalera probablement plusieurs avertissements, en particulier si vous n’utilisez pas de stockage partagé.</span><span class="sxs-lookup"><span data-stu-id="33592-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="33592-312">Vous n’êtes pas obligé d’utiliser le stockage partagé.</span><span class="sxs-lookup"><span data-stu-id="33592-312">You are not required to use shared storage.</span></span> <span data-ttu-id="33592-313">Toutefois, si  vous voyez des messages d’erreur, vous devez résoudre ces problèmes avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="33592-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="33592-314">Créez le cluster de failover Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="33592-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="33592-315">Dans **l’Assistant Gestion du cluster de failover,** cliquez avec le bouton droit sur Gestion du cluster de **failover,** puis cliquez **sur Créer un cluster.**</span><span class="sxs-lookup"><span data-stu-id="33592-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="33592-316">Sur la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-317">Ajoutez le nom du cluster et l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="33592-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="33592-318">Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-319">Sur la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-320">Une fois le cluster créé, cliquez sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="33592-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="33592-321">Nous vous recommandons de configurer les paramètres de quorum de cluster pour utiliser un témoin de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="33592-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="33592-322">Pour ce faire, utilisez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="33592-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="33592-323">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions,** puis cliquez sur **Configurer les paramètres de quorum du cluster.**</span><span class="sxs-lookup"><span data-stu-id="33592-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="33592-324">Dans la page **Sélectionner l’option de configuration du quorum,** cliquez sur Sélectionner le témoin de **quorum.**</span><span class="sxs-lookup"><span data-stu-id="33592-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="33592-325">Dans la page **Sélectionner un témoin de quorum,** cliquez sur Configurer un témoin de partage de **fichiers.**</span><span class="sxs-lookup"><span data-stu-id="33592-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="33592-326">Dans la page **Configurer le témoin de partage** de fichiers, tapez le chemin d’accès du partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="33592-327">Sur la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="33592-328">Sur chaque serveur du cluster, activez ag ag dans SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="33592-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="33592-329">Ouvrez le Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33592-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="33592-330">Dans l’arborescence sur le côté gauche de l’écran, cliquez sur **SQL Server Services,** puis double-cliquez sur SQL Server service.</span><span class="sxs-lookup"><span data-stu-id="33592-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="33592-331">Dans la **zone Propriétés,** sélectionnez **l’onglet Haute disponibilité AlwaysOn.** Activez la case à cocher Activer les groupes de disponibilité **AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="33592-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="33592-332">Redémarrez le service SQL Server lorsque vous y être invité.</span><span class="sxs-lookup"><span data-stu-id="33592-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="33592-333">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="33592-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="33592-334">Ouvrez SQL Server Management Studio et connectez-vous à SQL Server instance.</span><span class="sxs-lookup"><span data-stu-id="33592-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="33592-335">Dans l’Explorateur d’objets, développez **le dossier Haute disponibilité Always On.**</span><span class="sxs-lookup"><span data-stu-id="33592-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="33592-336">Cliquez avec le bouton droit **sur le dossier Groupes de** disponibilité, puis cliquez sur Assistant Nouveau groupe de **disponibilité.**</span><span class="sxs-lookup"><span data-stu-id="33592-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="33592-337">Si la page **Introduction** s’affiche, cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="33592-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="33592-338">Dans la page **Spécifier le nom du** groupe de disponibilité, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="33592-339">Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le ag.</span><span class="sxs-lookup"><span data-stu-id="33592-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="33592-340">Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="33592-341">N’incluez pas les bases de données **ReportServer,** **ReportServerTempDB** ou De conversation permanente dans la ag, car celles-ci ne sont pas pris en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="33592-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="33592-342">Vous pouvez inclure toutes les autres bases de données Skype Entreprise Server dans le ag.</span><span class="sxs-lookup"><span data-stu-id="33592-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="33592-343">Dans la page **Spécifier les réplicas,** cliquez sur **l’onglet Réplicas.** Cliquez ensuite sur le bouton Ajouter des **réplicas,** puis connectez-vous aux autres instances SQL que vous avez jointes en tant que nodes du WSFC.</span><span class="sxs-lookup"><span data-stu-id="33592-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="33592-344">Pour chaque instance, sélectionnez les options **Deover automatique et** **Validation synchrone.**</span><span class="sxs-lookup"><span data-stu-id="33592-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="33592-345">Ne sélectionnez pas **l’option Secondaire lisible.**</span><span class="sxs-lookup"><span data-stu-id="33592-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="33592-346">Cliquez sur **l’onglet Points de terminaison** et vérifiez que le **numéro de port** est 5022.</span><span class="sxs-lookup"><span data-stu-id="33592-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="33592-347">Cliquez sur **l’onglet d’écoute,** puis sélectionnez l’option Créer **un listener de** groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="33592-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="33592-348">Sous cette option, tapez un nom pour l’port d’écoute et définissez le **port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="33592-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="33592-349">Cliquez **sur** Ajouter, puis dans la zone **Adresse IPv4,** fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="33592-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="33592-350">Dans la **page** Sélectionner la synchronisation initiale des données, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et pour qui le compte de service SQL Server utilisé par les deux réplicas dispose d’autorisations d’écriture.</span><span class="sxs-lookup"><span data-stu-id="33592-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="33592-351">Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="33592-352">Ce partage de fichiers sera utilisé temporairement lors de l’initialisation des bases de données.</span><span class="sxs-lookup"><span data-stu-id="33592-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="33592-353">Si vous avez affaire à des bases de données de grande taille, nous vous recommandons de les initialiser manuellement si votre bande passante réseau ne peut pas prendre en charge la taille des sauvegardes de base de données.</span><span class="sxs-lookup"><span data-stu-id="33592-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="33592-354">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="33592-355">Dans la page **Résumé,** vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="33592-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="33592-356">Créez un magasin spécifiant l’écoute AG.</span><span class="sxs-lookup"><span data-stu-id="33592-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="33592-357">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="33592-357">Open Topology Builder.</span></span> <span data-ttu-id="33592-358">Dans votre topologie, développez **Composants partagés,** cliquez avec le bouton droit **sur SQL Server Store,** puis cliquez sur Nouveau **SQL Server Store.**</span><span class="sxs-lookup"><span data-stu-id="33592-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="33592-359">Dans la page Définir un nouveau **magasin SQL,** activez d’abord la case à cocher **Paramètres** de haute disponibilité, puis assurez-vous que les groupes de disponibilité AlwaysOn SQL apparaissent dans la zone de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="33592-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="33592-360">Dans la **SQL Server FQDN** de l’écouteur de disponibilité, tapez le FQDN de l’écoute que vous avez créé lorsque vous avez créé le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="33592-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="33592-361">Dans la **SQL Server FQDN,** tapez le FQDN du nœud principal de l’ag, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="33592-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="33592-362">Associez le nouveau groupe de disponibilité Always On au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="33592-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="33592-363">Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool à associer à l’AG, puis cliquez **sur Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="33592-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="33592-364">Sous **Associations,** dans la **SQL Server Store,** sélectionnez l’AG.</span><span class="sxs-lookup"><span data-stu-id="33592-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="33592-365">Sélectionnez le même groupe pour toutes les autres bases de données du pool que vous souhaitez déplacer vers l’ag.</span><span class="sxs-lookup"><span data-stu-id="33592-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="33592-366">Lorsque vous êtes sûr que toutes les bases de données nécessaires sont définies sur la ag ag, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="33592-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="33592-367">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="33592-367">Publish the topology.</span></span> <span data-ttu-id="33592-368">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="33592-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="33592-369">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="33592-370">Effectuez quelques étapes finales pour vous assurer que les connexions SQL sont sur chacun des réplicas du groupe de l’ag.</span><span class="sxs-lookup"><span data-stu-id="33592-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="33592-371">Ouvrez le Générateur de topologie, **sélectionnez Télécharger** la topologie à partir d’un déploiement existant, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="33592-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="33592-372">Développez Skype Entreprise Server, développez votre topologie et **développez SQL Server Stores.**</span><span class="sxs-lookup"><span data-stu-id="33592-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="33592-373">Cliquez avec le bouton droit SQL magasin de la nouvelle ag, puis cliquez **sur Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="33592-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="33592-374">En bas de la page, dans la zone **SQL Server FQDN,** modifiez la valeur en nom de nom de groupe de l’écoute de l’ag.</span><span class="sxs-lookup"><span data-stu-id="33592-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="33592-375">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="33592-375">Publish the topology.</span></span> <span data-ttu-id="33592-376">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="33592-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="33592-377">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="33592-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="33592-378">Patientez ensuite quelques minutes pour que la nouvelle topologie soit répliquée.</span><span class="sxs-lookup"><span data-stu-id="33592-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="33592-379">Ouvrez SQL Server Management Studio, puis accédez à l’AG.</span><span class="sxs-lookup"><span data-stu-id="33592-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="33592-380">Le faire échouer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="33592-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="33592-381">Ouvrez Skype Entreprise Server Management Shell et tapez l’cmdlet suivante pour créer SQL connexions sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="33592-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="33592-382">Répétez les deux étapes précédentes (faire échouer le groupe vers un réplica secondaire, puis  `Install-CsDatabase -Update` utilisez) pour chaque réplica du groupe.</span><span class="sxs-lookup"><span data-stu-id="33592-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
