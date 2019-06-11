---
title: Déplacer le serveur de gestion central de Lync Server 2010 vers Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abcb361beb82b98cd765b3797b63b22c280fdf70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="61304-102">Déplacer le serveur de gestion central de Lync Server 2010 vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61304-102">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61304-103">_**Dernière modification de la rubrique:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="61304-103">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="61304-104">Après la migration de Lync Server 2010 vers Lync Server 2013, vous devez déplacer le serveur de gestion central de Lync Server 2010 vers le pool ou le serveur frontal de Lync Server 2013, avant de pouvoir supprimer l’ancien serveur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="61304-104">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="61304-105">Le serveur de gestion central est un système de réplication maître/multiple unique, où la copie en lecture/écriture de la base de données est stockée par le serveur frontal qui contient le serveur de gestion central.</span><span class="sxs-lookup"><span data-stu-id="61304-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="61304-106">Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion central, dispose d’une copie en lecture seule de la base de données centrale de gestion de la base de données SQL Server (nommée RTCLOCAL par défaut) installée sur l’ordinateur lors de l’installation et développement.</span><span class="sxs-lookup"><span data-stu-id="61304-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="61304-107">La base de données locale reçoit les mises à jour de réplica par le biais de l’agent réplicateur de réplicas de Lync Server exécuté en tant que service sur tous les ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="61304-107">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="61304-108">Le nom de la base de données réelle du serveur de gestion central et du réplica local est XDS, qui est constitué des fichiers XDS. mdf et XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="61304-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="61304-109">L’emplacement de la base de données maître est référencé par un point de contrôle de service (SCP) dans les services de domaine Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="61304-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="61304-110">Tous les outils qui utilisent le serveur de gestion central pour gérer et configurer Lync Server utilisent le SCP pour trouver le magasin de gestion central.</span><span class="sxs-lookup"><span data-stu-id="61304-110">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="61304-111">Après avoir déplacé le serveur de gestion central, vous devez supprimer les bases de données du serveur principal de gestion du serveur frontal initial.</span><span class="sxs-lookup"><span data-stu-id="61304-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="61304-112">Pour plus d’informations sur la suppression de la base de données de serveur de gestion centrale, voir [Supprimer la base de données SQL Server d’un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="61304-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="61304-113">Pour déplacer la base de données \*\*\*\* de la base de données sql Server 2010 vers lync Server 2013 SQL Server à l’aide de la cmdlet Windows PowerShell, procédez comme s’il s’agit de la base de données sql Server SQL Server, puis mettez à jour le SCP pour qu’il pointe vers Lync. Emplacement du serveur de gestion central de Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61304-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="61304-114">Préparation des serveurs frontaux Lync Server 2013 avant le déplacement du serveur de gestion central</span><span class="sxs-lookup"><span data-stu-id="61304-114">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="61304-115">Suivez les procédures décrites dans cette section pour préparer les serveurs frontaux Lync Server 2013 avant de déplacer le serveur de gestion central de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="61304-115">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="61304-116">Pour préparer un pool frontal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="61304-116">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="61304-117">Sur le pool frontal de Lync Server 2013 Enterprise Edition dans lequel vous souhaitez relocaliser le serveur de gestion central: Connectez-vous à l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="61304-117">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="61304-118">Vous devez également disposer des droits d’utilisateur sysadmin et des autorisations de la base de données SQL Server sur la base de données dans laquelle vous voulez installer le centre de gestion central.</span><span class="sxs-lookup"><span data-stu-id="61304-118">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="61304-119">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="61304-119">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="61304-120">Pour créer la nouvelle Banque centrale de gestion dans la base de données SQL Server 2013 de Lync Server, dans Lync Server Management Shell, tapez:</span><span class="sxs-lookup"><span data-stu-id="61304-120">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="61304-121">Vérifiez que l’état du service **frontal de Lync Server** est **démarré**.</span><span class="sxs-lookup"><span data-stu-id="61304-121">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="61304-122">Pour préparer un serveur frontal Standard Edition</span><span class="sxs-lookup"><span data-stu-id="61304-122">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="61304-123">Sur le serveur frontal de Lync Server 2013 Standard Edition sur lequel vous voulez déplacer le serveur de gestion centralisée: Connectez-vous à l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="61304-123">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="61304-124">Ouvrez l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="61304-124">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="61304-125">Dans l’Assistant Déploiement de Lync Server, cliquez sur **préparer le premier serveur Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="61304-125">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="61304-126">Sur la page **exécution des commandes** , SQL Server Express est installé en tant que serveur de gestion central.</span><span class="sxs-lookup"><span data-stu-id="61304-126">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="61304-127">Des règles de pare-feu nécessaires sont créées.</span><span class="sxs-lookup"><span data-stu-id="61304-127">Necessary firewall rules are created.</span></span> <span data-ttu-id="61304-128">Lorsque l’installation de la base de données et du logiciel requis est terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="61304-128">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61304-129">L’installation initiale risque de prendre un certain temps sans qu’aucune mise à jour ne s’affiche à l’écran de synthèse de la sortie de commande.</span><span class="sxs-lookup"><span data-stu-id="61304-129">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="61304-130">Le problème est dû à l’installation de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="61304-130">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="61304-131">Si vous avez besoin de surveiller l’installation de la base de données, utilisez le gestionnaire des tâches pour contrôler la configuration.</span><span class="sxs-lookup"><span data-stu-id="61304-131">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="61304-132">Pour créer la nouvelle Banque centrale de gestion sur le serveur frontal Lync Server 2013 Standard Edition, dans Lync Server Management Shell, tapez:</span><span class="sxs-lookup"><span data-stu-id="61304-132">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="61304-133">Vérifiez que l’état du service **frontal de Lync Server** est **démarré**.</span><span class="sxs-lookup"><span data-stu-id="61304-133">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="61304-134">Pour déplacer le serveur de gestion centralisée de Lync Server 2010 vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61304-134">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="61304-135">Sur le serveur Lync Server 2013 qui sera le serveur de gestion central: Connectez-vous à l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="61304-135">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="61304-136">Vous devez également avoir les autorisations et les droits d’utilisateur de l’administrateur de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="61304-136">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="61304-137">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="61304-137">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="61304-138">Dans Lync Server Management Shell, tapez:</span><span class="sxs-lookup"><span data-stu-id="61304-138">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="61304-139">Si <CODE>Enable-CsTopology</CODE> ce n’est pas le cas, résolvez le problème empêchant l’exécution de la commande avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="61304-139">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="61304-140">Si <STRONG>Enable-CsTopology</STRONG> ne fonctionne pas, le déplacement échoue et il peut arriver que votre topologie soit dans un État où il n’y a aucune banque centrale de gestion.</span><span class="sxs-lookup"><span data-stu-id="61304-140">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="61304-141">Sur le serveur frontal ou le pool frontal Lync Server 2013, dans Lync Server Management Shell, tapez:</span><span class="sxs-lookup"><span data-stu-id="61304-141">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="61304-142">Lync Server Management Shell affiche les serveurs, les magasins de fichiers, les magasins de bases de données et les points de connexion de service de l’état actuel et de l’État proposé.</span><span class="sxs-lookup"><span data-stu-id="61304-142">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="61304-143">Lisez attentivement les informations et confirmez qu’il s’agit de la source et de la destination attendues.</span><span class="sxs-lookup"><span data-stu-id="61304-143">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="61304-144">Tapez **Y** pour continuer ou **N** pour arrêter le déplacement.</span><span class="sxs-lookup"><span data-stu-id="61304-144">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="61304-145">Examinez les avertissements ou erreurs générés par la commande **Move-CsManagementServer** et résolvez-les.</span><span class="sxs-lookup"><span data-stu-id="61304-145">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="61304-146">Sur le serveur Lync Server 2013, ouvrez l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="61304-146">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="61304-147">Dans l’Assistant Déploiement de Lync Server, cliquez sur **installer ou mettre à jour le système de serveur Lync**, cliquez sur **étape 2: installer ou supprimer des composants Lync Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="61304-147">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="61304-148">Sur le serveur Lync Server 2010, ouvrez l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="61304-148">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="61304-149">Dans l’Assistant Déploiement de Lync Server, cliquez sur **installer ou mettre à jour le système de serveur Lync**, cliquez sur **étape 2: installer ou supprimer des composants Lync Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="61304-149">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="61304-150">Redémarrez le serveur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61304-150">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="61304-151">Ceci est requis en raison d’une modification d’appartenance de groupe à une base de données du serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="61304-151">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="61304-152">Pour vérifier que la réplication avec le nouveau magasin central de gestion est en cours, dans Lync Server Management Shell, tapez:</span><span class="sxs-lookup"><span data-stu-id="61304-152">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61304-153">La réplication risque de prendre un certain temps pour mettre à jour tous les réplicas actuels.</span><span class="sxs-lookup"><span data-stu-id="61304-153">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="61304-154">Pour supprimer les fichiers du store de la gestion centrale de Lync Server 2010 après un déplacement</span><span class="sxs-lookup"><span data-stu-id="61304-154">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="61304-155">Sur Lync Server 2010 Server: Connectez-vous à l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="61304-155">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="61304-156">Vous devez également avoir les autorisations et les droits d’utilisateur de l’administrateur de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="61304-156">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="61304-157">Ouvrez Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="61304-157">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="61304-158">Ne continuez pas la suppression des fichiers de base de données précédents tant que la réplication n’est pas terminée et qu’elle est stable.</span><span class="sxs-lookup"><span data-stu-id="61304-158">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="61304-159">Si vous supprimez les fichiers avant de procéder à la réplication, vous désactiverez le processus de réplication et laissons le serveur de gestion central nouvellement déplacé dans un état inconnu.</span><span class="sxs-lookup"><span data-stu-id="61304-159">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="61304-160">Utilisez l’applet de connexion <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> pour vérifier l’état de la réplication.</span><span class="sxs-lookup"><span data-stu-id="61304-160">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="61304-161">Pour supprimer les fichiers de base de données du magasin de gestion centrale du serveur de gestion central de Lync Server 2010, tapez:</span><span class="sxs-lookup"><span data-stu-id="61304-161">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="61304-162">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="61304-162">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="61304-163">Où le \<FQDN de SQL Server\> est le serveur principal Lync Server 2010 dans un déploiement Enterprise Edition ou le nom de domaine complet (FQDN) du serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="61304-163">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

