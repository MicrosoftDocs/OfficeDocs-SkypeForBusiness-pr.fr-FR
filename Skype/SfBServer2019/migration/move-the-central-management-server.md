---
title: Déplacer le serveur d’administration centrale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après avoir migré vers Skype pour Business Server 2019, vous devez déplacer le serveur d’administration centrale à le Skype pour Business Server 2019 serveur frontal ou un pool, avant de pouvoir supprimer le serveur hérité.
ms.openlocfilehash: dc85548a3c81e55267bc0ed3a32e53860e4bce09
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231573"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="54886-103">Atteindre le serveur de gestion centralisée hérité Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="54886-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="54886-104">Après avoir migré vers Skype pour Business Server 2019, et avant de pouvoir supprimer le serveur hérité, vous devez déplacer le serveur de gestion centralisée vers le Skype pour Business Server 2019 serveur frontal ou le pool.</span><span class="sxs-lookup"><span data-stu-id="54886-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="54886-105">Le serveur de gestion centrale est un système maître/plusieurs réplicas, où la copie en lecture/écriture de la base de données est détenue par le serveur frontal qui contient le serveur d’administration centrale.</span><span class="sxs-lookup"><span data-stu-id="54886-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="54886-106">Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion centralisée, dispose d’une copie en lecture seule des données du magasin Central de gestion de la base de SQL Server (appelée RTCLOCAL par défaut) installée sur l’ordinateur pendant l’installation et déploiement.</span><span class="sxs-lookup"><span data-stu-id="54886-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="54886-107">La base de données local reçoit des mises à jour de réplica par l’entremise du Skype pour Business Server Agent réplica du réplicateur d’utilisateurs qui s’exécute en tant que service sur tous les ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="54886-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="54886-108">Le nom de la base de données sur le serveur de gestion centrale et du réplica local est XDS, qui est composée des fichiers xds.mdf et xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="54886-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="54886-109">L’emplacement de la base de données master est référencé par un point de contrôle de service (SCP) dans les Services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="54886-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="54886-110">Tous les outils qui utilisent le serveur d’administration centrale pour gérer et configurer Skype pour Business Server utilisent le SCP pour localiser le magasin Central de gestion.</span><span class="sxs-lookup"><span data-stu-id="54886-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="54886-111">Une fois que vous avez déplacé le serveur d’administration centrale, vous devez supprimer les bases de données du serveur de gestion centralisée depuis le serveur frontal d’origine.</span><span class="sxs-lookup"><span data-stu-id="54886-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="54886-112">Pour plus d’informations sur la suppression des bases de données serveur de gestion centralisée, voir [Supprimer la base de données SQL Server pour un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="54886-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="54886-113">Vous utilisez l’applet de commande Windows PowerShell **Move-CsManagementServer** dans la Skype pour Business Server Management Shell pour déplacer la base de données à partir de la base de données de SQL Server hérité d’installer le Skype pour la base de données Business Server 2019 SQL Server, puis mettre à jour le SCP pour pointer vers le Skype pour l’emplacement du serveur de gestion centralisée Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="54886-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="54886-114">Utilisez les procédures de cette section pour préparer le Skype Business Server 2019 serveurs frontaux avant de déplacer le serveur d’administration centrale.</span><span class="sxs-lookup"><span data-stu-id="54886-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="54886-115">Pour préparer un pool frontal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="54886-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="54886-116">Sur Skype pour Business Server 2019 Enterprise Edition un pool frontal où vous voulez déplacer le serveur d’administration centrale, ouvrez une session sur l’ordinateur où le Skype pour Business Server Management Shell est installé en tant que membre de la \*\*RTCUniversalServerAdmins \*\*groupe.</span><span class="sxs-lookup"><span data-stu-id="54886-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="54886-117">Vous devez également droits sysadmin de base de données SQL Server et les autorisations sur la base de données où vous souhaitez installer le magasin Central de gestion.</span><span class="sxs-lookup"><span data-stu-id="54886-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="54886-118">Ouvrez le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="54886-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="54886-119">Pour créer un nouveau magasin Central de gestion dans le Skype pour la base de données Business Server 2019 SQL Server, dans la Skype pour Business Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="54886-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="54886-120">Vérifiez que l’état du service **Skype pour Business Server frontal** est **démarré**.</span><span class="sxs-lookup"><span data-stu-id="54886-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="54886-121">Pour préparer un serveur Standard Edition serveur frontal</span><span class="sxs-lookup"><span data-stu-id="54886-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="54886-122">Sur Skype pour Business Server 2019 Standard Edition serveur frontal où vous voulez déplacer le serveur d’administration centrale, ouvrez une session sur l’ordinateur où le Skype pour Business Server Management Shell est installé en tant que membre de la \*\*RTCUniversalServerAdmins \*\*groupe.</span><span class="sxs-lookup"><span data-stu-id="54886-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="54886-123">Ouvrez le Skype pour l’Assistant de déploiement Business Server.</span><span class="sxs-lookup"><span data-stu-id="54886-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="54886-124">Dans Skype pour l’Assistant de déploiement Business Server, cliquez sur **préparer premier serveur Standard Edition server**.</span><span class="sxs-lookup"><span data-stu-id="54886-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="54886-125">Dans la page **Exécution de commandes** , SQL Server Express est installé en tant que le serveur d’administration centrale.</span><span class="sxs-lookup"><span data-stu-id="54886-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="54886-126">Règles de pare-feu nécessaires sont créés.</span><span class="sxs-lookup"><span data-stu-id="54886-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="54886-127">Une fois l’installation de la base de données et les logiciels prérequis terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="54886-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="54886-128">L’installation initiale peut prendre un certain temps avec aucune mise à jour visible à l’écran de résumé de sortie de commande.</span><span class="sxs-lookup"><span data-stu-id="54886-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="54886-129">Il s’agit en raison de l’installation de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="54886-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="54886-130">Si vous avez besoin contrôler l’installation de la base de données, utilisez le Gestionnaire des tâches pour surveiller le programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="54886-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="54886-131">Pour créer le nouveau magasin Central de gestion sur le Skype pour Business Server 2019 Standard Edition serveur frontal, le Skype pour Business Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="54886-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="54886-132">Vérifiez que l’état du service **Skype pour Business Server frontal** est **démarré**.</span><span class="sxs-lookup"><span data-stu-id="54886-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="54886-133">Pour déplacer que hérité installe le serveur de gestion centralisée pour Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="54886-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="54886-134">Sur Skype pour serveur Business Server 2019 qui sera le serveur de gestion centrale, ouvrez une session l’ordinateur où le Skype pour Business Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="54886-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="54886-135">Vous devez également les droits administrateur de base de données SQL Server et les autorisations.</span><span class="sxs-lookup"><span data-stu-id="54886-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="54886-136">Ouvrez Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="54886-136">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="54886-137">Dans Skype pour Business Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="54886-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="54886-138">Si `Enable-CsTopology` n’a pas réussi, résoudre le problème qui empêchent la commande avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="54886-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="54886-139">Si **Enable-CsTopology** ne réussit pas, le déplacement échoue et il peut laisser votre topologie dans un état où il n’y a aucun magasin Central de gestion.</span><span class="sxs-lookup"><span data-stu-id="54886-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="54886-140">Sur la Skype pour un pool frontal ou Business Server 2019 serveur frontal, dans le Skype pour Business Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="54886-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Move-CsManagementServer
   ```

5. <span data-ttu-id="54886-141">Skype pour Business Server Management Shell affiche les serveurs, magasins de fichiers, les magasins de base de données et les points de connexion de service de l’état actuel et l’état proposé.</span><span class="sxs-lookup"><span data-stu-id="54886-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="54886-142">Lisez attentivement les informations et confirmez qu’il s’agit de la destination source et destination.</span><span class="sxs-lookup"><span data-stu-id="54886-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="54886-143">Tapez **Y** pour continuer ou **N** pour arrêter le déplacement.</span><span class="sxs-lookup"><span data-stu-id="54886-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="54886-144">Passez en revue les avertissements ou erreurs générées par la commande **Move-CsManagementServer** et résolvez-les.</span><span class="sxs-lookup"><span data-stu-id="54886-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="54886-145">Sur Skype pour Business Server 2019 server, ouvrez le Skype pour l’Assistant de déploiement Business Server.</span><span class="sxs-lookup"><span data-stu-id="54886-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="54886-146">Dans Skype pour l’Assistant de déploiement Business Server, cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**, cliquez sur **étape 2 : installer ou supprimer des Skype pour les composants du serveur Business**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur \*\*Terminer \*\*.</span><span class="sxs-lookup"><span data-stu-id="54886-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="54886-147">Sur hérité installer server, ouvrez l’Assistant déploiement.</span><span class="sxs-lookup"><span data-stu-id="54886-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="54886-148">Dans Skype pour l’Assistant de déploiement Business Server, cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**, cliquez sur **étape 2 : installer ou supprimer des Skype pour les composants du serveur Business**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur \*\*Terminer \*\*.</span><span class="sxs-lookup"><span data-stu-id="54886-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="54886-149">Redémarrez le Skype pour serveur Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="54886-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="54886-150">Cela est nécessaire en raison d’une modification de l’appartenance de groupe pour la base de données du serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="54886-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="54886-151">Pour confirmer que la réplication avec la gestion centralisée nouveau magasin est en cours, dans le Skype pour Business Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="54886-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="54886-152">La réplication peut prendre un certain temps pour mettre à jour tous les réplicas.</span><span class="sxs-lookup"><span data-stu-id="54886-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="54886-153">Pour supprimer hérité pour installer les fichiers du magasin Central de gestion après un déplacement</span><span class="sxs-lookup"><span data-stu-id="54886-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="54886-154">Sur hérité installation du serveur, ouvrez une session sur l’ordinateur où le Skype pour Business Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="54886-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="54886-155">Vous devez également les droits administrateur de base de données SQL Server et les autorisations.</span><span class="sxs-lookup"><span data-stu-id="54886-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="54886-156">Ouvrez Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="54886-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="54886-157">Ne poursuivez pas la suppression des fichiers de base de données précédente jusqu'à ce que la réplication est terminée et est stable.</span><span class="sxs-lookup"><span data-stu-id="54886-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="54886-158">Si vous supprimez les fichiers avant la fin de la réplication, vous interrompre le processus de réplication et laisser le serveur de gestion centralisée déplacé dans un état inconnu.</span><span class="sxs-lookup"><span data-stu-id="54886-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="54886-159">Utilisez l’applet de commande **Get-CsManagementStoreReplicationStatus** pour vérifier l’état de réplication.</span><span class="sxs-lookup"><span data-stu-id="54886-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="54886-160">Pour supprimer les fichiers de base de données du magasin Central de gestion de l’installation héritée de serveur de gestion centralisée, tapez :</span><span class="sxs-lookup"><span data-stu-id="54886-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="54886-161">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="54886-161">For example:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="54886-162">Où les _ \<nom de domaine complet de SQL Server\> _ est hérité soit installer un serveur principal dans un déploiement Enterprise Edition ou le nom de domaine complet du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="54886-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

