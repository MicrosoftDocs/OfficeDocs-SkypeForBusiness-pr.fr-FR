---
title: Déploiement d’un groupe toujours disponible sur un serveur principal dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Déploiement (installation) d’un groupe toujours disponible dans le déploiement de Skype entreprise Server.
ms.openlocfilehash: d69e370716af2b23c57ad463ea7f4651ea0ea89a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798271"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="c52dd-103">Déploiement d’un groupe toujours disponible sur un serveur principal dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="c52dd-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="c52dd-104">Déploiement (installation) d’un groupe toujours disponible sur le déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c52dd-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="c52dd-105">Le mode de déploiement d’un programme AG dépend du mode de déploiement dans un nouveau pool, d’un pool existant qui utilise la mise en miroir ou d’un pool existant qui n’est actuellement pas disponible pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="c52dd-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c52dd-106">L’utilisation de la fonction AG avec un rôle serveur de chat permanent n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c52dd-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="c52dd-107">Déploiement d’un groupe toujours disponible sur une nouvelle liste frontale</span><span class="sxs-lookup"><span data-stu-id="c52dd-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="c52dd-108">Déployer un groupe toujours disponible sur un pool existant qui utilise la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="c52dd-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="c52dd-109">Déployer un groupe toujours disponible sur un pool existant qui n’utilise pas la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="c52dd-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="c52dd-110">Déploiement d’un groupe toujours disponible sur une nouvelle liste frontale</span><span class="sxs-lookup"><span data-stu-id="c52dd-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="c52dd-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="c52dd-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="c52dd-112">Activez la fonctionnalité de mise en cluster de basculement sur tous les serveurs de base de données qui feront partie de la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="c52dd-113">Sur chaque serveur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c52dd-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="c52dd-114">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="c52dd-p102">Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="c52dd-117">Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="c52dd-118">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="c52dd-119">Validez la configuration de cluster.</span><span class="sxs-lookup"><span data-stu-id="c52dd-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="c52dd-120">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="c52dd-121">Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="c52dd-122">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-123">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="c52dd-p103">Dans la boîte **Résumé**, vérifiez les erreurs signalées par l’Assistant, puis cliquez sur **Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p103">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="c52dd-p104">L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="c52dd-129">Créez le cluster de basculement de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="c52dd-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="c52dd-130">Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="c52dd-131">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-p105">Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-134">Dans la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-135">Après la création du cluster, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="c52dd-p106">Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c52dd-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="c52dd-138">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="c52dd-139">Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="c52dd-140">Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="c52dd-141">Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-142">Dans la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="c52dd-143">Sur chaque serveur dans le cluster, activez la fonction AG dans le gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c52dd-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="c52dd-p107">Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server. </span><span class="sxs-lookup"><span data-stu-id="c52dd-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="c52dd-p108">Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="c52dd-148">Utilisez le générateur de topologie pour créer le pool frontal, comme décrit dans la rubrique [créer et publier une nouvelle topologie dans Skype entreprise Server](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="c52dd-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="c52dd-149">Le cas échéant, spécifiez la AG comme magasin SQL pour le pool.</span><span class="sxs-lookup"><span data-stu-id="c52dd-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="c52dd-150">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c52dd-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="c52dd-151">Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c52dd-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="c52dd-152">Dans l’Explorateur d’objets, développez le dossier **toujours à haute disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="c52dd-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="c52dd-153">Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="c52dd-154">Si la page **Présentation** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-155">Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-156">Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous voulez inclure dans le groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c52dd-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="c52dd-157">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="c52dd-158">N’incluez pas les bases de données de chat **reportserver**, **ReportServerTempDB**ou persistante dans le groupe disponibilité AlwaysOn, car ces informations ne sont pas prises en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="c52dd-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="c52dd-159">Vous pouvez inclure les autres bases de données Skype entreprise Server dans le groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c52dd-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="c52dd-160">Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.</span><span class="sxs-lookup"><span data-stu-id="c52dd-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="c52dd-p113">Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p113">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="c52dd-163">Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.</span><span class="sxs-lookup"><span data-stu-id="c52dd-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="c52dd-p114">Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="c52dd-p114">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="c52dd-166">Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="c52dd-p115">Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p115">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="c52dd-p116">Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p116">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="c52dd-171">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-172">Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="c52dd-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="c52dd-173">Après le déploiement du pool et de la AG, réalisez quelques étapes finales pour vous assurer que les connexions SQL se trouvent sur chacun des réplicas du groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c52dd-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="c52dd-174">Ouvrez le générateur de topologie, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="c52dd-175">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="c52dd-176">Cliquez avec le bouton droit sur le magasin SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="c52dd-177">En bas de la page, dans la zone **FQDN SQL Server** , remplacez la valeur par le nom de domaine complet (FQDN) de l’écouteur de la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="c52dd-p118">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="c52dd-182">Ouvrez SQL Server Management Studio, puis accédez à la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="c52dd-183">Faites-le basculer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="c52dd-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="c52dd-184">Ouvrez Skype entreprise Server Management Shell et tapez l’applet de commande suivante pour créer les connexions SQL sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="c52dd-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="c52dd-185">Répétez les deux étapes précédentes (basculez le groupe vers un réplica secondaire, puis `Install-CsDatabase -Update`utilisez) pour chaque réplica du groupe.</span><span class="sxs-lookup"><span data-stu-id="c52dd-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="c52dd-186">Déployer un groupe toujours disponible sur un pool existant qui utilise la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="c52dd-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="c52dd-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="c52dd-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="c52dd-188">Si le pool sur lequel vous effectuez la mise à niveau vers un serveur AG héberge le magasin de gestion central de votre organisation, vous devez d’abord déplacer le MCG vers un autre pool avant de mettre à niveau ce pool.</span><span class="sxs-lookup"><span data-stu-id="c52dd-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="c52dd-189">Utilisez l’applet de commande Move-CsManagementServer pour déplacer le pool.</span><span class="sxs-lookup"><span data-stu-id="c52dd-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="c52dd-190">Si vous n’avez pas d’autre liste au sein de votre organisation, vous pouvez déployer temporairement un serveur Standard Edition et déplacer le CMS vers ce serveur avant de mettre à niveau votre groupe vers la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="c52dd-191">Basculez toutes les données du miroir vers le nœud principal en ouvrant Skype entreprise Server Management Shell et en tapant l’applet de commande suivante.</span><span class="sxs-lookup"><span data-stu-id="c52dd-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="c52dd-p121">Répétez cette applet de commande pour chaque type de base de données dans le pool. Vous pouvez utiliser l’applet de commande ci-dessous pour trouver tous les types de bases de données stockées dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="c52dd-194">Utilisez le générateur de topologie pour supprimer la mise en miroir de la base de données du pool.</span><span class="sxs-lookup"><span data-stu-id="c52dd-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="c52dd-195">Ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c52dd-195">Open Topology Builder.</span></span> <span data-ttu-id="c52dd-196">Dans votre topologie, développez **Pools frontaux Entreprise Edition**, cliquez avec le bouton droit sur le nom du pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="c52dd-197">Pour chaque type de magasin SQL dans le pool, désactivez la case à cocher **Activer la mise en miroir du magasin SQL**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="c52dd-p123">Publiez la topologie modifiée. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="c52dd-201">Utilisez SQL Server Management Studio afin de rompre la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="c52dd-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="c52dd-p124">Ouvrez SQL Server Management Studio, accédez à vos bases de données, cliquez avec le bouton droit sur **Tâches** et cliquez sur **Miroir**. Cliquez ensuite sur **Supprimer la mise en miroir** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="c52dd-204">Répétez cette opération pour toutes les bases de données de la liste de ressources partagées qui seront converties en AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="c52dd-205">Configurez la fonctionnalité de clustering de basculement sur tous les serveurs de base de données qui feront partie de la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="c52dd-206">Sur chaque serveur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c52dd-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="c52dd-207">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="c52dd-p126">Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="c52dd-210">Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="c52dd-211">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="c52dd-212">Validez la configuration de cluster.</span><span class="sxs-lookup"><span data-stu-id="c52dd-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="c52dd-213">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="c52dd-214">Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="c52dd-215">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-216">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="c52dd-p127">Dans la boîte **Résumé**, vérifiez les erreurs signalées par l’Assistant, puis cliquez sur **Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p127">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="c52dd-p128">L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="c52dd-222">Créez le cluster Windows Server Failover.</span><span class="sxs-lookup"><span data-stu-id="c52dd-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="c52dd-223">Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="c52dd-224">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-p129">Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-227">Dans la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-228">Après la création du cluster, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="c52dd-p130">Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c52dd-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="c52dd-231">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="c52dd-232">Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="c52dd-233">Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="c52dd-234">Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-235">Dans la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="c52dd-236">Sur chaque serveur dans le cluster, activez la fonction AG dans le gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c52dd-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="c52dd-p131">Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server. </span><span class="sxs-lookup"><span data-stu-id="c52dd-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="c52dd-p132">Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="c52dd-241">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c52dd-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="c52dd-242">Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c52dd-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="c52dd-243">Dans l’Explorateur d’objets, développez le dossier **toujours à haute disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="c52dd-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="c52dd-244">Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="c52dd-245">Si la page **Présentation** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="c52dd-246">Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="c52dd-247">Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous voulez inclure dans le groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c52dd-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="c52dd-248">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="c52dd-249">N’incluez pas les bases de données de chat **reportserver**, **ReportServerTempDB**ou persistante dans le groupe disponibilité AlwaysOn, car ces informations ne sont pas prises en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="c52dd-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="c52dd-250">Vous pouvez inclure les autres bases de données Skype entreprise Server dans le groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c52dd-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="c52dd-251">Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.</span><span class="sxs-lookup"><span data-stu-id="c52dd-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="c52dd-p136">Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="c52dd-254">Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.</span><span class="sxs-lookup"><span data-stu-id="c52dd-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="c52dd-p137">Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="c52dd-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="c52dd-257">Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="c52dd-p138">Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="c52dd-p139">Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="c52dd-262">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="c52dd-263">Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="c52dd-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="c52dd-264">Créez une nouvelle banque spécifiant l’écouteur AG et spécifiez le principal de l’ancien miroir en tant que nœud principal de la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="c52dd-265">Ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c52dd-265">Open Topology Builder.</span></span> <span data-ttu-id="c52dd-266">Dans votre topologie, développez **Composants partagés**, cliquez avec le bouton droit sur **Magasins SQL Server**, puis cliquez sur **Nouveau magasin SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="c52dd-267">Dans la page **Définir un nouveau magasin SQL**, activez tout d’abord la case à cocher **Paramètres de la haute disponibilité**, puis assurez-vous que Groupes de disponibilité SQL AlwaysOn s’affiche dans la zone déroulante.</span><span class="sxs-lookup"><span data-stu-id="c52dd-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="c52dd-268">Dans la zone **Nom de domaine complet de disponibilité SQL Server**, tapez le nom de domaine complet du port d’écoute que vous avez défini lors de la création du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c52dd-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="c52dd-269">Dans la zone **FQDN SQL Server** , entrez le nom de domaine complet (FQDN) du nœud principal de la AG, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="c52dd-270">Il doit s’agir du principal de l’ancien miroir pour ce magasin.</span><span class="sxs-lookup"><span data-stu-id="c52dd-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="c52dd-271">Associez le nouveau AG au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="c52dd-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="c52dd-272">Dans le générateur de topologie, cliquez avec le bouton droit sur le pool à associer à la AG, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="c52dd-273">Sous **associations**, dans la zone **SQL Server Store** , sélectionnez AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="c52dd-274">Sélectionnez le même groupe pour toutes les autres bases de données de la liste que vous voulez déplacer vers la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="c52dd-275">Lorsque vous êtes certain que toutes les bases de données nécessaires sont définies sur AG, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="c52dd-276">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="c52dd-276">Publish the topology.</span></span> <span data-ttu-id="c52dd-277">Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="c52dd-278">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="c52dd-279">Effectuez quelques étapes finales pour vous assurer que les connexions SQL se trouvent sur chacun des réplicas du groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c52dd-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="c52dd-280">Ouvrez le générateur de topologie, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="c52dd-281">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="c52dd-282">Cliquez avec le bouton droit sur le magasin SQL du nouveau AG, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="c52dd-283">En bas de la page, dans la zone **FQDN SQL Server** , remplacez la valeur par le nom de domaine complet (FQDN) de l’écouteur de la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="c52dd-p145">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="c52dd-288">Ouvrez SQL Server Management Studio, puis accédez à la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="c52dd-289">Faites-le basculer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="c52dd-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="c52dd-290">Ouvrez Skype entreprise Server Management Shell et tapez l’applet de commande suivante pour créer les connexions SQL sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="c52dd-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="c52dd-291">Répétez les deux étapes précédentes (basculez le groupe vers un réplica secondaire, puis `Install-CsDatabase -Update`utilisez) pour chaque réplica du groupe.</span><span class="sxs-lookup"><span data-stu-id="c52dd-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="c52dd-292">Déployer un groupe toujours disponible sur un pool existant qui n’utilise pas la mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="c52dd-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="c52dd-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="c52dd-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="c52dd-294">Si le pool sur lequel vous effectuez la mise à niveau vers un serveur AG héberge le magasin de gestion central de votre organisation, vous devez d’abord déplacer le MCG vers un autre pool avant de mettre à niveau ce pool.</span><span class="sxs-lookup"><span data-stu-id="c52dd-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="c52dd-295">Utilisez l’applet de commande Move-CsManagementServer pour déplacer le pool.</span><span class="sxs-lookup"><span data-stu-id="c52dd-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="c52dd-296">Si vous n’avez pas d’autre liste au sein de votre organisation, vous pouvez déployer temporairement un serveur Standard Edition et déplacer le CMS vers ce serveur avant de mettre à niveau votre groupe vers la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="c52dd-297">Configurez la fonctionnalité de clustering de basculement sur tous les serveurs de base de données qui feront partie de la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="c52dd-298">Sur chaque serveur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c52dd-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="c52dd-299">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="c52dd-p149">Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="c52dd-302">Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="c52dd-303">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="c52dd-304">Validez la configuration de cluster.</span><span class="sxs-lookup"><span data-stu-id="c52dd-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="c52dd-305">Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="c52dd-306">Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="c52dd-307">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-308">Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="c52dd-p150">Dans la boîte **Résumé**, vérifiez les erreurs signalées par l’Assistant, puis cliquez sur **Terminer** pour terminer la validation.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p150">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="c52dd-p151">L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="c52dd-314">Créez le cluster de basculement de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="c52dd-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="c52dd-315">Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="c52dd-316">Dans la page **Avant de commencer**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-p152">Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-319">Dans la page Confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-320">Après la création du cluster, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="c52dd-p153">Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c52dd-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="c52dd-323">Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="c52dd-324">Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="c52dd-325">Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="c52dd-326">Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-327">Dans la page **Confirmation**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="c52dd-328">Sur chaque serveur du cluster, activez AG dans le gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c52dd-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="c52dd-p154">Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server. </span><span class="sxs-lookup"><span data-stu-id="c52dd-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="c52dd-p155">Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="c52dd-333">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c52dd-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="c52dd-334">Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c52dd-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="c52dd-335">Dans l’Explorateur d’objets, développez le dossier **toujours à haute disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="c52dd-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="c52dd-336">Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="c52dd-337">Si la page **Présentation** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-338">Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-339">Dans la page Sélectionner une base de données, sélectionnez les bases de données que vous voulez inclure dans le AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="c52dd-340">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="c52dd-341">N’incluez pas les bases de données de chat **reportserver**, **ReportServerTempDB**ou permanentes dans la AG, car elles ne sont pas prises en charge dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="c52dd-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="c52dd-342">Vous pouvez inclure toutes les autres bases de données Skype entreprise Server du AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="c52dd-343">Dans la page **spécifier des réplicas** , cliquez sur l’onglet **fac-similés** . Cliquez ensuite sur le bouton **Ajouter des réplicas** , puis connectez-vous aux autres instances SQL que vous avez jointes en tant que nœuds du WSFC.</span><span class="sxs-lookup"><span data-stu-id="c52dd-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="c52dd-p159">Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="c52dd-346">Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.</span><span class="sxs-lookup"><span data-stu-id="c52dd-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="c52dd-p160">Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).</span><span class="sxs-lookup"><span data-stu-id="c52dd-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="c52dd-349">Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="c52dd-p161">Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="c52dd-p162">Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="c52dd-354">Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="c52dd-355">Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="c52dd-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="c52dd-356">Créez une nouvelle banque spécifiant l’écouteur AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="c52dd-357">Ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c52dd-357">Open Topology Builder.</span></span> <span data-ttu-id="c52dd-358">Dans votre topologie, développez **Composants partagés**, cliquez avec le bouton droit sur **Magasins SQL Server**, puis cliquez sur **Nouveau magasin SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="c52dd-359">Dans la page **Définir un nouveau magasin SQL**, activez tout d’abord la case à cocher **Paramètres de la haute disponibilité**, puis assurez-vous que Groupes de disponibilité SQL AlwaysOn s’affiche dans la zone déroulante.</span><span class="sxs-lookup"><span data-stu-id="c52dd-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="c52dd-360">Dans la zone **Nom de domaine complet de disponibilité SQL Server**, tapez le nom de domaine complet du port d’écoute que vous avez défini lors de la création du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c52dd-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="c52dd-361">Dans la zone **FQDN SQL Server** , entrez le nom de domaine complet (FQDN) du nœud principal de la AG, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="c52dd-362">Associez le nouveau groupe toujours disponible au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="c52dd-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="c52dd-363">Dans le générateur de topologie, cliquez avec le bouton droit sur le pool à associer à la AG, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="c52dd-364">Sous **associations**, dans la zone **SQL Server Store** , sélectionnez AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="c52dd-365">Sélectionnez le même groupe pour toutes les autres bases de données de la liste que vous voulez déplacer vers la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="c52dd-366">Lorsque vous êtes certain que toutes les bases de données nécessaires sont définies sur AG, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="c52dd-367">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="c52dd-367">Publish the topology.</span></span> <span data-ttu-id="c52dd-368">Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="c52dd-369">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="c52dd-370">Effectuez quelques étapes finales pour vous assurer que les connexions SQL se trouvent sur chacun des réplicas du AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="c52dd-371">Ouvrez le générateur de topologie, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="c52dd-372">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="c52dd-373">Cliquez avec le bouton droit sur le magasin SQL du nouveau AG, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c52dd-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="c52dd-374">En bas de la page, dans la zone **FQDN SQL Server** , remplacez la valeur par le nom de domaine complet (FQDN) de l’écouteur de la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="c52dd-p167">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="c52dd-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="c52dd-379">Ouvrez SQL Server Management Studio, puis accédez à la AG.</span><span class="sxs-lookup"><span data-stu-id="c52dd-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="c52dd-380">Faites-le basculer vers un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="c52dd-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="c52dd-381">Ouvrez Skype entreprise Server Management Shell et tapez l’applet de commande suivante pour créer les connexions SQL sur ce réplica :</span><span class="sxs-lookup"><span data-stu-id="c52dd-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="c52dd-382">Répétez les deux étapes précédentes (basculez le groupe vers un réplica secondaire, puis `Install-CsDatabase -Update`utilisez) pour chaque réplica du groupe.</span><span class="sxs-lookup"><span data-stu-id="c52dd-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
