---
title: Déployer le tableau de bord appel qualité pour Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Résumé : Découvrez le processus de déploiement pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: c9d641a8202560e558e33014670b4b1060795477
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531225"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="13c33-104">Déployer le tableau de bord appel qualité pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="13c33-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="13c33-105">**Résumé :** Découvrez le processus de déploiement pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="13c33-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="13c33-106">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="13c33-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="13c33-107">Vue d’ensemble du déploiement</span><span class="sxs-lookup"><span data-stu-id="13c33-107">Deployment Overview</span></span>

<span data-ttu-id="13c33-108">Tableau de bord de qualité d’appel (CQD) se compose de trois composants principaux :</span><span class="sxs-lookup"><span data-stu-id="13c33-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="13c33-109">**Base de données d’archivage**, où les données de qualité de l’expérience (QoE) sont répliquées et stockées.</span><span class="sxs-lookup"><span data-stu-id="13c33-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="13c33-110">**Cube**, où les données à partir de la base de données QoE Archive sont regroupées pour optimisé et un accès rapide.</span><span class="sxs-lookup"><span data-stu-id="13c33-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="13c33-111">**Portail**, où les utilisateurs peuvent facilement des requêtes et visualiser les données QoE.</span><span class="sxs-lookup"><span data-stu-id="13c33-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Composants CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="13c33-113">Le processus d’installation pour l’archivage QoE implique la création de la base de données QoE Archive, le déploiement d’une procédure stockée SQL Server qui déplace les données de la source de base de données des mesures QoE dans la base de données QoE Archive et configurer le travail de l’Agent SQL Server pour exécuter stockées procédure à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="13c33-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="13c33-114">Déploiement de cube Obtient des informations à partir de l’utilisateur où le QoE Archive se trouve, déploie le cube et configure un travail de l’agent SQL Server régulière qui sera actualiser le cube à intervalle régulier.</span><span class="sxs-lookup"><span data-stu-id="13c33-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="13c33-115">Installation de portail crée une base de données de référentiel qui stocke le mappage d’utilisateurs CQD à rapports/requêtes chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="13c33-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="13c33-116">Il configure ensuite une application web IIS est le tableau de bord dans lequel les utilisateurs peuvent voir un ensemble prédéfini de rapports ainsi que personnaliser et créer leurs propres requêtes pour visualiser les données du cube.</span><span class="sxs-lookup"><span data-stu-id="13c33-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="13c33-117">L’installation du portail crée deux applications web supplémentaires qui expose l’API pour les utilisateurs à accéder par programme le référentiel et le cube.</span><span class="sxs-lookup"><span data-stu-id="13c33-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="13c33-118">(Ces API sont utilisées en interne par le tableau de bord.)</span><span class="sxs-lookup"><span data-stu-id="13c33-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="13c33-119">**Phase**</span><span class="sxs-lookup"><span data-stu-id="13c33-119">**Phase**</span></span>|<span data-ttu-id="13c33-120">**Étapes**</span><span class="sxs-lookup"><span data-stu-id="13c33-120">**Steps**</span></span>|<span data-ttu-id="13c33-121">**Rôles et appartenances aux groupes**</span><span class="sxs-lookup"><span data-stu-id="13c33-121">**Roles and group membership**</span></span>|<span data-ttu-id="13c33-122">**Documentation**</span><span class="sxs-lookup"><span data-stu-id="13c33-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="13c33-123">Installer les logiciels et le matériel requis.</span><span class="sxs-lookup"><span data-stu-id="13c33-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="13c33-124">Déterminer la configuration CQD, puis choisissez un serveur SQL Server à partir de laquelle effectuer l’installation.</span><span class="sxs-lookup"><span data-stu-id="13c33-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="13c33-125">Utilisateur du domaine membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="13c33-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="13c33-126">Section « Conditions requises pour installer préalable » dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="13c33-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="13c33-127">Installez CQD.</span><span class="sxs-lookup"><span data-stu-id="13c33-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="13c33-128">Exécutez le fichier MSI suivant le document de déploiement.</span><span class="sxs-lookup"><span data-stu-id="13c33-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="13c33-129">Pour exécuter le programme d’installation, le compte d’installation doit être un utilisateur de domaine qui est membre du groupe Administrateurs local et ont accès en lecture à la base de données des mesures QoE sur le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="13c33-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="13c33-130">Sections « Comptes et étapes de déploiement » dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="13c33-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="13c33-131">Accorder l’accès des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="13c33-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="13c33-132">Pour gérer l’autorisation utilisateur sur le portail, nous recommandons l’utilisation de l’autorisation d’URL, ce qui a été introduite dans IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="13c33-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="13c33-133">Pour plus d’informations, voir [Understanding IIS 7.0 l’autorisation d’URL](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="13c33-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="13c33-134">Utilisateur du domaine membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="13c33-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="13c33-135">Gestion de l’accès utilisateur pour la section du portail dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="13c33-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="13c33-136">Facultatif : Fournir des informations de mappage de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="13c33-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="13c33-137">Remplir le réseau et les tables de mappage de construction de base de données QoE Archive.</span><span class="sxs-lookup"><span data-stu-id="13c33-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="13c33-138">Un compte avec accès en écriture à la base de données QoE Archive.</span><span class="sxs-lookup"><span data-stu-id="13c33-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="13c33-139">Section « Fournir des informations de sous-réseau » dans la documentation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="13c33-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="13c33-140">Déploiement du tableau de bord qualité des appels implique la configuration de l’infrastructure et de l’installation du logiciel.</span><span class="sxs-lookup"><span data-stu-id="13c33-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="13c33-141">La procédure suivante décrit le processus.</span><span class="sxs-lookup"><span data-stu-id="13c33-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="13c33-142">Étapes du déploiement</span><span class="sxs-lookup"><span data-stu-id="13c33-142">Deployment Steps</span></span>

