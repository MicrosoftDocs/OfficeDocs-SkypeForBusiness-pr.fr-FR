---
title: Déploiement de la mise en miroir SQL pour la haute disponibilité du serveur principal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0202b41c5da45513ccd4e08aa2ed054c3d20acbe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="65b20-102">Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65b20-102">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65b20-103">_**Dernière modification de la rubrique :** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="65b20-103">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="65b20-104">Pour pouvoir déployer la mise en miroir SQL, vos serveurs doivent exécuter au moins SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="65b20-104">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="65b20-105">Cette version doit s’exécuter sur tous les serveurs impliqués : principal, miroir et témoin.</span><span class="sxs-lookup"><span data-stu-id="65b20-105">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="65b20-106">Pour plus d’informations [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921), reportez-vous à.</span><span class="sxs-lookup"><span data-stu-id="65b20-106">For details, see [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="65b20-107">En général, la configuration de la mise en miroir SQL entre deux serveurs principaux avec un témoin exige ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="65b20-107">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="65b20-108">La version de SQL Server du serveur principal doit prendre en charge la mise en miroir SQL.</span><span class="sxs-lookup"><span data-stu-id="65b20-108">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="65b20-109">Le principal, le miroir et le témoin (s’il est déployé) doivent disposer de la même version de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="65b20-109">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="65b20-p102">Le principal et le miroir doivent disposer de la même édition de SQL Server. Le témoin peut en avoir une différente.</span><span class="sxs-lookup"><span data-stu-id="65b20-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="65b20-112">Pour connaître les meilleures pratiques SQL en matière de prise en charge des versions SQL pour un rôle de témoin, voir « témoin de mise en miroir de [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)bases de données » dans la bibliothèque MSDN à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="65b20-112">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="65b20-113">Vous utilisez le générateur de topologies pour déployer la mise en miroir SQL.</span><span class="sxs-lookup"><span data-stu-id="65b20-113">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="65b20-114">Sélectionnez une option dans le générateur de topologie pour mettre en miroir les bases de données, et le générateur de topologies configure la mise en miroir (y compris la configuration d’un témoin, si vous le souhaitez) lors de la publication de la topologie.</span><span class="sxs-lookup"><span data-stu-id="65b20-114">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="65b20-115">Notez que vous configurez ou supprimez le témoin en même temps que le miroir.</span><span class="sxs-lookup"><span data-stu-id="65b20-115">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="65b20-116">Il n’existe pas de commande distincte pour déployer ou supprimer uniquement un témoin.</span><span class="sxs-lookup"><span data-stu-id="65b20-116">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="65b20-117">Pour configurer la mise en miroir des serveurs, vous devez d’abord configurer les autorisations de base de données SQL correctement.</span><span class="sxs-lookup"><span data-stu-id="65b20-117">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="65b20-118">Pour plus d’informations, consultez la rubrique « Configurer des comptes de connexion pour la mise en miroir de bases de données [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454)ou les groupes de disponibilité AlwaysOn (SQL Server) » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="65b20-118">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="65b20-p105">Avec la mise en miroir SQL, le mode de récupération de la base de données a toujours la valeur **Complète**, ce qui signifie que vous devez surveiller de près la taille du journal des transactions et sauvegarder les journaux des transactions de manière régulière afin d’éviter toute insuffisance d’espace disque sur les serveurs principaux. La fréquence des sauvegardes des journaux des transactions dépend de la vitesse à laquelle leur taille augmente, laquelle dépend à son tour des transactions de base de données induites par les activités des utilisateurs sur le pool frontal. Nous vous recommandons d’estimer l’accroissement des journaux des transactions pour la charge de travail de votre déploiement Lync afin de procéder à une planification en conséquence. Les articles suivants fournissent des informations supplémentaires sur la gestion des journaux et sauvegardes SQL :</span><span class="sxs-lookup"><span data-stu-id="65b20-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="65b20-123">Modèles de récupération de base de données : « modèles de récupération (SQL Server) » à l’adresse[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="65b20-123">Database recovery models: "Recovery Models (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="65b20-124">Vue d’ensemble de la sauvegarde : « vue d’ensemble de la sauvegarde (SQL Server) » à[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="65b20-124">Backup overview: "Backup Overview (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="65b20-125">Sauvegarder le journal des transactions : « sauvegarder un journal des transactions (SQL Server) » à l’adresse[http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="65b20-125">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="65b20-126">Avec la mise en miroir SQL, vous pouvez configurer la topologie pour la mise en miroir lorsque vous créez les pools ou après les avoir déjà créés.</span><span class="sxs-lookup"><span data-stu-id="65b20-126">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="65b20-127">Le recours au générateur de topologie ou aux cmdlets pour configurer et supprimer la mise en miroir SQL est pris en charge uniquement lorsque les serveurs principal, miroir et témoin (si nécessaire) appartiennent tous au même domaine.</span><span class="sxs-lookup"><span data-stu-id="65b20-127">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="65b20-128">Si vous voulez configurer la mise en miroir SQL entre des serveurs de différents domaines, voir votre documentation SQL Server.</span><span class="sxs-lookup"><span data-stu-id="65b20-128">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="65b20-129">Dès lors que vous apportez une modification à une relation de mise en miroir d’une base de données principale, vous devez redémarrer tous les serveurs frontaux du pool.</span><span class="sxs-lookup"><span data-stu-id="65b20-129">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="65b20-130">Pour une modification de la mise en miroir (telle que la modification de l’emplacement d’un miroir), vous devez utiliser le générateur de topologies pour effectuer ces trois étapes :</span><span class="sxs-lookup"><span data-stu-id="65b20-130">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="65b20-131">Supprimez la mise en miroir de l’ancien serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="65b20-131">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="65b20-132">Ajoutez la mise en miroir au nouveau serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="65b20-132">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="65b20-133">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="65b20-133">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="65b20-134">Un partage de fichiers doit être créé pour que les fichiers en miroir soient écrits, et le service sous lequel SQL Server et l’agent SQL s’exécutent sous besoin d’un accès en lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="65b20-134">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="65b20-135">Si le service SQL Server est en cours d’exécution dans le contexte d’un service réseau &lt;,&gt; vous &lt;pouvez&gt;ajouter des&#92;de domaine SqlServerName $ des serveurs SQL principal et miroir aux autorisations de partage.</span><span class="sxs-lookup"><span data-stu-id="65b20-135">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="65b20-136">Le $ est important pour identifier qu’il s’agit d’un compte d’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="65b20-136">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="65b20-137">Pour configurer la mise en miroir SQL lors de la création d’un pool dans le générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="65b20-137">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="65b20-138">Dans la page **Définir le magasin SQL**, cliquez sur **Nouveau** en regard de la zone **Magasin SQL**.</span><span class="sxs-lookup"><span data-stu-id="65b20-138">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="65b20-139">Dans la page **Définir un nouveau magasin SQL**, spécifiez le magasin principal, sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (5022 par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b20-139">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="65b20-140">De retour dans la page **Définir le magasin SQL**, sélectionnez **Activer la mise en miroir du magasin SQL**.</span><span class="sxs-lookup"><span data-stu-id="65b20-140">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="65b20-p108">Dans la page **Définir un nouveau magasin SQL**, spécifiez le magasin SQL à utiliser en tant que miroir. Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port (5022 par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b20-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="65b20-143">Si vous voulez un témoin pour ce miroir, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="65b20-143">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="65b20-144">Sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**.</span><span class="sxs-lookup"><span data-stu-id="65b20-144">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="65b20-145">Dans la page **Définir le magasin SQL**, sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**, puis spécifiez le magasin SQL à utiliser en tant que témoin.</span><span class="sxs-lookup"><span data-stu-id="65b20-145">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="65b20-146">Spécifiez le numéro de port (7022 par défaut) et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b20-146">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="65b20-147">Une fois que vous avez terminé de définir votre pool frontal et tous les autres rôles dans votre topologie, utilisez le générateur de topologies pour publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="65b20-147">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="65b20-148">Lors de la publication de la topologie, si la mise en miroir SQL est activée pour le pool frontal qui héberge le magasin central de gestion, une option vous permet de créer des bases de données de magasin SQL principale et miroir.</span><span class="sxs-lookup"><span data-stu-id="65b20-148">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="65b20-149">Cliquez sur **Paramètres**, puis tapez le chemin d’accès à utiliser en tant que partage de fichiers pour la sauvegarde de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="65b20-149">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="65b20-p110">Cliquez sur **OK**, puis sur **Suivant** pour créer les bases de données et publier la topologie. Le miroir et le témoin (s’il est spécifié) sont déployés.</span><span class="sxs-lookup"><span data-stu-id="65b20-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="65b20-152">Vous pouvez utiliser le générateur de topologie pour modifier les propriétés d’un pool déjà existant afin d’activer la mise en miroir SQL.</span><span class="sxs-lookup"><span data-stu-id="65b20-152">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="65b20-153">Pour ajouter la mise en miroir SQL à un pool frontal existant dans le générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="65b20-153">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="65b20-154">Dans le générateur de topologies, cliquez avec le bouton droit sur le pool, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="65b20-154">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="65b20-155">Sélectionnez **Activer la mise en miroir du magasin SQL**, puis cliquez sur **Nouveau** en regard de **Magasin SQL de mise en miroir**.</span><span class="sxs-lookup"><span data-stu-id="65b20-155">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="65b20-156">Spécifiez le magasin SQL à utiliser en tant que miroir.</span><span class="sxs-lookup"><span data-stu-id="65b20-156">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="65b20-157">Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (5022 par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b20-157">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="65b20-158">Si vous voulez configurer un témoin, sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**, puis cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="65b20-158">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="65b20-159">Spécifiez le magasin SQL à utiliser en tant que témoin.</span><span class="sxs-lookup"><span data-stu-id="65b20-159">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="65b20-160">Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (7022 par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b20-160">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="65b20-161">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b20-161">Click **OK**.</span></span>

9.  <span data-ttu-id="65b20-p111">Publiez la topologie. Après cela, vous êtes invité à installer la base de données.</span><span class="sxs-lookup"><span data-stu-id="65b20-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="65b20-164">Pendant le processus de publication de la topologie, vous serez invité à définir un chemin d’accès de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="65b20-164">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="65b20-165">Les serveurs SQL qui participent à la mise en miroir doivent disposer d’un accès en lecture/écriture à ce partage de fichiers pour que le miroir soit établi.</span><span class="sxs-lookup"><span data-stu-id="65b20-165">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="65b20-166">Vous devez alors installer la base de données avant de passer à la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="65b20-166">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="65b20-167">Gardez les points suivants à l’esprit lorsque vous configurez la mise en miroir SQL :</span><span class="sxs-lookup"><span data-stu-id="65b20-167">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="65b20-168">S’il existe déjà un point de terminaison de mise en miroir, celui-ci est réutilisé à l’aide des ports définis ; ceux que vous spécifiez dans la topologie sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="65b20-168">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="65b20-p113">Tout port déjà alloué à d’autres applications sur le même serveur, y compris ceux des autres instances SQL, ne doit pas être utilisé pour les instances SQL installées. Cela signifie que si vous avez plusieurs instances SQL installées sur le même serveur, elles ne doivent pas utiliser le même port pour la mise en miroir. Pour plus d’informations, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="65b20-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="65b20-172">« Spécifier une adresse réseau de serveur (mise en miroir de bases de données) » dans la bibliothèque MSDN[http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="65b20-172">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="65b20-173">« Le point de terminaison de mise en miroir de base de données (SQL Server) » à[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="65b20-173">"The Database Mirroring Endpoint (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="65b20-174">Utilisation des applets de commande Lync Server Management Shell pour configurer la mise en miroir SQL</span><span class="sxs-lookup"><span data-stu-id="65b20-174">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="65b20-175">Le moyen le plus simple de configurer la mise en miroir consiste à utiliser le générateur de topologie, mais vous pouvez également le faire à l’aide d’applets de commande.</span><span class="sxs-lookup"><span data-stu-id="65b20-175">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="65b20-176">Ouvrez une fenêtre Lync Server Management Shell et exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="65b20-176">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="65b20-177">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="65b20-177">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="65b20-178">Les informations suivantes s’affichent :</span><span class="sxs-lookup"><span data-stu-id="65b20-178">You will see the following:</span></span>
    
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

2.  <span data-ttu-id="65b20-179">Vérifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="65b20-179">Verify the following:</span></span>
    
      - <span data-ttu-id="65b20-180">Le port 5022 est accessible via le pare-feu si le pare-feu Windows est activé dans le\_serveur SQL Server principal E04\\. Los a. LSIPT. local RTC.</span><span class="sxs-lookup"><span data-stu-id="65b20-180">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="65b20-181">Le port 5022 est accessible via le pare-feu si le pare-feu Windows est activé dans le\_miroir SQL Server K16.\\Los a. LSIPT. local RTC.</span><span class="sxs-lookup"><span data-stu-id="65b20-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="65b20-182">Le port 7022 est accessible via le pare-feu si le pare-feu Windows est activé dans le\_Ab14 SQL Server témoin.\\Los a. LSIPT. local RTC.</span><span class="sxs-lookup"><span data-stu-id="65b20-182">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="65b20-183">Les comptes exécutant les serveurs SQL Server sur tous les serveurs SQL primaire et miroir ont une autorisation en lecture/ \\ \\écriture sur le\\partage de fichiers E04-OCS csdatabackup</span><span class="sxs-lookup"><span data-stu-id="65b20-183">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="65b20-p114">Vérifiez que le fournisseur WMI (Windows Management Instrumentation) est en cours d’exécution sur tous ces serveurs. L’applet de commande utilise ce fournisseur pour rechercher les informations de compte pour les services SQL Server qui s’exécutent sur tous les serveurs principaux, miroir et témoin.</span><span class="sxs-lookup"><span data-stu-id="65b20-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="65b20-186">Vérifiez que le compte qui exécute cette applet de commande est autorisé à créer les dossiers pour les données et fichiers journaux de tous les serveurs miroir.</span><span class="sxs-lookup"><span data-stu-id="65b20-186">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="65b20-p115">Notez que le compte d’utilisateur que l’instance SQL utilise pour s’exécuter doit posséder une autorisation de lecture/écriture sur le partage de fichiers. Si ce dernier se trouve sur un autre serveur, et que l’instance SQL exécute un compte système local, vous devez octroyer au partage de fichier des autorisations d’accès au serveur qui héberge l’instance SQL.</span><span class="sxs-lookup"><span data-stu-id="65b20-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="65b20-189">Tapez A, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="65b20-189">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="65b20-190">La mise en miroir est configurée.</span><span class="sxs-lookup"><span data-stu-id="65b20-190">The mirroring will be configured.</span></span>

<span data-ttu-id="65b20-191">**Install-CsMirrorDatabase** installe le miroir et configure la mise en miroir de toutes les bases de données présentes sur le magasin SQL principal.</span><span class="sxs-lookup"><span data-stu-id="65b20-191">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="65b20-192">Pour configurer la mise en miroir pour des bases de données spécifiques uniquement, vous pouvez utiliser l’option –DatabaseType, ou pour configurer la mise en miroir de toutes les bases de données à l’exception de quelques-unes, vous pouvez utiliser l’option -ExcludeDatabaseList, avec la liste séparée par des virgules des noms des bases de données à exclure.</span><span class="sxs-lookup"><span data-stu-id="65b20-192">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="65b20-193">Par exemple, si vous ajoutez l’option suivante à **Install-CsMirrorDatabase**, toutes les bases de données à l’exception de rtcab et rtcxds sont mises en miroir.</span><span class="sxs-lookup"><span data-stu-id="65b20-193">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="65b20-194">Par exemple, si vous ajoutez l’option suivante à **Install-CsMirrorDatabase**, seules les bases de données rtcab, rtcshared et rtcxds sont mises en miroir.</span><span class="sxs-lookup"><span data-stu-id="65b20-194">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="65b20-195">Suppression ou modification de la mise en miroir SQL</span><span class="sxs-lookup"><span data-stu-id="65b20-195">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="65b20-p117">Pour supprimer la mise en miroir SQL d’un pool dans le Générateur de topologie, vous devez d’abord utiliser une applet de commande pour supprimer le miroir dans SQL Server. Vous pouvez ensuite utiliser le Générateur de topologie pour supprimer le miroir de la topologie. Pour supprimer le miroir dans SQL Server, utilisez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="65b20-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="65b20-199">Par exemple, pour supprimer la mise en miroir et ignorer les bases de données pour les bases de données User, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="65b20-199">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="65b20-200">L' `-DropExistingDatabasesOnMirror` option entraîne la suppression des bases de données concernées du miroir.</span><span class="sxs-lookup"><span data-stu-id="65b20-200">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="65b20-201">Ensuite, pour supprimer le miroir de la topologie, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="65b20-201">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="65b20-202">Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="65b20-202">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="65b20-203">Désactivez la case à cocher **Activer la mise en miroir du magasin SQL** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b20-203">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="65b20-204">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="65b20-204">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="65b20-205">Suppression d’un témoin de mise en miroir</span><span class="sxs-lookup"><span data-stu-id="65b20-205">Removing a Mirroring Witness</span></span>

<span data-ttu-id="65b20-206">Utilisez cette procédure si vous devez supprimer le témoin d’une configuration de mise en miroir du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="65b20-206">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="65b20-207">Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="65b20-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="65b20-208">Désactivez la case à cocher **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b20-208">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="65b20-209">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="65b20-209">Publish the topology.</span></span>
    
    <span data-ttu-id="65b20-210">Après la publication de la topologie, le générateur de topologie affiche un message qui inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="65b20-210">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="65b20-211">Toutefois, ne suivez pas cette étape et ne tapez `Uninstall-CsMirrorDatabase` pas comme cela aurait pour effet de désinstaller toute la configuration de la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="65b20-211">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="65b20-212">Pour supprimer uniquement le témoin de la configuration SQL Server, suivez les instructions de la section « supprimer le témoin d’une session de mise en miroir de bases de [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456)données (SQL Server) » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="65b20-212">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

