---
title: Déployer la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Pour pouvoir déployer la mise en miroir SQL, vos serveurs doivent exécuter au moins SQL Server 2008 R2. Cette version doit s’exécuter sur tous les serveurs impliqués : principal, miroir et témoin. Pour plus d’informations, consultez Cumulative mise à jour de package 9 pour SQL Server 2008 Service Pack 1.'
ms.openlocfilehash: 8de94fc0e15b1d851b43b386b476abfa776fad2d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="e1031-105">Déployer la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e1031-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>
 

<span data-ttu-id="e1031-106">Pour pouvoir déployer la mise en miroir SQL, vos serveurs doivent exécuter au moins SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="e1031-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="e1031-107">Cette version doit s’exécuter sur tous les serveurs impliqués : principal, miroir et témoin.</span><span class="sxs-lookup"><span data-stu-id="e1031-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="e1031-108">Pour plus d’informations, reportez-vous à la section [9 pour SQL Server 2008 Service Pack 1 de package de mises à jour cumulatives ](http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span><span class="sxs-lookup"><span data-stu-id="e1031-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1 ](http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>
  
<span data-ttu-id="e1031-109">En général, la configuration de la mise en miroir SQL entre deux serveurs principaux avec un témoin exige ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e1031-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="e1031-110">Version du serveur principal de SQL Server doit prendre en charge la mise en miroir de SQL.</span><span class="sxs-lookup"><span data-stu-id="e1031-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="e1031-111">Le principal, le miroir et le témoin (s’il est déployé) doivent disposer de la même version de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e1031-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="e1031-p103">Le principal et le miroir doivent disposer de la même édition de SQL Server. Le témoin peut en avoir une différente.</span><span class="sxs-lookup"><span data-stu-id="e1031-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="e1031-114">Pour SQL recommandées en ce qui concerne les versions SQL sont pris en charge pour un rôle témoin, consultez [Témoin de la mise en miroir de base de données](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span><span class="sxs-lookup"><span data-stu-id="e1031-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span></span>
  
<span data-ttu-id="e1031-115">Vous utilisez le Générateur de topologies pour déployer la mise en miroir de SQL.</span><span class="sxs-lookup"><span data-stu-id="e1031-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="e1031-116">Vous sélectionnez une option dans le Générateur de topologies pour mettre en miroir des bases de données, et le Générateur de topologies définit la mise en miroir (y compris le paramétrage d’un témoin, si vous le souhaitez) lorsque vous publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="e1031-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="e1031-117">Notez que vous configurez ou supprimez le témoin en même temps que le miroir.</span><span class="sxs-lookup"><span data-stu-id="e1031-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="e1031-118">Il n’existe pas de commande distincte pour déployer ou supprimer uniquement un témoin.</span><span class="sxs-lookup"><span data-stu-id="e1031-118">There is no separate command to deploy or remove only a witness.</span></span>
  
<span data-ttu-id="e1031-119">Pour configurer la mise en miroir des serveurs, vous devez d’abord configurer les autorisations de base de données SQL correctement.</span><span class="sxs-lookup"><span data-stu-id="e1031-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="e1031-120">Pour plus d’informations, consultez [Définir des comptes de connexion pour la mise en miroir de base de données ou groupes de disponibilité AlwaysOn (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span><span class="sxs-lookup"><span data-stu-id="e1031-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="e1031-p106">Avec la mise en miroir SQL, le mode de récupération de la base de données a toujours la valeur **Complète**, ce qui signifie que vous devez surveiller de près la taille du journal des transactions et sauvegarder les journaux des transactions de manière régulière afin d’éviter toute insuffisance d’espace disque sur les serveurs principaux. La fréquence des sauvegardes des journaux des transactions dépend de la vitesse à laquelle leur taille augmente, laquelle dépend à son tour des transactions de base de données induites par les activités des utilisateurs sur le pool frontal. Nous vous recommandons d’estimer l’accroissement des journaux des transactions pour la charge de travail de votre déploiement afin de procéder à une planification en conséquence. Les articles suivants fournissent des informations supplémentaires sur la gestion des journaux et sauvegardes SQL :</span><span class="sxs-lookup"><span data-stu-id="e1031-p106">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
- [<span data-ttu-id="e1031-125">Modèles de récupération de base de données</span><span class="sxs-lookup"><span data-stu-id="e1031-125">Database recovery models</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268446)
    
- [<span data-ttu-id="e1031-126">Présentation de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="e1031-126">Backup overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268449)
    
- [<span data-ttu-id="e1031-127">Journal de transactions de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="e1031-127">Backup transaction log</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268452)
    
<span data-ttu-id="e1031-128">Avec la mise en miroir SQL, vous pouvez configurer la topologie pour la mise en miroir lorsque vous créez les pools ou après les avoir déjà créés.</span><span class="sxs-lookup"><span data-stu-id="e1031-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e1031-129">À l’aide du Générateur de topologies ou des applets de commande pour installer et supprimer SQL mise en miroir est prise en charge uniquement primaire, miroir et serveurs de rappel (le cas échéant) appartiennent au même domaine.</span><span class="sxs-lookup"><span data-stu-id="e1031-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="e1031-130">Si vous voulez configurer la mise en miroir SQL entre des serveurs de différents domaines, reportez-vous à votre documentation SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e1031-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e1031-131">Dès lors que vous apportez une modification à une relation de mise en miroir d’une base de données principale, vous devez redémarrer tous les serveurs frontaux du pool. </span><span class="sxs-lookup"><span data-stu-id="e1031-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="e1031-132">> Pour une modification de la mise en miroir, (comme la modification de l’emplacement d’un miroir), vous devez utiliser le Générateur de topologies pour effectuer ces trois étapes :</span><span class="sxs-lookup"><span data-stu-id="e1031-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
  
1. <span data-ttu-id="e1031-133">Supprimez la mise en miroir de l’ancien serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="e1031-133">Remove mirroring from the old mirror server.</span></span>
    
2. <span data-ttu-id="e1031-134">Ajoutez la mise en miroir au nouveau serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="e1031-134">Add mirroring to the new mirror server.</span></span>
    
3. <span data-ttu-id="e1031-135">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="e1031-135">Publish the topology.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e1031-136">Un partage de fichiers doit être créé pour pouvoir y écrire les fichiers miroir, et le service sous lequel SQL Server et SQL Agent s’exécutent doit disposer d’un accès en lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="e1031-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="e1031-137">Si le service SQL Server s’exécute sous le contexte de Service réseau, vous pouvez ajouter \<domaine\>\\< SQLSERVERNAME\>$ de l’entité de sécurité et serveurs SQL de mise en miroir pour les autorisations de partage.</span><span class="sxs-lookup"><span data-stu-id="e1031-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="e1031-138">Le signe $ est important afin d’identifier qu’il s’agit d’un compte ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e1031-138">The $ is important to identify that this is a computer account.</span></span> 
  
## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="e1031-139">Pour configurer la mise en miroir de SQL lors de la création d’un pool dans le Générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="e1031-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="e1031-140">Dans la page **Définir le magasin SQL**, cliquez sur **Nouveau** en regard de la zone **Magasin SQL**. </span><span class="sxs-lookup"><span data-stu-id="e1031-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>
    
2. <span data-ttu-id="e1031-141">Dans la page **Définir un nouveau magasin SQL**, spécifiez le magasin principal, sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (5022 par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1031-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>
    
3. <span data-ttu-id="e1031-142">De retour dans la page **Définir le magasin SQL**, sélectionnez **Activer la mise en miroir du magasin SQL**. </span><span class="sxs-lookup"><span data-stu-id="e1031-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span> 
    
4. <span data-ttu-id="e1031-p110">Dans la page **Définir un nouveau magasin SQL**, spécifiez le magasin SQL à utiliser en tant que miroir. Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port (5022 par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1031-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>
    
5. <span data-ttu-id="e1031-145">Si vous voulez un témoin pour ce miroir, procédez comme suit : </span><span class="sxs-lookup"><span data-stu-id="e1031-145">If you want a witness for this mirror, do the following:</span></span> 
    
    <span data-ttu-id="e1031-146">a.</span><span class="sxs-lookup"><span data-stu-id="e1031-146">a.</span></span> <span data-ttu-id="e1031-147">Sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**. </span><span class="sxs-lookup"><span data-stu-id="e1031-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span> 
    
    <span data-ttu-id="e1031-148">b.</span><span class="sxs-lookup"><span data-stu-id="e1031-148">b.</span></span> <span data-ttu-id="e1031-149">Dans la page **Définir le magasin SQL**, sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**, puis spécifiez le magasin SQL à utiliser en tant que témoin. </span><span class="sxs-lookup"><span data-stu-id="e1031-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span> 
    
    <span data-ttu-id="e1031-150">c.</span><span class="sxs-lookup"><span data-stu-id="e1031-150">c.</span></span> <span data-ttu-id="e1031-151">Spécifiez le numéro de port (7022 par défaut) et cliquez sur **OK**. </span><span class="sxs-lookup"><span data-stu-id="e1031-151">Specify the port number (the default is 7022) and click **OK**.</span></span> 
    
6. <span data-ttu-id="e1031-152">Après avoir fini définissant votre pool frontal et tous les autres rôles dans votre topologie, d’utiliser le Générateur de topologies pour publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="e1031-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="e1031-153">Lorsque la topologie est publiée, si le pool frontal qui héberge le magasin Central de gestion a la mise en miroir de SQL activé, vous verrez une option permettant de créer les deux principales et la mise en miroir de bases de données de banque d’informations SQL.</span><span class="sxs-lookup"><span data-stu-id="e1031-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="e1031-154">Cliquez sur **Paramètres**, puis tapez le chemin d’accès à utiliser en tant que partage de fichiers pour la sauvegarde de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="e1031-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="e1031-p115">Cliquez sur **OK**, puis sur **Suivant ** pour créer les bases de données et publier la topologie. Le miroir et le témoin (s’il est spécifié) sont déployés.</span><span class="sxs-lookup"><span data-stu-id="e1031-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>
    
<span data-ttu-id="e1031-157">Vous pouvez utiliser le Générateur de topologies pour modifier les propriétés d’un pool déjà existant pour permettre la mise en miroir de SQL.</span><span class="sxs-lookup"><span data-stu-id="e1031-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span> 
  
## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="e1031-158">Pour ajouter la mise en miroir SQL à un pool frontal existant dans le Générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="e1031-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="e1031-159">Dans le Générateur de topologies, avec le bouton droit de la liste et puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e1031-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="e1031-160">Sélectionnez **Activer la mise en miroir du magasin SQL**, puis cliquez sur **Nouveau ** en regard de **Magasin SQL de mise en miroir**. </span><span class="sxs-lookup"><span data-stu-id="e1031-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span> 
    
3. <span data-ttu-id="e1031-161">Spécifiez le magasin SQL à utiliser en tant que miroir. </span><span class="sxs-lookup"><span data-stu-id="e1031-161">Specify the SQL store that you want to use as the mirror.</span></span> 
    
4. <span data-ttu-id="e1031-162">Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (5022 par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1031-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>
    
5. <span data-ttu-id="e1031-163">Si vous voulez configurer un témoin, sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**, puis cliquez sur **Nouveau**. </span><span class="sxs-lookup"><span data-stu-id="e1031-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span> 
    
6. <span data-ttu-id="e1031-164">Spécifiez le magasin SQL à utiliser en tant que témoin. </span><span class="sxs-lookup"><span data-stu-id="e1031-164">Specify the SQL store that you want to use as the witness.</span></span> 
    
7. <span data-ttu-id="e1031-165">Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (7022 par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1031-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>
    
8. <span data-ttu-id="e1031-166">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1031-166">Click **OK**.</span></span>
    
9. <span data-ttu-id="e1031-p116">Publiez la topologie. Après cela, vous êtes invité à installer la base de données. </span><span class="sxs-lookup"><span data-stu-id="e1031-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span> 
    
    <span data-ttu-id="e1031-p117">Lors du processus de publication de la topologie, vous serez invité à définir un chemin d’accès au partage de fichiers. Les serveurs SQL Server qui participent à la mise en miroir doivent disposer d’un accès en lecture/écriture à ce partage de fichiers pour que le miroir puisse être établi.</span><span class="sxs-lookup"><span data-stu-id="e1031-p117">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>
    
<span data-ttu-id="e1031-171">Vous devez alors installer la base de données avant de passer à la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="e1031-171">You must then install the database before going on to the next procedure.</span></span>
  
<span data-ttu-id="e1031-172">Gardez les points suivants à l’esprit lorsque vous configurez la mise en miroir SQL :</span><span class="sxs-lookup"><span data-stu-id="e1031-172">You should keep the following in mind when setting up SQL mirroring:</span></span>
  
- <span data-ttu-id="e1031-173">S’il existe déjà un point de terminaison de mise en miroir, celui-ci est réutilisé à l’aide des ports définis ; ceux que vous spécifiez dans la topologie sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="e1031-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>
    
- <span data-ttu-id="e1031-p118">Tout port déjà alloué à d’autres applications sur le même serveur, dont ceux des autres instances SQL, ne doit pas être utilisé pour les instances SQL installées. Cela signifie que si vous avez plusieurs instances SQL installées sur le même serveur, elles ne doivent pas utiliser le même port pour la mise en miroir. Pour plus d’informations, reportez-vous aux articles suivants :</span><span class="sxs-lookup"><span data-stu-id="e1031-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
  - [<span data-ttu-id="e1031-177">Spécifier une adresse réseau de serveur (mise en miroir de base de données)</span><span class="sxs-lookup"><span data-stu-id="e1031-177">Specify a Server Network Address (Database Mirroring)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247346)
    
  - [<span data-ttu-id="e1031-178">La base de données mise en miroir de point de terminaison (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e1031-178">The Database Mirroring Endpoint (SQL Server)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247347)
    
## <a name="using-skype-for-business-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="e1031-179">À l’aide de Skype pour les applets de commande Business Server Management Shell pour configurer la mise en miroir de SQL</span><span class="sxs-lookup"><span data-stu-id="e1031-179">Using Skype for Business Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="e1031-180">La façon la plus simple pour configurer la mise en miroir est à l’aide du Générateur de topologies, mais vous pouvez également utiliser des applets de commande.</span><span class="sxs-lookup"><span data-stu-id="e1031-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>
  
1. <span data-ttu-id="e1031-181">Ouvrir un Skype pour la fenêtre de Business Server Management Shell et exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="e1031-181">Open a Skype for Business Server Management Shell window and run the following cmdlet:</span></span>
    
   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 

   ```

    <span data-ttu-id="e1031-182">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e1031-182">For example:</span></span>
    
   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 

   ```

    <span data-ttu-id="e1031-183">Les informations suivantes s’affichent :</span><span class="sxs-lookup"><span data-stu-id="e1031-183">You will see the following:</span></span>
    
  ```
  Database Name:rtcxds 
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rtcshared 
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rtcab 
        Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
         Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rgsconfig 
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rgsdyn 
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:cpsdyn 
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:xds 
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:lis 
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

  ```

2. <span data-ttu-id="e1031-184">Vérifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e1031-184">Verify the following:</span></span>
    
    - <span data-ttu-id="e1031-185">Le port 5022 est accessible via le pare-feu si le Pare-feu Windows est activé sur le serveur SQL principal e04-ocs.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="e1031-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span> 
    
    - <span data-ttu-id="e1031-186">Le port 5022 est accessible via le pare-feu si le Pare-feu Windows est activé dans le serveur SQL miroir K16-ocs.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="e1031-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span> 
    
    - <span data-ttu-id="e1031-187">Le port 7022 est accessible via le pare-feu si le Pare-feu Windows est activé dans le serveur SQL témoin AB14-lct.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="e1031-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span> 
    
   - <span data-ttu-id="e1031-188">Comptes exécute le principal de tous les serveurs SQL et les serveurs de mise en miroir SQL ont des autorisations en lecture/écriture pour le partage de fichiers \\OCS\csdatabackup-E04</span><span class="sxs-lookup"><span data-stu-id="e1031-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span> 
    
   - <span data-ttu-id="e1031-p119">Vérifiez que le fournisseur WMI (Windows Management Instrumentation) est en cours d’exécution sur tous ces serveurs. L’applet de commande utilise ce fournisseur pour rechercher les informations de compte pour les services SQL Server qui s’exécutent sur tous les serveurs principaux, miroir et témoin. </span><span class="sxs-lookup"><span data-stu-id="e1031-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span> 
    
   - <span data-ttu-id="e1031-191">Vérifiez que le compte qui exécute cette applet de commande est autorisé à créer les dossiers pour les données et fichiers journaux de tous les serveurs miroir. </span><span class="sxs-lookup"><span data-stu-id="e1031-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span> 
    
   - <span data-ttu-id="e1031-p120">Notez que le compte d’utilisateur que l’instance SQL utilise pour s’exécuter doit posséder une autorisation de lecture/écriture sur le partage de fichiers. Si ce dernier se trouve sur un autre serveur, et que l’instance SQL exécute un compte système local, vous devez octroyer au partage de fichier des autorisations d’accès au serveur qui héberge l’instance SQL.</span><span class="sxs-lookup"><span data-stu-id="e1031-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>
    
3. <span data-ttu-id="e1031-194">Tapez A, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="e1031-194">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="e1031-195">La mise en miroir est configurée.</span><span class="sxs-lookup"><span data-stu-id="e1031-195">The mirroring will be configured.</span></span>
    
    <span data-ttu-id="e1031-196">**Installation-CsMirrorDatabase** installe le miroir et configure la mise en miroir de bases de données qui sont présents dans le magasin principal de SQL.</span><span class="sxs-lookup"><span data-stu-id="e1031-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="e1031-197">Si vous voulez configurer la mise en miroir de bases de données spécifiques uniquement, vous pouvez utiliser l’option - argument typebasededonnées, ou si vous voulez configurer la mise en miroir des bases de données, à l’exception de quelques exemples, vous pouvez utiliser l’option - ExcludeDatabaseList, ainsi qu’une liste séparée par des virgules de base de données noms à exclure.</span><span class="sxs-lookup"><span data-stu-id="e1031-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>
  
    <span data-ttu-id="e1031-198">Par exemple, si vous ajoutez l’option suivante à **CsMirrorDatabase de l’installation**, toutes les bases de données, à l’exception de rtcab et rtcxds seront mis en miroir.</span><span class="sxs-lookup"><span data-stu-id="e1031-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>
  
    `-ExcludeDatabaseList rtcab,rtcxds`
  
   <span data-ttu-id="e1031-199">Par exemple, si vous ajoutez l’option suivante à **Installer-CsMirrorDatabase**, les rtcab, rtcshared et rtcxds de bases de données seront mis en miroir.</span><span class="sxs-lookup"><span data-stu-id="e1031-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>
  
    `-DatabaseType User`
  
## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="e1031-200">Suppression ou modification de la mise en miroir SQL</span><span class="sxs-lookup"><span data-stu-id="e1031-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="e1031-p122">Pour supprimer la mise en miroir SQL d’un pool dans le générateur de topologie, vous devez d’abord utiliser une applet de commande pour supprimer le miroir dans SQL Server. Vous pouvez ensuite utiliser le générateur de topologie pour supprimer le miroir de la topologie. Pour supprimer le miroir dans SQL Server, utilisez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="e1031-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>
  
```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

```

<span data-ttu-id="e1031-204">Par exemple, pour supprimer la mise en miroir et ignorer les bases de données pour les bases de données User, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e1031-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>
  
```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

```

<span data-ttu-id="e1031-205">Le `-DropExistingDatabasesOnMirror` avec l’option, les bases de données affectées à supprimer à partir du miroir.</span><span class="sxs-lookup"><span data-stu-id="e1031-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>
  
<span data-ttu-id="e1031-206">Ensuite, pour supprimer le miroir de la topologie, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e1031-206">Then, to remove the mirror from the topology, do the following:</span></span>
  
1. <span data-ttu-id="e1031-207">Dans le générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e1031-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="e1031-208">Désactivez la case à cocher **Activer la mise en miroir du magasin SQL ** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1031-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>
    
3. <span data-ttu-id="e1031-209">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="e1031-209">Publish the topology.</span></span>
    
## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="e1031-210">Suppression d’un témoin de mise en miroir</span><span class="sxs-lookup"><span data-stu-id="e1031-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="e1031-211">Utilisez cette procédure si vous devez supprimer le rappel à partir d’un serveur principal la mise en miroir de la configuration.</span><span class="sxs-lookup"><span data-stu-id="e1031-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>
  
1. <span data-ttu-id="e1031-212">Dans le générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e1031-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span> 
    
2. <span data-ttu-id="e1031-213">Désactivez la case à cocher **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1031-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>
    
3. <span data-ttu-id="e1031-214">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="e1031-214">Publish the topology.</span></span>
    
    <span data-ttu-id="e1031-215">Après la publication de la topologie, le Générateur de topologies vous verrez un message qui inclut les éléments suivants</span><span class="sxs-lookup"><span data-stu-id="e1031-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="e1031-216">Toutefois, ne suivez pas cette étape et ne tapez pas `Uninstall-CsMirrorDatabase` comme qui serait désinstaller toute la configuration mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="e1031-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>
    
4. <span data-ttu-id="e1031-217">Pour supprimer uniquement le témoin de la configuration de SQL Server, suivez les instructions de [suppression du rappel à partir d’une Session de mise en miroir de base de données (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span><span class="sxs-lookup"><span data-stu-id="e1031-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span></span>
    

