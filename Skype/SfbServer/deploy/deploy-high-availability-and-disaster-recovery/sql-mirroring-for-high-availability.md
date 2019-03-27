---
title: Déployer la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Pour pouvoir déployer la mise en miroir SQL, vos serveurs doivent exécuter au moins SQL Server 2008 R2. Cette version doit s’exécuter sur tous les serveurs impliqués : principal, miroir et témoin. Pour plus d’informations, voir Cumulative mise à jour de package 9 pour SQL Server 2008 Service Pack 1.'
ms.openlocfilehash: ebf1d222bff572100fe7824e52acdef2ff85216d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886274"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="344df-105">Déployer la mise en miroir SQL pour le serveur principal une haute disponibilité dans Skype pour Business server 2015</span><span class="sxs-lookup"><span data-stu-id="344df-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>


<span data-ttu-id="344df-106">Pour pouvoir déployer la mise en miroir SQL, vos serveurs doivent exécuter au moins SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="344df-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="344df-107">Cette version doit s’exécuter sur tous les serveurs impliqués : principal, miroir et témoin.</span><span class="sxs-lookup"><span data-stu-id="344df-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="344df-108">Pour plus d’informations, voir [9 pour SQL Server 2008 Service Pack 1 de package de mises à jour cumulatives ](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span><span class="sxs-lookup"><span data-stu-id="344df-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1 ](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>

<span data-ttu-id="344df-109">En général, la configuration de la mise en miroir SQL entre deux serveurs principaux avec un témoin exige ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="344df-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

- <span data-ttu-id="344df-110">Version du serveur principal de SQL Server doit prendre en charge la mise en miroir SQL.</span><span class="sxs-lookup"><span data-stu-id="344df-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>

- <span data-ttu-id="344df-111">Le principal, le miroir et le témoin (s’il est déployé) doivent disposer de la même version de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="344df-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

- <span data-ttu-id="344df-p103">Le principal et le miroir doivent disposer de la même édition de SQL Server. Le témoin peut en avoir une différente.</span><span class="sxs-lookup"><span data-stu-id="344df-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="344df-114">Pour les meilleures pratiques en termes de quelles versions SQL sont pris en charge pour un rôle de témoin SQL, voir [Témoin de mise en miroir de base de données](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span><span class="sxs-lookup"><span data-stu-id="344df-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span></span>

<span data-ttu-id="344df-115">Vous utilisez le Générateur de topologie pour déployer la mise en miroir SQL.</span><span class="sxs-lookup"><span data-stu-id="344df-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="344df-116">Vous sélectionnez une option dans le Générateur de topologie pour mettre en miroir de bases de données et le Générateur de topologie définit la mise en miroir (y compris la configuration d’un témoin, si vous le souhaitez) lorsque vous publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="344df-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="344df-117">Notez que vous configurez ou supprimez le témoin en même temps que le miroir.</span><span class="sxs-lookup"><span data-stu-id="344df-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="344df-118">Il n’existe pas de commande distincte pour déployer ou supprimer uniquement un témoin.</span><span class="sxs-lookup"><span data-stu-id="344df-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="344df-119">Pour configurer la mise en miroir des serveurs, vous devez d’abord configurer les autorisations de base de données SQL correctement.</span><span class="sxs-lookup"><span data-stu-id="344df-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="344df-120">Pour plus d’informations, voir [Définir des comptes de connexion pour la mise en miroir de base de données ou groupes de disponibilité AlwaysOn (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span><span class="sxs-lookup"><span data-stu-id="344df-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>

<span data-ttu-id="344df-p106">Avec la mise en miroir SQL, le mode de récupération de la base de données a toujours la valeur **Complète**, ce qui signifie que vous devez surveiller de près la taille du journal des transactions et sauvegarder les journaux des transactions de manière régulière afin d’éviter toute insuffisance d’espace disque sur les serveurs principaux. La fréquence des sauvegardes des journaux des transactions dépend de la vitesse à laquelle leur taille augmente, laquelle dépend à son tour des transactions de base de données induites par les activités des utilisateurs sur le pool frontal. Nous vous recommandons d’estimer l’accroissement des journaux des transactions pour la charge de travail de votre déploiement afin de procéder à une planification en conséquence. Les articles suivants fournissent des informations supplémentaires sur la gestion des journaux et sauvegardes SQL :</span><span class="sxs-lookup"><span data-stu-id="344df-p106">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

- [<span data-ttu-id="344df-125">Modèles de récupération de base de données</span><span class="sxs-lookup"><span data-stu-id="344df-125">Database recovery models</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [<span data-ttu-id="344df-126">Présentation de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="344df-126">Backup overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [<span data-ttu-id="344df-127">Journaux de transactions</span><span class="sxs-lookup"><span data-stu-id="344df-127">Backup transaction log</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268452)

<span data-ttu-id="344df-128">Avec la mise en miroir SQL, vous pouvez configurer la topologie pour la mise en miroir lorsque vous créez les pools ou après les avoir déjà créés.</span><span class="sxs-lookup"><span data-stu-id="344df-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="344df-129">À l’aide du Générateur de topologie ou des applets de commande pour configurer et supprimer SQL la mise en miroir est prise en charge uniquement lorsque le serveur principal, miroir et le serveur témoin (le cas échéant) appartiennent au même domaine.</span><span class="sxs-lookup"><span data-stu-id="344df-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="344df-130">Si vous voulez configurer la mise en miroir SQL entre des serveurs de différents domaines, reportez-vous à votre documentation SQL Server.</span><span class="sxs-lookup"><span data-stu-id="344df-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="344df-131">Dès lors que vous apportez une modification à une relation de mise en miroir d’une base de données principale, vous devez redémarrer tous les serveurs frontaux du pool. </span><span class="sxs-lookup"><span data-stu-id="344df-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="344df-132">> pour une modification de la mise en miroir, (telles que la modification de l’emplacement d’un miroir), vous devez utiliser le Générateur de topologie pour effectuer ces trois étapes :</span><span class="sxs-lookup"><span data-stu-id="344df-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span>

1. <span data-ttu-id="344df-133">Supprimez la mise en miroir de l’ancien serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="344df-133">Remove mirroring from the old mirror server.</span></span>

2. <span data-ttu-id="344df-134">Ajoutez la mise en miroir au nouveau serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="344df-134">Add mirroring to the new mirror server.</span></span>

3. <span data-ttu-id="344df-135">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="344df-135">Publish the topology.</span></span>

> [!NOTE]
> <span data-ttu-id="344df-136">Un partage de fichiers doit être créé pour pouvoir y écrire les fichiers miroir, et le service sous lequel SQL Server et SQL Agent s’exécutent doit disposer d’un accès en lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="344df-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="344df-137">Si le service SQL Server est en cours d’exécution dans le contexte de Service réseau, vous pouvez ajouter \<domaine\>\\<SQLSERVERNAME\>$ d’à la fois les serveurs Principal et miroir SQL pour les autorisations de partage.</span><span class="sxs-lookup"><span data-stu-id="344df-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="344df-138">Le signe $ est important afin d’identifier qu’il s’agit d’un compte ordinateur.</span><span class="sxs-lookup"><span data-stu-id="344df-138">The $ is important to identify that this is a computer account.</span></span>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="344df-139">Pour configurer la mise en miroir SQL lors de la création d’un pool dans le Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="344df-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="344df-140">Dans la page **Définir le magasin SQL**, cliquez sur **Nouveau** en regard de la zone **Magasin SQL**. </span><span class="sxs-lookup"><span data-stu-id="344df-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2. <span data-ttu-id="344df-141">Dans la page **Définir un nouveau magasin SQL**, spécifiez le magasin principal, sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (5022 par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="344df-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3. <span data-ttu-id="344df-142">De retour dans la page **Définir le magasin SQL**, sélectionnez **Activer la mise en miroir du magasin SQL**. </span><span class="sxs-lookup"><span data-stu-id="344df-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4. <span data-ttu-id="344df-p110">Dans la page **Définir un nouveau magasin SQL**, spécifiez le magasin SQL à utiliser en tant que miroir. Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port (5022 par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="344df-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="344df-145">Si vous voulez un témoin pour ce miroir, procédez comme suit : </span><span class="sxs-lookup"><span data-stu-id="344df-145">If you want a witness for this mirror, do the following:</span></span>

    <span data-ttu-id="344df-146">a.</span><span class="sxs-lookup"><span data-stu-id="344df-146">a.</span></span> <span data-ttu-id="344df-147">Sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**. </span><span class="sxs-lookup"><span data-stu-id="344df-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>

    <span data-ttu-id="344df-148">b.</span><span class="sxs-lookup"><span data-stu-id="344df-148">b.</span></span> <span data-ttu-id="344df-149">Dans la page **Définir le magasin SQL**, sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**, puis spécifiez le magasin SQL à utiliser en tant que témoin. </span><span class="sxs-lookup"><span data-stu-id="344df-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>

    <span data-ttu-id="344df-150">c.</span><span class="sxs-lookup"><span data-stu-id="344df-150">c.</span></span> <span data-ttu-id="344df-151">Spécifiez le numéro de port (7022 par défaut) et cliquez sur **OK**. </span><span class="sxs-lookup"><span data-stu-id="344df-151">Specify the port number (the default is 7022) and click **OK**.</span></span>

6. <span data-ttu-id="344df-152">Une fois que vous avez terminé définition de votre pool frontal et tous les autres rôles dans votre topologie, utilisez le Générateur de topologie pour publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="344df-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="344df-153">Une fois la topologie publiée, si le pool frontal qui héberge le magasin Central de gestion a miroir SQL, vous verrez une option pour créer les deux principal et de mise en miroir de bases de données de magasin SQL.</span><span class="sxs-lookup"><span data-stu-id="344df-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>

    <span data-ttu-id="344df-154">Cliquez sur **Paramètres**, puis tapez le chemin d’accès à utiliser en tant que partage de fichiers pour la sauvegarde de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="344df-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>

    <span data-ttu-id="344df-p115">Cliquez sur **OK**, puis sur \*\*Suivant \*\* pour créer les bases de données et publier la topologie. Le miroir et le témoin (s’il est spécifié) sont déployés.</span><span class="sxs-lookup"><span data-stu-id="344df-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="344df-157">Vous pouvez utiliser le Générateur de topologie pour modifier les propriétés d’un pool déjà existant pour activer la mise en miroir SQL.</span><span class="sxs-lookup"><span data-stu-id="344df-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="344df-158">Pour ajouter la mise en miroir SQL à un pool frontal existant dans le Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="344df-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="344df-159">Dans le Générateur de topologie avec le bouton droit de la liste, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="344df-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2. <span data-ttu-id="344df-160">Sélectionnez **Activer la mise en miroir du magasin SQL**, puis cliquez sur \*\*Nouveau \*\* en regard de **Magasin SQL de mise en miroir**. </span><span class="sxs-lookup"><span data-stu-id="344df-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3. <span data-ttu-id="344df-161">Spécifiez le magasin SQL à utiliser en tant que miroir. </span><span class="sxs-lookup"><span data-stu-id="344df-161">Specify the SQL store that you want to use as the mirror.</span></span>

4. <span data-ttu-id="344df-162">Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (5022 par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="344df-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="344df-163">Si vous voulez configurer un témoin, sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**, puis cliquez sur **Nouveau**. </span><span class="sxs-lookup"><span data-stu-id="344df-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6. <span data-ttu-id="344df-164">Spécifiez le magasin SQL à utiliser en tant que témoin. </span><span class="sxs-lookup"><span data-stu-id="344df-164">Specify the SQL store that you want to use as the witness.</span></span>

7. <span data-ttu-id="344df-165">Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (7022 par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="344df-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8. <span data-ttu-id="344df-166">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="344df-166">Click **OK**.</span></span>

9. <span data-ttu-id="344df-p116">Publiez la topologie. Après cela, vous êtes invité à installer la base de données. </span><span class="sxs-lookup"><span data-stu-id="344df-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span>

    <span data-ttu-id="344df-p117">Lors du processus de publication de la topologie, vous serez invité à définir un chemin d’accès au partage de fichiers. Les serveurs SQL Server qui participent à la mise en miroir doivent disposer d’un accès en lecture/écriture à ce partage de fichiers pour que le miroir puisse être établi.</span><span class="sxs-lookup"><span data-stu-id="344df-p117">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="344df-171">Vous devez alors installer la base de données avant de passer à la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="344df-171">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="344df-172">Gardez les points suivants à l’esprit lorsque vous configurez la mise en miroir SQL :</span><span class="sxs-lookup"><span data-stu-id="344df-172">You should keep the following in mind when setting up SQL mirroring:</span></span>

- <span data-ttu-id="344df-173">S’il existe déjà un point de terminaison de mise en miroir, celui-ci est réutilisé à l’aide des ports définis ; ceux que vous spécifiez dans la topologie sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="344df-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

- <span data-ttu-id="344df-p118">Tout port déjà alloué à d’autres applications sur le même serveur, dont ceux des autres instances SQL, ne doit pas être utilisé pour les instances SQL installées. Cela signifie que si vous avez plusieurs instances SQL installées sur le même serveur, elles ne doivent pas utiliser le même port pour la mise en miroir. Pour plus d’informations, reportez-vous aux articles suivants :</span><span class="sxs-lookup"><span data-stu-id="344df-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>

  - [<span data-ttu-id="344df-177">Spécifier une adresse réseau du serveur (mise en miroir de base de données)</span><span class="sxs-lookup"><span data-stu-id="344df-177">Specify a Server Network Address (Database Mirroring)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [<span data-ttu-id="344df-178">La base de données mise en miroir de point de terminaison (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="344df-178">The Database Mirroring Endpoint (SQL Server)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="344df-179">À l’aide de Skype pour Business Server 2015 Management Shell applets de commande Set Up la mise en miroir SQL</span><span class="sxs-lookup"><span data-stu-id="344df-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="344df-180">Le moyen le plus simple pour configurer la mise en miroir est à l’aide du Générateur de topologie, mais vous pouvez également effectuer à l’aide des applets de commande.</span><span class="sxs-lookup"><span data-stu-id="344df-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1. <span data-ttu-id="344df-181">Ouvrez un Skype pour fenêtre Business Server 2015 Management Shell et exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="344df-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>

   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    <span data-ttu-id="344df-182">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="344df-182">For example:</span></span>

   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    <span data-ttu-id="344df-183">Les informations suivantes s’affichent :</span><span class="sxs-lookup"><span data-stu-id="344df-183">You will see the following:</span></span>

   <pre>
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
   </pre>

2. <span data-ttu-id="344df-184">Vérifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="344df-184">Verify the following:</span></span>

    - <span data-ttu-id="344df-185">Le port 5022 est accessible via le pare-feu si le Pare-feu Windows est activé sur le serveur SQL principal e04-ocs.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="344df-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="344df-186">Le port 5022 est accessible via le pare-feu si le Pare-feu Windows est activé dans le serveur SQL miroir K16-ocs.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="344df-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="344df-187">Le port 7022 est accessible via le pare-feu si le Pare-feu Windows est activé dans le serveur SQL témoin AB14-lct.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="344df-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span>

   - <span data-ttu-id="344df-188">Les comptes qui exécutent les serveurs miroir SQL Server principal tous les serveurs SQL ont l’autorisation en lecture/écriture pour le partage de fichiers \\OCS\csdatabackup-E04</span><span class="sxs-lookup"><span data-stu-id="344df-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span>

   - <span data-ttu-id="344df-p119">Vérifiez que le fournisseur WMI (Windows Management Instrumentation) est en cours d’exécution sur tous ces serveurs. L’applet de commande utilise ce fournisseur pour rechercher les informations de compte pour les services SQL Server qui s’exécutent sur tous les serveurs principaux, miroir et témoin. </span><span class="sxs-lookup"><span data-stu-id="344df-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>

   - <span data-ttu-id="344df-191">Vérifiez que le compte qui exécute cette applet de commande est autorisé à créer les dossiers pour les données et fichiers journaux de tous les serveurs miroir. </span><span class="sxs-lookup"><span data-stu-id="344df-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>

   - <span data-ttu-id="344df-p120">Notez que le compte d’utilisateur que l’instance SQL utilise pour s’exécuter doit posséder une autorisation de lecture/écriture sur le partage de fichiers. Si ce dernier se trouve sur un autre serveur, et que l’instance SQL exécute un compte système local, vous devez octroyer au partage de fichier des autorisations d’accès au serveur qui héberge l’instance SQL.</span><span class="sxs-lookup"><span data-stu-id="344df-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3. <span data-ttu-id="344df-194">Tapez A, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="344df-194">Type A and press ENTER.</span></span>

    <span data-ttu-id="344df-195">La mise en miroir est configurée.</span><span class="sxs-lookup"><span data-stu-id="344df-195">The mirroring will be configured.</span></span>

    <span data-ttu-id="344df-196">**Install-CsMirrorDatabase** installe le miroir et configure la mise en miroir de toutes les bases de données présentes sur le magasin SQL principal.</span><span class="sxs-lookup"><span data-stu-id="344df-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="344df-197">Si vous souhaitez configurer la mise en miroir de bases de données spécifiques, vous pouvez utiliser l’option - DatabaseType, ou si vous souhaitez configurer la mise en miroir pour toutes les bases de données à l’exception de quelques, vous pouvez utiliser l’option - ExcludeDatabaseList, ainsi que d’une liste séparée par des virgules de base de données noms à exclure.</span><span class="sxs-lookup"><span data-stu-id="344df-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

    <span data-ttu-id="344df-198">Par exemple, si vous ajoutez l’option suivante à **Install-CsMirrorDatabase**, toutes les bases de données à l’exception de rtcab et rtcxds sont mises en miroir.</span><span class="sxs-lookup"><span data-stu-id="344df-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

    `-ExcludeDatabaseList rtcab,rtcxds`

   <span data-ttu-id="344df-199">Par exemple, si vous ajoutez l’option suivante à **Install-CsMirrorDatabase**, seules les bases de données rtcab, rtcshared et rtcxds sont mises en miroir.</span><span class="sxs-lookup"><span data-stu-id="344df-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="344df-200">Suppression ou modification de la mise en miroir SQL</span><span class="sxs-lookup"><span data-stu-id="344df-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="344df-p122">Pour supprimer la mise en miroir SQL d’un pool dans le générateur de topologie, vous devez d’abord utiliser une applet de commande pour supprimer le miroir dans SQL Server. Vous pouvez ensuite utiliser le générateur de topologie pour supprimer le miroir de la topologie. Pour supprimer le miroir dans SQL Server, utilisez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="344df-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="344df-204">Par exemple, pour supprimer la mise en miroir et ignorer les bases de données pour les bases de données User, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="344df-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="344df-205">Le `-DropExistingDatabasesOnMirror` avec l’option, les bases de données affectées à supprimer de la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="344df-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="344df-206">Ensuite, pour supprimer le miroir de la topologie, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="344df-206">Then, to remove the mirror from the topology, do the following:</span></span>

1. <span data-ttu-id="344df-207">Dans le générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="344df-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="344df-208">Désactivez la case à cocher \*\*Activer la mise en miroir du magasin SQL \*\* et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="344df-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3. <span data-ttu-id="344df-209">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="344df-209">Publish the topology.</span></span>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="344df-210">Suppression d’un témoin de mise en miroir</span><span class="sxs-lookup"><span data-stu-id="344df-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="344df-211">Utilisez cette procédure si vous avez besoin supprimer le témoin d’un serveur principal configuration de la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="344df-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1. <span data-ttu-id="344df-212">Dans le générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="344df-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="344df-213">Désactivez la case à cocher **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="344df-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3. <span data-ttu-id="344df-214">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="344df-214">Publish the topology.</span></span>

    <span data-ttu-id="344df-215">Après la publication de la topologie, le Générateur de topologie vous verrez un message qui inclut les éléments suivants</span><span class="sxs-lookup"><span data-stu-id="344df-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>

   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="344df-216">Toutefois, ne suivez pas cette étape et ne tapez pas `Uninstall-CsMirrorDatabase` car cela désinstallerait toute la configuration de la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="344df-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4. <span data-ttu-id="344df-217">Pour supprimer uniquement le témoin de la configuration de SQL Server, suivez les instructions de [Supprimer le témoin d’une Session de la mise en miroir de base de données (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span><span class="sxs-lookup"><span data-stu-id="344df-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span></span>


