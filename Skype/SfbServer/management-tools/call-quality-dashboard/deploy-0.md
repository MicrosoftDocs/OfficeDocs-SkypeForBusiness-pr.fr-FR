---
title: Déployer le tableau de bord qualité appel pour Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Résumé : En savoir plus sur le processus de déploiement pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: ff8f9bae2c292720bb3fd9943bc541a8eeb6759c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a><span data-ttu-id="d3ba6-104">Déployer le tableau de bord qualité appel pour Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d3ba6-104">Deploy Call Quality Dashboard for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d3ba6-105">**Résumé :** Obtenir des informations sur le processus de déploiement pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="d3ba6-106">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="d3ba6-107">Vue d’ensemble du déploiement</span><span class="sxs-lookup"><span data-stu-id="d3ba6-107">Deployment Overview</span></span>

<span data-ttu-id="d3ba6-108">Appel de qualité du tableau de bord (CQD) se compose de trois composants principaux :</span><span class="sxs-lookup"><span data-stu-id="d3ba6-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="d3ba6-109">**Archivage de base de données**, où les données de la qualité d’expérience (QoE) sont répliquées et stockées.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="d3ba6-110">**Cube**, où les données à partir de la base de données Archive de QoE sont regroupées pour optimisé et un accès rapide.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="d3ba6-111">**Portail**, où les utilisateurs peuvent facilement rechercher et visualiser les données QoE.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Composants CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="d3ba6-113">Le processus d’installation pour l’archivage de QoE implique la création de la base de données Archive de QoE, le déploiement d’une procédure SQL Server stockées qui déplace les données de la source de base de données QoE métrique dans la base de données Archive de QoE et configuration de la tâche de l’Agent de SQL Server pour exécuter la commande stockées procédure à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="d3ba6-114">Déploiement de cube Obtient des informations à l’utilisateur où le QoE Archive se trouve, déploie le cube et configure un travail d’agent SQL Server régulière qui actualise le cube à intervalle régulier.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="d3ba6-115">Installation de portail crée une base de données de référentiel qui stocke le mappage des utilisateurs CQD aux rapports/requêtes chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="d3ba6-116">Il définit ensuite une application web IIS est le tableau de bord où les utilisateurs peuvent voir un ensemble de rapports prédéfinis ainsi que personnaliser et créer leurs propres requêtes pour visualiser les données du cube.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="d3ba6-117">L’installation du portail crée deux applications web supplémentaires qui expose des API permettant aux utilisateurs d’accéder par programme le référentiel et le cube.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="d3ba6-118">(Ces API sont utilisées en interne par le tableau de bord.)</span><span class="sxs-lookup"><span data-stu-id="d3ba6-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="d3ba6-119">**Phase de**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-119">**Phase**</span></span>|<span data-ttu-id="d3ba6-120">**Étapes**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-120">**Steps**</span></span>|<span data-ttu-id="d3ba6-121">**Rôles et appartenance à un groupe**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-121">**Roles and group membership**</span></span>|<span data-ttu-id="d3ba6-122">**Documentation**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d3ba6-123">Installer les logiciels et le matériel requis.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="d3ba6-124">Choisissez la configuration CQD et choisissez un SQL Server à partir de laquelle effectuer l’installation.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="d3ba6-125">Utilisateur du domaine membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="d3ba6-126">Section de « Installation configuration requise » dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="d3ba6-127">Installation de CQD.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="d3ba6-128">Exécutez le fichier MSI suivant le document de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="d3ba6-129">Pour exécuter le programme d’installation, le compte d’installation doit être un utilisateur de domaine qui est membre du groupe Administrateurs local et ont un accès en lecture à la base de données QoE métrique sur le serveur d’analyse.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="d3ba6-130">Sections « Comptes et étapes de déploiement » dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="d3ba6-131">Accorder l’accès de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="d3ba6-132">Gérez les autorisations utilisateur sur le portail, nous recommandons à l’aide de l’autorisation d’URL, ce qui a été introduit dans IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="d3ba6-133">Pour plus d’informations, consultez [Autorisation d’URL de présentation IIS 7.0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="d3ba6-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="d3ba6-134">Utilisateur du domaine membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="d3ba6-135">Gestion de l’accès utilisateur pour la section du portail dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="d3ba6-136">Facultatif : Fournissent des informations de mappage de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="d3ba6-137">Remplir le réseau et le mappage de création des tables dans la base de données Archive de QoE.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="d3ba6-138">Un compte avec un accès en écriture à la base de données Archive de QoE.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="d3ba6-139">Section « En fournissant les informations de sous-réseau » dans la documentation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   
## 

<span data-ttu-id="d3ba6-140">Déploiement du tableau de bord qualité appel implique la configuration de l’infrastructure et l’installation du logiciel.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="d3ba6-141">La procédure suivante décrit le processus.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-141">The following procedure outlines the process.</span></span>
  
### <a name="deployment-steps"></a><span data-ttu-id="d3ba6-142">Étapes de déploiement</span><span class="sxs-lookup"><span data-stu-id="d3ba6-142">Deployment Steps</span></span>

1. <span data-ttu-id="d3ba6-143">Copier le CallQualityDashboard.msi sur l’ordinateur où le composant de base de données archive de CQD doit être installé (il s’agit de l’ordinateur sur lequel SQL Server installé).</span><span class="sxs-lookup"><span data-stu-id="d3ba6-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="d3ba6-144">Exécutez le MSI (Windows vous invite à exécuter avec les privilèges d’administrateur, de le faire).</span><span class="sxs-lookup"><span data-stu-id="d3ba6-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="d3ba6-145">Accepter le CLUF.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="d3ba6-146">Sélectionnez le dossier de destination où les fichiers liés à des composants de tableau de bord qualité appeler seront situé ou acceptez l’emplacement par défaut.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="d3ba6-147">Sélectionnez toutes les fonctions.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-147">Select all features.</span></span>
    
6. <span data-ttu-id="d3ba6-148">Dans la page Configuration de l’Archive QoE, fournissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3ba6-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="d3ba6-149">**Les mesures QoE SQL Server :** Nom de l’instance de SQL Server pour où se trouve la base de données de mesures QoE (il s’agit de la source de données).</span><span class="sxs-lookup"><span data-stu-id="d3ba6-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="d3ba6-150">**Nom de SQL Server QoE Archive :** Ce champ en lecture seule et fixe pour le nom de domaine complet de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="d3ba6-151">Archivage de base de données peut être installé uniquement sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="d3ba6-152">**QoE Archive SQL Server Instance :** Un nom d’instance SQL Server local pour lequel la base de données d’Archive doit être créé.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="d3ba6-153">Pour utiliser une instance de SQL Server par défaut, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="d3ba6-154">Pour utiliser une instance nommée de SQL Server, spécifiez le nom d’instance (par exemple, le nom après le "\").</span><span class="sxs-lookup"><span data-stu-id="d3ba6-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="d3ba6-155">**Base de données Archive de QoE :** Par défaut, cette option est définie à « Créer nouvelle base de données ».</span><span class="sxs-lookup"><span data-stu-id="d3ba6-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="d3ba6-156">Étant donné que la mise à niveau de la base de données Archive n’est pas pris en charge, le seul cas dans lequel l’option « Utiliser la base de données existante » peut être utilisée est si la base de données d’archivage existante a le même schéma que la génération doit être installé.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="d3ba6-157">**De base de données de répertoire du fichier :** Chemin d’accès où les fichiers de base de données (.mdf et .ldf) pour la base de données d’archivage doivent être placés.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="d3ba6-158">Ce doit être sur un lecteur distinct (HDD2 dans la configuration matérielle recommandée) du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="d3ba6-159">Notez que les noms de fichier sont corrigés dans l’installation, afin d’éviter tout conflit potentiel, il est recommandé qu’un répertoire vide sans fichiers utilisé.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="d3ba6-160">**Utilisation de plusieurs Partitions :** La valeur par défaut est défini sur « Partition plusieurs », ce qui nécessite une édition de Business Intelligence ou l’édition entreprise de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="d3ba6-161">Pour l’Édition Standard, l’option « Partition unique ».</span><span class="sxs-lookup"><span data-stu-id="d3ba6-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="d3ba6-162">Notez que les performances de traitement de cube peuvent être affectés si la Partition unique est utilisée.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d3ba6-163">La sélection de l’option d’utilisation de plusieurs Partitions ne peut pas être modifiée une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="d3ba6-164">Pour le modifier, le Cube doit être la première fonction désinstallé et réinstallé à l’aide de « modifier » dans le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="d3ba6-165">**Partition de répertoire du fichier :** Chemin d’accès où les partitions de la base de données Archive de QoE doivent être placées.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="d3ba6-166">Ce doit être sur un lecteur distinct (HDD3 dans la configuration matérielle recommandée) à partir du lecteur du système d’exploitation et le lecteur de fichiers de journal de base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="d3ba6-167">Notez que les noms de fichier sont corrigés dans l’installation, afin d’éviter tout conflit potentiel, il est recommandé qu’un répertoire vide sans fichiers utilisé.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="d3ba6-168">**Utilisateur de travail de l’Agent SQL - nom d’utilisateur &amp; mot de passe :** Nom de compte de service de domaine et mot de passe (masqué) qui sera utilisé pour exécuter l’étape « Archive les données QoE » de la tâche de l’Agent de SQL Server (qui s’exécute la procédure stockée pour extraire les données de base de données de mesures QoE dans Archive de base de données, ce compte doit avoir accès en lecture à QoE métriques de base de données,  comme indiqué dans la section comptes.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="d3ba6-169">Ce compte doit également disposer d’une connexion dans l’Instance de SQL Server QoE Archive).</span><span class="sxs-lookup"><span data-stu-id="d3ba6-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d3ba6-170">Le compte de l’instance de SQL Server sous lequel s’exécute, telles que NT SERVICE\MSSQLSERVER, doit avoir accès aux répertoires indiquées ci-dessus pour réussir l’installation.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="d3ba6-171">Pour plus d’informations, voir [Configurer des autorisations de système de fichiers pour l’accès au moteur de base de données](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d3ba6-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="d3ba6-172">Après avoir cliqué sur Suivant, le programme d’installation effectue les vérifications préalables et rapport si des problèmes sont rencontrés.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="d3ba6-173">Lorsque tous les pré-requis chèques passe, le programme d’installation passe à la page Configuration du Cube.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d3ba6-174">Si le programme d’installation affiche un avertissement indiquant que le service SQL Server Agent pour l’instance de SQL Server Archive QoE n’est actuellement pas en cours d’exécution, l’installation peut se poursuivre, mais après l’installation, veuillez vous assurer que SQL Agent est en cours d’exécution et le type de démarrage de service Automatique afin que la tâche planifiée s’exécute.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="d3ba6-175">Dans la page de Configuration du Cube, fournissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3ba6-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="d3ba6-176">**Nom de SQL Server QoE Archive :** Ce champ en lecture seule et fixe pour le nom de domaine complet de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="d3ba6-177">Cube peut être installé uniquement à partir de l’ordinateur qui contient la base de données Archive de QoE (Remarque.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="d3ba6-178">Cube proprement dit peut être installé sur un ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="d3ba6-179">Voir ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="d3ba6-179">See below)</span></span>
    
   - <span data-ttu-id="d3ba6-180">**QoE Archive SQL Server Instance :** Nom de l’instance de SQL Server pour où se trouve la base de données Archive QoE.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="d3ba6-181">Pour spécifier une instance de SQL Server par défaut, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="d3ba6-182">Pour spécifier une instance nommée de SQL Server, entrez le nom d’instance (par exemple, le nom après le "\").</span><span class="sxs-lookup"><span data-stu-id="d3ba6-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="d3ba6-183">Si le composant de QoE Archive a été sélectionné pour l’installation, ce champ est prédéfinie avec la valeur fournie dans la page Configuration de l’Archive QoE.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="d3ba6-184">**De cube Analysis Server :** Nom de l’instance SQL Server Analysis Services pour lequel le cube est créé.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="d3ba6-185">Ce peut être un autre ordinateur, mais l’utilisateur chargé de l’installation doit être un membre du groupe Administrateurs de serveur de l’instance de SQL Server Analysis Service cible.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="d3ba6-186">Pour plus d’informations sur la configuration des autorisations d’administrateur de serveur Analysis Services, voir [Accorder des autorisations administrateur du serveur (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="d3ba6-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="d3ba6-187">**Utilisation de plusieurs Partitions :** La valeur par défaut est défini sur « Partition plusieurs », ce qui nécessite une édition de Business Intelligence ou l’édition entreprise de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="d3ba6-188">Pour l’Édition Standard, l’option « Partition unique ».</span><span class="sxs-lookup"><span data-stu-id="d3ba6-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="d3ba6-189">Notez que les performances de traitement de cube peuvent être affectés si la Partition unique est utilisée.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="d3ba6-190">La sélection de l’option d’utilisation de plusieurs Partitions ne peut pas être modifiée une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="d3ba6-191">Pour le modifier, le Cube doit être la première fonction désinstallé et réinstallé à l’aide de « modifier » dans le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="d3ba6-192">**Utilisateur - nom d’utilisateur de cube &amp; mot de passe :** Nom de compte de service de domaine et mot de passe (masqué) qui déclenchera le traitement du cube.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="d3ba6-193">Si le composant de QoE Archive a été sélectionné pour l’installation, ce champ est préremplie avec la valeur fournie dans la page Configuration de l’Archive pour l’utilisateur de travail de l’Agent SQL, mais nous vous recommandons de spécifier un compte de service de domaine différent afin que le programme d’installation peut accorder le au moins le privilège requis pour l’il.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="d3ba6-194">Lorsque vous cliquez sur Suivant, une autre série de validation est effectuée et que tout problème sera déclarée.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="d3ba6-195">En cas de réussite de la validation, le programme d’installation passe à la page Configuration du portail.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="d3ba6-196">Dans la page de Configuration du portail, fournissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3ba6-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="d3ba6-197">**De SQL Server QoE Archive :** Nom de l’instance de SQL Server pour où se trouve la base de données Archive de QoE.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="d3ba6-198">Notez que contrairement à la page de Configuration de l’Archive QoE et la page de Configuration du Cube, le nom de l’ordinateur n’est pas fixe et doit être fourni.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="d3ba6-199">Si le composant de QoE Archive a été sélectionné pour l’installation, ce champ est prédéfinie avec la valeur fournie dans la page Configuration de l’Archive QoE.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="d3ba6-200">**De cube Analysis Server :** Nom de l’instance SQL Server Analysis Services pour où se trouve le cube.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="d3ba6-201">Si le composant de Cube a été sélectionné pour l’installation, ce champ est préremplie avec la valeur fournie dans la page Configuration du Cube.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="d3ba6-202">**Référentiel SQL Server :** Nom de l’instance de SQL Server dans laquelle la base de données de référentiel doit être créé.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="d3ba6-203">Si le nom de l’instance de SQL Server pour où se trouve la base de données Archive de QoE a été fourni plus haut dans le programme d’installation (dans d’autres composants), ce champ est préremplie avec le nom d’instance QoE Archive DB SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="d3ba6-204">Cela peut être n’importe quelle instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="d3ba6-205">**Base de données de référentiel :** Par défaut, l’option est définie à « Créer nouvelle base de données ».</span><span class="sxs-lookup"><span data-stu-id="d3ba6-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="d3ba6-206">Étant donné que la mise à niveau de la base de données de référentiel n’est pas pris en charge, le seul cas dans lequel l’option « Utiliser la base de données existante » peut être utilisée est si la base de données de référentiel existant a le même schéma que la génération doit être installé.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="d3ba6-207">**Utilisateur du Pool d’applications IIS - nom d’utilisateur &amp; mot de passe :** Le pool d’applications IIS doit s’exécuter sous le compte.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="d3ba6-208">Les champs nom d’utilisateur et mot de passe seront grisés si les comptes du système intégré sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="d3ba6-209">Ces champs sont activés uniquement si « Autre » est sélectionné dans la liste déroulante afin que l’utilisateur puisse entrer les informations de compte de service de domaine.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="d3ba6-210">Lorsque vous cliquez sur Suivant, l’arrondi final de la validation est effectué afin de garantir que les instances de SQL Server sont accessibles à l’aide des informations d’identification fournies et que IIS est disponible sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="d3ba6-211">En cas de réussite de la validation, le programme d’installation poursuit l’installation.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="d3ba6-212">Lorsque le programme d’installation est terminé, très probablement le travail de l’Agent de SQL Server est en cours, en effectuant le chargement initial des données QoE et le traitement du cube.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="d3ba6-213">Selon la quantité de données QoE, le portail n’aura pas les données disponibles pour affichage encore.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="d3ba6-214">Pour vérifier l’état de la charge des données et le traitement du cube, accédez à `http://<machinename>/CQD/#/Health`.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="d3ba6-215">Notez que l’URL de vérification de l’état du téléchargement de traitement de cube respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="d3ba6-216">Si vous entrez « santé » l’URL ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="d3ba6-217">Vous devez entrer « Santé » à la fin de l’URL avec une majuscule H.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="d3ba6-218">Messages du journal détaillée seront affiche si le mode débogage est activé.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="d3ba6-219">Pour activer le mode débogage, accédez à **%SYSTEMDRIVE%\Program Files\Skype pour le CQD\QoEDataService\web.config Business 2015**et mettre à jour la ligne suivante afin que la valeur est définie sur **True**:</span><span class="sxs-lookup"><span data-stu-id="d3ba6-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="d3ba6-220">La page principale du portail est accessible via `http://<machinename>/CQD`.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="d3ba6-221">Gestion de l’accès de l’utilisateur pour le portail</span><span class="sxs-lookup"><span data-stu-id="d3ba6-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="d3ba6-222">Gérez les autorisations utilisateur sur le portail, nous recommandons à l’aide de l’autorisation d’URL, ce qui a été introduit dans IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="d3ba6-223">Pour plus d’informations sur la sécurité IIS, reportez-vous à la section [Présentation IIS 7.0 l’autorisation d’URL ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="d3ba6-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="d3ba6-224">Toutes les applications web ou site web héritent par défaut configuré pour l’ensemble IIS, qui est généralement de « Autoriser tous les utilisateurs » l’autorisation d’URL.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="d3ba6-225">Si l’accès au portail doit être plus restrictif, puis les administrateurs peuvent accorder l’accès pour seulement le groupe d’utilisateurs spécifique en modifiant les « règles d’autorisation ».</span><span class="sxs-lookup"><span data-stu-id="d3ba6-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Déployer la qualité des appels - règles d’autorisation dans IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="d3ba6-227">L’icône de règles d’autorisation est à ne pas confondre avec l’autorisation « .NET » dans la section d’ASP.NET, qui est un mécanisme d’autorisation différents.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="d3ba6-228">Les administrateurs doivent d’abord supprimer la règle héritée « autoriser tous les utilisateurs ».</span><span class="sxs-lookup"><span data-stu-id="d3ba6-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="d3ba6-229">Cela empêche les utilisateurs non autorisés d’accéder au portail.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Déployer CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="d3ba6-231">Ensuite, les administrateurs doivent ajouter de nouvelles règles Autoriser et donner à des utilisateurs spécifiques l’autorisation pour accéder au portail.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="d3ba6-232">Il est recommandé qu’un groupe local appelé « CQDPortalUsers » est créé pour gérer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Déployer le Tableau de bord de la qualité des appels](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="d3ba6-234">Les détails de configuration sont stockés dans le fichier web.config situé dans le répertoire physique du portail.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="d3ba6-235">L’étape suivante consiste à configurer le tableau de bord de la CQD.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="d3ba6-236">Une fois que les utilisateurs sont authentifiés par IIS, ils doivent disposer d’autorisations sur le répertoire CQD pour accéder au contenu de portail web.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="d3ba6-237">Il est possible de modifier les listes ACL par le biais de l’onglet sécurité des propriétés du répertoire CQD pour ajouter des utilisateurs individuels ou des groupes ; Toutefois, l’approche recommandée consiste à laisser les autorisations de fichiers inchangés.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="d3ba6-238">Au lieu de cela, modifiez le paramètre IIS pour utiliser le processus de travail IIS pour accéder au répertoire CQD quel utilisateur est authentifié.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d3ba6-239">Il est important de ne modifier ce paramètre pour l’application de CQD et non pour les deux applications API : QoEDataService et QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
### <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="d3ba6-240">Configuration de l’accès de fichier pour le CQD (tableau de bord)</span><span class="sxs-lookup"><span data-stu-id="d3ba6-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="d3ba6-241">Ouvrez l’éditeur de Configuration de CQD.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="d3ba6-243">Sous la Section, choisissez **system.webServer/serverRuntime**.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="d3ba6-245">Remplacez authenticatedUserOverride par **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels - Éditeur de configuration](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="d3ba6-247">Cliquez sur **Appliquer** dans la partie droite de la page.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="d3ba6-248">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="d3ba6-248">Known Issues</span></span>

<span data-ttu-id="d3ba6-249">Dans de rares cas, le programme d’installation ne peut pas créer les paramètres appropriés dans IIS.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-249">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="d3ba6-250">Modification manuelle est nécessaire pour permettre aux utilisateurs de se connecter à la CQD.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-250">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="d3ba6-251">Si les utilisateurs rencontrent des problèmes de connexion, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d3ba6-251">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="d3ba6-252">Ouvrir le Gestionnaire des services Internet haut et accédez au Site Web par défaut.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-252">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="d3ba6-254">Cliquez sur « Authentification ».</span><span class="sxs-lookup"><span data-stu-id="d3ba6-254">Click on "Authentication".</span></span> <span data-ttu-id="d3ba6-255">Si le « Anonyme », « L’emprunt d’identité ASP.NET », « Authentification par formulaire » et « Authentification Windows » ne correspondent pas les paramètres présentés ci-dessous, les changer manuellement pour faire correspondre les paramètres ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-255">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="d3ba6-256">Tous les autres mécanismes d’authentification doivent être désactivés.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-256">All other authentication mechanisms should be disabled.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="d3ba6-258">Pour « Authentification Windows », cliquez sur Paramètres avancés sur le côté droit.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-258">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="d3ba6-260">Accepter la valeur « Protection étendue » et cochez la case « authentification du mode noyau activer ».</span><span class="sxs-lookup"><span data-stu-id="d3ba6-260">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="d3ba6-262">Répétez les étapes ci-dessus pour chacune des entrées ci-dessous « Site Web par défaut » « CQD », « QoEDataService » et « QoERepositoryService ».</span><span class="sxs-lookup"><span data-stu-id="d3ba6-262">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="d3ba6-263">Pour les liaisons de port HTTP et HTTPS le programme d’installation va créer des liaisons de port sur les numéros de port par défaut (port 80 pour HTTP) et le port 443 pour HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-263">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="d3ba6-264">S’il existe un autre site Web sur l’ordinateur qui utilise ces liaisons, il y aura un conflit et il est impossible de prédire le comportement d’IIS.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-264">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="d3ba6-265">La meilleure façon d’éviter ce problème est de s’assurer qu’aucun autre site Web n’est mappés sur les ports 80 et 443 avant d’installer CQD.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-265">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="d3ba6-266">Pour activer le protocole SSL/TLS dans IIS et forcer les utilisateurs à se connecter via le protocole HTTPS sécurisé au lieu de HTTP :</span><span class="sxs-lookup"><span data-stu-id="d3ba6-266">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="d3ba6-267">Configurer le protocole SSL (Secure Sockets Layer) dans IIS, consultez [Configuration de SSL dans IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="d3ba6-267">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="d3ba6-268">Une fois fait, remplacez `http` avec `https`.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-268">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="d3ba6-269">Pour obtenir des instructions sur l’activation de TLS dans les connexions SQL Server, voir [comment activer le cryptage SSL pour une instance de SQL Server à l’aide de Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="d3ba6-269">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
### <a name="cube-sync-fails"></a><span data-ttu-id="d3ba6-270">Échec de la synchronisation de cube</span><span class="sxs-lookup"><span data-stu-id="d3ba6-270">Cube Sync Fails</span></span>

<span data-ttu-id="d3ba6-271">QoEMetrics peut contenir des enregistrements non valides selon les horloges de l’utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-271">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="d3ba6-272">Si le délai maximal autorisé est supérieur à 60 ans, l’importation de cube échoue.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-272">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="d3ba6-273">Vérifiez les Min et Max début/fin, à l’aide des sélections ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-273">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="d3ba6-274">Recherche et suppression d’enregistrements dans le futur dépassée et très éloigné, ils peuvent ne pas être et qu’ils seront diviser les processus de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-274">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="d3ba6-275">Sélectionnez MIN(StartTime) à partir de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="d3ba6-275">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="d3ba6-276">Sélectionnez MAX(StartTime) à partir de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="d3ba6-276">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="d3ba6-277">Sélectionnez MIN(EndTime) à partir de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="d3ba6-277">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="d3ba6-278">Sélectionnez MAX(EndTime) à partir de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="d3ba6-278">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="d3ba6-279">Tâches après installation</span><span class="sxs-lookup"><span data-stu-id="d3ba6-279">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="d3ba6-280">Importation des bâtiments et des réseaux</span><span class="sxs-lookup"><span data-stu-id="d3ba6-280">Importing Buildings and Networks</span></span>

<span data-ttu-id="d3ba6-281">Après l’installation de CQD, effectuez les tâches de configuration suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3ba6-281">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="d3ba6-282">Définir des types de construction (recommandés)</span><span class="sxs-lookup"><span data-stu-id="d3ba6-282">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="d3ba6-283">Définir les types de propriété de construction (recommandés)</span><span class="sxs-lookup"><span data-stu-id="d3ba6-283">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="d3ba6-284">Définir les types de réseau (recommandés)</span><span class="sxs-lookup"><span data-stu-id="d3ba6-284">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="d3ba6-285">Bâtiments d’importation (recommandé)</span><span class="sxs-lookup"><span data-stu-id="d3ba6-285">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="d3ba6-286">Importation des sous-réseaux (recommandés)</span><span class="sxs-lookup"><span data-stu-id="d3ba6-286">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="d3ba6-287">Définir des Types de construction</span><span class="sxs-lookup"><span data-stu-id="d3ba6-287">Define Building Types</span></span>

<span data-ttu-id="d3ba6-288">Types de construction sont utilisés pour décrire les définitions de bâtiments différents types au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-288">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d3ba6-289">Cette étape est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-289">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="d3ba6-290">Exemples</span><span class="sxs-lookup"><span data-stu-id="d3ba6-290">Examples</span></span>
  
- <span data-ttu-id="d3ba6-291">Siège social</span><span class="sxs-lookup"><span data-stu-id="d3ba6-291">Headquarters</span></span>
    
- <span data-ttu-id="d3ba6-292">Bureau à distance</span><span class="sxs-lookup"><span data-stu-id="d3ba6-292">Remote Office</span></span>
    
- <span data-ttu-id="d3ba6-293">Emplacement de l’entreprise commune</span><span class="sxs-lookup"><span data-stu-id="d3ba6-293">Joint-venture location</span></span>
    
 <span data-ttu-id="d3ba6-294">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-294">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters') 
  
```

<span data-ttu-id="d3ba6-295">Les paramètres BuildingTypeId et BuildingTypeDesc sont requis.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-295">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="d3ba6-296">Définir les Types de propriété de construction</span><span class="sxs-lookup"><span data-stu-id="d3ba6-296">Define Building Ownership Types</span></span>

<span data-ttu-id="d3ba6-297">Les types de propriété sont utilisés pour distinguer les actifs loués vs détenus.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-297">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3ba6-298">Cette étape est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-298">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="d3ba6-299">Exemples</span><span class="sxs-lookup"><span data-stu-id="d3ba6-299">Examples</span></span>
  
- <span data-ttu-id="d3ba6-300">Contoso louées non-RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="d3ba6-300">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="d3ba6-301">Contoso louées RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="d3ba6-301">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="d3ba6-302">La propriété de Contoso</span><span class="sxs-lookup"><span data-stu-id="d3ba6-302">Contoso Owned</span></span>
    
- <span data-ttu-id="d3ba6-303">Filiale spécialisée</span><span class="sxs-lookup"><span data-stu-id="d3ba6-303">Subsidiary Leased</span></span>
    
 <span data-ttu-id="d3ba6-304">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-304">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc],
)

VALUES
(1,
'Contoso Owned',
)
```

<span data-ttu-id="d3ba6-305">Les paramètres OwnershipTypeId et OwnershipTypeDesc sont requis.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-305">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="d3ba6-306">Définir des noms de réseau</span><span class="sxs-lookup"><span data-stu-id="d3ba6-306">Define Network Names</span></span>

<span data-ttu-id="d3ba6-307">Types de réseau sont utilisés pour décrire les différents types de réseaux au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-307">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="d3ba6-308">Cela vous donne la possibilité de filtrer (ou isoler) les Types de réseau spécifiques.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-308">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3ba6-309">Il est vivement recommandé de définir les noms de réseau, mais elle est facultative.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-309">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="d3ba6-310">Si vous décidez de ne définit ne pas de noms de réseau, assurez-vous que le chaque entrée CqdNetwork a un BuildingId de 0.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-310">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="d3ba6-311">Exemples</span><span class="sxs-lookup"><span data-stu-id="d3ba6-311">Examples</span></span>
  
- <span data-ttu-id="d3ba6-312">VPN</span><span class="sxs-lookup"><span data-stu-id="d3ba6-312">VPN</span></span>
    
- <span data-ttu-id="d3ba6-313">ATELIER</span><span class="sxs-lookup"><span data-stu-id="d3ba6-313">LAB</span></span>
    
 <span data-ttu-id="d3ba6-314">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-314">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="d3ba6-315">Les paramètres NetworkNameID et NetworkName sont requis, le paramètre NetworkType est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-315">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="d3ba6-316">Bâtiments d’importation</span><span class="sxs-lookup"><span data-stu-id="d3ba6-316">Import Buildings</span></span>

<span data-ttu-id="d3ba6-317">Importation de bâtiments vous donne la possibilité d’obtenir création d’analyses spécifiques (appels médiocres par construction sur WiFi/câblé, etc.)..</span><span class="sxs-lookup"><span data-stu-id="d3ba6-317">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d3ba6-318">Cette étape est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-318">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="d3ba6-319">Avant d’importer une nouvelle génération vous disposez déjà d’un BuildingKey prédéfini identifié.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-319">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="d3ba6-320">Pour ce faire, émettez la commande « Sélectionner les MAX(BuildingKey) de CqdBuilding » SQL pour identifier la valeur actuelle et ajoute 1 au résultat.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-320">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="d3ba6-321">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-321">**Sample SQL Syntax**</span></span>
  
```
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

<span data-ttu-id="d3ba6-322">Le BuildingKey BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId des paramètres sont requis, les autres paramètres sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-322">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="d3ba6-323">Importer des sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="d3ba6-323">Import Subnets</span></span>

<span data-ttu-id="d3ba6-324">Importation de bâtiments vous donne la possibilité d’obtenir création d’analyses spécifiques (appels médiocres par construction sur WiFi/câblé, etc.)..</span><span class="sxs-lookup"><span data-stu-id="d3ba6-324">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d3ba6-325">Cette étape est facultative, mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-325">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="d3ba6-326">Importer des sous-réseaux et de les mapper aux bâtiments importés dans la dernière étape.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-326">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="d3ba6-327">Si vous décidez de ne pas remplir NetworkName, assurez-vous que chaque entrée de ce tableau utilise un NetworkNameID de 0.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-327">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="d3ba6-328">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-328">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

<span data-ttu-id="d3ba6-329">Le réseau et les paramètres UpdatedDate sont obligatoires, les autres paramètres sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-329">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="d3ba6-330">Facultatif : BSSID</span><span class="sxs-lookup"><span data-stu-id="d3ba6-330">Optional: BSSID</span></span>

<span data-ttu-id="d3ba6-331">Remplissage des informations de BSSID vous donne corrélation de flux WiFi supplémentaire par le contrôleur ou radio.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-331">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="d3ba6-332">C’est en plus du filtrage par bâtiment ou par sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-332">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="d3ba6-333">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-333">**Sample SQL Syntax**</span></span>
  
```
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

<span data-ttu-id="d3ba6-334">**Détails de la CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-334">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="d3ba6-335">**Comme illustré à la CQD**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-335">**As shown in CQD**</span></span>|<span data-ttu-id="d3ba6-336">**Table de CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-336">**CQDBssid Table**</span></span>|<span data-ttu-id="d3ba6-337">**Entrées de l’exemple**</span><span class="sxs-lookup"><span data-stu-id="d3ba6-337">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3ba6-338">PA Name</span><span class="sxs-lookup"><span data-stu-id="d3ba6-338">Ap NName</span></span>  <br/> |<span data-ttu-id="d3ba6-339">POINT D’ACCÈS</span><span class="sxs-lookup"><span data-stu-id="d3ba6-339">AP</span></span>  <br/> |<span data-ttu-id="d3ba6-340">POINT D’ACCÈS 1</span><span class="sxs-lookup"><span data-stu-id="d3ba6-340">AP1</span></span>  <br/> |
|<span data-ttu-id="d3ba6-341">BBssid</span><span class="sxs-lookup"><span data-stu-id="d3ba6-341">BBssid</span></span>  <br/> |<span data-ttu-id="d3ba6-342">BSS</span><span class="sxs-lookup"><span data-stu-id="d3ba6-342">BSS</span></span>  <br/> |<span data-ttu-id="d3ba6-343">00-00-00-00-00-00 (vous devez utiliser le format délimité)</span><span class="sxs-lookup"><span data-stu-id="d3ba6-343">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="d3ba6-344">Contrôleur de</span><span class="sxs-lookup"><span data-stu-id="d3ba6-344">Controller</span></span>  <br/> |<span data-ttu-id="d3ba6-345">Bâtiment</span><span class="sxs-lookup"><span data-stu-id="d3ba6-345">Building</span></span>  <br/> |<span data-ttu-id="d3ba6-346">Aruba PA 7</span><span class="sxs-lookup"><span data-stu-id="d3ba6-346">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="d3ba6-347">DISPOSITIF</span><span class="sxs-lookup"><span data-stu-id="d3ba6-347">Device</span></span>  <br/> |<span data-ttu-id="d3ba6-348">ess</span><span class="sxs-lookup"><span data-stu-id="d3ba6-348">ess</span></span>  <br/> |<span data-ttu-id="d3ba6-349">: Contrôleur1</span><span class="sxs-lookup"><span data-stu-id="d3ba6-349">Controller1</span></span>  <br/> |
|<span data-ttu-id="d3ba6-350">Radio</span><span class="sxs-lookup"><span data-stu-id="d3ba6-350">Radio</span></span>  <br/> |<span data-ttu-id="d3ba6-351">phy</span><span class="sxs-lookup"><span data-stu-id="d3ba6-351">phy</span></span>  <br/> |<span data-ttu-id="d3ba6-352">BGN</span><span class="sxs-lookup"><span data-stu-id="d3ba6-352">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="d3ba6-353">Traitement des données importées</span><span class="sxs-lookup"><span data-stu-id="d3ba6-353">Processing the imported data</span></span>

<span data-ttu-id="d3ba6-354">Par défaut, après avoir importé les données de construction ou le réseau qu’il s’applique uniquement aux enregistrements générés après ce point dans le temps.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-354">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="d3ba6-355">Pour marquer tous les enregistrements précédents avec ces nouvelles données, vous devrez exécuter la procédure stockée de CqdUpdateBuilding comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="d3ba6-355">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="d3ba6-356">Lui donner la date de votre premier enregistrement (identifier à l’aide de la commande Sélectionner le MIN(StartTime) à partir de SQL CqdPartitionedStreamView), une date de fin de demain, puis vide pour les deux dernières valeurs.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-356">Give it the date of your first record( identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="d3ba6-357">Une fois les données sont associées à des données de flux de données, le Cube SSIS doit retraiter tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-357">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="d3ba6-358">Cela s’applique également lorsque en bloc de l’ajout de données BSSID/fournisseur de services Internet.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-358">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="d3ba6-359">Assurez-vous que « Procédure complet » est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d3ba6-359">Ensure that "Process Full" is selected.</span></span>
  

