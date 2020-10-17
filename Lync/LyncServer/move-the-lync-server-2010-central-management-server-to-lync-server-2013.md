---
title: Déplacer le serveur de gestion centralisée Lync Server 2010 vers Lync Server 2013
description: Déplacez le serveur de gestion centralisée Lync Server 2010 vers Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19d53d797375b1eb8fde72f6b999e509b97f85ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571280"
---
# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="4b2b0-103">Déplacer le serveur de gestion centralisée Lync Server 2010 vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b2b0-103">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b2b0-104">_**Dernière modification de la rubrique :** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="4b2b0-104">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="4b2b0-105">Après avoir effectué une migration de Lync Server 2010 vers Lync Server 2013, vous devez déplacer le serveur de gestion centralisée Lync Server 2010 vers le serveur ou pool frontal Lync Server 2013, avant de pouvoir supprimer le serveur Lync Server 2010 hérité.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-105">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="4b2b0-106">Le serveur de gestion centralisée est un système de réplication maître/multiple unique, dans lequel la copie en lecture/écriture de la base de données est conservée par le serveur frontal qui contient le serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-106">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="4b2b0-107">Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion centralisée, dispose d’une copie en lecture seule des données du magasin central de gestion dans la base de données SQL Server (nommée RTCLOCAL par défaut) installée sur l’ordinateur lors de l’installation et du déploiement.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-107">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="4b2b0-108">La base de données locale reçoit les mises à jour de réplica par le biais de l’agent réplicateur de réplicas de Lync Server qui s’exécute en tant que service sur tous les ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-108">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="4b2b0-109">Le nom de la base de données réelle sur le serveur de gestion centralisée et le réplica local est XDS, composé des fichiers XDS. mdf et XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-109">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="4b2b0-110">L’emplacement de la base de données maître est référencé par un point de contrôle de service (SCP) dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-110">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="4b2b0-111">Tous les outils qui utilisent le serveur de gestion centralisée pour gérer et configurer Lync Server utilisent le SCP pour localiser le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-111">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="4b2b0-112">Une fois que vous avez réussi à déplacer le serveur de gestion centralisée, vous devez supprimer les bases de données du serveur de gestion centralisée à partir du serveur frontal d’origine.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-112">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="4b2b0-113">Pour plus d’informations sur la suppression des bases de données du serveur de gestion centralisée, consultez [la rubrique Remove the SQL Server Database for a front end pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="4b2b0-113">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="4b2b0-114">Vous utilisez l’applet de commande Windows PowerShell **Move-CsManagementServer** dans Lync Server Management Shell pour déplacer la base de données de la base de données SQL Server de lync Server 2010 vers la base de données SQL Server de lync Server 2013, puis mettre à jour le point de gestion de la mise à niveau vers l’emplacement du serveur de gestion centralisée lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-114">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="4b2b0-115">Préparation des serveurs frontaux Lync Server 2013 avant le transfert du serveur de gestion centralisée</span><span class="sxs-lookup"><span data-stu-id="4b2b0-115">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="4b2b0-116">Utilisez les procédures de cette section pour préparer les serveurs frontaux Lync Server 2013 avant de déplacer le serveur de gestion centralisée Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-116">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="4b2b0-117">Pour préparer un pool frontal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="4b2b0-117">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="4b2b0-118">Sur le pool frontal Lync Server 2013 Enterprise Edition où vous voulez déplacer le serveur de gestion centralisée : Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="4b2b0-118">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="4b2b0-119">Vous devez également disposer des droits et des autorisations d’utilisateur sysadmin de la base de données SQL Server sur la base de données où vous souhaitez installer le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-119">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="4b2b0-120">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-120">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="4b2b0-121">Pour créer le nouveau magasin central de gestion dans la base de données SQL Server de Lync Server 2013, dans Lync Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="4b2b0-121">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="4b2b0-122">Confirmez que le statut du service du **Serveur principal Lync Server** est **Démarré**.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-122">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="4b2b0-123">Pour préparer un serveur frontal Standard Edition</span><span class="sxs-lookup"><span data-stu-id="4b2b0-123">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="4b2b0-124">Sur le serveur frontal Lync Server 2013 Standard Edition où vous voulez déplacer le serveur de gestion centralisée : Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="4b2b0-124">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="4b2b0-125">Ouvrez l’Assistant Déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-125">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="4b2b0-126">Dans l’Assistant Déploiement Lync Server, cliquez sur **préparer d’abord le serveur Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-126">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="4b2b0-127">Sur la page **exécution de commandes** , SQL Server Express est installé en tant que serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-127">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="4b2b0-128">Les règles de pare-feu nécessaires sont créées.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-128">Necessary firewall rules are created.</span></span> <span data-ttu-id="4b2b0-129">Lorsque l’installation de la base de données et des logiciels prérequis est terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-129">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b2b0-130">L’installation initiale peut durer un certain temps sans que les mises à jour ne soient visibles sur l’écran récapitulatif des résultats de la commande.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-130">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="4b2b0-131">Ceci est dû à l’installation de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-131">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="4b2b0-132">Pour surveiller l’installation de la base de données, utilisez le Gestionnaire des tâches.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-132">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="4b2b0-133">Pour créer le nouveau magasin central de gestion sur le serveur frontal Lync Server 2013 Standard Edition, dans Lync Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="4b2b0-133">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="4b2b0-134">Confirmez que le statut du service du **Serveur principal Lync Server** est **Démarré**.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-134">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="4b2b0-135">Pour déplacer le serveur de gestion centralisée Lync Server 2010 vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b2b0-135">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="4b2b0-136">Sur le serveur Lync Server 2013 qui sera le serveur de gestion centralisée : Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="4b2b0-136">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="4b2b0-137">Vous devez aussi disposer des droits et autorisation d’administrateur système sur la base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-137">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="4b2b0-138">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-138">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="4b2b0-139">Dans Lync Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="4b2b0-139">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4b2b0-140">Si ce <CODE>Enable-CsTopology</CODE> n’est pas le cas, résolvez le problème en empêchant la commande de se terminer avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-140">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="4b2b0-141">Si <STRONG>Enable-CsTopology</STRONG> ne réussit pas, le déplacement échoue et il peut laisser votre topologie dans un État où il n’existe pas de magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-141">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="4b2b0-142">Sur le serveur frontal ou le pool frontal Lync Server 2013, dans Lync Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="4b2b0-142">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="4b2b0-143">Lync Server Management Shell affiche les serveurs, les magasins de fichiers, les magasins de bases de données et les points de connexion de service de l’état actuel et de l’État proposé.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-143">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="4b2b0-144">Lisez soigneusement les informations et confirmez qu’il s’agit de la source et de la destination prévues.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-144">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="4b2b0-145">Tapez **Y** pour continuer, ou **N** pour cesser le déplacement.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-145">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="4b2b0-146">Examinez l’ensemble des erreurs et des avertissements générés par la commande **Move-CsManagementServer** et corrigez-les.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-146">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="4b2b0-147">Sur le serveur Lync Server 2013, ouvrez l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-147">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="4b2b0-148">Dans l’Assistant Déploiement de Lync Server, cliquez sur **installer ou mettre à jour le système Lync Server**, cliquez sur **étape 2 : installer ou supprimer des composants Lync Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-148">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="4b2b0-149">Sur le serveur Lync Server 2010, ouvrez l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-149">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="4b2b0-150">Dans l’Assistant Déploiement de Lync Server, cliquez sur **installer ou mettre à jour le système Lync Server**, cliquez sur **étape 2 : installer ou supprimer des composants Lync Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-150">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="4b2b0-151">Redémarrez le serveur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-151">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="4b2b0-152">Ceci est nécessaire en raison d’une modification de l’appartenance au groupe vers la base de données du serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-152">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="4b2b0-153">Pour confirmer que la réplication avec le nouveau magasin central de gestion est en cours, dans Lync Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="4b2b0-153">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b2b0-154">La réplication peut prendre un certain temps pour mettre à jour tous les réplicas.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-154">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="4b2b0-155">Pour supprimer les fichiers du magasin central de gestion Lync Server 2010 après un déplacement</span><span class="sxs-lookup"><span data-stu-id="4b2b0-155">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="4b2b0-156">Sur le serveur Lync Server 2010 : Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="4b2b0-156">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="4b2b0-157">Vous devez aussi disposer des droits et autorisation d’administrateur système sur la base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-157">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="4b2b0-158">Ouvrir Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="4b2b0-158">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4b2b0-159">Ne procédez pas à la suppression des fichiers de base de données précédents avant que la réplication ne soit terminée et stable.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-159">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="4b2b0-160">Si vous supprimez les fichiers avant de terminer la réplication, vous interrompez le processus de réplication et laissez le nouveau serveur de gestion centrale déplacé dans un état inconnu.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-160">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="4b2b0-161">Utilisez l’applet de commande <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> pour confirmer le statut de réplication.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-161">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="4b2b0-162">Pour supprimer les fichiers de base de données du magasin central de gestion du serveur de gestion centralisée Lync Server 2010, tapez :</span><span class="sxs-lookup"><span data-stu-id="4b2b0-162">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="4b2b0-163">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4b2b0-163">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="4b2b0-164">Où \<FQDN of SQL Server\> est le serveur principal Lync server 2010 dans un déploiement Enterprise Edition ou le nom de domaine complet (FQDN) du serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-164">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

