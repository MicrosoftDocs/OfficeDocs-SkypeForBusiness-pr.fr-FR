---
title: Déployer le tableau de bord de qualité des appels pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Résumé : Découvrez le processus de déploiement du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 5879c4a99eec8471763e0fccc3a4886be660dbb6
ms.sourcegitcommit: 54cbcf917d9663e6aa9760d7399b36c00d66478c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "42840158"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="26f19-104">Déployer le tableau de bord de qualité des appels pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="26f19-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="26f19-105">**Résumé :** Découvrez le processus de déploiement du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="26f19-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="26f19-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="26f19-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="26f19-107">Présentation du déploiement</span><span class="sxs-lookup"><span data-stu-id="26f19-107">Deployment Overview</span></span>

<span data-ttu-id="26f19-108">Le tableau de bord de qualité des appels (CQD) se compose de trois composants principaux :</span><span class="sxs-lookup"><span data-stu-id="26f19-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="26f19-109">**Base de données d’archivage**, dans laquelle les données de qualité de l’expérience (QoE) sont répliquées et stockées.</span><span class="sxs-lookup"><span data-stu-id="26f19-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="26f19-110">**Cube**, où les données de la base de données d’archivage QoE sont regroupées pour un accès optimisé et rapide.</span><span class="sxs-lookup"><span data-stu-id="26f19-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="26f19-111">**Portail**, où les utilisateurs peuvent facilement interroger et visualiser les données QoE.</span><span class="sxs-lookup"><span data-stu-id="26f19-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Composants CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="26f19-113">Le processus de configuration de l’archive QoE implique la création de la base de données d’archivage QoE, le déploiement d’une procédure stockée SQL Server qui déplace les données de la base de données de mesures QoE source vers la base de données d’archivage QoE et la configuration du travail de l’agent SQL Server pour l’exécution de l’enregistrement procédure à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="26f19-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="26f19-114">Déploiement de cube obtient des informations de l’utilisateur sur l’emplacement où se trouve l’archive QoE, déploie le cube et configure un travail d’agent SQL Server régulier qui actualisera le cube à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="26f19-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="26f19-115">L’installation du portail crée une base de données de référentiel qui stocke le mappage des utilisateurs CQD sur les rapports/requêtes de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="26f19-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="26f19-116">Il configure ensuite une application Web IIS qui est le tableau de bord dans lequel les utilisateurs peuvent afficher un ensemble prédéfini de rapports, ainsi que personnaliser et créer leurs propres requêtes pour visualiser les données à partir du cube.</span><span class="sxs-lookup"><span data-stu-id="26f19-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="26f19-117">L’installation du portail crée deux applications Web supplémentaires qui exposent les API permettant aux utilisateurs d’accéder par programme au référentiel et au cube.</span><span class="sxs-lookup"><span data-stu-id="26f19-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="26f19-118">(Ces API sont également utilisées en interne par le tableau de bord.)</span><span class="sxs-lookup"><span data-stu-id="26f19-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="26f19-119">**Étape**</span><span class="sxs-lookup"><span data-stu-id="26f19-119">**Phase**</span></span>|<span data-ttu-id="26f19-120">**Étapes**</span><span class="sxs-lookup"><span data-stu-id="26f19-120">**Steps**</span></span>|<span data-ttu-id="26f19-121">**Rôles et appartenance aux groupes**</span><span class="sxs-lookup"><span data-stu-id="26f19-121">**Roles and group membership**</span></span>|<span data-ttu-id="26f19-122">**Documentation**</span><span class="sxs-lookup"><span data-stu-id="26f19-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="26f19-123">Installez le matériel et les logiciels prérequis.</span><span class="sxs-lookup"><span data-stu-id="26f19-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="26f19-124">Déterminez la configuration de CQD, puis choisissez un serveur SQL Server à partir duquel effectuer l’installation.</span><span class="sxs-lookup"><span data-stu-id="26f19-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="26f19-125">Utilisateur du domaine membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="26f19-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="26f19-126">Section « conditions préalables à l’installation » dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="26f19-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="26f19-127">Installez CQD.</span><span class="sxs-lookup"><span data-stu-id="26f19-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="26f19-128">Exécutez le fichier MSI en suivant le document de déploiement.</span><span class="sxs-lookup"><span data-stu-id="26f19-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="26f19-129">Pour effectuer la configuration, le compte d’installation doit être un utilisateur de domaine membre du groupe Administrateurs local et disposer d’un accès en lecture à la base de données des mesures QoE sur le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="26f19-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="26f19-130">Sections « comptes et étapes de déploiement » dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="26f19-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="26f19-131">Accorder l’accès utilisateur.</span><span class="sxs-lookup"><span data-stu-id="26f19-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="26f19-132">Pour gérer l’autorisation des utilisateurs sur le portail, nous vous recommandons d’utiliser l’autorisation d’URL, qui a été introduite dans IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="26f19-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="26f19-133">Pour plus d’informations, consultez la rubrique [Understanding IIS 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="26f19-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="26f19-134">Utilisateur du domaine membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="26f19-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="26f19-135">Managing User Access for the Portal section dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="26f19-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="26f19-136">Facultatif : fournissez les informations de mappage de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="26f19-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="26f19-137">Remplissez le réseau et créez des tables de mappage dans la base de données d’archivage QoE.</span><span class="sxs-lookup"><span data-stu-id="26f19-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="26f19-138">Un compte avec un accès en écriture à la base de données d’archivage QoE.</span><span class="sxs-lookup"><span data-stu-id="26f19-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="26f19-139">Section « fourniture des informations de sous-réseau » dans la documentation utilisateur.</span><span class="sxs-lookup"><span data-stu-id="26f19-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="26f19-140">Le déploiement du tableau de bord de qualité des appels implique la configuration de l’infrastructure et l’installation du logiciel.</span><span class="sxs-lookup"><span data-stu-id="26f19-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="26f19-141">La procédure suivante décrit le processus.</span><span class="sxs-lookup"><span data-stu-id="26f19-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="26f19-142">Étapes de déploiement</span><span class="sxs-lookup"><span data-stu-id="26f19-142">Deployment Steps</span></span>

