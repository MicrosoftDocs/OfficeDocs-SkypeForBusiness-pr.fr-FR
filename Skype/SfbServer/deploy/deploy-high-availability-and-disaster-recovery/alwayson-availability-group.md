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
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="cdbad-103">Déployer un groupe de disponibilité Always On sur un serveur principal dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cdbad-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="cdbad-104">Déployez (installez) un groupe de disponibilité Always On (AG) dans votre déploiement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="cdbad-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="cdbad-105">La façon dont vous déployez une ag ag varie selon que vous la déployez dans un nouveau pool, un pool existant qui utilise la mise en miroir ou un pool existant qui n’a actuellement aucune haute disponibilité pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="cdbad-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cdbad-106">L’utilisation d’une ag ag avec un rôle serveur de conversation permanente n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="cdbad-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="cdbad-107">Déployer un groupe de disponibilité Always On sur un nouveau pool frontal</span><span class="sxs-lookup"><span data-stu-id="cdbad-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="cdbad-108">Déployer un groupe de disponibilité Always On sur un pool existant qui utilise la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="cdbad-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="cdbad-109">Déployer un groupe de disponibilité Always On sur un pool existant qui n’utilise pas la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="cdbad-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="cdbad-110">Déployer un groupe de disponibilité Always On sur un nouveau pool frontal</span><span class="sxs-lookup"><span data-stu-id="cdbad-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="cdbad-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="cdbad-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="cdbad-112">Activez la fonctionnalité clustering de failover sur tous les serveurs de base de données qui feront partie de l’AG.</span><span class="sxs-lookup"><span data-stu-id="cdbad-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="cdbad-113">Sur chaque serveur, faites les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cdbad-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="cdbad-114">Ouvrez le Gestionnaire de serveur et cliquez **sur Ajouter des rôles et des fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="cdbad-115">Cliquez **sur Suivant** jusqu’à atteindre la zone Sélectionner les **fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="cdbad-116">Ici, cochez la case **Clustering deover.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="cdbad-117">Dans la **zone Ajouter des fonctionnalités requises pour** le clustering de failover, cliquez sur Ajouter des **fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="cdbad-118">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="cdbad-119">Validez la configuration du cluster.</span><span class="sxs-lookup"><span data-stu-id="cdbad-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="cdbad-120">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils,** puis cliquez sur Gestionnaire **du cluster de failover.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="cdbad-121">Sous **Actions** sur le côté droit de l’écran, cliquez **sur Valider la configuration.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="cdbad-122">Sur la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-123">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="cdbad-124">Dans la **zone Résumé,** vérifiez les erreurs que l’Assistant signale.</span><span class="sxs-lookup"><span data-stu-id="cdbad-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="cdbad-125">Cliquez ensuite **sur Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="cdbad-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="cdbad-126">L’Assistant signalera probablement plusieurs avertissements, en particulier si vous n’utilisez pas de stockage partagé.</span><span class="sxs-lookup"><span data-stu-id="cdbad-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="cdbad-127">Vous n’êtes pas obligé d’utiliser le stockage partagé.</span><span class="sxs-lookup"><span data-stu-id="cdbad-127">You are not required to use shared storage.</span></span> <span data-ttu-id="cdbad-128">Toutefois, si  vous voyez des messages d’erreur, vous devez résoudre ces problèmes avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="cdbad-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="cdbad-129">Créez le cluster de failover Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="cdbad-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="cdbad-130">Dans **l’Assistant Gestion du cluster de failover,** cliquez avec le bouton droit sur Gestion du cluster de **failover,** puis cliquez **sur Créer un cluster.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="cdbad-131">Sur la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-132">Ajoutez le nom du cluster et l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="cdbad-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="cdbad-133">Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-134">Sur la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-135">Une fois le cluster créé, cliquez sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="cdbad-136">Nous vous recommandons de configurer les paramètres de quorum de cluster pour utiliser un témoin de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="cdbad-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="cdbad-137">Pour ce faire, utilisez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cdbad-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="cdbad-138">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions,** puis cliquez sur **Configurer les paramètres de quorum du cluster.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="cdbad-139">Dans la page **Sélectionner l’option de configuration du quorum,** cliquez sur Sélectionner le témoin de **quorum.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="cdbad-140">Dans la page **Sélectionner un témoin de quorum,** cliquez sur Configurer un témoin de partage de **fichiers.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="cdbad-141">Dans la page **Configurer le témoin de partage** de fichiers, tapez le chemin d’accès du partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-142">Sur la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="cdbad-143">Sur chaque serveur du cluster, activez la fonctionnalité AG dans SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="cdbad-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="cdbad-144">Ouvrez le Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cdbad-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="cdbad-145">Dans l’arborescence sur le côté gauche de l’écran, cliquez sur **SQL Server Services,** puis double-cliquez sur SQL Server service.</span><span class="sxs-lookup"><span data-stu-id="cdbad-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="cdbad-146">Dans la **zone Propriétés,** sélectionnez **l’onglet Haute disponibilité AlwaysOn.** Activez la case à cocher Activer les groupes de disponibilité **AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="cdbad-147">Redémarrez le service SQL Server lorsque vous y être invité.</span><span class="sxs-lookup"><span data-stu-id="cdbad-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="cdbad-148">Utilisez le Générateur de topologie pour créer le pool frontal, comme expliqué dans Créer et publier une nouvelle [topologie dans Skype Entreprise Server.](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="cdbad-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="cdbad-149">Lorsque vous le faites, spécifiez la ag ag comme SQL magasin pour le pool.</span><span class="sxs-lookup"><span data-stu-id="cdbad-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="cdbad-150">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="cdbad-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="cdbad-151">Ouvrez SQL Server Management Studio et connectez-vous à SQL Server instance.</span><span class="sxs-lookup"><span data-stu-id="cdbad-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="cdbad-152">Dans l’Explorateur d’objets, développez **le dossier Haute disponibilité Always On.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="cdbad-153">Cliquez avec le bouton droit **sur le dossier Groupes de** disponibilité, puis cliquez sur Assistant Nouveau groupe de **disponibilité.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="cdbad-154">Si la page **Introduction** s’affiche, cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-155">Dans la page **Spécifier le nom du** groupe de disponibilité, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-156">Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="cdbad-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="cdbad-157">Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="cdbad-158">N’incluez pas les bases de données **ReportServer,** **ReportServerTempDB** ou Persistent Chat dans le groupe de disponibilité AlwaysOn, car elles ne sont pas pris en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="cdbad-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="cdbad-159">Vous pouvez inclure toutes les autres bases de données Skype Entreprise Server dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="cdbad-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="cdbad-160">Dans la page **Spécifier les réplicas,** cliquez sur **l’onglet Réplicas.** Cliquez ensuite sur le bouton Ajouter des **réplicas,** puis connectez-vous aux autres instances SQL que vous avez jointes en tant que nodes du cluster de bas niveau Windows Server.</span><span class="sxs-lookup"><span data-stu-id="cdbad-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="cdbad-161">Pour chaque instance, sélectionnez les options **Deover automatique et** **Validation synchrone.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="cdbad-162">Ne sélectionnez pas **l’option Secondaire lisible.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="cdbad-163">Cliquez sur **l’onglet Points de terminaison** et vérifiez que le **numéro de port** est 5022.</span><span class="sxs-lookup"><span data-stu-id="cdbad-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="cdbad-164">Cliquez sur **l’onglet d’écoute,** puis sélectionnez l’option Créer **un listener de** groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="cdbad-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="cdbad-165">Sous cette option, tapez un nom pour l’port d’écoute et définissez le **port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="cdbad-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="cdbad-166">Cliquez **sur** Ajouter, puis dans la zone **Adresse IPv4,** fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="cdbad-167">Dans la **page** Sélectionner la synchronisation initiale des données, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et pour qui le compte de service SQL Server utilisé par les deux réplicas dispose d’autorisations d’écriture.</span><span class="sxs-lookup"><span data-stu-id="cdbad-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="cdbad-168">Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="cdbad-169">Ce partage de fichiers sera utilisé temporairement lors de l’initialisation des bases de données.</span><span class="sxs-lookup"><span data-stu-id="cdbad-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="cdbad-170">Si vous avez affaire à des bases de données de grande taille, nous vous recommandons de les initialiser manuellement si votre bande passante réseau ne peut pas prendre en charge la taille des sauvegardes de base de données.</span><span class="sxs-lookup"><span data-stu-id="cdbad-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="cdbad-171">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-172">Dans la page **Résumé,** vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="cdbad-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="cdbad-173">Une fois le pool et le groupe de disponibilité de service déployés, effectuez quelques étapes finales pour vous assurer que les connexions SQL sont sur chacun des réplicas du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="cdbad-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="cdbad-174">Ouvrez le Générateur de topologie, **sélectionnez Télécharger** la topologie à partir d’un déploiement existant, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="cdbad-175">Développez Skype Entreprise Server, développez votre topologie et **développez SQL Server Stores.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="cdbad-176">Cliquez avec le bouton droit SQL magasin du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="cdbad-177">En bas de la page, dans la zone **SQL Server FQDN,** modifiez la valeur en nom de nom de groupe de l’écoute de l’ag.</span><span class="sxs-lookup"><span data-stu-id="cdbad-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="cdbad-178">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="cdbad-178">Publish the topology.</span></span> <span data-ttu-id="cdbad-179">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="cdbad-180">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="cdbad-181">Patientez ensuite quelques minutes pour que la nouvelle topologie soit répliquée.</span><span class="sxs-lookup"><span data-stu-id="cdbad-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="cdbad-182">Ouvrez SQL Server Management Studio, puis accédez à l’AG.</span><span class="sxs-lookup"><span data-stu-id="cdbad-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="cdbad-183">Le faire échouer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="cdbad-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="cdbad-184">Ouvrez Skype Entreprise Server Management Shell et tapez l’cmdlet suivante pour créer SQL connexions sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="cdbad-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="cdbad-185">Répétez les deux étapes précédentes (faire échouer le groupe vers un réplica secondaire, puis  `Install-CsDatabase -Update` utilisez) pour chaque réplica du groupe.</span><span class="sxs-lookup"><span data-stu-id="cdbad-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="cdbad-186">Déployer un groupe de disponibilité Always On sur un pool existant qui utilise la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="cdbad-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="cdbad-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="cdbad-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="cdbad-188">Si le pool que vous misez à niveau vers une ag ag héberge le magasin central de gestion de votre organisation, vous devez d’abord déplacer le cms vers un autre pool avant de mettre à niveau ce pool.</span><span class="sxs-lookup"><span data-stu-id="cdbad-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="cdbad-189">Utilisez lMove-CsManagementServer cmdlet pour déplacer le pool.</span><span class="sxs-lookup"><span data-stu-id="cdbad-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="cdbad-190">Si vous n’avez pas d’autre pool dans votre organisation, vous pouvez déployer temporairement un serveur Standard Edition Server et déplacer le cmS vers ce serveur avant de mettre à niveau votre pool vers le groupe de sécurité d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="cdbad-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="cdbad-191">Pour faire échouer toutes les données du miroir vers le nœud principal, ouvrent Skype Entreprise Server Management Shell et tapent l’cmdlet suivante.</span><span class="sxs-lookup"><span data-stu-id="cdbad-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="cdbad-192">Répétez cette cmdlet pour chaque type de base de données dans le pool.</span><span class="sxs-lookup"><span data-stu-id="cdbad-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="cdbad-193">Vous pouvez utiliser l’cmdlet suivante pour rechercher tous les types de base de données stockés dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="cdbad-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="cdbad-194">Utilisez le Générateur de topologie pour supprimer la mise en miroir de base de données du pool.</span><span class="sxs-lookup"><span data-stu-id="cdbad-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="cdbad-195">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="cdbad-195">Open Topology Builder.</span></span> <span data-ttu-id="cdbad-196">Dans votre topologie, développez pools frontux **Enterprise Edition,** cliquez avec le bouton droit sur le nom du pool, puis cliquez sur **Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="cdbad-197">Pour chaque type de SQL dans le pool, activez la case à **cocher Activer SQL mise** en miroir du Store.</span><span class="sxs-lookup"><span data-stu-id="cdbad-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="cdbad-198">Publiez la topologie modifiée.</span><span class="sxs-lookup"><span data-stu-id="cdbad-198">Publish the changed topology.</span></span> <span data-ttu-id="cdbad-199">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="cdbad-200">Ensuite, dans la page de confirmation, cliquez sur **Suivant**</span><span class="sxs-lookup"><span data-stu-id="cdbad-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="cdbad-201">Utilisez SQL Server Management Studio pour rompre le miroir.</span><span class="sxs-lookup"><span data-stu-id="cdbad-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="cdbad-202">Ouvrez SQL Server Management Studio, accédez à vos bases de données, cliquez avec le bouton droit sur **Tâches** et cliquez sur **Miroir.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="cdbad-203">Cliquez ensuite **sur Supprimer la mise en** miroir et sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="cdbad-204">Répétez cette phase pour toutes les bases de données du pool qui seront converties en ag.</span><span class="sxs-lookup"><span data-stu-id="cdbad-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="cdbad-205">Configurer la fonctionnalité clustering de failover sur tous les serveurs de base de données qui feront partie de l’AG.</span><span class="sxs-lookup"><span data-stu-id="cdbad-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="cdbad-206">Sur chaque serveur, faites les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cdbad-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="cdbad-207">Ouvrez le Gestionnaire de serveur et cliquez **sur Ajouter des rôles et des fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="cdbad-208">Cliquez **sur Suivant** jusqu’à atteindre la zone Sélectionner les **fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="cdbad-209">Ici, cochez la case **Clustering deover.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="cdbad-210">Dans la **zone Ajouter des fonctionnalités requises pour** le clustering de failover, cliquez sur Ajouter des **fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="cdbad-211">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="cdbad-212">Validez la configuration du cluster.</span><span class="sxs-lookup"><span data-stu-id="cdbad-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="cdbad-213">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils,** puis cliquez sur Gestionnaire **du cluster de failover.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="cdbad-214">Sous **Actions** sur le côté droit de l’écran, cliquez **sur Valider la configuration.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="cdbad-215">Sur la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-216">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="cdbad-217">Dans la **zone Résumé,** vérifiez les erreurs que l’Assistant signale.</span><span class="sxs-lookup"><span data-stu-id="cdbad-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="cdbad-218">Cliquez ensuite **sur Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="cdbad-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="cdbad-219">L’Assistant signalera probablement plusieurs avertissements, en particulier si vous n’utilisez pas de stockage partagé.</span><span class="sxs-lookup"><span data-stu-id="cdbad-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="cdbad-220">Vous n’êtes pas obligé d’utiliser le stockage partagé.</span><span class="sxs-lookup"><span data-stu-id="cdbad-220">You are not required to use shared storage.</span></span> <span data-ttu-id="cdbad-221">Toutefois, si  vous voyez des messages d’erreur, vous devez résoudre ces problèmes avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="cdbad-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="cdbad-222">Créez le cluster de failover Windows Server.</span><span class="sxs-lookup"><span data-stu-id="cdbad-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="cdbad-223">Dans **l’Assistant Gestion du cluster de failover,** cliquez avec le bouton droit sur Gestion du cluster de **failover,** puis cliquez **sur Créer un cluster.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="cdbad-224">Sur la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-225">Ajoutez le nom du cluster et l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="cdbad-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="cdbad-226">Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-227">Sur la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-228">Une fois le cluster créé, cliquez sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="cdbad-229">Nous vous recommandons de configurer les paramètres de quorum de cluster pour utiliser un témoin de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="cdbad-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="cdbad-230">Pour ce faire, utilisez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cdbad-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="cdbad-231">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions,** puis cliquez sur **Configurer les paramètres de quorum du cluster.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="cdbad-232">Dans la page **Sélectionner l’option de configuration du quorum,** cliquez sur Sélectionner le témoin de **quorum.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="cdbad-233">Dans la page **Sélectionner un témoin de quorum,** cliquez sur Configurer un témoin de partage de **fichiers.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="cdbad-234">Dans la page **Configurer le témoin de partage** de fichiers, tapez le chemin d’accès du partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-235">Sur la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="cdbad-236">Sur chaque serveur du cluster, activez la fonctionnalité AG dans SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="cdbad-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="cdbad-237">Ouvrez le Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cdbad-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="cdbad-238">Dans l’arborescence sur le côté gauche de l’écran, cliquez sur **SQL Server Services,** puis double-cliquez sur SQL Server service.</span><span class="sxs-lookup"><span data-stu-id="cdbad-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="cdbad-239">Dans la **zone Propriétés,** sélectionnez **l’onglet Haute disponibilité AlwaysOn.** Activez la case à cocher Activer les groupes de disponibilité **AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="cdbad-240">Redémarrez le service SQL Server lorsque vous y être invité.</span><span class="sxs-lookup"><span data-stu-id="cdbad-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="cdbad-241">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="cdbad-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="cdbad-242">Ouvrez SQL Server Management Studio et connectez-vous à SQL Server instance.</span><span class="sxs-lookup"><span data-stu-id="cdbad-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="cdbad-243">Dans l’Explorateur d’objets, développez **le dossier Haute disponibilité Always On.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="cdbad-244">Cliquez avec le bouton droit **sur le dossier Groupes de** disponibilité, puis cliquez sur Assistant Nouveau groupe de **disponibilité.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="cdbad-245">Si la page **Introduction** s’affiche, cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="cdbad-246">Dans la page **Spécifier le nom du** groupe de disponibilité, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="cdbad-247">Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="cdbad-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="cdbad-248">Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="cdbad-249">N’incluez pas les bases de données **ReportServer,** **ReportServerTempDB** ou Persistent Chat dans le groupe de disponibilité AlwaysOn, car elles ne sont pas pris en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="cdbad-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="cdbad-250">Vous pouvez inclure toutes les autres bases de données Skype Entreprise Server dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="cdbad-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="cdbad-251">Dans la page **Spécifier les réplicas,** cliquez sur **l’onglet Réplicas.** Cliquez ensuite sur le bouton Ajouter des **réplicas,** puis connectez-vous aux autres instances SQL que vous avez jointes en tant que nodes du cluster de bas niveau Windows Server.</span><span class="sxs-lookup"><span data-stu-id="cdbad-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="cdbad-252">Pour chaque instance, sélectionnez les options **Deover automatique et** **Validation synchrone.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="cdbad-253">Ne sélectionnez pas **l’option Secondaire lisible.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="cdbad-254">Cliquez sur **l’onglet Points de terminaison** et vérifiez que le **numéro de port** est 5022.</span><span class="sxs-lookup"><span data-stu-id="cdbad-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="cdbad-255">Cliquez sur **l’onglet d’écoute,** puis sélectionnez l’option Créer **un listener de** groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="cdbad-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="cdbad-256">Sous cette option, tapez un nom pour l’port d’écoute et définissez le **port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="cdbad-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="cdbad-257">Cliquez **sur** Ajouter, puis dans la zone **Adresse IPv4,** fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="cdbad-258">Dans la **page** Sélectionner la synchronisation initiale des données, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et pour qui le compte de service SQL Server utilisé par les deux réplicas dispose d’autorisations d’écriture.</span><span class="sxs-lookup"><span data-stu-id="cdbad-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="cdbad-259">Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="cdbad-260">Ce partage de fichiers sera utilisé temporairement lors de l’initialisation des bases de données.</span><span class="sxs-lookup"><span data-stu-id="cdbad-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="cdbad-261">Si vous avez affaire à des bases de données de grande taille, nous vous recommandons de les initialiser manuellement si votre bande passante réseau ne peut pas prendre en charge la taille des sauvegardes de base de données.</span><span class="sxs-lookup"><span data-stu-id="cdbad-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="cdbad-262">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="cdbad-263">Dans la page **Résumé,** vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="cdbad-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="cdbad-264">Créez un magasin en spécifiant l’auditeur AG et en spécifiant le principal de l’ancien miroir comme nœud principal de l’AG.</span><span class="sxs-lookup"><span data-stu-id="cdbad-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="cdbad-265">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="cdbad-265">Open Topology Builder.</span></span> <span data-ttu-id="cdbad-266">Dans votre topologie, développez **Composants partagés,** cliquez avec le bouton droit **sur SQL Server Store,** puis cliquez sur Nouveau **SQL Server Store.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="cdbad-267">Dans la page Définir un nouveau **magasin SQL,** activez d’abord la case à cocher **Paramètres** de haute disponibilité, puis assurez-vous que les groupes de disponibilité AlwaysOn SQL apparaissent dans la zone de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="cdbad-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="cdbad-268">Dans la **SQL Server FQDN** de l’écouteur de disponibilité, tapez le FQDN de l’écoute que vous avez créé lorsque vous avez créé le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="cdbad-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="cdbad-269">Dans la **SQL Server FQDN,** tapez le FQDN du nœud principal de l’ag, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="cdbad-270">Il doit s’y prendre comme principal de l’ancien miroir pour ce magasin.</span><span class="sxs-lookup"><span data-stu-id="cdbad-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="cdbad-271">Associez la nouvelle AG au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="cdbad-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="cdbad-272">Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool à associer à l’AG, puis cliquez **sur Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="cdbad-273">Sous **Associations,** dans la **SQL Server Store,** sélectionnez l’AG.</span><span class="sxs-lookup"><span data-stu-id="cdbad-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="cdbad-274">Sélectionnez le même groupe pour toutes les autres bases de données du pool que vous souhaitez déplacer vers l’ag.</span><span class="sxs-lookup"><span data-stu-id="cdbad-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="cdbad-275">Lorsque vous êtes sûr que toutes les bases de données nécessaires sont définies sur la ag ag, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="cdbad-276">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="cdbad-276">Publish the topology.</span></span> <span data-ttu-id="cdbad-277">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="cdbad-278">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="cdbad-279">Effectuez quelques étapes finales pour vous assurer que les connexions SQL sont sur chacun des réplicas du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="cdbad-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="cdbad-280">Ouvrez le Générateur de topologie, **sélectionnez Télécharger** la topologie à partir d’un déploiement existant, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="cdbad-281">Développez Skype Entreprise Server, développez votre topologie et **développez SQL Server Stores.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="cdbad-282">Cliquez avec le bouton droit SQL magasin de la nouvelle ag, puis cliquez **sur Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="cdbad-283">En bas de la page, dans la zone **SQL Server FQDN,** modifiez la valeur en nom de nom de groupe de l’écoute de l’ag.</span><span class="sxs-lookup"><span data-stu-id="cdbad-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="cdbad-284">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="cdbad-284">Publish the topology.</span></span> <span data-ttu-id="cdbad-285">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="cdbad-286">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="cdbad-287">Patientez ensuite quelques minutes pour que la nouvelle topologie soit répliquée.</span><span class="sxs-lookup"><span data-stu-id="cdbad-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="cdbad-288">Ouvrez SQL Server Management Studio, puis accédez à l’AG.</span><span class="sxs-lookup"><span data-stu-id="cdbad-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="cdbad-289">Le faire échouer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="cdbad-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="cdbad-290">Ouvrez Skype Entreprise Server Management Shell et tapez l’cmdlet suivante pour créer SQL connexions sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="cdbad-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="cdbad-291">Répétez les deux étapes précédentes (faire échouer le groupe vers un réplica secondaire, puis  `Install-CsDatabase -Update` utilisez) pour chaque réplica du groupe.</span><span class="sxs-lookup"><span data-stu-id="cdbad-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="cdbad-292">Déployer un groupe de disponibilité Always On sur un pool existant qui n’utilise pas la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="cdbad-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="cdbad-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="cdbad-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="cdbad-294">Si le pool que vous misez à niveau vers une ag ag héberge le magasin central de gestion de votre organisation, vous devez d’abord déplacer le cms vers un autre pool avant de mettre à niveau ce pool.</span><span class="sxs-lookup"><span data-stu-id="cdbad-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="cdbad-295">Utilisez lMove-CsManagementServer cmdlet pour déplacer le pool.</span><span class="sxs-lookup"><span data-stu-id="cdbad-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="cdbad-296">Si vous n’avez pas d’autre pool dans votre organisation, vous pouvez déployer temporairement un serveur Standard Edition Server et déplacer le cmS vers ce serveur avant de mettre à niveau votre pool vers le groupe de sécurité d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="cdbad-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="cdbad-297">Configurer la fonctionnalité clustering de failover sur tous les serveurs de base de données qui feront partie de l’AG.</span><span class="sxs-lookup"><span data-stu-id="cdbad-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="cdbad-298">Sur chaque serveur, faites les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cdbad-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="cdbad-299">Ouvrez le Gestionnaire de serveur et cliquez **sur Ajouter des rôles et des fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="cdbad-300">Cliquez **sur Suivant** jusqu’à atteindre la zone Sélectionner les **fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="cdbad-301">Ici, cochez la case **Clustering deover.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="cdbad-302">Dans la **zone Ajouter des fonctionnalités requises pour** le clustering de failover, cliquez sur Ajouter des **fonctionnalités.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="cdbad-303">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="cdbad-304">Validez la configuration du cluster.</span><span class="sxs-lookup"><span data-stu-id="cdbad-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="cdbad-305">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils,** puis cliquez sur Gestionnaire **du cluster de failover.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="cdbad-306">Sous **Actions** sur le côté droit de l’écran, cliquez **sur Valider la configuration.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="cdbad-307">Sur la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-308">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="cdbad-309">Dans la **zone Résumé,** vérifiez les erreurs que l’Assistant signale.</span><span class="sxs-lookup"><span data-stu-id="cdbad-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="cdbad-310">Cliquez ensuite **sur Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="cdbad-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="cdbad-311">L’Assistant signalera probablement plusieurs avertissements, en particulier si vous n’utilisez pas de stockage partagé.</span><span class="sxs-lookup"><span data-stu-id="cdbad-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="cdbad-312">Vous n’êtes pas obligé d’utiliser le stockage partagé.</span><span class="sxs-lookup"><span data-stu-id="cdbad-312">You are not required to use shared storage.</span></span> <span data-ttu-id="cdbad-313">Toutefois, si  vous voyez des messages d’erreur, vous devez résoudre ces problèmes avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="cdbad-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="cdbad-314">Créez le cluster de failover Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="cdbad-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="cdbad-315">Dans **l’Assistant Gestion du cluster de failover,** cliquez avec le bouton droit sur Gestion du cluster de **failover,** puis cliquez **sur Créer un cluster.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="cdbad-316">Sur la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-317">Ajoutez le nom du cluster et l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="cdbad-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="cdbad-318">Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-319">Sur la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-320">Une fois le cluster créé, cliquez sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="cdbad-321">Nous vous recommandons de configurer les paramètres de quorum de cluster pour utiliser un témoin de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="cdbad-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="cdbad-322">Pour ce faire, utilisez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cdbad-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="cdbad-323">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions,** puis cliquez sur **Configurer les paramètres de quorum du cluster.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="cdbad-324">Dans la page **Sélectionner l’option de configuration du quorum,** cliquez sur Sélectionner le témoin de **quorum.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="cdbad-325">Dans la page **Sélectionner un témoin de quorum,** cliquez sur Configurer un témoin de partage de **fichiers.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="cdbad-326">Dans la page **Configurer le témoin de partage** de fichiers, tapez le chemin d’accès du partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-327">Sur la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="cdbad-328">Sur chaque serveur du cluster, activez ag ag dans SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="cdbad-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="cdbad-329">Ouvrez le Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cdbad-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="cdbad-330">Dans l’arborescence sur le côté gauche de l’écran, cliquez sur **SQL Server Services,** puis double-cliquez sur SQL Server service.</span><span class="sxs-lookup"><span data-stu-id="cdbad-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="cdbad-331">Dans la **zone Propriétés,** sélectionnez **l’onglet Haute disponibilité AlwaysOn.** Activez la case à cocher Activer les groupes de disponibilité **AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="cdbad-332">Redémarrez le service SQL Server lorsque vous y être invité.</span><span class="sxs-lookup"><span data-stu-id="cdbad-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="cdbad-333">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="cdbad-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="cdbad-334">Ouvrez SQL Server Management Studio et connectez-vous à SQL Server instance.</span><span class="sxs-lookup"><span data-stu-id="cdbad-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="cdbad-335">Dans l’Explorateur d’objets, développez **le dossier Haute disponibilité Always On.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="cdbad-336">Cliquez avec le bouton droit **sur le dossier Groupes de** disponibilité, puis cliquez sur Assistant Nouveau groupe de **disponibilité.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="cdbad-337">Si la page **Introduction** s’affiche, cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-338">Dans la page **Spécifier le nom du** groupe de disponibilité, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-339">Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le ag.</span><span class="sxs-lookup"><span data-stu-id="cdbad-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="cdbad-340">Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="cdbad-341">N’incluez pas les bases de données **ReportServer,** **ReportServerTempDB** ou De conversation permanente dans la ag, car celles-ci ne sont pas pris en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="cdbad-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="cdbad-342">Vous pouvez inclure toutes les autres bases de données Skype Entreprise Server dans le ag.</span><span class="sxs-lookup"><span data-stu-id="cdbad-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="cdbad-343">Dans la page **Spécifier les réplicas,** cliquez sur **l’onglet Réplicas.** Cliquez ensuite sur le bouton Ajouter des **réplicas,** puis connectez-vous aux autres instances SQL que vous avez jointes en tant que nodes du WSFC.</span><span class="sxs-lookup"><span data-stu-id="cdbad-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="cdbad-344">Pour chaque instance, sélectionnez les options **Deover automatique et** **Validation synchrone.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="cdbad-345">Ne sélectionnez pas **l’option Secondaire lisible.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="cdbad-346">Cliquez sur **l’onglet Points de terminaison** et vérifiez que le **numéro de port** est 5022.</span><span class="sxs-lookup"><span data-stu-id="cdbad-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="cdbad-347">Cliquez sur **l’onglet d’écoute,** puis sélectionnez l’option Créer **un listener de** groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="cdbad-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="cdbad-348">Sous cette option, tapez un nom pour l’port d’écoute et définissez le **port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="cdbad-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="cdbad-349">Cliquez **sur** Ajouter, puis dans la zone **Adresse IPv4,** fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="cdbad-350">Dans la **page** Sélectionner la synchronisation initiale des données, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et pour qui le compte de service SQL Server utilisé par les deux réplicas dispose d’autorisations d’écriture.</span><span class="sxs-lookup"><span data-stu-id="cdbad-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="cdbad-351">Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="cdbad-352">Ce partage de fichiers sera utilisé temporairement lors de l’initialisation des bases de données.</span><span class="sxs-lookup"><span data-stu-id="cdbad-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="cdbad-353">Si vous avez affaire à des bases de données de grande taille, nous vous recommandons de les initialiser manuellement si votre bande passante réseau ne peut pas prendre en charge la taille des sauvegardes de base de données.</span><span class="sxs-lookup"><span data-stu-id="cdbad-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="cdbad-354">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="cdbad-355">Dans la page **Résumé,** vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="cdbad-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="cdbad-356">Créez un magasin spécifiant l’écoute AG.</span><span class="sxs-lookup"><span data-stu-id="cdbad-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="cdbad-357">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="cdbad-357">Open Topology Builder.</span></span> <span data-ttu-id="cdbad-358">Dans votre topologie, développez **Composants partagés,** cliquez avec le bouton droit **sur SQL Server Store,** puis cliquez sur Nouveau **SQL Server Store.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="cdbad-359">Dans la page Définir un nouveau **magasin SQL,** activez d’abord la case à cocher **Paramètres** de haute disponibilité, puis assurez-vous que les groupes de disponibilité AlwaysOn SQL apparaissent dans la zone de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="cdbad-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="cdbad-360">Dans la **SQL Server FQDN** de l’écouteur de disponibilité, tapez le FQDN de l’écoute que vous avez créé lorsque vous avez créé le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="cdbad-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="cdbad-361">Dans la **SQL Server FQDN,** tapez le FQDN du nœud principal de l’ag, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="cdbad-362">Associez le nouveau groupe de disponibilité Always On au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="cdbad-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="cdbad-363">Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool à associer à l’AG, puis cliquez **sur Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="cdbad-364">Sous **Associations,** dans la **SQL Server Store,** sélectionnez l’AG.</span><span class="sxs-lookup"><span data-stu-id="cdbad-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="cdbad-365">Sélectionnez le même groupe pour toutes les autres bases de données du pool que vous souhaitez déplacer vers l’ag.</span><span class="sxs-lookup"><span data-stu-id="cdbad-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="cdbad-366">Lorsque vous êtes sûr que toutes les bases de données nécessaires sont définies sur la ag ag, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="cdbad-367">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="cdbad-367">Publish the topology.</span></span> <span data-ttu-id="cdbad-368">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="cdbad-369">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="cdbad-370">Effectuez quelques étapes finales pour vous assurer que les connexions SQL sont sur chacun des réplicas du groupe de l’ag.</span><span class="sxs-lookup"><span data-stu-id="cdbad-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="cdbad-371">Ouvrez le Générateur de topologie, **sélectionnez Télécharger** la topologie à partir d’un déploiement existant, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="cdbad-372">Développez Skype Entreprise Server, développez votre topologie et **développez SQL Server Stores.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="cdbad-373">Cliquez avec le bouton droit SQL magasin de la nouvelle ag, puis cliquez **sur Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="cdbad-374">En bas de la page, dans la zone **SQL Server FQDN,** modifiez la valeur en nom de nom de groupe de l’écoute de l’ag.</span><span class="sxs-lookup"><span data-stu-id="cdbad-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="cdbad-375">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="cdbad-375">Publish the topology.</span></span> <span data-ttu-id="cdbad-376">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="cdbad-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="cdbad-377">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cdbad-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="cdbad-378">Patientez ensuite quelques minutes pour que la nouvelle topologie soit répliquée.</span><span class="sxs-lookup"><span data-stu-id="cdbad-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="cdbad-379">Ouvrez SQL Server Management Studio, puis accédez à l’AG.</span><span class="sxs-lookup"><span data-stu-id="cdbad-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="cdbad-380">Le faire échouer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="cdbad-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="cdbad-381">Ouvrez Skype Entreprise Server Management Shell et tapez l’cmdlet suivante pour créer SQL connexions sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="cdbad-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="cdbad-382">Répétez les deux étapes précédentes (faire échouer le groupe vers un réplica secondaire, puis  `Install-CsDatabase -Update` utilisez) pour chaque réplica du groupe.</span><span class="sxs-lookup"><span data-stu-id="cdbad-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