1. <span data-ttu-id="13c33-143">Copier le CallQualityDashboard.msi sur l’ordinateur où le composant de base de données d’archivage de CQD doit être installé (il s’agit de l’ordinateur sur lequel SQL Server est installé).</span><span class="sxs-lookup"><span data-stu-id="13c33-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="13c33-144">Exécutez le MSI (Windows vous invite à exécuter avec des privilèges d’administrateur, faites-le).</span><span class="sxs-lookup"><span data-stu-id="13c33-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="13c33-145">Acceptez le CLUF.</span><span class="sxs-lookup"><span data-stu-id="13c33-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="13c33-146">Sélectionnez le dossier de destination où les fichiers liés aux composants du tableau de bord qualité d’appel seront est introuvable ou acceptez l’emplacement par défaut.</span><span class="sxs-lookup"><span data-stu-id="13c33-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="13c33-147">Sélectionnez toutes les fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="13c33-147">Select all features.</span></span>
    
6. <span data-ttu-id="13c33-148">Dans la page Configuration de l’Archive QoE, fournissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="13c33-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="13c33-149">**Mesures QoE SQL Server :** Nom de l’instance SQL Server pour où se trouve la base de données des mesures QoE (il s’agit de la source de données).</span><span class="sxs-lookup"><span data-stu-id="13c33-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="13c33-150">**Nom du serveur SQL QoE Archive :** Ce champ en lecture seule et fixe sur le nom de domaine complet de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="13c33-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="13c33-151">Base de données d’archivage peut être installé uniquement sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="13c33-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="13c33-152">**QoE Archive une Instance SQL Server :** Un nom d’instance SQL Server local pour lequel la base de données d’archivage doit être créé.</span><span class="sxs-lookup"><span data-stu-id="13c33-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="13c33-153">Pour utiliser une instance de SQL Server par défaut, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="13c33-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="13c33-154">Pour utiliser une instance nommée de SQL Server, spécifiez le nom d’instance (par exemple, le nom après le «\").</span><span class="sxs-lookup"><span data-stu-id="13c33-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="13c33-155">**Base de données QoE Archive :** Par défaut, cette option est définie sur « Créer nouvelle base de données ».</span><span class="sxs-lookup"><span data-stu-id="13c33-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="13c33-156">Étant donné que la mise à niveau de la base de données Archive n’est pas pris en charge, le seul cas sous lequel l’option « Utiliser la base de données existante » peut être utilisée est si cette base de données existante a le même schéma que la version à installer.</span><span class="sxs-lookup"><span data-stu-id="13c33-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="13c33-157">**Répertoire du fichier de base de données :** Chemin d’accès où les fichiers de base de données (fichiers .mdf et .ldf) pour la base de données d’archivage doivent être placés.</span><span class="sxs-lookup"><span data-stu-id="13c33-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="13c33-158">Il doit s’agir sur un lecteur distinct (HDD2 dans la configuration matérielle recommandée) du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="13c33-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="13c33-159">Notez que les noms de fichier sont corrigés dans l’installation, afin d’éviter tout conflit potentiel, il est recommandé qu’un répertoire vide avec aucun fichier n’est utilisé.</span><span class="sxs-lookup"><span data-stu-id="13c33-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="13c33-160">**Utilisez plusieurs Partitions :** La valeur par défaut est défini sur « Plusieurs partition », ce qui nécessite l’édition Business Intelligence ou Enterprise edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="13c33-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="13c33-161">Pour Standard edition, sélectionnez l’option « Partition unique ».</span><span class="sxs-lookup"><span data-stu-id="13c33-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="13c33-162">Notez que les performances de traitement du cube peuvent être affectés si seule Partition est utilisée.</span><span class="sxs-lookup"><span data-stu-id="13c33-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="13c33-163">La sélection pour l’option d’utilisation de plusieurs Partitions ne peut pas être modifiée une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="13c33-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="13c33-164">Pour modifier, le Cube doit être la première fonctionnalité désinstallé et réinstallé utilisant l’option « Modifier » dans le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="13c33-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="13c33-165">**Répertoire du fichier de partition :** Chemin d’accès où les partitions pour cette base de données QoE doivent être placées.</span><span class="sxs-lookup"><span data-stu-id="13c33-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="13c33-166">Il doit s’agir sur un lecteur distinct (HDD3 dans la configuration matérielle recommandée) du lecteur de système d’exploitation et d’un lecteur de fichiers du journal de base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="13c33-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="13c33-167">Notez que les noms de fichier sont corrigés dans l’installation, afin d’éviter tout conflit potentiel, il est recommandé qu’un répertoire vide avec aucun fichier n’est utilisé.</span><span class="sxs-lookup"><span data-stu-id="13c33-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="13c33-168">**Utilisateur de travail de l’Agent SQL - nom d’utilisateur &amp; le mot de passe :** Nom de compte de service de domaine et le mot de passe (masqué) qui sera utilisé pour exécuter l’étape « Archive les données QoE » de la tâche de l’Agent SQL Server (qui s’exécute la procédure stockée pour extraire les données de base de données de mesures QoE dans base de données Archive, ce compte doit avoir accès en lecture à la base de données QoE mesures,  comme indiqué dans la section comptes.</span><span class="sxs-lookup"><span data-stu-id="13c33-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="13c33-169">Ce compte doit également disposer d’une connexion dans l’Instance de SQL Server Archive QoE).</span><span class="sxs-lookup"><span data-stu-id="13c33-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="13c33-170">L’instance SQL Server s’exécutant sous, telles que NT SERVICE\MSSQLSERVER, le compte doit avoir accès aux répertoires donné ci-dessus pour réussir l’installation.</span><span class="sxs-lookup"><span data-stu-id="13c33-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="13c33-171">Pour plus d’informations, voir [Configurer des autorisations de système de fichiers pour l’accès au moteur de base de données](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="13c33-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="13c33-172">Lorsque vous cliquez sur Suivant, le programme d’installation effectue les vérifications préalables et rapport si des problèmes sont rencontrés.</span><span class="sxs-lookup"><span data-stu-id="13c33-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="13c33-173">Lorsque les vérifications préalables toutes les pass, le programme d’installation est dirigés vers la page Configuration du Cube.</span><span class="sxs-lookup"><span data-stu-id="13c33-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="13c33-174">Si le programme d’installation affiche un avertissement indiquant que le service SQL Server Agent pour l’instance SQL Server de QoE Archive ne fonctionne pas actuellement, procéder à l’installation, mais après l’installation, assurez-vous que l’Agent SQL est en cours d’exécution et le type de démarrage de service Automatique afin que la tâche planifiée s’exécute.</span><span class="sxs-lookup"><span data-stu-id="13c33-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="13c33-175">Dans la page Configuration du Cube, fournissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="13c33-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="13c33-176">**Nom du serveur SQL QoE Archive :** Ce champ en lecture seule et fixe sur le nom de domaine complet de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="13c33-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="13c33-177">Cube peut être installé uniquement à partir de l’ordinateur qui contient la base de données QoE Archive (Note.</span><span class="sxs-lookup"><span data-stu-id="13c33-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="13c33-178">Cube lui-même peut être installé sur un ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="13c33-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="13c33-179">Voir ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="13c33-179">See below)</span></span>
    
   - <span data-ttu-id="13c33-180">**QoE Archive une Instance SQL Server :** Nom d’instance de SQL Server pour où se trouve la base de données Archive QoE.</span><span class="sxs-lookup"><span data-stu-id="13c33-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="13c33-181">Pour spécifier une instance de SQL Server par défaut, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="13c33-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="13c33-182">Pour spécifier une instance nommée de SQL Server, entrez le nom d’instance (par exemple, le nom après le «\").</span><span class="sxs-lookup"><span data-stu-id="13c33-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="13c33-183">Si le composant QoE Archive a été sélectionné pour l’installation, ce champ est prérempli avec la valeur fournie dans la page Configuration de l’Archive QoE.</span><span class="sxs-lookup"><span data-stu-id="13c33-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="13c33-184">**Cube Analysis Server :** Nom de l’instance SQL Server Analysis Services pour lequel le cube doit être créé.</span><span class="sxs-lookup"><span data-stu-id="13c33-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="13c33-185">Il peut s’agir d’un autre ordinateur, mais l’utilisateur de l’installation doit être un membre du groupe Administrateurs de serveur de l’instance de SQL Server Analysis Services cible.</span><span class="sxs-lookup"><span data-stu-id="13c33-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="13c33-186">Pour plus d’informations sur la configuration des autorisations d’administrateur de serveur Analysis Services, voir [Accorder des autorisations administrateur du serveur (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="13c33-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="13c33-187">**Utilisez plusieurs Partitions :** La valeur par défaut est défini sur « Plusieurs partition », ce qui nécessite l’édition Business Intelligence ou Enterprise edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="13c33-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="13c33-188">Pour Standard edition, sélectionnez l’option « Partition unique ».</span><span class="sxs-lookup"><span data-stu-id="13c33-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="13c33-189">Notez que les performances de traitement du cube peuvent être affectés si seule Partition est utilisée.</span><span class="sxs-lookup"><span data-stu-id="13c33-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="13c33-190">La sélection pour l’option d’utilisation de plusieurs Partitions ne peut pas être modifiée une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="13c33-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="13c33-191">Pour modifier, le Cube doit être la première fonctionnalité désinstallé et réinstallé utilisant l’option « Modifier » dans le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="13c33-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="13c33-192">**Utilisateur - nom d’utilisateur de cube &amp; le mot de passe :** Nom de compte de service de domaine et le mot de passe (masqué) qui déclenche le traitement du cube.</span><span class="sxs-lookup"><span data-stu-id="13c33-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="13c33-193">Si le composant QoE Archive a été sélectionné pour l’installation, ce champ est prérempli avec la valeur fournie dans la page Configuration de l’archivage pour l’utilisateur de travail de l’Agent SQL, mais nous vous recommandons de spécifier un compte de service de domaine différent afin que le programme d’installation peut accorder le Privilège requis à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="13c33-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="13c33-194">Lorsque vous cliquez sur Suivant, une autre série de validation est effectuée et tout problème est reportée.</span><span class="sxs-lookup"><span data-stu-id="13c33-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="13c33-195">En cas de réussite de la validation, le programme d’installation est dirigés vers la page Configuration du portail.</span><span class="sxs-lookup"><span data-stu-id="13c33-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="13c33-196">Dans la page Configuration du portail, fournissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="13c33-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="13c33-197">**QoE Archive SQL Server :** Nom d’instance de SQL Server pour où se trouve la base de données QoE Archive.</span><span class="sxs-lookup"><span data-stu-id="13c33-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="13c33-198">Notez que, contrairement à la page Configuration de l’Archive QoE et la page Configuration du Cube, le nom de l’ordinateur n’est pas résolu et doit être fourni.</span><span class="sxs-lookup"><span data-stu-id="13c33-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="13c33-199">Si le composant QoE Archive a été sélectionné pour l’installation, ce champ est prérempli avec la valeur fournie dans la page Configuration de l’Archive QoE.</span><span class="sxs-lookup"><span data-stu-id="13c33-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="13c33-200">**Cube Analysis Server :** Nom de l’instance SQL Server Analysis Services pour où se trouve le cube.</span><span class="sxs-lookup"><span data-stu-id="13c33-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="13c33-201">Si le composant de Cube a été sélectionné pour l’installation, ce champ est prérempli avec la valeur fournie dans la page Configuration du Cube.</span><span class="sxs-lookup"><span data-stu-id="13c33-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="13c33-202">**Référentiel SQL Server :** Nom d’instance SQL Server où la base de données de référentiel doit être créé.</span><span class="sxs-lookup"><span data-stu-id="13c33-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="13c33-203">Si le nom d’instance SQL Server pour où se trouve la base de données QoE Archive a été fourni plus haut dans l’installation (dans d’autres composants), ce champ est prérempli avec le nom d’instance de base de données SQL Server QoE Archive.</span><span class="sxs-lookup"><span data-stu-id="13c33-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="13c33-204">Il peut s’agir d’une instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="13c33-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="13c33-205">**Base de données de référentiel :** Par défaut, l’option est définie sur « Créer nouvelle base de données ».</span><span class="sxs-lookup"><span data-stu-id="13c33-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="13c33-206">Étant donné que la mise à niveau de la base de données de référentiel n’est pas pris en charge, le seul cas sous lequel l’option « Utiliser la base de données existante » peut être utilisée est si la base de données de référentiel existant a le même schéma que la version à installer.</span><span class="sxs-lookup"><span data-stu-id="13c33-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="13c33-207">**Utilisateur du Pool d’applications IIS - nom d’utilisateur &amp; le mot de passe :** Le compte du pool d’applications IIS doit s’exécuter sous.</span><span class="sxs-lookup"><span data-stu-id="13c33-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="13c33-208">Les champs nom d’utilisateur et mot de passe seront grisés si les comptes intégrés sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="13c33-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="13c33-209">Ces champs seulement seront activés si « Other » est sélectionnée dans la liste déroulante afin que l’utilisateur puisse entrer les informations de compte de service de domaine.</span><span class="sxs-lookup"><span data-stu-id="13c33-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="13c33-210">Lorsque vous cliquez sur Suivant, la dernière série de validation sera effectuée pour s’assurer que les instances de SQL Server sont accessibles à l’aide des informations d’identification fournies et que IIS est disponible sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="13c33-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="13c33-211">En cas de réussite de la validation, le programme d’installation poursuit l’installation.</span><span class="sxs-lookup"><span data-stu-id="13c33-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="13c33-212">Lorsque le programme d’installation est terminé, probablement le travail de l’Agent SQL Server sera en cours, en effectuant le chargement initial des données QoE et le traitement du cube.</span><span class="sxs-lookup"><span data-stu-id="13c33-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="13c33-213">Selon la quantité de données dans les données QoE, le portail n’aura données disponibles pour l’affichage encore.</span><span class="sxs-lookup"><span data-stu-id="13c33-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="13c33-214">Pour vérifier l’état de la charge de données et le traitement du cube, accédez à `http://<machinename>/CQD/#/Health`.</span><span class="sxs-lookup"><span data-stu-id="13c33-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="13c33-215">Notez que l’URL de vérification de l’état du téléchargement de traitement de cube respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="13c33-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="13c33-216">Si vous entrez « santé », que l’URL ne fonctionneront pas.</span><span class="sxs-lookup"><span data-stu-id="13c33-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="13c33-217">Vous devez entrer « Santé » à la fin de l’URL en majuscule H.</span><span class="sxs-lookup"><span data-stu-id="13c33-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="13c33-218">Messages du journal détaillé seront affichera si le mode débogage est activé.</span><span class="sxs-lookup"><span data-stu-id="13c33-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="13c33-219">Pour activer le mode de débogage, accédez à **%SYSTEMDRIVE%\Program Files\Skype pour Business 2015 CQD\QoEDataService\web.config**et mettre à jour de la ligne suivante afin que la valeur est définie sur **True**:</span><span class="sxs-lookup"><span data-stu-id="13c33-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="13c33-220">La principale page du portail est accessible via `http://<machinename>/CQD`.</span><span class="sxs-lookup"><span data-stu-id="13c33-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="13c33-221">Gestion de l’accès des utilisateurs pour le portail</span><span class="sxs-lookup"><span data-stu-id="13c33-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="13c33-222">Pour gérer l’autorisation utilisateur sur le portail, nous recommandons l’utilisation de l’autorisation d’URL, ce qui a été introduite dans IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="13c33-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="13c33-223">Pour plus d’informations sur la sécurité IIS, voir [Understanding IIS 7.0 l’autorisation d’URL ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="13c33-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="13c33-224">N’importe quelle application web de site ou héritent de la valeur par défaut de l’autorisation d’URL configuré pour l’ensemble IIS, qui est généralement « Autoriser tous les utilisateurs ».</span><span class="sxs-lookup"><span data-stu-id="13c33-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="13c33-225">Si l’accès au portail doit être plus restrictif, puis administrateurs peuvent accorder un accès pour seulement le groupe d’utilisateurs spécifique en modifiant les « règles d’autorisation ».</span><span class="sxs-lookup"><span data-stu-id="13c33-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Déployer la qualité des appels - règles d’autorisation dans IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="13c33-227">L’icône de règles d’autorisation ne doit ne pas être confondu avec l’autorisation « .NET » dans la section ASP.NET, qui est un mécanisme d’autorisation différentes.</span><span class="sxs-lookup"><span data-stu-id="13c33-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="13c33-228">Les administrateurs doivent d’abord supprimer la règle héritée « autoriser tous les utilisateurs ».</span><span class="sxs-lookup"><span data-stu-id="13c33-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="13c33-229">Cela empêche des utilisateurs non autorisés de l’accès au portail.</span><span class="sxs-lookup"><span data-stu-id="13c33-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Déployer CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="13c33-231">Ensuite, les administrateurs doivent ajouter de nouvelles règles Autoriser et autoriser des utilisateurs spécifiques pour accéder au portail.</span><span class="sxs-lookup"><span data-stu-id="13c33-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="13c33-232">Il est recommandé qu’un groupe local nommé « CQDPortalUsers » être créées pour gérer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="13c33-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Déployer le Tableau de bord de la qualité des appels](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="13c33-234">Les détails de configuration sont stockés dans le fichier web.config situé dans le répertoire physique du portail.</span><span class="sxs-lookup"><span data-stu-id="13c33-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="13c33-235">L’étape suivante consiste à configurer le tableau de bord de la CQD.</span><span class="sxs-lookup"><span data-stu-id="13c33-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="13c33-236">Une fois que les utilisateurs sont authentifiés par IIS, ils doivent disposer d’autorisations sur le répertoire CQD afin d’accéder au contenu de portail web.</span><span class="sxs-lookup"><span data-stu-id="13c33-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="13c33-237">Il est possible de modifier les listes ACL par le biais de l’onglet sécurité des propriétés du répertoire CQD pour ajouter des utilisateurs individuels ou des groupes ; Toutefois, l’approche recommandée consiste à laisser les autorisations de fichiers inchangés.</span><span class="sxs-lookup"><span data-stu-id="13c33-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="13c33-238">Au lieu de cela, modifiez le paramètre IIS à utiliser le processus de travail IIS pour accéder au répertoire CQD quelle que soit l’utilisateur est authentifié.</span><span class="sxs-lookup"><span data-stu-id="13c33-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="13c33-239">Il est important de ne modifier ce paramètre pour l’application CQD et non pour les deux applications API : QoEDataService et QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="13c33-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="13c33-240">Configuration de l’accès de fichier pour le CQD (tableau de bord)</span><span class="sxs-lookup"><span data-stu-id="13c33-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="13c33-241">Ouvrez l’éditeur de Configuration pour CQD.</span><span class="sxs-lookup"><span data-stu-id="13c33-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="13c33-243">Sous la Section, choisissez **system.webServer/serverRuntime**.</span><span class="sxs-lookup"><span data-stu-id="13c33-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="13c33-245">Remplacez authenticatedUserOverride **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="13c33-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels - Éditeur de configuration](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="13c33-247">Cliquez sur **Appliquer** dans la partie droite de la page.</span><span class="sxs-lookup"><span data-stu-id="13c33-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="13c33-248">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="13c33-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="13c33-249">La CQD n’indique qu’aucune donnée après le déploiement</span><span class="sxs-lookup"><span data-stu-id="13c33-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="13c33-250">Vous pouvez recevoir le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="13c33-250">You may receive the following error:</span></span>

<span data-ttu-id="13c33-251">*Nous n’exécuter la requête pendant son exécution sur le Cube. Utilisez l’éditeur de requête pour modifier la requête et résoudre les problèmes. Assurez-vous également que le Cube est accessible.*</span><span class="sxs-lookup"><span data-stu-id="13c33-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="13c33-252">Cela signifie que le cube doit être traité dans SQL Server Analysis Services avant utilisées dans CQD.</span><span class="sxs-lookup"><span data-stu-id="13c33-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="13c33-253">Vous pouvez résoudre ce problème en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="13c33-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="13c33-254">Ouvrez SQL Management Studio et sélectionnez **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="13c33-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="13c33-255">Développez le droit objet, sélectionnez **Mesure QoE**, **QoECube** , puis cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="13c33-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="13c33-256">Si ce script renvoie navigateur vide, le cube n’a pas été passez encore.</span><span class="sxs-lookup"><span data-stu-id="13c33-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="13c33-257">Avec le bouton droit angain **Mesure QoE** et cliquez sur **traiter**.</span><span class="sxs-lookup"><span data-stu-id="13c33-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="13c33-258">Lorsque le traitement est terminé, cliquez à nouveau sur l’objet et cliquez sur **Parcourir** pour confirmer que la page du navigateur affiche maintenant les données.</span><span class="sxs-lookup"><span data-stu-id="13c33-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="13c33-259">Les utilisateurs ont des problèmes de connexion, car le programme d’installation ne parvient pas à créer les paramètres appropriés dans IIS</span><span class="sxs-lookup"><span data-stu-id="13c33-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="13c33-260">Dans les cas rares, le programme d’installation ne peut pas créer les paramètres appropriés dans IIS.</span><span class="sxs-lookup"><span data-stu-id="13c33-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="13c33-261">Modification manuelle est nécessaire pour permettre aux utilisateurs de se connecter à la CQD.</span><span class="sxs-lookup"><span data-stu-id="13c33-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="13c33-262">Si les utilisateurs rencontrent des problèmes de connexion, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="13c33-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="13c33-263">Ouvrir le Gestionnaire des services Internet haut, puis accédez au Site Web par défaut.</span><span class="sxs-lookup"><span data-stu-id="13c33-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="13c33-265">Cliquez sur « Authentification ».</span><span class="sxs-lookup"><span data-stu-id="13c33-265">Click on "Authentication".</span></span> <span data-ttu-id="13c33-266">Si les « Authentification anonyme », « Emprunt d’identité ASP.NET », « Authentification par formulaire » et « Authentification Windows » ne correspondent pas les paramètres indiqués ci-dessous, manuellement les modifier pour faire correspondre les paramètres ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="13c33-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="13c33-267">Tous les autres mécanismes d’authentification doivent être désactivés.</span><span class="sxs-lookup"><span data-stu-id="13c33-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="13c33-269">Pour « Authentification Windows », cliquez sur Paramètres avancés sur le côté droit.</span><span class="sxs-lookup"><span data-stu-id="13c33-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="13c33-271">Accepter la valeur « Protection étendue » et la case à cocher « authentification en mode noyau activer ».</span><span class="sxs-lookup"><span data-stu-id="13c33-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="13c33-273">Répétez les étapes ci-dessus pour chacune des entrées « CQD », « QoEDataService » et « QoERepositoryService » sous « Site Web par défaut ».</span><span class="sxs-lookup"><span data-stu-id="13c33-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="13c33-274">Pour les liaisons de port HTTP et HTTPS le programme d’installation crée les liaisons de port sur les numéros de port par défaut (port 80 pour HTTP) et le port 443 pour le protocole HTTPS.</span><span class="sxs-lookup"><span data-stu-id="13c33-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="13c33-275">S’il existe un autre site Web sur l’ordinateur qui utilise ces liaisons, il y aura un conflit et le comportement IIS ne peut pas être prévu.</span><span class="sxs-lookup"><span data-stu-id="13c33-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="13c33-276">La meilleure façon pour éviter ce problème est pour vous assurer qu’aucuns les autres sites Web n’est mappées sur les ports 80 et 443 avant d’installer CQD.</span><span class="sxs-lookup"><span data-stu-id="13c33-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="13c33-277">Pour activer SSL/TLS dans IIS et forcer les utilisateurs à se connecter via le protocole HTTPS au lieu de HTTP secure :</span><span class="sxs-lookup"><span data-stu-id="13c33-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="13c33-278">Configurer le protocole SSL (Secure Sockets Layer) dans IIS, voir [Configuration de SSL dans IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="13c33-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="13c33-279">Une fois que vous avez terminé, remplacez `http` avec `https`.</span><span class="sxs-lookup"><span data-stu-id="13c33-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="13c33-280">Pour obtenir des instructions sur l’activation de TLS dans les connexions SQL Server, voir [comment activer le chiffrement SSL pour une instance de SQL Server à l’aide de Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="13c33-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="13c33-281">Échec de synchronisation de cube</span><span class="sxs-lookup"><span data-stu-id="13c33-281">Cube Sync Fails</span></span>

<span data-ttu-id="13c33-282">QoEMetrics peut contenir des enregistrements non valides en fonction de l’utilisateur final horloges.</span><span class="sxs-lookup"><span data-stu-id="13c33-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="13c33-283">Si le délai maximal autorisé est supérieure à 60 ans, l’importation de cube échoue.</span><span class="sxs-lookup"><span data-stu-id="13c33-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="13c33-284">Vérifiez les Min et Max début/fin à l’aide des sélections ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="13c33-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="13c33-285">Rechercher et supprimer des enregistrements dans le futur dépassée et très éloigné, ils peuvent ne pas être et qu’ils seront décomposer les processus de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="13c33-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="13c33-286">Sélectionnez MIN(StartTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="13c33-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="13c33-287">Sélectionnez MAX(StartTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="13c33-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="13c33-288">Sélectionnez MIN(EndTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="13c33-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="13c33-289">Sélectionnez MAX(EndTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="13c33-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="13c33-290">Tâches de post-installation</span><span class="sxs-lookup"><span data-stu-id="13c33-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="13c33-291">Importation de bâtiments et les réseaux</span><span class="sxs-lookup"><span data-stu-id="13c33-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="13c33-292">Après l’installation de CQD, effectuez les tâches de configuration suivantes :</span><span class="sxs-lookup"><span data-stu-id="13c33-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="13c33-293">Définir des types de construction (recommandés)</span><span class="sxs-lookup"><span data-stu-id="13c33-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="13c33-294">Définir les types de propriété construction (recommandés)</span><span class="sxs-lookup"><span data-stu-id="13c33-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="13c33-295">Définir les types de réseau (recommandés)</span><span class="sxs-lookup"><span data-stu-id="13c33-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="13c33-296">Importation de bâtiments (recommandé)</span><span class="sxs-lookup"><span data-stu-id="13c33-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="13c33-297">Importation des sous-réseaux (recommandés)</span><span class="sxs-lookup"><span data-stu-id="13c33-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="13c33-298">Définir des Types de construction</span><span class="sxs-lookup"><span data-stu-id="13c33-298">Define Building Types</span></span>

<span data-ttu-id="13c33-299">Types de construction sont utilisés pour décrire les définitions de bâtiments différents types au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="13c33-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="13c33-300">Cette étape est facultative mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="13c33-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="13c33-301">Exemples</span><span class="sxs-lookup"><span data-stu-id="13c33-301">Examples</span></span>
  
- <span data-ttu-id="13c33-302">Siège social</span><span class="sxs-lookup"><span data-stu-id="13c33-302">Headquarters</span></span>
    
- <span data-ttu-id="13c33-303">Bureau à distance</span><span class="sxs-lookup"><span data-stu-id="13c33-303">Remote Office</span></span>
    
- <span data-ttu-id="13c33-304">Emplacement de l’entreprise commune</span><span class="sxs-lookup"><span data-stu-id="13c33-304">Joint-venture location</span></span>
    
  <span data-ttu-id="13c33-305">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="13c33-305">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="13c33-306">Les paramètres BuildingTypeId et BuildingTypeDesc sont requis.</span><span class="sxs-lookup"><span data-stu-id="13c33-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="13c33-307">Définir les Types de propriété de construction</span><span class="sxs-lookup"><span data-stu-id="13c33-307">Define Building Ownership Types</span></span>

<span data-ttu-id="13c33-308">Types de propriété sont utilisés pour distinguer les biens spécialisées vs détenus.</span><span class="sxs-lookup"><span data-stu-id="13c33-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="13c33-309">Cette étape est facultative mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="13c33-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="13c33-310">Exemples</span><span class="sxs-lookup"><span data-stu-id="13c33-310">Examples</span></span>
  
- <span data-ttu-id="13c33-311">Contoso allouée non-RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="13c33-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="13c33-312">Connexion en bail Contoso RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="13c33-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="13c33-313">Propriété de Contoso</span><span class="sxs-lookup"><span data-stu-id="13c33-313">Contoso Owned</span></span>
    
- <span data-ttu-id="13c33-314">Filiale spécialisée</span><span class="sxs-lookup"><span data-stu-id="13c33-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="13c33-315">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="13c33-315">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="13c33-316">Les paramètres OwnershipTypeId et OwnershipTypeDesc sont requis.</span><span class="sxs-lookup"><span data-stu-id="13c33-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="13c33-317">Définir les noms de réseau</span><span class="sxs-lookup"><span data-stu-id="13c33-317">Define Network Names</span></span>

<span data-ttu-id="13c33-318">Types de réseau sont utilisés pour décrire différents types de réseaux au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="13c33-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="13c33-319">Cela vous donne la possibilité de filtrer (ou filtrer) les Types de réseau spécifiques.</span><span class="sxs-lookup"><span data-stu-id="13c33-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="13c33-320">Il est vivement recommandé de définir les noms de réseau, mais il est facultatif.</span><span class="sxs-lookup"><span data-stu-id="13c33-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="13c33-321">Si vous décidez de ne définit ne pas les noms de réseau, vérifiez que le chaque entrée CqdNetwork a un BuildingId de 0.</span><span class="sxs-lookup"><span data-stu-id="13c33-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="13c33-322">Exemples</span><span class="sxs-lookup"><span data-stu-id="13c33-322">Examples</span></span>
  
- <span data-ttu-id="13c33-323">VPN</span><span class="sxs-lookup"><span data-stu-id="13c33-323">VPN</span></span>
    
- <span data-ttu-id="13c33-324">ATELIER</span><span class="sxs-lookup"><span data-stu-id="13c33-324">LAB</span></span>
    
  <span data-ttu-id="13c33-325">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="13c33-325">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="13c33-326">Les paramètres NetworkNameID et NetworkName sont nécessaires, le paramètre NetworkType est facultatif mais recommandé.</span><span class="sxs-lookup"><span data-stu-id="13c33-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="13c33-327">Importation de bâtiments</span><span class="sxs-lookup"><span data-stu-id="13c33-327">Import Buildings</span></span>

<span data-ttu-id="13c33-328">Importation de bâtiments vous donne la possibilité d’obtenir création insights spécifiques (appels médiocres par création/câblé Wi-Fi, etc.)..</span><span class="sxs-lookup"><span data-stu-id="13c33-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="13c33-329">Cette étape est facultative mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="13c33-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="13c33-330">Avant d’importer une nouvelle génération vous disposez déjà d’un BuildingKey prédéfini identifié.</span><span class="sxs-lookup"><span data-stu-id="13c33-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="13c33-331">Pour cela, exécutez la commande SQL « Sélectionnez MAX(BuildingKey) de CqdBuilding » pour identifier la valeur actuelle et ajouter des 1 sur le résultat.</span><span class="sxs-lookup"><span data-stu-id="13c33-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="13c33-332">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="13c33-332">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="13c33-333">Le BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId paramètres sont obligatoires, les autres paramètres sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="13c33-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="13c33-334">Importer des sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="13c33-334">Import Subnets</span></span>

<span data-ttu-id="13c33-335">Importation de bâtiments vous donne la possibilité d’obtenir création insights spécifiques (appels médiocres par création/câblé Wi-Fi, etc.)..</span><span class="sxs-lookup"><span data-stu-id="13c33-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="13c33-336">Cette étape est facultative mais recommandée.</span><span class="sxs-lookup"><span data-stu-id="13c33-336">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="13c33-337">Importer des sous-réseaux et les mapper aux bâtiments importés à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="13c33-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="13c33-338">Si vous décidez de ne pas remplir NetworkName, veillez à que chaque entrée de ce tableau utilise un NetworkNameID de 0.</span><span class="sxs-lookup"><span data-stu-id="13c33-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="13c33-339">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="13c33-339">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="13c33-340">Le réseau et les paramètres UpdatedDate sont obligatoires, les autres paramètres sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="13c33-340">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="13c33-341">Facultatif : BSSID</span><span class="sxs-lookup"><span data-stu-id="13c33-341">Optional: BSSID</span></span>

<span data-ttu-id="13c33-342">Informations BSSID vous permet de corrélation de flux Wi-Fi supplémentaire par contrôleur ou radio.</span><span class="sxs-lookup"><span data-stu-id="13c33-342">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="13c33-343">Il s’agit en plus de filtrage de création ou le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="13c33-343">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="13c33-344">**Exemple de syntaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="13c33-344">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="13c33-345">**Détails CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="13c33-345">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="13c33-346">**Comme indiqué dans CQD**</span><span class="sxs-lookup"><span data-stu-id="13c33-346">**As shown in CQD**</span></span>|<span data-ttu-id="13c33-347">**Tableau CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="13c33-347">**CQDBssid Table**</span></span>|<span data-ttu-id="13c33-348">**Entrées de l’exemple**</span><span class="sxs-lookup"><span data-stu-id="13c33-348">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="13c33-349">Name AP</span><span class="sxs-lookup"><span data-stu-id="13c33-349">Ap NName</span></span>  <br/> |<span data-ttu-id="13c33-350">POINT D’ACCÈS</span><span class="sxs-lookup"><span data-stu-id="13c33-350">AP</span></span>  <br/> |<span data-ttu-id="13c33-351">POINT D’ACCÈS 1</span><span class="sxs-lookup"><span data-stu-id="13c33-351">AP1</span></span>  <br/> |
|<span data-ttu-id="13c33-352">BBssid</span><span class="sxs-lookup"><span data-stu-id="13c33-352">BBssid</span></span>  <br/> |<span data-ttu-id="13c33-353">BSS</span><span class="sxs-lookup"><span data-stu-id="13c33-353">BSS</span></span>  <br/> |<span data-ttu-id="13c33-354">00-00-00-00-00-00 (vous devez utiliser le format délimité)</span><span class="sxs-lookup"><span data-stu-id="13c33-354">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="13c33-355">Contrôleur</span><span class="sxs-lookup"><span data-stu-id="13c33-355">Controller</span></span>  <br/> |<span data-ttu-id="13c33-356">Bâtiment</span><span class="sxs-lookup"><span data-stu-id="13c33-356">Building</span></span>  <br/> |<span data-ttu-id="13c33-357">Aruba AP 7</span><span class="sxs-lookup"><span data-stu-id="13c33-357">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="13c33-358">APPAREIL</span><span class="sxs-lookup"><span data-stu-id="13c33-358">Device</span></span>  <br/> |<span data-ttu-id="13c33-359">ess</span><span class="sxs-lookup"><span data-stu-id="13c33-359">ess</span></span>  <br/> |<span data-ttu-id="13c33-360">: Contrôleur1</span><span class="sxs-lookup"><span data-stu-id="13c33-360">Controller1</span></span>  <br/> |
|<span data-ttu-id="13c33-361">Case d’option</span><span class="sxs-lookup"><span data-stu-id="13c33-361">Radio</span></span>  <br/> |<span data-ttu-id="13c33-362">phy</span><span class="sxs-lookup"><span data-stu-id="13c33-362">phy</span></span>  <br/> |<span data-ttu-id="13c33-363">BGN</span><span class="sxs-lookup"><span data-stu-id="13c33-363">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="13c33-364">Traitement des données importées</span><span class="sxs-lookup"><span data-stu-id="13c33-364">Processing the imported data</span></span>

<span data-ttu-id="13c33-365">Par défaut, une fois que vous importez des données de création/réseau il s’applique uniquement aux enregistrements générés une fois que le point dans le temps.</span><span class="sxs-lookup"><span data-stu-id="13c33-365">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="13c33-366">Pour ajouter une balise à tous les enregistrements précédents avec ces nouvelles données, vous devrez exécuter la procédure stockée de CqdUpdateBuilding comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="13c33-366">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="13c33-367">Lui donner la date de votre premier enregistrement (identifier à l’aide de la commande SQL sélectionnez de MIN(StartTime) de CqdPartitionedStreamView), une date de fin de demain, puis NULL pour les deux dernières valeurs.</span><span class="sxs-lookup"><span data-stu-id="13c33-367">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="13c33-368">Une fois les données sont associées à des données de flux de données, le Cube SSIS doit traiter à nouveau tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="13c33-368">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="13c33-369">Cela s’applique également lorsque en bloc de l’ajout de données BSSID/fournisseur de services Internet.</span><span class="sxs-lookup"><span data-stu-id="13c33-369">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="13c33-370">Vérifiez que « Processus Full » est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13c33-370">Ensure that "Process Full" is selected.</span></span>
  