1. <span data-ttu-id="26f19-143">Copiez le CallQualityDashboard. msi sur l’ordinateur sur lequel le composant de base de données d’archivage de CQD doit être installé (il s’agit de l’ordinateur sur lequel SQL Server est installé).</span><span class="sxs-lookup"><span data-stu-id="26f19-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="26f19-144">Exécutez le MSI (Windows invite à s’exécuter avec les privilèges d’administrateur).</span><span class="sxs-lookup"><span data-stu-id="26f19-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="26f19-145">Acceptez le CLUF.</span><span class="sxs-lookup"><span data-stu-id="26f19-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="26f19-146">Sélectionnez le dossier de destination où les fichiers associés aux composants de tableau de bord de qualité des appels seront localisés ou accepteront l’emplacement par défaut.</span><span class="sxs-lookup"><span data-stu-id="26f19-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="26f19-147">Sélectionnez toutes les fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="26f19-147">Select all features.</span></span>
    
6. <span data-ttu-id="26f19-148">Sur la page Configuration de l’archive QoE, fournissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="26f19-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="26f19-149">Valeurs **QoE SQL Server :** Nom de l’instance SQL Server où se trouve la base de données de mesures QoE (il s’agit de la source de données).</span><span class="sxs-lookup"><span data-stu-id="26f19-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="26f19-150">**Nom de serveur SQL de l’archive QoE :** Ce champ est en lecture seule et correspond au nom de domaine complet de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="26f19-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="26f19-151">La base de données d’archivage ne peut être installée que sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="26f19-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="26f19-152">**Instance de serveur d’archive QoE SQL Server :** Nom de l’instance SQL Server locale pour laquelle la base de données d’archivage doit être créée.</span><span class="sxs-lookup"><span data-stu-id="26f19-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="26f19-153">Pour utiliser une instance SQL Server par défaut, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="26f19-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="26f19-154">Pour utiliser une instance SQL Server nommée, spécifiez le nom de l’instance (par exemple, le\"nom qui suit ").</span><span class="sxs-lookup"><span data-stu-id="26f19-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="26f19-155">**Base de données d’archivage QoE :** Par défaut, cette option est définie sur « créer une nouvelle base de données ».</span><span class="sxs-lookup"><span data-stu-id="26f19-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="26f19-156">Étant donné que la mise à niveau de la base de données d’archivage n’est pas prise en charge, le seul cas où l’option « utiliser une base de données existante » peut être utilisée est si la base de données d’archivage existante a le même schéma que la build à installer.</span><span class="sxs-lookup"><span data-stu-id="26f19-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="26f19-157">**Répertoire du fichier de base de données :** Chemin d’accès à l’emplacement des fichiers de base de données (. mdf et. ldf) de la base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="26f19-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="26f19-158">Il doit se trouver sur un lecteur (HDD2 dans la configuration matérielle recommandée) distinct du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="26f19-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="26f19-159">Notez que, étant donné que les noms de fichier sont résolus dans l’installation, pour éviter tout conflit potentiel, il est recommandé d’utiliser un répertoire vide sans fichiers.</span><span class="sxs-lookup"><span data-stu-id="26f19-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="26f19-160">**Utiliser plusieurs partitions :** La valeur par défaut est « multiple partition », ce qui nécessite Business Intelligence Edition ou Enterprise Edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26f19-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="26f19-161">Pour Standard Edition, sélectionnez l’option « partition unique ».</span><span class="sxs-lookup"><span data-stu-id="26f19-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="26f19-162">Notez que les performances de traitement de cube peuvent être affectées si une seule partition est utilisée.</span><span class="sxs-lookup"><span data-stu-id="26f19-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="26f19-163">La sélection de l’option utiliser plusieurs partitions ne peut pas être modifiée une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="26f19-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="26f19-164">Pour le modifier, la fonctionnalité de cube doit être désinstallée, puis réinstallée à l’aide de l’option « modifier » dans le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="26f19-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="26f19-165">**Répertoire du fichier de partition :** Chemin d’accès à l’emplacement où les partitions de la base de données d’archivage QoE doivent être placées.</span><span class="sxs-lookup"><span data-stu-id="26f19-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="26f19-166">Il doit se trouver sur un lecteur (HDD3 dans la configuration matérielle recommandée) distinct du lecteur du système d’exploitation et du lecteur des fichiers journaux de base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="26f19-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="26f19-167">Notez que, étant donné que les noms de fichier sont résolus dans l’installation, pour éviter tout conflit potentiel, il est recommandé d’utiliser un répertoire vide sans fichiers.</span><span class="sxs-lookup"><span data-stu-id="26f19-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="26f19-168">**Utilisateur du travail de l’agent SQL &amp; -mot de passe du nom d’utilisateur :** Nom de compte de service de domaine et mot de passe (masqué) qui sera utilisé pour exécuter l’étape « données d’archivage QoE » du travail de l’agent SQL Server (qui exécutera la procédure stockée pour extraire les données de la base de données de valeurs QoE dans la base de données d’archivage, de sorte que ce compte doit disposer d’un accès en lecture à la base de</span><span class="sxs-lookup"><span data-stu-id="26f19-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="26f19-169">Ce compte doit également disposer d’une connexion dans l’instance de SQL Server d’archive QoE).</span><span class="sxs-lookup"><span data-stu-id="26f19-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="26f19-170">Le compte sous lequel l’instance SQL Server est en cours d’exécution, tel que NT SERVICE\MSSQLSERVER, doit disposer d’une autorisation ou d’un accès aux annuaires ci-dessus pour que l’installation réussisse.</span><span class="sxs-lookup"><span data-stu-id="26f19-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="26f19-171">Pour plus d’informations, voir [configurer les autorisations du système de fichiers pour l’accès au moteur de base de données](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="26f19-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="26f19-172">Lorsque vous cliquez sur suivant, le programme d’installation effectue des vérifications préalables et un rapport si des problèmes sont détectés.</span><span class="sxs-lookup"><span data-stu-id="26f19-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="26f19-173">Lorsque toutes les vérifications de conditions préalables sont réussies, le programme d’installation accède à la page Configuration du cube.</span><span class="sxs-lookup"><span data-stu-id="26f19-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="26f19-174">Si le programme d’installation affiche un message d’avertissement indiquant que le service SQL Server Agent pour l’instance SQL Server d’archive QoE n’est pas en cours d’exécution, l’installation peut se poursuivre, mais après l’installation, vérifiez que le service Agent SQL est en cours d’exécution et définissez le type de démarrage sur Automatique afin que la tâche planifiée s’exécute.</span><span class="sxs-lookup"><span data-stu-id="26f19-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="26f19-175">Sur la page Configuration du cube, fournissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="26f19-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="26f19-176">**Nom de serveur SQL de l’archive QoE :** Ce champ est en lecture seule et correspond au nom de domaine complet de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="26f19-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="26f19-177">Le cube ne peut être installé qu’à partir de l’ordinateur disposant d’une base de données d’archivage QoE (Remarque.</span><span class="sxs-lookup"><span data-stu-id="26f19-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="26f19-178">Le cube lui-même peut être installé sur un ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="26f19-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="26f19-179">Voir ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="26f19-179">See below)</span></span>
    
   - <span data-ttu-id="26f19-180">**Instance de serveur d’archive QoE SQL Server :** Nom de l’instance SQL Server où se trouve la base de données d’archive QoE.</span><span class="sxs-lookup"><span data-stu-id="26f19-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="26f19-181">Pour spécifier une instance SQL Server par défaut, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="26f19-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="26f19-182">Pour spécifier une instance nommée de SQL Server, entrez le nom de l’instance (par exemple, le\"nom qui suit ").</span><span class="sxs-lookup"><span data-stu-id="26f19-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="26f19-183">Si le composant d’archive QoE a été sélectionné pour l’installation, ce champ est pré-rempli avec la valeur fournie dans la page Configuration de l’archive QoE.</span><span class="sxs-lookup"><span data-stu-id="26f19-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="26f19-184">**Serveur d’analyse de cube :** Nom de l’instance du service SQL Server Analysis pour lequel le cube doit être créé.</span><span class="sxs-lookup"><span data-stu-id="26f19-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="26f19-185">Il peut s’agir d’un autre ordinateur, mais l’utilisateur qui provient de l’installation doit être membre des administrateurs de serveur de l’instance SQL Server Analysis service cible.</span><span class="sxs-lookup"><span data-stu-id="26f19-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="26f19-186">Pour plus d’informations sur la configuration des autorisations d’administrateur de serveur Analysis Services, consultez la rubrique [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx) .</span><span class="sxs-lookup"><span data-stu-id="26f19-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="26f19-187">**Utiliser plusieurs partitions :** La valeur par défaut est « multiple partition », ce qui nécessite Business Intelligence Edition ou Enterprise Edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26f19-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="26f19-188">Pour Standard Edition, sélectionnez l’option « partition unique ».</span><span class="sxs-lookup"><span data-stu-id="26f19-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="26f19-189">Notez que les performances de traitement de cube peuvent être affectées si une seule partition est utilisée.</span><span class="sxs-lookup"><span data-stu-id="26f19-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="26f19-190">La sélection de l’option utiliser plusieurs partitions ne peut pas être modifiée une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="26f19-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="26f19-191">Pour le modifier, la fonctionnalité de cube doit être désinstallée, puis réinstallée à l’aide de l’option « modifier » dans le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="26f19-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="26f19-192">**Cube user-nom &amp; d’utilisateur mot de passe :** Nom et mot de passe du compte de service de domaine (masqué) qui déclencheront le traitement du cube.</span><span class="sxs-lookup"><span data-stu-id="26f19-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="26f19-193">Si le composant d’archive QoE a été sélectionné pour l’installation, ce champ est pré-rempli avec la valeur fournie sur la page Configuration de l’Archive pour l’utilisateur du travail de l’agent SQL, mais nous vous recommandons de spécifier un autre compte de service de domaine afin que le programme d’installation puisse accorder au privilège le moins requis.</span><span class="sxs-lookup"><span data-stu-id="26f19-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="26f19-194">Lorsque vous cliquez sur suivant, une autre série de validations est effectuée et tout problème est signalé.</span><span class="sxs-lookup"><span data-stu-id="26f19-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="26f19-195">Une fois la validation terminée, le programme d’installation accède à la page Configuration du portail.</span><span class="sxs-lookup"><span data-stu-id="26f19-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="26f19-196">Sur la page Configuration du portail, fournissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="26f19-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="26f19-197">**Serveur d’archive QoE SQL Server :** Nom de l’instance SQL Server où se trouve la base de données d’archivage QoE.</span><span class="sxs-lookup"><span data-stu-id="26f19-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="26f19-198">Notez que contrairement à la page Configuration de l’archive QoE et la page Configuration du cube, le nom de l’ordinateur n’est pas fixe et doit être fourni.</span><span class="sxs-lookup"><span data-stu-id="26f19-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="26f19-199">Si le composant d’archive QoE a été sélectionné pour l’installation, ce champ est pré-rempli avec la valeur fournie dans la page Configuration de l’archive QoE.</span><span class="sxs-lookup"><span data-stu-id="26f19-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="26f19-200">**Serveur d’analyse de cube :** Nom de l’instance du service SQL Server Analysis pour lequel se trouve le cube.</span><span class="sxs-lookup"><span data-stu-id="26f19-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="26f19-201">Si le composant de cube a été sélectionné pour l’installation, ce champ est pré-rempli avec la valeur fournie sur la page Configuration du cube.</span><span class="sxs-lookup"><span data-stu-id="26f19-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="26f19-202">**Référentiel SQL Server :** Nom de l’instance SQL Server dans laquelle la base de données de référentiel doit être créée.</span><span class="sxs-lookup"><span data-stu-id="26f19-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="26f19-203">Si le nom de l’instance SQL Server correspondant à l’emplacement de la base de données d’archivage QoE a été précédemment fourni dans le programme d’installation (dans les autres composants), ce champ sera pré-rempli avec le nom d’instance SQL Server de la base de données d’archive QoE.</span><span class="sxs-lookup"><span data-stu-id="26f19-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="26f19-204">Il peut s’agir de n’importe quelle instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26f19-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="26f19-205">**Base de données de référentiel :** Par défaut, l’option est définie sur « créer une nouvelle base de données ».</span><span class="sxs-lookup"><span data-stu-id="26f19-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="26f19-206">Étant donné que la mise à niveau de la base de données du référentiel n’est pas prise en charge, le seul cas où l’option « utiliser une base de données existante » peut être utilisée est si la base de données de référentiel existante a le même schéma que la build à installer.</span><span class="sxs-lookup"><span data-stu-id="26f19-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="26f19-207">**Utilisateur du pool d’applications IIS- &amp; mot de passe du nom d’utilisateur :** Compte sous lequel le pool d’applications IIS doit s’exécuter.</span><span class="sxs-lookup"><span data-stu-id="26f19-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="26f19-208">Les champs nom d’utilisateur et mot de passe sont grisés si les comptes système prédéfinis sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="26f19-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="26f19-209">Ces champs seront uniquement activés si l’option « autres » est sélectionnée dans la zone de liste déroulante pour permettre à l’utilisateur d’entrer les informations de compte de service de domaine.</span><span class="sxs-lookup"><span data-stu-id="26f19-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="26f19-210">Lorsque vous cliquez sur suivant, le dernier cycle de validation est effectué afin de s’assurer que les instances de SQL Server sont accessibles à l’aide des informations d’identification fournies et qu’IIS est disponible sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="26f19-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="26f19-211">Une fois la validation terminée, le programme d’installation procède à la configuration.</span><span class="sxs-lookup"><span data-stu-id="26f19-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="26f19-212">Lorsque le programme d’installation est exécuté, le plus probablement le travail de l’agent SQL Server est en cours, ce qui entraîne le chargement initial des données QoE et du traitement du cube.</span><span class="sxs-lookup"><span data-stu-id="26f19-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="26f19-213">En fonction de la quantité de données dans QoE, le portail ne disposera pas de données disponibles pour l’affichage.</span><span class="sxs-lookup"><span data-stu-id="26f19-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="26f19-214">Pour vérifier l’état du chargement des données et du traitement des cubes, `http://<machinename>/CQD/#/Health`accédez à.</span><span class="sxs-lookup"><span data-stu-id="26f19-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="26f19-215">Notez que l’URL permettant de vérifier l’état du traitement de téléchargement de cube est sensible à la casse.</span><span class="sxs-lookup"><span data-stu-id="26f19-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="26f19-216">Si vous entrez « Health », l’URL ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="26f19-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="26f19-217">Vous devez entrer « Health » à la fin de l’URL par un H majuscule.</span><span class="sxs-lookup"><span data-stu-id="26f19-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="26f19-218">Les messages de journal détaillés s’affichent si le mode de débogage est activé.</span><span class="sxs-lookup"><span data-stu-id="26f19-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="26f19-219">Pour activer le mode débogage, accédez à **%systemdrive%\Program Files\Skype for Business 2015 CQD\QoEDataService\web.config**et mettez à jour la ligne suivante de sorte que la valeur soit définie sur **true**:</span><span class="sxs-lookup"><span data-stu-id="26f19-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="26f19-220">La page principale du portail est accessible `http://<machinename>/CQD`via.</span><span class="sxs-lookup"><span data-stu-id="26f19-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="26f19-221">Gestion de l’accès des utilisateurs pour le portail</span><span class="sxs-lookup"><span data-stu-id="26f19-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="26f19-222">Pour gérer l’autorisation des utilisateurs sur le portail, nous vous recommandons d’utiliser l’autorisation d’URL, qui a été introduite dans IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="26f19-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="26f19-223">Pour plus d’informations sur la sécurité IIS, consultez la rubrique [Understanding iis 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="26f19-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="26f19-224">Tout site Web ou application Web hérite de l’autorisation d’URL par défaut configurée pour l’ensemble des services Internet (IIS), ce qui est généralement « autoriser tous les utilisateurs ».</span><span class="sxs-lookup"><span data-stu-id="26f19-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="26f19-225">Si l’accès au portail doit être plus restrictif, les administrateurs peuvent accorder l’accès uniquement à un groupe spécifique d’utilisateurs en modifiant les « règles d’autorisation ».</span><span class="sxs-lookup"><span data-stu-id="26f19-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Déployer les règles d’autorisation de qualité des appels dans les services Internet (IIS)](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="26f19-227">L’icône des règles d’autorisation ne doit pas être confondue avec le « .NET Authorization » dans la section ASP.NET, qui est un autre mécanisme d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="26f19-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="26f19-228">Les administrateurs doivent d’abord supprimer la règle « autoriser tous les utilisateurs » héritée.</span><span class="sxs-lookup"><span data-stu-id="26f19-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="26f19-229">Cela empêche les utilisateurs non autorisés d’accéder au portail.</span><span class="sxs-lookup"><span data-stu-id="26f19-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Déployer CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="26f19-231">Ensuite, les administrateurs doivent ajouter de nouvelles règles d’autorisation et accorder à des utilisateurs spécifiques l’autorisation d’accéder au portail.</span><span class="sxs-lookup"><span data-stu-id="26f19-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="26f19-232">Il est recommandé de créer un groupe local appelé « CQDPortalUsers » pour gérer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="26f19-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Déployer le tableau de bord de qualité des appels](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="26f19-234">Les détails de la configuration sont stockés dans le fichier Web. config situé dans le répertoire physique du portail.</span><span class="sxs-lookup"><span data-stu-id="26f19-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="26f19-235">L’étape suivante consiste à configurer le tableau de bord du CQD.</span><span class="sxs-lookup"><span data-stu-id="26f19-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="26f19-236">Une fois que les utilisateurs sont authentifiés par les services Internet (IIS), ils doivent disposer d’autorisations de fichier dans le répertoire CQD pour accéder au contenu du portail Web.</span><span class="sxs-lookup"><span data-stu-id="26f19-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="26f19-237">Il est possible de modifier les listes de Contrã’le d’accès par le biais de l’onglet sécurité des propriétés du répertoire CQD pour ajouter des utilisateurs ou des groupes individuels ; Toutefois, l’approche recommandée consiste à laisser les autorisations de fichier intactes.</span><span class="sxs-lookup"><span data-stu-id="26f19-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="26f19-238">Au lieu de cela, modifiez le paramètre IIS de manière à utiliser le processus de travail IIS pour accéder au répertoire CQD, quel que soit l’utilisateur authentifié.</span><span class="sxs-lookup"><span data-stu-id="26f19-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="26f19-239">Il est important de modifier uniquement ce paramètre pour l’application CQD, et non pour les deux applications API : QoEDataService et QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="26f19-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="26f19-240">Configuration de l’accès au fichier pour le CQD (tableau de bord)</span><span class="sxs-lookup"><span data-stu-id="26f19-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="26f19-241">Ouvrez l’éditeur de configuration pour CQD.</span><span class="sxs-lookup"><span data-stu-id="26f19-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Déployer le tableau de bord de qualité des appels](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="26f19-243">Sous section, choisissez **System. webServer/ServerRuntime**.</span><span class="sxs-lookup"><span data-stu-id="26f19-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Déployer le tableau de bord de qualité des appels](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="26f19-245">Remplacez authenticatedUserOverride par **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="26f19-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Déployer le tableau de bord de qualité des appels-éditeur de configuration](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="26f19-247">Cliquez sur **appliquer** dans la partie droite de la page.</span><span class="sxs-lookup"><span data-stu-id="26f19-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="26f19-248">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="26f19-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="26f19-249">Le CQD n’affiche aucune donnée après le déploiement</span><span class="sxs-lookup"><span data-stu-id="26f19-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="26f19-250">Le message d’erreur suivant peut s’afficher :</span><span class="sxs-lookup"><span data-stu-id="26f19-250">You may receive the following error:</span></span>

<span data-ttu-id="26f19-251">*Nous n’avons pas pu exécuter la requête pendant son exécution sur le cube. Utilisez l’éditeur de requête pour modifier la requête et résoudre les problèmes. Assurez-vous également que le cube est accessible.*</span><span class="sxs-lookup"><span data-stu-id="26f19-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="26f19-252">Cela signifie que le cube doit être traité dans SQL Server Analysis Services avant d’être utilisé dans CQD.</span><span class="sxs-lookup"><span data-stu-id="26f19-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="26f19-253">Vous pouvez résoudre ce processus en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="26f19-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="26f19-254">Ouvrez SQL Management Studio et sélectionnez **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="26f19-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="26f19-255">Développez l’objet **QoECube** , sélectionnez la **mesure QoE**, cliquez avec le bouton droit, puis cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="26f19-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="26f19-256">Si cette valeur renvoie un navigateur vide, le cube n’a pas encore été exécuté.</span><span class="sxs-lookup"><span data-stu-id="26f19-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="26f19-257">Cliquez avec le bouton droit sur **QoE Metric** angain et choisissez **Process**.</span><span class="sxs-lookup"><span data-stu-id="26f19-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="26f19-258">Une fois le traitement terminé, cliquez à nouveau avec le bouton droit sur l’objet, puis choisissez **Parcourir** pour confirmer que la page du navigateur affiche maintenant des données.</span><span class="sxs-lookup"><span data-stu-id="26f19-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="26f19-259">Les utilisateurs ont des difficultés à se connecter car le programme d’installation ne parvient pas à créer les paramètres corrects dans IIS</span><span class="sxs-lookup"><span data-stu-id="26f19-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="26f19-260">Dans de rares cas, le programme d’installation ne parvient pas à créer les paramètres corrects dans IIS.</span><span class="sxs-lookup"><span data-stu-id="26f19-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="26f19-261">La modification manuelle est requise pour permettre aux utilisateurs de se connecter à CQD.</span><span class="sxs-lookup"><span data-stu-id="26f19-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="26f19-262">Si les utilisateurs rencontrent des problèmes de connexion, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="26f19-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="26f19-263">Ouvrez le gestionnaire des services Internet (IIS), puis accédez au site Web par défaut.</span><span class="sxs-lookup"><span data-stu-id="26f19-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Déployer le tableau de bord de qualité des appels](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="26f19-265">Cliquez sur « authentification ».</span><span class="sxs-lookup"><span data-stu-id="26f19-265">Click on "Authentication".</span></span> <span data-ttu-id="26f19-266">Si les options « authentification anonyme », « emprunt d’identité ASP.NET », « authentification de formulaire » et « authentification Windows » ne correspondent pas aux paramètres indiqués ci-dessous, modifiez-les manuellement pour qu’ils correspondent aux paramètres ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="26f19-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="26f19-267">Tous les autres mécanismes d’authentification doivent être désactivés.</span><span class="sxs-lookup"><span data-stu-id="26f19-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Déployer le tableau de bord de qualité des appels](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="26f19-269">Pour « authentification Windows », cliquez sur Paramètres avancés dans la partie droite.</span><span class="sxs-lookup"><span data-stu-id="26f19-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Déployer le tableau de bord de qualité des appels](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="26f19-271">Définissez « protection étendue » pour accepter et activer la case à cocher « Activer l’authentification en mode noyau ».</span><span class="sxs-lookup"><span data-stu-id="26f19-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Déployer le tableau de bord de qualité des appels](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="26f19-273">Répétez les étapes ci-dessus pour chacune des entrées « CQD », « QoEDataService » et « QoERepositoryService » en dessous de « Default Web site ».</span><span class="sxs-lookup"><span data-stu-id="26f19-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="26f19-274">Pour les liaisons de ports HTTP et HTTPs, le programme d’installation crée des liaisons de ports sur les numéros de port par défaut (port 80 pour HTTP et port 443 pour HTTPs).</span><span class="sxs-lookup"><span data-stu-id="26f19-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="26f19-275">S’il existe un autre site Web sur l’ordinateur qui utilise ces liaisons, il y aura un conflit et le comportement des services Internet (IIS) ne peut pas être prédit.</span><span class="sxs-lookup"><span data-stu-id="26f19-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="26f19-276">La meilleure façon d’éviter ce problème est de s’assurer qu’aucun autre site Web n’est mappé sur les ports 80 et 443 avant l’installation de CQD.</span><span class="sxs-lookup"><span data-stu-id="26f19-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="26f19-277">Pour activer SSL/TLS dans les services Internet (IIS) et obliger les utilisateurs à se connecter via HTTPs sécurisé au lieu de HTTP :</span><span class="sxs-lookup"><span data-stu-id="26f19-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="26f19-278">Configure Secure Sockets Layer dans les services Internet (IIS), consultez la rubrique [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="26f19-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="26f19-279">Une fois terminée, `http` remplacez `https`par.</span><span class="sxs-lookup"><span data-stu-id="26f19-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="26f19-280">Pour obtenir des instructions sur l’activation de TLS dans les connexions SQL Server, consultez [la rubrique How to Enable SSL encryption for an instance of SQL Server Using the Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="26f19-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="26f19-281">Échec de la synchronisation du cube</span><span class="sxs-lookup"><span data-stu-id="26f19-281">Cube Sync Fails</span></span>

<span data-ttu-id="26f19-282">QoEMetrics peut contenir des enregistrements non valides en fonction des horloges de l’utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="26f19-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="26f19-283">Si le décalage temporel est supérieur à 60 ans, l’importation du cube échouera.</span><span class="sxs-lookup"><span data-stu-id="26f19-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="26f19-284">Cochez les cases min et Max StartTime/EndTime à l’aide des options ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="26f19-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="26f19-285">Recherchez et supprimez des enregistrements à l’avenir et à un futur éloigné, mais ils ne peuvent pas être pris en considération et ils vont rompre les processus de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="26f19-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="26f19-286">Sélectionnez MIN (StartTime) à partir de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="26f19-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="26f19-287">SELECT MAX (StartTime) à partir de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="26f19-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="26f19-288">Sélectionnez MIN (EndTime) à partir de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="26f19-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="26f19-289">Sélectionner MAX (EndTime) à partir de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="26f19-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="26f19-290">Tâches consécutives à l’installation</span><span class="sxs-lookup"><span data-stu-id="26f19-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="26f19-291">Importation de bâtiments et de réseaux</span><span class="sxs-lookup"><span data-stu-id="26f19-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="26f19-292">Après avoir installé CQD, effectuez les tâches de configuration suivantes :</span><span class="sxs-lookup"><span data-stu-id="26f19-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="26f19-293">Définir des types de construction (recommandé)</span><span class="sxs-lookup"><span data-stu-id="26f19-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="26f19-294">Définir les types de propriété de création (recommandé)</span><span class="sxs-lookup"><span data-stu-id="26f19-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="26f19-295">Définir des types de réseau (fortement recommandé)</span><span class="sxs-lookup"><span data-stu-id="26f19-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="26f19-296">Importer des bâtiments (recommandé)</span><span class="sxs-lookup"><span data-stu-id="26f19-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="26f19-297">Importer des sous-réseaux (recommandé)</span><span class="sxs-lookup"><span data-stu-id="26f19-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="26f19-298">Définir des types de construction</span><span class="sxs-lookup"><span data-stu-id="26f19-298">Define Building Types</span></span>

<span data-ttu-id="26f19-299">Les types de construction sont utilisés pour décrire les différentes définitions ou types de bâtiments au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="26f19-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="26f19-300">Cette étape est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="26f19-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="26f19-301">Exemples</span><span class="sxs-lookup"><span data-stu-id="26f19-301">Examples</span></span>
  
- <span data-ttu-id="26f19-302">Siège social</span><span class="sxs-lookup"><span data-stu-id="26f19-302">Headquarters</span></span>
    
- <span data-ttu-id="26f19-303">Bureau distant</span><span class="sxs-lookup"><span data-stu-id="26f19-303">Remote Office</span></span>
    
- <span data-ttu-id="26f19-304">Emplacement de l’entreprise conjointe</span><span class="sxs-lookup"><span data-stu-id="26f19-304">Joint-venture location</span></span>
    
  <span data-ttu-id="26f19-305">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="26f19-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="26f19-306">Les paramètres BuildingTypeId et BuildingTypeDesc sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="26f19-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="26f19-307">Définition des types de propriété de génération</span><span class="sxs-lookup"><span data-stu-id="26f19-307">Define Building Ownership Types</span></span>

<span data-ttu-id="26f19-308">Les types de propriété sont utilisés pour distinguer les biens loués vs.</span><span class="sxs-lookup"><span data-stu-id="26f19-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="26f19-309">Cette étape est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="26f19-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="26f19-310">Exemples</span><span class="sxs-lookup"><span data-stu-id="26f19-310">Examples</span></span>
  
- <span data-ttu-id="26f19-311">Contoso avec bail non RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="26f19-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="26f19-312">Contoso bail RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="26f19-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="26f19-313">Contoso, propriétaire</span><span class="sxs-lookup"><span data-stu-id="26f19-313">Contoso Owned</span></span>
    
- <span data-ttu-id="26f19-314">Filiale louée</span><span class="sxs-lookup"><span data-stu-id="26f19-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="26f19-315">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="26f19-315">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

<span data-ttu-id="26f19-316">Les paramètres OwnershipTypeId et OwnershipTypeDesc sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="26f19-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="26f19-317">Définir les noms réseau</span><span class="sxs-lookup"><span data-stu-id="26f19-317">Define Network Names</span></span>

<span data-ttu-id="26f19-318">Les types de réseau sont utilisés pour décrire différents types de réseaux au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="26f19-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="26f19-319">Cela vous permet de filtrer les types de réseau spécifiques (ou de les filtrer).</span><span class="sxs-lookup"><span data-stu-id="26f19-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="26f19-320">Il est vivement recommandé de définir des noms réseau, mais cela est facultatif.</span><span class="sxs-lookup"><span data-stu-id="26f19-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="26f19-321">Si vous décidez de ne pas définir de noms réseau, vérifiez que chaque entrée CqdNetwork a un BuildingId de 0.</span><span class="sxs-lookup"><span data-stu-id="26f19-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="26f19-322">Exemples</span><span class="sxs-lookup"><span data-stu-id="26f19-322">Examples</span></span>
  
- <span data-ttu-id="26f19-323">VPN</span><span class="sxs-lookup"><span data-stu-id="26f19-323">VPN</span></span>
    
- <span data-ttu-id="26f19-324">EXERCICES</span><span class="sxs-lookup"><span data-stu-id="26f19-324">LAB</span></span>
    
  <span data-ttu-id="26f19-325">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="26f19-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="26f19-326">Les paramètres NetworkNameID et NetworkName sont obligatoires, mais le paramètre type est facultatif mais recommandé.</span><span class="sxs-lookup"><span data-stu-id="26f19-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="26f19-327">Importer des bâtiments</span><span class="sxs-lookup"><span data-stu-id="26f19-327">Import Buildings</span></span>

<span data-ttu-id="26f19-328">L’importation de bâtiments vous donne la possibilité de créer des informations spécifiques (appels médiocres par bâtiment sur WiFi/Wired, etc.).</span><span class="sxs-lookup"><span data-stu-id="26f19-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="26f19-329">Cette étape est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="26f19-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="26f19-330">Avant d’importer un nouveau bâtiment, un BuildingKey prédéfini doit déjà être identifié.</span><span class="sxs-lookup"><span data-stu-id="26f19-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="26f19-331">Pour ce faire, émettez la commande SQL « SELECT MAX (BuildingKey) FROM CqdBuilding » pour identifier la valeur actuelle et ajouter 1 au résultat.</span><span class="sxs-lookup"><span data-stu-id="26f19-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="26f19-332">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="26f19-332">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

<span data-ttu-id="26f19-333">Les paramètres BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId sont obligatoires, les autres paramètres sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="26f19-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="26f19-334">Importer des sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="26f19-334">Import Subnets</span></span>

<span data-ttu-id="26f19-335">L’importation de bâtiments vous donne la possibilité de créer des informations spécifiques (appels médiocres par bâtiment sur WiFi/Wired, etc.).</span><span class="sxs-lookup"><span data-stu-id="26f19-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="26f19-336">Cette étape est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="26f19-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="26f19-337">Importez des sous-réseaux et mappez-les aux bâtiments importés lors de la dernière étape.</span><span class="sxs-lookup"><span data-stu-id="26f19-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="26f19-338">Si vous décidez de ne pas renseigner NetworkName, assurez-vous que chaque entrée de cette table utilise un NetworkNameID de 0.</span><span class="sxs-lookup"><span data-stu-id="26f19-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="26f19-339">Pour plus d’informations sur la syntaxe et les paramètres SQL du tableau de bord de qualité des appels, voir [Use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span><span class="sxs-lookup"><span data-stu-id="26f19-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span></span>
  
 <span data-ttu-id="26f19-340">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="26f19-340">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

<span data-ttu-id="26f19-341">Le réseau et les paramètres UpdatedDate sont obligatoires, les autres paramètres sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="26f19-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="26f19-342">Facultatif : BSSID</span><span class="sxs-lookup"><span data-stu-id="26f19-342">Optional: BSSID</span></span>

<span data-ttu-id="26f19-343">Le remplissage des informations BSSID vous donne une corrélation de flux WiFi supplémentaire par contrôleur ou radio.</span><span class="sxs-lookup"><span data-stu-id="26f19-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="26f19-344">Cela s’ajoute au filtrage par construction ou sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="26f19-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="26f19-345">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="26f19-345">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

<span data-ttu-id="26f19-346">**Détails de l’CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="26f19-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="26f19-347">**Comme illustré dans CQD**</span><span class="sxs-lookup"><span data-stu-id="26f19-347">**As shown in CQD**</span></span>|<span data-ttu-id="26f19-348">**Table CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="26f19-348">**CQDBssid Table**</span></span>|<span data-ttu-id="26f19-349">**Exemples d’entrées**</span><span class="sxs-lookup"><span data-stu-id="26f19-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="26f19-350">NName AP</span><span class="sxs-lookup"><span data-stu-id="26f19-350">Ap NName</span></span>  <br/> |<span data-ttu-id="26f19-351">POINT</span><span class="sxs-lookup"><span data-stu-id="26f19-351">AP</span></span>  <br/> |<span data-ttu-id="26f19-352">API</span><span class="sxs-lookup"><span data-stu-id="26f19-352">AP1</span></span>  <br/> |
|<span data-ttu-id="26f19-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="26f19-353">BBssid</span></span>  <br/> |<span data-ttu-id="26f19-354">MODES</span><span class="sxs-lookup"><span data-stu-id="26f19-354">BSS</span></span>  <br/> |<span data-ttu-id="26f19-355">00-00-00-00-00-00 (vous devez utiliser le fformat délimité)</span><span class="sxs-lookup"><span data-stu-id="26f19-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="26f19-356">Contrôleur</span><span class="sxs-lookup"><span data-stu-id="26f19-356">Controller</span></span>  <br/> |<span data-ttu-id="26f19-357">Construit</span><span class="sxs-lookup"><span data-stu-id="26f19-357">Building</span></span>  <br/> |<span data-ttu-id="26f19-358">AP d’Aruba 7</span><span class="sxs-lookup"><span data-stu-id="26f19-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="26f19-359">Device</span><span class="sxs-lookup"><span data-stu-id="26f19-359">Device</span></span>  <br/> |<span data-ttu-id="26f19-360">capot</span><span class="sxs-lookup"><span data-stu-id="26f19-360">ess</span></span>  <br/> |<span data-ttu-id="26f19-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="26f19-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="26f19-362">Option</span><span class="sxs-lookup"><span data-stu-id="26f19-362">Radio</span></span>  <br/> |<span data-ttu-id="26f19-363">PHY</span><span class="sxs-lookup"><span data-stu-id="26f19-363">phy</span></span>  <br/> |<span data-ttu-id="26f19-364">BGN</span><span class="sxs-lookup"><span data-stu-id="26f19-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="26f19-365">Traitement des données importées</span><span class="sxs-lookup"><span data-stu-id="26f19-365">Processing the imported data</span></span>

<span data-ttu-id="26f19-366">Par défaut, une fois que vous avez importé des données de création/réseau, il s’applique uniquement aux enregistrements générés après cette date.</span><span class="sxs-lookup"><span data-stu-id="26f19-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="26f19-367">Pour marquer tous les enregistrements précédents avec ces nouvelles données, vous devez exécuter la procédure stockée CqdUpdateBuilding, comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="26f19-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="26f19-368">Donnez-lui la date de votre premier enregistrement (identifiez-la à l’aide de la commande SELECT MIN (StartTime) FROM CqdPartitionedStreamView SQL), une date de demain, puis la valeur NULL pour les deux dernières valeurs.</span><span class="sxs-lookup"><span data-stu-id="26f19-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="26f19-369">Une fois que les données sont associées à des données de flux, le cube SSIS doit retraiter tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="26f19-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="26f19-370">Cela s’applique également lors de l’ajout en bloc de données BSSID/ISP.</span><span class="sxs-lookup"><span data-stu-id="26f19-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="26f19-371">Assurez-vous que l’option « traiter tout le processus » est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="26f19-371">Ensure that "Process Full" is selected.</span></span>
  

