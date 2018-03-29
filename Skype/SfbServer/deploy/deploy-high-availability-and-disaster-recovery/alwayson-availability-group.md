---
title: Déploiement d’un groupe de disponibilité AlwaysOn sur un serveur principal dans Skype Entreprise Server 2015
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
description: Déployer (installer) un groupe de disponibilité AlwaysOn dans votre Skype pour Business Server déploiement.
ms.openlocfilehash: 858f8cd317ecccde315475bc6489c74d79bf72c6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-an-alwayson-availability-group-on-a-back-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="87f98-103">Déploiement d’un groupe de disponibilité AlwaysOn sur un serveur principal dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="87f98-103">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="87f98-104">Déployer (installer) un groupe de disponibilité AlwaysOn dans votre Skype pour Business Server déploiement.</span><span class="sxs-lookup"><span data-stu-id="87f98-104">Deploy (install) an AlwaysOn Availability Group in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="87f98-105">Comment déployer un groupe de disponibilité AlwaysOn dépend de si vous déployez dans un nouveau pool, un pool existant qui utilise la mise en miroir ou un pool existant qui n’a actuellement aucun haute disponibilité de la base de données Back-End.</span><span class="sxs-lookup"><span data-stu-id="87f98-105">How you deploy an AlwaysOn Availability Group depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="87f98-106">À l’aide d’un groupe de disponibilité AlwaysOn avec un rôle de serveur de conversation persistant n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="87f98-106">Using an AlwaysOn Availability Group with a Persistent Chat Server role is not supported.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="87f98-107">Les noms d’instance pour plusieurs instances du groupe de disponibilité AlwaysOn doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="87f98-107">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
- [<span data-ttu-id="87f98-108">Déploiement d’un groupe de disponibilité AlwaysOn sur un nouveau pool frontal</span><span class="sxs-lookup"><span data-stu-id="87f98-108">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="87f98-109">Déploiement d’un groupe de disponibilité AlwaysOn sur un pool existant qui utilise la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="87f98-109">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="87f98-110">Déploiement d’un groupe de disponibilité AlwaysOn sur un pool existant qui n’utilise pas la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="87f98-110">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-alwayson-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="87f98-111">Déploiement d’un groupe de disponibilité AlwaysOn sur un nouveau pool frontal</span><span class="sxs-lookup"><span data-stu-id="87f98-111">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>
<span data-ttu-id="87f98-112"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="87f98-112"></span></span>

1. <span data-ttu-id="87f98-113">Permet de paramétrer le Clustering avec basculement de Windows Server sur tous les serveurs de base de données qui feront partie du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-113">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="87f98-114">Sur chaque serveur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="87f98-114">On each server, do the following</span></span>
    
   - <span data-ttu-id="87f98-115">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="87f98-115">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="87f98-p102">Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="87f98-118">Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="87f98-118">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="87f98-119">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="87f98-119">Click **Install**.</span></span>
    
2. <span data-ttu-id="87f98-120">Validez la configuration de cluster.</span><span class="sxs-lookup"><span data-stu-id="87f98-120">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="87f98-121">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.</span><span class="sxs-lookup"><span data-stu-id="87f98-121">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="87f98-122">Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.</span><span class="sxs-lookup"><span data-stu-id="87f98-122">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="87f98-123">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-123">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-124">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.</span><span class="sxs-lookup"><span data-stu-id="87f98-124">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="87f98-125">Dans la zone**Résumé** , vérifiez les erreurs qui le rapports de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="87f98-125">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="87f98-126">Cliquez ensuite sur **Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="87f98-126">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="87f98-p104">L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="87f98-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="87f98-130">Créez le cluster.</span><span class="sxs-lookup"><span data-stu-id="87f98-130">Create the cluster.</span></span>
    
   - <span data-ttu-id="87f98-131">Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.</span><span class="sxs-lookup"><span data-stu-id="87f98-131">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="87f98-132">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-132">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-p105">Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-135">Dans la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-135">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-136">Après la création du cluster, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="87f98-136">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="87f98-p106">Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="87f98-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="87f98-139">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.</span><span class="sxs-lookup"><span data-stu-id="87f98-139">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="87f98-140">Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.</span><span class="sxs-lookup"><span data-stu-id="87f98-140">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="87f98-141">Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.</span><span class="sxs-lookup"><span data-stu-id="87f98-141">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="87f98-142">Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-142">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-143">Dans la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-143">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="87f98-144">Sur chaque serveur du cluster, activez Always On dans le Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="87f98-144">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="87f98-p107">Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server. </span><span class="sxs-lookup"><span data-stu-id="87f98-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="87f98-p108">Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="87f98-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="87f98-149">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="87f98-149">Create the availability group.</span></span>
    
   - <span data-ttu-id="87f98-150">Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="87f98-150">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="87f98-p109">Dans l’Explorateur d’objets, développez la **Haute disponibilité AlwaysOn**. Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p109">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="87f98-153">Si la page **Présentation** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-153">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-154">Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-154">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-155">Dans la page Sélectionner les bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-155">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="87f98-156">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="87f98-156">Then click **Next**.</span></span>
    
    <span data-ttu-id="87f98-157">N’incluez pas le **ReportServer**, **ReportServerTempDB**ou Chat permanente les bases de données dans le groupe de disponibilité AlwaysOn, comme ils ne sont pas pris en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="87f98-157">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="87f98-158">Vous pouvez inclure tous les autre Skype pour les bases de données Business Server dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-158">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="87f98-159">Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.</span><span class="sxs-lookup"><span data-stu-id="87f98-159">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="87f98-p112">Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="87f98-162">Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.</span><span class="sxs-lookup"><span data-stu-id="87f98-162">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="87f98-p113">Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="87f98-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="87f98-165">Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f98-165">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="87f98-p114">Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="87f98-p115">Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="87f98-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="87f98-170">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-170">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-171">Dans la page**Résumé** , vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="87f98-171">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="87f98-172">Utilisez le Générateur de topologies pour créer le pool frontal, comme expliqué dans [créer et publier la nouvelle topologie dans Skype pour Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="87f98-172">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="87f98-173">Spécifiez le groupe de disponibilité AlwaysOn comme magasin SQL pour le pool.</span><span class="sxs-lookup"><span data-stu-id="87f98-173">When you do, specify the AlwaysOn Availability Group as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="87f98-174">Une fois le pool et le groupe de disponibilité AlwaysOn déployées, exécuter certaines étapes finals pour vous assurer que les noms d’accès SQL sur chacune des répliques dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-174">After the pool and the AlwaysOn Availability Group are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="87f98-175">Ouvrir le Générateur de topologies, sélectionnez **Télécharger la topologie de déploiement existant**et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f98-175">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="87f98-176">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="87f98-176">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="87f98-177">Avec le bouton droit de la banque SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur ** Modifier propriétés **.</span><span class="sxs-lookup"><span data-stu-id="87f98-177">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="87f98-178">Au bas de la page, dans la zone **Nom de domaine complet de SQL Server** , modifiez la valeur pour le nom de domaine complet de l’écouteur du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-178">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="87f98-p118">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="87f98-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="87f98-183">Ouvrez SQL Server Management Studio et accédez au groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-183">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="87f98-184">Faites-le basculer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="87f98-184">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="87f98-185">Ouvrez Skype pour Business Server Management Shell et entrez l’applet de commande suivante pour créer les connexions d’accès SQL sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="87f98-185">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="87f98-186">Répétez les deux étapes précédentes (basculer le groupe vers un réplica secondaire, puis utilisez `Install-CsDatabase -Update`) pour chaque réplica dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="87f98-186">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="87f98-187">Déploiement d’un groupe de disponibilité AlwaysOn sur un pool existant qui utilise la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="87f98-187">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="87f98-188"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="87f98-188"></span></span>

> [!NOTE]
> <span data-ttu-id="87f98-189">Si le pool que vous mettez à niveau un hôtes du groupe de disponibilité AlwaysOn la direction centrale stocke pour votre organisation, vous devez déplacer le CMS vers un autre pool avant de vous mettre à niveau ce pool.</span><span class="sxs-lookup"><span data-stu-id="87f98-189">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="87f98-190">Utilisez l’applet de commande Move-CsManagementServer pour déplacer le pool.</span><span class="sxs-lookup"><span data-stu-id="87f98-190">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="87f98-191">Si vous ne disposez pas d’un autre pool de votre organisation, vous pouvez déployer un serveur Standard Edition server temporairement et déplacer le serveur CMS à ce serveur avant de vous mettre à niveau votre pool pour le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-191">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="87f98-192">Basculer toutes les données du miroir vers le nœud principal par ouverture Skype pour Business Server Management Shell, l’applet de commande suivante en tapant.</span><span class="sxs-lookup"><span data-stu-id="87f98-192">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="87f98-p121">Répétez cette applet de commande pour chaque type de base de données dans le pool. Vous pouvez utiliser l’applet de commande ci-dessous pour trouver tous les types de bases de données stockées dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="87f98-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="87f98-195">Utilisation du Générateur de topologie pour supprimer la mise en miroir de base de données à partir du pool</span><span class="sxs-lookup"><span data-stu-id="87f98-195">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="87f98-196">Ouvrez le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="87f98-196">Open Topology Builder.</span></span> <span data-ttu-id="87f98-197">Dans votre topologie, développez **Pools frontaux Entreprise Edition**, cliquez avec le bouton droit sur le nom du pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="87f98-197">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="87f98-198">Pour chaque type de magasin SQL dans le pool, désactivez la case à cocher **Activer la mise en miroir du magasin SQL**.</span><span class="sxs-lookup"><span data-stu-id="87f98-198">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="87f98-p123">Publiez la topologie modifiée. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="87f98-202">Utilisez SQL Server Management Studio afin de rompre la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="87f98-202">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="87f98-p124">Ouvrez SQL Server Management Studio, accédez à vos bases de données, cliquez avec le bouton droit sur **Tâches** et cliquez sur **Miroir**. Cliquez ensuite sur **Supprimer la mise en miroir** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="87f98-205">Répétez cette procédure pour toutes les bases de données dans le pool qui seront convertis en un groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-205">Repeat this for all databases in the pool which will be converted to an AlwaysOn Availability Group.</span></span>
    
5. <span data-ttu-id="87f98-206">Permet de paramétrer le Clustering avec basculement de Windows Server sur tous les serveurs de base de données qui feront partie du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-206">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="87f98-207">Sur chaque serveur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="87f98-207">On each server, do the following</span></span>
    
   - <span data-ttu-id="87f98-208">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="87f98-208">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="87f98-p126">Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="87f98-211">Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="87f98-211">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="87f98-212">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="87f98-212">Click **Install**.</span></span>
    
6. <span data-ttu-id="87f98-213">Validez la configuration de cluster.</span><span class="sxs-lookup"><span data-stu-id="87f98-213">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="87f98-214">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.</span><span class="sxs-lookup"><span data-stu-id="87f98-214">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="87f98-215">Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.</span><span class="sxs-lookup"><span data-stu-id="87f98-215">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="87f98-216">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-216">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-217">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.</span><span class="sxs-lookup"><span data-stu-id="87f98-217">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="87f98-218">Dans la zone**Résumé** , vérifiez les erreurs qui le rapports de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="87f98-218">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="87f98-219">Cliquez ensuite sur **Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="87f98-219">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="87f98-p128">L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="87f98-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="87f98-223">Créez le cluster.</span><span class="sxs-lookup"><span data-stu-id="87f98-223">Create the cluster.</span></span>
    
   - <span data-ttu-id="87f98-224">Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.</span><span class="sxs-lookup"><span data-stu-id="87f98-224">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="87f98-225">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-225">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-p129">Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-228">Dans la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-228">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-229">Après la création du cluster, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="87f98-229">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="87f98-p130">Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="87f98-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="87f98-232">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.</span><span class="sxs-lookup"><span data-stu-id="87f98-232">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="87f98-233">Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.</span><span class="sxs-lookup"><span data-stu-id="87f98-233">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="87f98-234">Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.</span><span class="sxs-lookup"><span data-stu-id="87f98-234">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="87f98-235">Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-235">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-236">Dans la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-236">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="87f98-237">Sur chaque serveur du cluster, activez Always On dans le Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="87f98-237">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="87f98-p131">Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server. </span><span class="sxs-lookup"><span data-stu-id="87f98-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="87f98-p132">Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="87f98-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="87f98-242">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="87f98-242">Create the availability group.</span></span>
    
    - <span data-ttu-id="87f98-243">Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="87f98-243">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="87f98-p133">Dans l’Explorateur d’objets, développez la **Haute disponibilité AlwaysOn**. Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p133">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="87f98-246">Si la page **Présentation** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-246">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="87f98-247">Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-247">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="87f98-248">Dans la page Sélectionner les bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-248">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="87f98-249">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="87f98-249">Then click **Next**.</span></span>
    
    <span data-ttu-id="87f98-250">N’incluez pas le **ReportServer**, **ReportServerTempDB**ou Chat permanente les bases de données dans le groupe de disponibilité AlwaysOn, comme ils ne sont pas pris en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="87f98-250">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="87f98-251">Vous pouvez inclure tous les autre Skype pour les bases de données Business Server dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-251">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="87f98-252">Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.</span><span class="sxs-lookup"><span data-stu-id="87f98-252">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="87f98-p136">Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="87f98-255">Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.</span><span class="sxs-lookup"><span data-stu-id="87f98-255">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
     - <span data-ttu-id="87f98-p137">Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="87f98-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="87f98-258">Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f98-258">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="87f98-p138">Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="87f98-p139">Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="87f98-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="87f98-263">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-263">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="87f98-264">Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="87f98-264">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="87f98-265">Créer un nouveau magasin spécifiant l’écouteur du groupe de disponibilité AlwaysOn, ainsi l’objet principal du miroir ancien comme nœud principal du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-265">Create a new store specifying the AlwaysOn Availability Group listener, and specifying the principal of the old mirror as the primary node of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="87f98-266">Ouvrez le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="87f98-266">Open Topology Builder.</span></span> <span data-ttu-id="87f98-267">Dans votre topologie, développez **Composants partagés**, cliquez avec le bouton droit sur **Magasins SQL Server**, puis cliquez sur **Nouveau magasin SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="87f98-267">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="87f98-268">Dans la page **Définir un nouveau magasin SQL**, activez tout d’abord la case à cocher **Paramètres de la haute disponibilité**, puis assurez-vous que Groupes de disponibilité SQL AlwaysOn s’affiche dans la zone déroulante.</span><span class="sxs-lookup"><span data-stu-id="87f98-268">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="87f98-269">Dans la zone **Nom de domaine complet de disponibilité SQL Server**, tapez le nom de domaine complet du port d’écoute que vous avez défini lors de la création du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="87f98-269">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="87f98-270">Dans la zone **Nom de domaine complet de SQL Server** , tapez le nom de domaine complet du nœud principal du groupe de disponibilité AlwaysOn, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f98-270">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span> <span data-ttu-id="87f98-271">Il doit s’agir du principal de l’ancien miroir pour ce magasin.</span><span class="sxs-lookup"><span data-stu-id="87f98-271">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="87f98-272">Associer le nouveau groupe de disponibilité AlwaysOn avec le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="87f98-272">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
    - <span data-ttu-id="87f98-273">Dans le Générateur de topologies, avec le bouton droit de la liste à associer au groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="87f98-273">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="87f98-274">**Associations**, dans la zone de **Stockage de SQL Server** , cliquez sur le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-274">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="87f98-275">Sélectionnez le groupe de même pour les autres bases de données dans le pool dans lequel vous souhaitez déplacer vers le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-275">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="87f98-276">Lorsque vous êtes sûr que toutes les bases de données nécessaires sont définies pour le groupe de disponibilité AlwaysOn, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f98-276">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
13. <span data-ttu-id="87f98-p143">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="87f98-280">Certaines étapes pour vous assurer que les noms d’accès SQL sur chacune des répliques dans le groupe de disponibilité AlwaysOn finale.</span><span class="sxs-lookup"><span data-stu-id="87f98-280">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="87f98-281">Ouvrir le Générateur de topologies, sélectionnez **Télécharger la topologie de déploiement existant**et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f98-281">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="87f98-282">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="87f98-282">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="87f98-283">Avec le bouton droit de la banque SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="87f98-283">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="87f98-284">Au bas de la page, dans la zone **Nom de domaine complet de SQL Server** , modifiez la valeur pour le nom de domaine complet de l’écouteur du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-284">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="87f98-p145">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="87f98-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="87f98-289">Ouvrez SQL Server Management Studio et accédez au groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-289">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="87f98-290">Faites-le basculer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="87f98-290">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="87f98-291">Ouvrez Skype pour Business Server Management Shell et entrez l’applet de commande suivante pour créer les connexions d’accès SQL sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="87f98-291">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="87f98-292">Répétez les deux étapes précédentes (basculer le groupe vers un réplica secondaire, puis utilisez `Install-CsDatabase -Update`) pour chaque réplica dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="87f98-292">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="87f98-293">Déploiement d’un groupe de disponibilité AlwaysOn sur un pool existant qui n’utilise pas la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="87f98-293">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="87f98-294"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="87f98-294"></span></span>

> [!NOTE]
> <span data-ttu-id="87f98-295">Si le pool que vous mettez à niveau un hôtes du groupe de disponibilité AlwaysOn la direction centrale stocke pour votre organisation, vous devez déplacer le CMS vers un autre pool avant de vous mettre à niveau ce pool.</span><span class="sxs-lookup"><span data-stu-id="87f98-295">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="87f98-296">Utilisez l’applet de commande Move-CsManagementServer pour déplacer le pool.</span><span class="sxs-lookup"><span data-stu-id="87f98-296">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="87f98-297">Si vous ne disposez pas d’un autre pool de votre organisation, vous pouvez déployer un serveur Standard Edition server temporairement et déplacer le serveur CMS à ce serveur avant de vous mettre à niveau votre pool pour le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-297">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="87f98-298">Permet de paramétrer le Clustering avec basculement de Windows Server sur tous les serveurs de base de données qui feront partie du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-298">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="87f98-299">Sur chaque serveur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="87f98-299">On each server, do the following</span></span>
    
   - <span data-ttu-id="87f98-300">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="87f98-300">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="87f98-p149">Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="87f98-303">Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="87f98-303">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="87f98-304">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="87f98-304">Click **Install**.</span></span>
    
2. <span data-ttu-id="87f98-305">Validez la configuration de cluster.</span><span class="sxs-lookup"><span data-stu-id="87f98-305">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="87f98-306">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.</span><span class="sxs-lookup"><span data-stu-id="87f98-306">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="87f98-307">Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.</span><span class="sxs-lookup"><span data-stu-id="87f98-307">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="87f98-308">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-308">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-309">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.</span><span class="sxs-lookup"><span data-stu-id="87f98-309">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="87f98-310">Dans la zone**Résumé** , vérifiez les erreurs qui le rapports de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="87f98-310">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="87f98-311">Cliquez ensuite sur **Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="87f98-311">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="87f98-p151">L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="87f98-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="87f98-315">Créez le cluster.</span><span class="sxs-lookup"><span data-stu-id="87f98-315">Create the cluster.</span></span>
    
   - <span data-ttu-id="87f98-316">Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.</span><span class="sxs-lookup"><span data-stu-id="87f98-316">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="87f98-317">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-317">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-p152">Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-320">Dans la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-320">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-321">Après la création du cluster, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="87f98-321">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="87f98-p153">Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="87f98-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="87f98-324">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.</span><span class="sxs-lookup"><span data-stu-id="87f98-324">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="87f98-325">Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.</span><span class="sxs-lookup"><span data-stu-id="87f98-325">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="87f98-326">Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.</span><span class="sxs-lookup"><span data-stu-id="87f98-326">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="87f98-327">Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-327">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-328">Dans la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-328">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="87f98-329">Sur chaque serveur du cluster, activez Always On dans le Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="87f98-329">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="87f98-p154">Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server. </span><span class="sxs-lookup"><span data-stu-id="87f98-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="87f98-p155">Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="87f98-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="87f98-334">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="87f98-334">Create the availability group.</span></span>
    
   - <span data-ttu-id="87f98-335">Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="87f98-335">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="87f98-p156">Dans l’Explorateur d’objets, développez la **Haute disponibilité AlwaysOn**. Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p156">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="87f98-338">Si la page **Présentation** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-338">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-339">Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-339">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-340">Dans la page Sélectionner les bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-340">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="87f98-341">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="87f98-341">Then click **Next**.</span></span>
    
    <span data-ttu-id="87f98-342">N’incluez pas le **ReportServer**, **ReportServerTempDB**ou Chat permanente les bases de données dans le groupe de disponibilité AlwaysOn, comme ils ne sont pas pris en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="87f98-342">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="87f98-343">Vous pouvez inclure tous les autre Skype pour les bases de données Business Server dans le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-343">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="87f98-344">Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.</span><span class="sxs-lookup"><span data-stu-id="87f98-344">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="87f98-p159">Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="87f98-347">Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.</span><span class="sxs-lookup"><span data-stu-id="87f98-347">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="87f98-p160">Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="87f98-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="87f98-350">Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f98-350">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="87f98-p161">Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="87f98-p162">Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="87f98-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="87f98-355">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-355">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="87f98-356">Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="87f98-356">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="87f98-357">Créer une nouvelle banque de spécification de l’écouteur du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-357">Create a new store specifying the AlwaysOn Availability Group listener.</span></span>
    
   - <span data-ttu-id="87f98-358">Ouvrez le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="87f98-358">Open Topology Builder.</span></span> <span data-ttu-id="87f98-359">Dans votre topologie, développez **Composants partagés**, cliquez avec le bouton droit sur **Magasins SQL Server**, puis cliquez sur **Nouveau magasin SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="87f98-359">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="87f98-360">Dans la page **Définir un nouveau magasin SQL**, activez tout d’abord la case à cocher **Paramètres de la haute disponibilité**, puis assurez-vous que Groupes de disponibilité SQL AlwaysOn s’affiche dans la zone déroulante.</span><span class="sxs-lookup"><span data-stu-id="87f98-360">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="87f98-361">Dans la zone **Nom de domaine complet de disponibilité SQL Server**, tapez le nom de domaine complet du port d’écoute que vous avez défini lors de la création du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="87f98-361">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="87f98-362">Dans la zone **Nom de domaine complet de SQL Server** , tapez le nom de domaine complet du nœud principal du groupe de disponibilité AlwaysOn, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f98-362">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span>
    
8. <span data-ttu-id="87f98-363">Associer le nouveau groupe de disponibilité AlwaysOn avec le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="87f98-363">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="87f98-364">Dans le Générateur de topologies, avec le bouton droit de la liste à associer au groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="87f98-364">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="87f98-365">**Associations**, dans la zone de **Stockage de SQL Server** , cliquez sur le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-365">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="87f98-366">Sélectionnez le groupe de même pour les autres bases de données dans le pool dans lequel vous souhaitez déplacer vers le groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-366">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="87f98-367">Lorsque vous êtes sûr que toutes les bases de données nécessaires sont définies pour le groupe de disponibilité AlwaysOn, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f98-367">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
9. <span data-ttu-id="87f98-p165">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87f98-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="87f98-371">Certaines étapes pour vous assurer que les noms d’accès SQL sur chacune des répliques dans le groupe de disponibilité AlwaysOn finale.</span><span class="sxs-lookup"><span data-stu-id="87f98-371">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="87f98-372">Ouvrir le Générateur de topologies, sélectionnez **Télécharger la topologie de déploiement existant**et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f98-372">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="87f98-373">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="87f98-373">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="87f98-374">Avec le bouton droit de la banque SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur ** Modifier propriétés **.</span><span class="sxs-lookup"><span data-stu-id="87f98-374">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="87f98-375">Au bas de la page, dans la zone **Nom de domaine complet de SQL Server** , modifiez la valeur pour le nom de domaine complet de l’écouteur du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-375">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="87f98-p167">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="87f98-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="87f98-380">Ouvrez SQL Server Management Studio et accédez au groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="87f98-380">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="87f98-381">Faites-le basculer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="87f98-381">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="87f98-382">Ouvrez Skype pour Business Server Management Shell et entrez l’applet de commande suivante pour créer les connexions d’accès SQL sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="87f98-382">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
     ```
     Install-CsDatabase -Update
     ```

     - <span data-ttu-id="87f98-383">Répétez les deux étapes précédentes (basculer le groupe vers un réplica secondaire, puis utilisez `Install-CsDatabase -Update`) pour chaque réplica dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="87f98-383">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    

