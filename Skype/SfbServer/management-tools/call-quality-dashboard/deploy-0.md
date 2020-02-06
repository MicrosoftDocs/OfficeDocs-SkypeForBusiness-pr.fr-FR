---
title: Déploiement du tableau de bord de qualité des appels pour Skype entreprise Server
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
description: 'Résumé : en savoir plus sur le processus de déploiement du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: ccfb19bf8069bf72d52d7399b012d81af72e4110
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816853"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="60161-104">Déploiement du tableau de bord de qualité des appels pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="60161-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="60161-105">**Résumé :** En savoir plus sur le processus de déploiement du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="60161-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="60161-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="60161-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="60161-107">Présentation du déploiement</span><span class="sxs-lookup"><span data-stu-id="60161-107">Deployment Overview</span></span>

<span data-ttu-id="60161-108">Le tableau de bord de qualité des appels (bord) comporte trois composants principaux :</span><span class="sxs-lookup"><span data-stu-id="60161-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="60161-109">**Base de données d’archivage**dans laquelle les données de qualité de l’expertise sont répliquées et stockées.</span><span class="sxs-lookup"><span data-stu-id="60161-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="60161-110">**Cube**, dans lequel les données de la base de données d’archive QoE sont agrégées pour un accès optimisé et rapide.</span><span class="sxs-lookup"><span data-stu-id="60161-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="60161-111">**Portail**permettant aux utilisateurs de rechercher et de visualiser facilement des données QoE.</span><span class="sxs-lookup"><span data-stu-id="60161-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Composants CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="60161-113">Le processus de configuration de l’archivage QoE implique la création de la base de données d’archive QoE, le déploiement d’une procédure stockée SQL Server permettant de déplacer les données de la base de données de valeurs QoE sources dans la base de données d’archive QoE et de configurer le travail de l’agent SQL Server pour exécuter les données stockées. procédure à un intervalle régulier.</span><span class="sxs-lookup"><span data-stu-id="60161-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="60161-114">Le déploiement d’un cube obtient des informations de la part de l’utilisateur sur l’emplacement de l’archive QoE, déploie le cube et configure une tâche standard de l’agent SQL Server qui actualisera le cube à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="60161-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="60161-115">L’installation du portail crée une base de données de référentiel qui stocke le mappage des utilisateurs de bord sur les rapports/requêtes de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="60161-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="60161-116">Il configure alors une application Web IIS, qui est le tableau de bord dans lequel les utilisateurs peuvent voir un ensemble prédéfini de rapports, ainsi que personnaliser et créer leurs propres requêtes pour visualiser les données du cube.</span><span class="sxs-lookup"><span data-stu-id="60161-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="60161-117">L’installation du portail crée deux applications Web supplémentaires qui exposent les API destinées aux utilisateurs pour accéder par programmation au référentiel et au cube.</span><span class="sxs-lookup"><span data-stu-id="60161-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="60161-118">(Ces API sont également utilisées en interne par le tableau de bord.)</span><span class="sxs-lookup"><span data-stu-id="60161-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="60161-119">**Phase**</span><span class="sxs-lookup"><span data-stu-id="60161-119">**Phase**</span></span>|<span data-ttu-id="60161-120">**Étapes**</span><span class="sxs-lookup"><span data-stu-id="60161-120">**Steps**</span></span>|<span data-ttu-id="60161-121">**Rôles et appartenances aux groupes**</span><span class="sxs-lookup"><span data-stu-id="60161-121">**Roles and group membership**</span></span>|<span data-ttu-id="60161-122">**Documentation**</span><span class="sxs-lookup"><span data-stu-id="60161-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="60161-123">Installez le matériel et les logiciels requis.</span><span class="sxs-lookup"><span data-stu-id="60161-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="60161-124">Déterminez la configuration de bord, puis choisissez un serveur SQL à partir duquel effectuer l’installation.</span><span class="sxs-lookup"><span data-stu-id="60161-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="60161-125">Utilisateur du domaine membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="60161-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="60161-126">Section « Configuration requise pour la préinstallation » de la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="60161-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="60161-127">Installez bord.</span><span class="sxs-lookup"><span data-stu-id="60161-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="60161-128">Exécutez le MSI en suivant le document de déploiement.</span><span class="sxs-lookup"><span data-stu-id="60161-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="60161-129">Pour effectuer l’installation, le compte d’installation doit être un utilisateur de domaine membre du groupe Administrateurs local et disposer d’un accès en lecture à la base de données QoE Metrics du serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="60161-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="60161-130">Sections « comptes et étapes de déploiement » de la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="60161-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="60161-131">Octroyez l’accès aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="60161-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="60161-132">Pour gérer les autorisations de l’utilisateur sur le portail, nous vous recommandons d’utiliser l’autorisation d’URL incluse dans IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="60161-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="60161-133">Pour plus d’informations, voir présentation de l' [autorisation d’URL d’IIS 7,0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="60161-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="60161-134">Utilisateur du domaine membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="60161-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="60161-135">Gestion de l’accès utilisateur de la section portail dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="60161-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="60161-136">Facultatif : fournissez les informations de mappage de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="60161-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="60161-137">Peuplez les tables de mappage réseau et de construction dans la base de données d’archive QoE.</span><span class="sxs-lookup"><span data-stu-id="60161-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="60161-138">Un compte avec accès en écriture à la base de données d’archive QoE.</span><span class="sxs-lookup"><span data-stu-id="60161-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="60161-139">Section « fourniture des informations de sous-réseau » dans la documentation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="60161-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="60161-140">Le déploiement du tableau de bord de qualité des appels consiste à configurer l’infrastructure et à installer le logiciel.</span><span class="sxs-lookup"><span data-stu-id="60161-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="60161-141">La procédure suivante décrit le processus.</span><span class="sxs-lookup"><span data-stu-id="60161-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="60161-142">Étapes du déploiement</span><span class="sxs-lookup"><span data-stu-id="60161-142">Deployment Steps</span></span>

