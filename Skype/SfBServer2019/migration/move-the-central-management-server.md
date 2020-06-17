---
title: Déplacer le serveur de gestion centralisée
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après avoir effectué une migration vers Skype entreprise Server 2019, vous devez déplacer le serveur de gestion centralisée vers le serveur frontal ou le pool Skype entreprise Server 2019 avant de pouvoir supprimer le serveur hérité.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752466"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="60838-103">Déplacer le serveur de gestion centralisée hérité vers Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="60838-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="60838-104">Après avoir effectué la migration vers Skype entreprise Server 2019 et avant de pouvoir supprimer le serveur hérité, vous devez déplacer le serveur de gestion centralisée vers le serveur ou le pool de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="60838-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="60838-105">Le serveur de gestion centralisée est un système de réplication maître/multiple unique, dans lequel la copie en lecture/écriture de la base de données est conservée par le serveur frontal qui contient le serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="60838-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="60838-106">Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion centralisée, dispose d’une copie en lecture seule des données du magasin central de gestion dans la base de données SQL Server (nommée RTCLOCAL par défaut) installée sur l’ordinateur lors de l’installation et du déploiement.</span><span class="sxs-lookup"><span data-stu-id="60838-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="60838-107">La base de données locale reçoit les mises à jour de réplica par le biais de l’agent réplicateur de réplicas de Skype entreprise qui s’exécute en tant que service sur tous les ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="60838-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="60838-108">Le nom de la base de données réelle sur le serveur de gestion centralisée et le réplica local est XDS, composé des fichiers XDS. mdf et XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="60838-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="60838-109">L’emplacement de la base de données maître est référencé par un point de contrôle de service (SCP) dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="60838-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="60838-110">Tous les outils qui utilisent le serveur de gestion centralisée pour gérer et configurer Skype entreprise Server utilisent le SCP pour localiser le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="60838-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="60838-111">Une fois que vous avez réussi à déplacer le serveur de gestion centralisée, vous devez supprimer les bases de données du serveur de gestion centralisée à partir du serveur frontal d’origine.</span><span class="sxs-lookup"><span data-stu-id="60838-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="60838-112">Pour plus d’informations sur la suppression des bases de données du serveur de gestion centralisée, consultez [la rubrique Remove the SQL Server Database for a front end pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="60838-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="60838-113">Vous utilisez l’applet de commande Windows PowerShell **Move-CsManagementServer** dans Skype for Business Server Management Shell pour déplacer la base de données de la base de données SQL Server héritée vers la base de données sql Server 2019 de Skype entreprise Server, puis mettre à jour le point de gestion de la mise à niveau vers l’emplacement du serveur de gestion centralisée de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="60838-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="60838-114">Utilisez les procédures de cette section pour préparer les serveurs frontaux Skype entreprise Server 2019 avant de déplacer le serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="60838-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="60838-115">Pour préparer un pool frontal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="60838-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="60838-116">Dans le pool frontal Skype entreprise Server 2019 Enterprise Edition où vous voulez déplacer le serveur de gestion centralisée, ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="60838-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="60838-117">Vous devez également disposer des droits et des autorisations d’utilisateur sysadmin de la base de données SQL Server sur la base de données où vous souhaitez installer le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="60838-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="60838-118">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="60838-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="60838-119">Pour créer le nouveau magasin central de gestion dans la base de données de Skype entreprise Server 2019 de la base de données SQL Server, dans Skype entreprise Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="60838-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="60838-120">Vérifiez que l’état du service **frontal Skype entreprise Server** est **démarré**.</span><span class="sxs-lookup"><span data-stu-id="60838-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="60838-121">Pour préparer un serveur frontal Standard Edition</span><span class="sxs-lookup"><span data-stu-id="60838-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="60838-122">Sur le serveur frontal Skype entreprise Server 2019 Standard Edition où vous voulez déplacer le serveur de gestion centralisée, ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="60838-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="60838-123">Ouvrez l’Assistant Déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="60838-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="60838-124">Dans l’Assistant Déploiement de Skype entreprise Server, cliquez sur **préparer d’abord le serveur Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="60838-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="60838-125">Sur la page **exécution de commandes** , SQL Server Express est installé en tant que serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="60838-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="60838-126">Les règles de pare-feu nécessaires sont créées.</span><span class="sxs-lookup"><span data-stu-id="60838-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="60838-127">Lorsque l’installation de la base de données et des logiciels prérequis est terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="60838-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="60838-128">L’installation initiale peut durer un certain temps sans que les mises à jour ne soient visibles sur l’écran récapitulatif des résultats de la commande.</span><span class="sxs-lookup"><span data-stu-id="60838-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="60838-129">Ceci est dû à l’installation de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="60838-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="60838-130">Pour surveiller l’installation de la base de données, utilisez le Gestionnaire des tâches.</span><span class="sxs-lookup"><span data-stu-id="60838-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="60838-131">Pour créer le nouveau magasin central de gestion sur le serveur frontal Skype entreprise Server 2019 Standard Edition, dans Skype entreprise Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="60838-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="60838-132">Vérifiez que l’état du service **frontal Skype entreprise Server** est **démarré**.</span><span class="sxs-lookup"><span data-stu-id="60838-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="60838-133">Pour déplacer le serveur de gestion centralisée des installations héritées vers Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="60838-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="60838-134">Sur le serveur Skype entreprise Server 2019 qui sera le serveur de gestion centralisée, connectez-vous à l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="60838-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="60838-135">Vous devez aussi disposer des droits et autorisation d’administrateur système sur la base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="60838-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="60838-136">Ouvrez Skype entreprise Server Management Shell (exécuter en tant qu’administrateur).</span><span class="sxs-lookup"><span data-stu-id="60838-136">Open Skype for Business Server Management Shell (run as administrator).</span></span>
    
3. <span data-ttu-id="60838-137">Dans Skype entreprise Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="60838-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="60838-138">Si ce `Enable-CsTopology` n’est pas le cas, résolvez le problème en empêchant la commande de se terminer avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="60838-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="60838-139">Si **Enable-CsTopology** ne réussit pas, le déplacement échoue et il peut laisser votre topologie dans un État où il n’existe pas de magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="60838-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="60838-140">Sur le serveur frontal ou le pool frontal Skype entreprise Server 2019, dans Skype entreprise Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="60838-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. <span data-ttu-id="60838-141">Skype entreprise Server Management Shell affiche les serveurs, les magasins de fichiers, les magasins de bases de données et les points de connexion au service de l’état actuel et de l’État proposé.</span><span class="sxs-lookup"><span data-stu-id="60838-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="60838-142">Lisez soigneusement les informations et confirmez qu’il s’agit de la source et de la destination prévues.</span><span class="sxs-lookup"><span data-stu-id="60838-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="60838-143">Tapez **Y** pour continuer, ou **N** pour cesser le déplacement.</span><span class="sxs-lookup"><span data-stu-id="60838-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="60838-144">Examinez l’ensemble des erreurs et des avertissements générés par la commande **Move-CsManagementServer** et corrigez-les.</span><span class="sxs-lookup"><span data-stu-id="60838-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="60838-145">Sur le serveur Skype entreprise Server 2019, ouvrez l’Assistant Déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="60838-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="60838-146">Dans l’Assistant Déploiement de Skype entreprise Server, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, cliquez sur **étape 2 : installer ou supprimer des composants Skype entreprise Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="60838-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="60838-147">Sur le serveur d’installation hérité, ouvrez l’Assistant déploiement.</span><span class="sxs-lookup"><span data-stu-id="60838-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="60838-148">Dans l’Assistant Déploiement de Skype entreprise Server, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, cliquez sur **étape 2 : installer ou supprimer des composants Skype entreprise Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="60838-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="60838-149">Redémarrez le serveur Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="60838-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="60838-150">Ceci est nécessaire en raison d’une modification de l’appartenance au groupe vers la base de données du serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="60838-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="60838-151">Pour confirmer que la réplication avec le nouveau magasin central de gestion est en cours, dans Skype entreprise Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="60838-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="60838-152">La réplication peut prendre un certain temps pour mettre à jour tous les réplicas.</span><span class="sxs-lookup"><span data-stu-id="60838-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="60838-153">Pour supprimer les fichiers du magasin central de gestion d’installation héritée après un déplacement</span><span class="sxs-lookup"><span data-stu-id="60838-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="60838-154">Sur le serveur d’installation hérité, ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="60838-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="60838-155">Vous devez aussi disposer des droits et autorisation d’administrateur système sur la base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="60838-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="60838-156">Ouvrir Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="60838-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="60838-157">Ne procédez pas à la suppression des fichiers de base de données précédents avant que la réplication ne soit terminée et stable.</span><span class="sxs-lookup"><span data-stu-id="60838-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="60838-158">Si vous supprimez les fichiers avant de terminer la réplication, vous interrompez le processus de réplication et laissez le nouveau serveur de gestion centrale déplacé dans un état inconnu.</span><span class="sxs-lookup"><span data-stu-id="60838-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="60838-159">Utilisez l’applet de commande **Get-CsManagementStoreReplicationStatus** pour confirmer le statut de réplication.</span><span class="sxs-lookup"><span data-stu-id="60838-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="60838-160">Pour supprimer les fichiers de base de données du magasin central de gestion du serveur de gestion centralisée d’installation héritée, tapez :</span><span class="sxs-lookup"><span data-stu-id="60838-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="60838-161">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="60838-161">For example:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="60838-162">Où _\<FQDN of SQL Server\>_ est le serveur principal install hérité dans un déploiement Enterprise Edition ou le nom de domaine complet (FQDN) du serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="60838-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