1. <span data-ttu-id="60161-143">Copiez le fichier CallQualityDashboard. msi sur l’ordinateur sur lequel le composant de base de données d’archive d’bord doit être installé (il s’agit de l’ordinateur sur lequel est installé SQL Server).</span><span class="sxs-lookup"><span data-stu-id="60161-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="60161-144">Exécutez le fichier MSI (Windows sera invité à s’exécuter avec les privilèges d’administrateur, procédez ainsi).</span><span class="sxs-lookup"><span data-stu-id="60161-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="60161-145">Acceptez le contrat de licence.</span><span class="sxs-lookup"><span data-stu-id="60161-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="60161-146">Sélectionnez le dossier de destination dans lequel les fichiers liés aux composants de tableau de bord de qualité des appels seront localisés ou acceptent l’emplacement par défaut.</span><span class="sxs-lookup"><span data-stu-id="60161-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="60161-147">Sélectionnez toutes les fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="60161-147">Select all features.</span></span>
    
6. <span data-ttu-id="60161-148">Dans la page Configuration de l’archivage QoE, entrez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="60161-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="60161-149">**Valeur QoE de SQL Server :** Nom de l’instance SQL Server pour l’emplacement de la base de données QoE Metrics (il s’agit de la source de données).</span><span class="sxs-lookup"><span data-stu-id="60161-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="60161-150">**Nom de serveur SQL du serveur d’archivage :** Il s’agit d’un champ en lecture seule et est fixé sur le nom de domaine complet de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="60161-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="60161-151">La base de BDD d’archivage ne peut être installée que sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="60161-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="60161-152">**Instance QoE SQL Server d’archive :** Nom d’instance SQL Server local pour l’emplacement où la base de donnees d’archive doit être créée.</span><span class="sxs-lookup"><span data-stu-id="60161-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="60161-153">Pour utiliser une instance SQL Server par défaut, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="60161-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="60161-154">Pour utiliser une instance SQL Server nommée, spécifiez le nom de l’instance (par exemple, le\"nom du « ) ».</span><span class="sxs-lookup"><span data-stu-id="60161-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="60161-155">**Base de données d’archive QoE :** Par défaut, cette option est définie sur « créer une nouvelle base de données ».</span><span class="sxs-lookup"><span data-stu-id="60161-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="60161-156">Dans la mesure où la mise à niveau d’archive de base de données n’est pas prise en charge, les seules circonstances pour lesquelles l’option « utiliser la base de données existante » peut être utilisée sont les mêmes que celles de la build à installer.</span><span class="sxs-lookup"><span data-stu-id="60161-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="60161-157">**Répertoire du fichier de base de données :** Chemin d’accès à l’emplacement où se trouvent les fichiers de base de données (. mdf et. ldf) de la base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="60161-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="60161-158">Il doit s’agir d’un lecteur (HDD2 dans la configuration matérielle recommandée) distinct du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="60161-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="60161-159">Notez que, dans la mesure où les noms de fichiers sont résolus dans l’installation, nous vous conseillons de ne pas utiliser un répertoire vide sans fichier pour éviter tout conflit potentiel.</span><span class="sxs-lookup"><span data-stu-id="60161-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="60161-160">**Utiliser plusieurs partitions :** Par défaut, la valeur est « multiple partition », qui nécessite Business Intelligence Edition ou Enterprise Edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60161-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="60161-161">Pour l’édition standard, sélectionnez l’option « partition unique ».</span><span class="sxs-lookup"><span data-stu-id="60161-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="60161-162">Notez que les performances de traitement de cube risquent d’être affectées en cas d’utilisation d’une partition unique.</span><span class="sxs-lookup"><span data-stu-id="60161-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="60161-163">L’option sélection de plusieurs partitions ne peut pas être modifiée une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="60161-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="60161-164">Pour le modifier, la fonctionnalité de cube doit d’abord être désinstallée, puis réinstallée à l’aide de l’option « modifier » dans le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="60161-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="60161-165">**Répertoire de fichiers de partitions :** Chemin d’accès vers l’emplacement où vous souhaitez placer les partitions pour la base de données d’archive QoE.</span><span class="sxs-lookup"><span data-stu-id="60161-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="60161-166">Il doit s’agir d’un lecteur (HDD3 dans la configuration matérielle recommandée) distinct du lecteur du système d’exploitation et du lecteur de fichiers journaux de base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="60161-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="60161-167">Notez que, dans la mesure où les noms de fichiers sont résolus dans l’installation, nous vous conseillons de ne pas utiliser un répertoire vide sans fichier pour éviter tout conflit potentiel.</span><span class="sxs-lookup"><span data-stu-id="60161-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="60161-168">**Tâche de l’agent SQL user- &amp; mot de passe nom d’utilisateur :** Nom du compte de domaine et mot de passe (masqué) qui seront utilisés pour exécuter l’étape « données d’archive QoE » du poste de travail de l’agent SQL Server (qui exécute la procédure stockée pour extraire les données de la base de données QoE de la base de données d’archivage, comme indiqué dans la section comptes.</span><span class="sxs-lookup"><span data-stu-id="60161-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="60161-169">Ce compte doit également avoir une connexion dans l’instance de SQL Server d’archive QoE.</span><span class="sxs-lookup"><span data-stu-id="60161-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="60161-170">Le compte sous lequel l’instance SQL Server est en cours d’exécution (par exemple, NT SERVICE\MSSQLSERVER) doit disposer d’un accès ou d’une autorisation aux annuaires ci-dessus pour que l’installation réussisse.</span><span class="sxs-lookup"><span data-stu-id="60161-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="60161-171">Pour plus d’informations, voir [configurer les autorisations du système de fichiers pour l’accès du moteur de base de données](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="60161-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="60161-172">Lorsque vous cliquez sur suivant, le programme d’installation effectue des vérifications et signale les conditions préalables en cas de problème.</span><span class="sxs-lookup"><span data-stu-id="60161-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="60161-173">Lorsque toutes les vérifications préalables sont réussies, le programme d’installation accède à la page Configuration du cube.</span><span class="sxs-lookup"><span data-stu-id="60161-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="60161-174">Si le programme d’installation affiche un message d’avertissement indiquant que le service Agent SQL Server pour l’instance de SQL Server d’archive QoE n’est pas en cours d’exécution, l’installation peut avoir lieu, mais après l’installation, assurez-vous que le service Agent SQL est en cours d’exécution et définissez le type de démarrage sur Automatique pour que le travail planifié s’exécute.</span><span class="sxs-lookup"><span data-stu-id="60161-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="60161-175">Dans la page Configuration du cube, entrez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="60161-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="60161-176">**Nom de serveur SQL du serveur d’archivage :** Il s’agit d’un champ en lecture seule et est fixé sur le nom de domaine complet de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="60161-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="60161-177">Le cube peut être installé uniquement à partir de l’ordinateur qui dispose de la base de données d’archive QoE (Remarque.</span><span class="sxs-lookup"><span data-stu-id="60161-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="60161-178">Le cube proprement dit doit être installé sur un ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="60161-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="60161-179">Voir ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="60161-179">See below)</span></span>
    
   - <span data-ttu-id="60161-180">**Instance QoE SQL Server d’archive :** Nom de l’instance SQL Server pour lequel se trouve la BDD d’archive QoE.</span><span class="sxs-lookup"><span data-stu-id="60161-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="60161-181">Pour spécifier une instance SQL Server par défaut, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="60161-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="60161-182">Pour spécifier une instance nommée de SQL Server, entrez le nom de l’instance (par exemple, le\"nom suivant le ").</span><span class="sxs-lookup"><span data-stu-id="60161-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="60161-183">Si le composant d’archive QoE a été sélectionné pour l’installation, ce champ est pré-rempli avec la valeur figurant dans la page Configuration d’archive QoE.</span><span class="sxs-lookup"><span data-stu-id="60161-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="60161-184">**Serveur d’analyse du cube :** Nom de l’instance de SQL Server Analysis Services pour l’emplacement de création du cube.</span><span class="sxs-lookup"><span data-stu-id="60161-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="60161-185">Il peut s’agir d’un autre ordinateur, mais l’utilisateur doit être membre des administrateurs de serveurs de l’instance de service SQL Server Analysis Services cible.</span><span class="sxs-lookup"><span data-stu-id="60161-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="60161-186">Pour plus d’informations sur la configuration des autorisations d’administrateur du serveur Analysis Services, voir [accorder des autorisations d’administrateur serveur (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx) .</span><span class="sxs-lookup"><span data-stu-id="60161-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="60161-187">**Utiliser plusieurs partitions :** Par défaut, la valeur est « multiple partition », qui nécessite Business Intelligence Edition ou Enterprise Edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60161-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="60161-188">Pour l’édition standard, sélectionnez l’option « partition unique ».</span><span class="sxs-lookup"><span data-stu-id="60161-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="60161-189">Notez que les performances de traitement de cube risquent d’être affectées en cas d’utilisation d’une partition unique.</span><span class="sxs-lookup"><span data-stu-id="60161-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="60161-190">L’option sélection de plusieurs partitions ne peut pas être modifiée une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="60161-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="60161-191">Pour le modifier, la fonctionnalité de cube doit d’abord être désinstallée, puis réinstallée à l’aide de l’option « modifier » dans le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="60161-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="60161-192">**Utilisateur du cube-mot &amp; de passe du nom d’utilisateur :** Nom du compte de service de domaine et mot de passe (masqué) déclenchant le traitement du cube.</span><span class="sxs-lookup"><span data-stu-id="60161-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="60161-193">Si le composant d’archive QoE a été sélectionné pour l’installation, ce champ est pré-rempli avec la valeur fournie dans la page Configuration de l’archivage pour l’utilisateur du travail d’agent SQL, mais nous vous recommandons de spécifier un autre compte de service de domaine pour que le programme d’installation puisse accorder le le moins de privilèges requis.</span><span class="sxs-lookup"><span data-stu-id="60161-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="60161-194">Lorsque vous cliquez sur suivant, un autre arrondi de validation est effectué et tout problème est signalé.</span><span class="sxs-lookup"><span data-stu-id="60161-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="60161-195">Une fois la validation terminée, le programme d’installation accède à la page de configuration du portail.</span><span class="sxs-lookup"><span data-stu-id="60161-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="60161-196">Dans la page Configuration du portail, entrez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="60161-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="60161-197">**QoE archiver SQL Server :** Nom de l’instance SQL Server pour lequel se trouve la base de données d’archive QoE.</span><span class="sxs-lookup"><span data-stu-id="60161-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="60161-198">Notez que, contrairement à la page Configuration d’archive QoE et la page de configuration du cube, le nom de l’ordinateur n’est pas fixe et doit être fourni.</span><span class="sxs-lookup"><span data-stu-id="60161-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="60161-199">Si le composant d’archive QoE a été sélectionné pour l’installation, ce champ est pré-rempli avec la valeur figurant dans la page Configuration d’archive QoE.</span><span class="sxs-lookup"><span data-stu-id="60161-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="60161-200">**Serveur d’analyse du cube :** Nom de l’instance de SQL Server Analysis Services pour l’emplacement du cube.</span><span class="sxs-lookup"><span data-stu-id="60161-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="60161-201">Si le composant cube a été sélectionné pour l’installation, ce champ est pré-rempli avec la valeur fournie dans la page Configuration du cube.</span><span class="sxs-lookup"><span data-stu-id="60161-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="60161-202">**Référentiel SQL Server :** Nom de l’instance SQL Server où la base de données du référentiel doit être créée.</span><span class="sxs-lookup"><span data-stu-id="60161-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="60161-203">Si le nom de l’instance SQL Server pour l’emplacement de la base de données d’archive QoE a été fourni auparavant dans le programme d’installation (dans d’autres composants), ce champ sera pré-rempli avec le nom de l’instance de SQL Server BDD archive.</span><span class="sxs-lookup"><span data-stu-id="60161-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="60161-204">Il peut s’agir d’une instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60161-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="60161-205">**Base de données du référentiel :** Par défaut, l’option est définie sur « créer une nouvelle base de données ».</span><span class="sxs-lookup"><span data-stu-id="60161-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="60161-206">Dans la mesure où la mise à niveau de la base de données du référentiel n’est pas prise en charge, les seules circonstances pour lesquelles l’option « utiliser la base de données existante » peut être utilisée sont les mêmes que la base de données du référentiel existant à installer.</span><span class="sxs-lookup"><span data-stu-id="60161-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="60161-207">**Utilisateur du pool d’applications IIS- &amp; mot de passe du nom d’utilisateur :** Le compte sous lequel le pool d’applications IIS doit s’exécuter.</span><span class="sxs-lookup"><span data-stu-id="60161-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="60161-208">Les champs nom d’utilisateur et mot de passe seront grisés si les comptes système intégrés sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="60161-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="60161-209">Ces champs ne seront activés que si l’option « autre » est sélectionnée dans la zone de liste déroulante, afin que l’utilisateur puisse entrer les informations de compte de service de domaine.</span><span class="sxs-lookup"><span data-stu-id="60161-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="60161-210">Lorsque vous cliquez sur suivant, le dernier arrondi de validation est effectué pour vérifier que les instances SQL Server sont accessibles à l’aide des informations d’identification fournies et qu’IIS est disponible sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="60161-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="60161-211">Une fois la validation terminée, le programme d’installation continue de procéder à la configuration.</span><span class="sxs-lookup"><span data-stu-id="60161-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="60161-212">Lorsque le programme d’installation est en cours d’exécution, il est probable que le travail de l’agent SQL Server soit en cours, ce qui a pour effet de charger l’initiale des données QoE et de traiter le cube.</span><span class="sxs-lookup"><span data-stu-id="60161-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="60161-213">En fonction de la quantité de données dans QoE, les données du portail ne seront pas encore disponibles pour être affichées.</span><span class="sxs-lookup"><span data-stu-id="60161-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="60161-214">Pour vérifier l’état du traitement des données et du chargement des données, accédez `http://<machinename>/CQD/#/Health`à.</span><span class="sxs-lookup"><span data-stu-id="60161-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="60161-215">Notez que l’URL pour vérifier le statut de téléchargement du cube est sensible à la casse.</span><span class="sxs-lookup"><span data-stu-id="60161-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="60161-216">Si vous entrez « Health », l’URL ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="60161-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="60161-217">Vous devez entrer « Health » à la fin de l’URL avec un H majuscule.</span><span class="sxs-lookup"><span data-stu-id="60161-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="60161-218">Les messages détaillés du journal seront affichés en mode débogage.</span><span class="sxs-lookup"><span data-stu-id="60161-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="60161-219">Pour activer le mode de débogage, accédez à **%systemdrive%\Program Files\Skype pour Business 2015 CQD\QoEDataService\web.config**, puis mettez à jour la ligne suivante de sorte que la valeur soit définie sur **true**:</span><span class="sxs-lookup"><span data-stu-id="60161-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="60161-220">La page principale du portail est accessible `http://<machinename>/CQD`via.</span><span class="sxs-lookup"><span data-stu-id="60161-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="60161-221">Gestion de l’accès des utilisateurs au portail</span><span class="sxs-lookup"><span data-stu-id="60161-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="60161-222">Pour gérer les autorisations de l’utilisateur sur le portail, nous vous recommandons d’utiliser l’autorisation d’URL incluse dans IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="60161-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="60161-223">Pour plus d’informations sur la sécurité IIS, voir présentation de l' [autorisation d’URL d’iis 7,0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="60161-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="60161-224">Tout site Web ou application Web hérite de l’autorisation d’URL par défaut configurée pour l’ensemble des services Internet, qui est généralement « autoriser tous les utilisateurs ».</span><span class="sxs-lookup"><span data-stu-id="60161-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="60161-225">Si l’accès au portail doit être plus restrictif, les administrateurs peuvent accorder l’accès uniquement aux groupes d’utilisateurs spécifiques en modifiant les « règles d’autorisation ».</span><span class="sxs-lookup"><span data-stu-id="60161-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Déployer la qualité des appels - règles d’autorisation dans IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="60161-227">L’icône règles d’autorisation ne doit pas être confondus avec l’autorisation « .NET Authorization » sous la section ASP.NET, qui est un autre mécanisme d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="60161-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="60161-228">Les administrateurs doivent commencer par supprimer la règle « autoriser tous les utilisateurs ».</span><span class="sxs-lookup"><span data-stu-id="60161-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="60161-229">Cela empêche les utilisateurs non autorisés d’accéder au portail.</span><span class="sxs-lookup"><span data-stu-id="60161-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Déployer CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="60161-231">Par la suite, les administrateurs doivent ajouter de nouvelles règles d’autorisation et accorder à des utilisateurs spécifiques l’accès au portail.</span><span class="sxs-lookup"><span data-stu-id="60161-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="60161-232">Il est recommandé de créer un groupe local appelé « CQDPortalUsers » pour gérer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="60161-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Déployer le Tableau de bord de la qualité des appels](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="60161-234">Les détails de la configuration sont stockés dans le fichier Web. config situé dans le répertoire physique du portail.</span><span class="sxs-lookup"><span data-stu-id="60161-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```XML
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="60161-235">L’étape suivante consiste à configurer le tableau de bord du bord.</span><span class="sxs-lookup"><span data-stu-id="60161-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="60161-236">Une fois les utilisateurs authentifiés par IIS, ils doivent disposer d’autorisations de fichiers sur le répertoire bord pour pouvoir accéder au contenu du portail Web.</span><span class="sxs-lookup"><span data-stu-id="60161-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="60161-237">Il est possible de modifier les ACL par le biais de l’onglet sécurité des propriétés de l’annuaire bord pour ajouter des utilisateurs ou des groupes individuels. Néanmoins, nous vous conseillons de ne pas laisser les autorisations de fichier intactes.</span><span class="sxs-lookup"><span data-stu-id="60161-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="60161-238">Au lieu de cela, modifiez le paramètre IIS pour utiliser le processus de travail IIS pour accéder au répertoire bord, quel que soit l’utilisateur authentifié.</span><span class="sxs-lookup"><span data-stu-id="60161-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="60161-239">Il est important de changer uniquement ce paramètre pour l’application bord et non pour les deux applications API : QoEDataService et QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="60161-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="60161-240">Configuration de l’accès aux fichiers pour le bord (tableau de bord)</span><span class="sxs-lookup"><span data-stu-id="60161-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="60161-241">Ouvrez l’éditeur de configuration pour bord.</span><span class="sxs-lookup"><span data-stu-id="60161-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="60161-243">Sous section, sélectionnez **System. webServer/ServerRuntime**.</span><span class="sxs-lookup"><span data-stu-id="60161-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="60161-245">Remplacez authenticatedUserOverride par **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="60161-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels - Éditeur de configuration](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="60161-247">Cliquez sur **appliquer** sur le côté droit de la page.</span><span class="sxs-lookup"><span data-stu-id="60161-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="60161-248">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="60161-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="60161-249">BORD n’affiche aucune donnée après le déploiement</span><span class="sxs-lookup"><span data-stu-id="60161-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="60161-250">Le message d’erreur suivant peut apparaître :</span><span class="sxs-lookup"><span data-stu-id="60161-250">You may receive the following error:</span></span>

<span data-ttu-id="60161-251">*Nous n’avons pas pu exécuter la requête lors de son exécution sur le cube. Utilisez l’éditeur de requête pour modifier la requête et résoudre les éventuels problèmes. Assurez-vous également que le cube est accessible.*</span><span class="sxs-lookup"><span data-stu-id="60161-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="60161-252">Cela signifie que le cube doit être traité dans SQL Server Analysis Services avant d’être utilisé dans bord.</span><span class="sxs-lookup"><span data-stu-id="60161-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="60161-253">Vous pouvez résoudre ce problème en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="60161-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="60161-254">Ouvrez SQL Management Studio et sélectionnez **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="60161-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="60161-255">Développez l’objet **QoECube** , sélectionnez le **QoE métrique**, cliquez avec le bouton droit, puis sélectionnez **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="60161-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="60161-256">Si cela renvoie un navigateur vide, le cube n’a pas encore été exécuté.</span><span class="sxs-lookup"><span data-stu-id="60161-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="60161-257">Cliquez avec le bouton droit sur **QoE Metric** angain et sélectionnez **processus**.</span><span class="sxs-lookup"><span data-stu-id="60161-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="60161-258">Lorsque le traitement est terminé, cliquez à nouveau avec le bouton droit sur l’objet, puis sélectionnez **Parcourir** pour vérifier que la page du navigateur affiche désormais des données.</span><span class="sxs-lookup"><span data-stu-id="60161-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="60161-259">Les utilisateurs rencontrent des problèmes de connexion, car le programme d’installation ne parvient pas à créer les paramètres corrects dans IIS</span><span class="sxs-lookup"><span data-stu-id="60161-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="60161-260">Dans de rares cas, le programme d’installation ne parvient pas à créer les paramètres appropriés dans les services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="60161-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="60161-261">Le changement manuel est requis pour permettre aux utilisateurs de se connecter à bord.</span><span class="sxs-lookup"><span data-stu-id="60161-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="60161-262">Si les utilisateurs rencontrent des problèmes de connexion, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="60161-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="60161-263">Ouvrez le gestionnaire des services Internet (IIS), puis accédez au site Web par défaut.</span><span class="sxs-lookup"><span data-stu-id="60161-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="60161-265">Cliquez sur « authentification ».</span><span class="sxs-lookup"><span data-stu-id="60161-265">Click on "Authentication".</span></span> <span data-ttu-id="60161-266">Si les options « authentification anonyme », « l’emprunt d’identité ASP.NET », « authentification par formulaire » et « authentification Windows » ne correspondent pas aux paramètres indiqués ci-dessous, modifiez-les manuellement pour qu’ils correspondent aux paramètres ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="60161-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="60161-267">Tout autre mécanisme d’authentification doit être désactivé.</span><span class="sxs-lookup"><span data-stu-id="60161-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="60161-269">Pour « authentification Windows », cliquez sur Paramètres avancés sur le côté droit de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="60161-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="60161-271">Définissez « protection étendue » pour accepter et cocher la case « Activer l’authentification en mode noyau ».</span><span class="sxs-lookup"><span data-stu-id="60161-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="60161-273">Répétez les étapes ci-dessus pour chacune des entrées « bord », « QoEDataService » et « QoERepositoryService » sous « site Web par défaut ».</span><span class="sxs-lookup"><span data-stu-id="60161-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="60161-274">Pour les liaisons de port HTTP et HTTPs, le programme d’installation va créer des liaisons de port sur les numéros de port par défaut (port 80 pour HTTP et 443 pour HTTPs).</span><span class="sxs-lookup"><span data-stu-id="60161-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="60161-275">S’il existe un autre site Web sur l’ordinateur qui utilise ces liaisons, il y a un conflit alors que le comportement d’IIS ne peut pas être prédit.</span><span class="sxs-lookup"><span data-stu-id="60161-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="60161-276">Le meilleur moyen d’éviter ce problème consiste à vous assurer qu’aucun autre site Web n’est mappé aux ports 80 et 443 avant d’installer bord.</span><span class="sxs-lookup"><span data-stu-id="60161-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="60161-277">Pour activer SSL/TLS dans IIS et obliger les utilisateurs à se connecter par le biais de HTTPS au lieu de HTTP :</span><span class="sxs-lookup"><span data-stu-id="60161-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="60161-278">Configurer le protocole SSL (Secure Sockets Layer) dans IIS, voir [configurer le protocole SSL (Secure Sockets Layer) dans IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="60161-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="60161-279">Après cela, remplacez `http` par `https`.</span><span class="sxs-lookup"><span data-stu-id="60161-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="60161-280">Pour obtenir des instructions sur l’activation de TLS dans les connexions SQL Server, voir [activation du chiffrement SSL pour une instance de SQL Server à l’aide de Microsoft Management Console](https://support.microsoft.com/en-us/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="60161-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="60161-281">Échec de la synchronisation du cube</span><span class="sxs-lookup"><span data-stu-id="60161-281">Cube Sync Fails</span></span>

<span data-ttu-id="60161-282">QoEMetrics pourrait contenir des enregistrements non valides en fonction des horloges de l’utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="60161-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="60161-283">Si le décalage de temps est supérieur à 60 ans, l’importation du cube échoue.</span><span class="sxs-lookup"><span data-stu-id="60161-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="60161-284">Utilisez les sélections suivantes pour les options min et Max StartTime/heure_fin.</span><span class="sxs-lookup"><span data-stu-id="60161-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="60161-285">Recherchez et supprimez des enregistrements à l’avenir et à un avenir très éloigné, ils peuvent être ignorés et débloquer les processus de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="60161-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="60161-286">Select MIN (StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="60161-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="60161-287">SELECT MAX (StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="60161-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="60161-288">Sélectionner MIN (heure_fin) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="60161-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="60161-289">Sélectionner MAX (heure_fin) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="60161-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="60161-290">Tâches après l’installation</span><span class="sxs-lookup"><span data-stu-id="60161-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="60161-291">Importation d’immeubles et de réseaux</span><span class="sxs-lookup"><span data-stu-id="60161-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="60161-292">Après l’installation de bord, effectuez les tâches de configuration suivantes :</span><span class="sxs-lookup"><span data-stu-id="60161-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="60161-293">Définir les types de construction (recommandé)</span><span class="sxs-lookup"><span data-stu-id="60161-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="60161-294">Définir les types de propriété de construction (recommandé)</span><span class="sxs-lookup"><span data-stu-id="60161-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="60161-295">Définir les types de réseaux (fortement recommandés)</span><span class="sxs-lookup"><span data-stu-id="60161-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="60161-296">Importer des bâtiments (recommandé)</span><span class="sxs-lookup"><span data-stu-id="60161-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="60161-297">Importez des sous-réseaux (recommandé)</span><span class="sxs-lookup"><span data-stu-id="60161-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="60161-298">Définir les types de construction</span><span class="sxs-lookup"><span data-stu-id="60161-298">Define Building Types</span></span>

<span data-ttu-id="60161-299">Les types de construction permettent de décrire les différentes définitions ou types de constructions au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="60161-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="60161-300">Cette étape est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="60161-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="60161-301">Exemples</span><span class="sxs-lookup"><span data-stu-id="60161-301">Examples</span></span>
  
- <span data-ttu-id="60161-302">Siège social</span><span class="sxs-lookup"><span data-stu-id="60161-302">Headquarters</span></span>
    
- <span data-ttu-id="60161-303">Bureau distant</span><span class="sxs-lookup"><span data-stu-id="60161-303">Remote Office</span></span>
    
- <span data-ttu-id="60161-304">Emplacement d’entreprise conjointe</span><span class="sxs-lookup"><span data-stu-id="60161-304">Joint-venture location</span></span>
    
  <span data-ttu-id="60161-305">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="60161-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="60161-306">Les paramètres BuildingTypeId et BuildingTypeDesc sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="60161-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="60161-307">Définir les types de propriété</span><span class="sxs-lookup"><span data-stu-id="60161-307">Define Building Ownership Types</span></span>

<span data-ttu-id="60161-308">Les types de propriété permettent de faire la distinction entre les ressources appartenant à un bail.</span><span class="sxs-lookup"><span data-stu-id="60161-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60161-309">Cette étape est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="60161-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="60161-310">Exemples</span><span class="sxs-lookup"><span data-stu-id="60161-310">Examples</span></span>
  
- <span data-ttu-id="60161-311">Contoso bail non-&amp;F</span><span class="sxs-lookup"><span data-stu-id="60161-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="60161-312">Contoso bail RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="60161-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="60161-313">Contoso appartient</span><span class="sxs-lookup"><span data-stu-id="60161-313">Contoso Owned</span></span>
    
- <span data-ttu-id="60161-314">Filiale en location</span><span class="sxs-lookup"><span data-stu-id="60161-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="60161-315">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="60161-315">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="60161-316">Les paramètres OwnershipTypeId et OwnershipTypeDesc sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="60161-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="60161-317">Définir des noms de réseaux</span><span class="sxs-lookup"><span data-stu-id="60161-317">Define Network Names</span></span>

<span data-ttu-id="60161-318">Les types de réseaux permettent de décrire différents types de réseaux au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="60161-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="60161-319">Cela vous permet de filtrer les types de réseaux spécifiques (ou de les filtrer).</span><span class="sxs-lookup"><span data-stu-id="60161-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60161-320">Il est vivement recommandé de définir des noms de réseau, mais facultatif.</span><span class="sxs-lookup"><span data-stu-id="60161-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="60161-321">Si vous décidez de ne pas définir de nom réseau, assurez-vous que chaque entrée CqdNetwork a un BuildingId de 0.</span><span class="sxs-lookup"><span data-stu-id="60161-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="60161-322">Exemples</span><span class="sxs-lookup"><span data-stu-id="60161-322">Examples</span></span>
  
- <span data-ttu-id="60161-323">VPN</span><span class="sxs-lookup"><span data-stu-id="60161-323">VPN</span></span>
    
- <span data-ttu-id="60161-324">LABO</span><span class="sxs-lookup"><span data-stu-id="60161-324">LAB</span></span>
    
  <span data-ttu-id="60161-325">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="60161-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="60161-326">Les paramètres NetworkNameID et nom réseau sont requis, le paramètre NetworkType est facultatif, mais recommandé.</span><span class="sxs-lookup"><span data-stu-id="60161-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="60161-327">Importer des bâtiments</span><span class="sxs-lookup"><span data-stu-id="60161-327">Import Buildings</span></span>

<span data-ttu-id="60161-328">L’importation d’immeubles vous donne la possibilité de créer des analyses spécifiques (appels médiocres par bâtiment sur WiFi/filaire, etc.).</span><span class="sxs-lookup"><span data-stu-id="60161-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="60161-329">Cette étape est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="60161-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="60161-330">Avant d’importer un nouveau bâtiment, une BuildingKey prédéfinie doit déjà être identifiée.</span><span class="sxs-lookup"><span data-stu-id="60161-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="60161-331">Pour ce faire, utilisez la commande SQL « SELECT MAX (BuildingKey) FROM CqdBuilding » pour identifier la valeur actuelle et ajouter 1 au résultat.</span><span class="sxs-lookup"><span data-stu-id="60161-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="60161-332">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="60161-332">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="60161-333">Les paramètres BuildingKey, nom du bâtiment, BuildingShortName, OwnershipTypeId, BuildingTypeId sont requis, et les autres paramètres sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="60161-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="60161-334">Importez des sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="60161-334">Import Subnets</span></span>

<span data-ttu-id="60161-335">L’importation d’immeubles vous donne la possibilité de créer des analyses spécifiques (appels médiocres par bâtiment sur WiFi/filaire, etc.).</span><span class="sxs-lookup"><span data-stu-id="60161-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="60161-336">Cette étape est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="60161-336">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="60161-337">Importez des sous-réseaux et associez-les aux bâtiments importés lors de la dernière étape.</span><span class="sxs-lookup"><span data-stu-id="60161-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="60161-338">Si vous décidez de ne pas remplir nom réseau, assurez-vous que chaque entrée de ce tableau utilise un NetworkNameID de 0.</span><span class="sxs-lookup"><span data-stu-id="60161-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="60161-339">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="60161-339">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

<span data-ttu-id="60161-340">Les paramètres réseau et UpdatedDate sont obligatoires, et les autres paramètres sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="60161-340">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="60161-341">Facultatif : BSSID</span><span class="sxs-lookup"><span data-stu-id="60161-341">Optional: BSSID</span></span>

<span data-ttu-id="60161-342">Le fait de renseigner les informations BSSID vous donne accès à des flux Wi-Fi supplémentaires par Controller ou radio.</span><span class="sxs-lookup"><span data-stu-id="60161-342">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="60161-343">Il s’agit d’une nouveauté de filtrage par bâtiment ou sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="60161-343">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="60161-344">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="60161-344">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="60161-345">**Détails sur CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="60161-345">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="60161-346">**Comme illustré dans bord**</span><span class="sxs-lookup"><span data-stu-id="60161-346">**As shown in CQD**</span></span>|<span data-ttu-id="60161-347">**Table CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="60161-347">**CQDBssid Table**</span></span>|<span data-ttu-id="60161-348">**Exemples d’entrée**</span><span class="sxs-lookup"><span data-stu-id="60161-348">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="60161-349">AP NName</span><span class="sxs-lookup"><span data-stu-id="60161-349">Ap NName</span></span>  <br/> |<span data-ttu-id="60161-350">CALQUE</span><span class="sxs-lookup"><span data-stu-id="60161-350">AP</span></span>  <br/> |<span data-ttu-id="60161-351">AP1</span><span class="sxs-lookup"><span data-stu-id="60161-351">AP1</span></span>  <br/> |
|<span data-ttu-id="60161-352">BBssid</span><span class="sxs-lookup"><span data-stu-id="60161-352">BBssid</span></span>  <br/> |<span data-ttu-id="60161-353">BSS</span><span class="sxs-lookup"><span data-stu-id="60161-353">BSS</span></span>  <br/> |<span data-ttu-id="60161-354">00-00-00-00-00-00 (vous devez utiliser le fformat délimité)</span><span class="sxs-lookup"><span data-stu-id="60161-354">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="60161-355">Commande</span><span class="sxs-lookup"><span data-stu-id="60161-355">Controller</span></span>  <br/> |<span data-ttu-id="60161-356">Bâtiment</span><span class="sxs-lookup"><span data-stu-id="60161-356">Building</span></span>  <br/> |<span data-ttu-id="60161-357">Aruba AP 7</span><span class="sxs-lookup"><span data-stu-id="60161-357">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="60161-358">Device</span><span class="sxs-lookup"><span data-stu-id="60161-358">Device</span></span>  <br/> |<span data-ttu-id="60161-359">ess</span><span class="sxs-lookup"><span data-stu-id="60161-359">ess</span></span>  <br/> |<span data-ttu-id="60161-360">Controller1</span><span class="sxs-lookup"><span data-stu-id="60161-360">Controller1</span></span>  <br/> |
|<span data-ttu-id="60161-361">-</span><span class="sxs-lookup"><span data-stu-id="60161-361">Radio</span></span>  <br/> |<span data-ttu-id="60161-362">phy</span><span class="sxs-lookup"><span data-stu-id="60161-362">phy</span></span>  <br/> |<span data-ttu-id="60161-363">BGN</span><span class="sxs-lookup"><span data-stu-id="60161-363">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="60161-364">Traitement des données importées</span><span class="sxs-lookup"><span data-stu-id="60161-364">Processing the imported data</span></span>

<span data-ttu-id="60161-365">Par défaut, une fois que vous avez importé des données de bâtiment/réseau, il s’applique uniquement aux enregistrements générés après ce moment.</span><span class="sxs-lookup"><span data-stu-id="60161-365">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="60161-366">Pour marquer tous les enregistrements précédents avec ces nouvelles données, vous devez exécuter la procédure stockée CqdUpdateBuilding, comme illustré ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="60161-366">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="60161-367">Attribuez-la à la date de votre premier enregistrement (à l’aide de la commande SELECT MIN (StartTime) de CqdPartitionedStreamView), d’une date de demain, puis de la valeur NULL pour les deux dernières valeurs.</span><span class="sxs-lookup"><span data-stu-id="60161-367">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="60161-368">Lorsque les données sont associées à des données de flux, le cube SSIS doit retraiter tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="60161-368">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="60161-369">Cela s’applique également lors de l’ajout en bloc des données de BSSID/fournisseur de services Internet.</span><span class="sxs-lookup"><span data-stu-id="60161-369">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="60161-370">Assurez-vous que la case « processus complet » est cochée.</span><span class="sxs-lookup"><span data-stu-id="60161-370">Ensure that "Process Full" is selected.</span></span>
  

