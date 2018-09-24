---
title: Antivirus exclusions d’analyse pour Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Vue d’ensemble de l’interopérabilité de scanneur antivirus avec Skype pour Business Server.
ms.openlocfilehash: 782f7bc6fe004eb5106fa07c93b6f22993849d98
ms.sourcegitcommit: c864a4b5337960deed01ff8c481326dbbd23c960
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2018
ms.locfileid: "24975193"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="410ad-103">Antivirus exclusions d’analyse pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="410ad-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="410ad-104">Vue d’ensemble de l’interopérabilité de scanneur antivirus avec Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="410ad-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="410ad-105">Cet article contient des recommandations qui peuvent aider à un administrateur de déterminer la cause de l’instabilité potentielle sur un ordinateur qui exécute une version prise en charge de Microsoft Windows lorsqu’il est utilisé avec un logiciel antivirus dans un domaine Active Directory environnement ou dans un environnement professionnel géré.</span><span class="sxs-lookup"><span data-stu-id="410ad-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="410ad-106">Nous vous recommandons d’appliquer temporairement ces procédures pour évaluer un système.</span><span class="sxs-lookup"><span data-stu-id="410ad-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="410ad-107">Si vos performances du système ou la stabilité est améliorée par les recommandations effectuées dans cet article, contactez votre fournisseur d’antivirus pour obtenir des instructions ou une version mise à jour du logiciel antiviru.</span><span class="sxs-lookup"><span data-stu-id="410ad-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="410ad-108">Cet article contient des informations indiquant comment les paramètres de sécurité inférieur ou désactiver temporairement les fonctionnalités de sécurité sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="410ad-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="410ad-109">Vous pouvez apporter ces modifications pour comprendre la nature d’un problème spécifique.</span><span class="sxs-lookup"><span data-stu-id="410ad-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="410ad-110">Avant d’apporter ces modifications, nous vous recommandons d’évaluer les risques qui sont associés à l’implémentation de cette solution de contournement dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="410ad-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="410ad-111">Si vous implémentez cette solution de contournement, prendre toutes les mesures appropriées pour protéger les fichiers qui ne sont plus en cours d’analyse par un logiciel antivirus sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="410ad-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="410ad-112">Pour vous assurer que le scanneur antivirus n’interfère pas avec l’opération de Skype pour Business Server, vous devez exclure des répertoires et les processus spécifiques pour chaque Skype pour serveur Business Server ou rôle de serveur sur lequel vous exécutez un logiciel antivirus.</span><span class="sxs-lookup"><span data-stu-id="410ad-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="410ad-113">Vous devez exclure les processus et les répertoires suivants :</span><span class="sxs-lookup"><span data-stu-id="410ad-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="410ad-114">Les emplacements de fichiers et de dossier répertoriées ci-dessous sont les emplacements par défaut pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="410ad-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="410ad-115">Pour les emplacements pour lesquels vous n’avez pas utilisé la valeur par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut spécifiés dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="410ad-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="410ad-116">Notez que certains programmes antivirus peuvent avoir besoin de chemins d’accès absolus, non relatifs, pour leur liste d’exclusions.</span><span class="sxs-lookup"><span data-stu-id="410ad-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="410ad-117">Skype pour les processus Business Server :</span><span class="sxs-lookup"><span data-stu-id="410ad-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="410ad-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-118">ABServer.exe</span></span>

  - <span data-ttu-id="410ad-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="410ad-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="410ad-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-121">ChannelService.exe</span></span>

  - <span data-ttu-id="410ad-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="410ad-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="410ad-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="410ad-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-125">DataProxy.exe</span></span>

  - <span data-ttu-id="410ad-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="410ad-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="410ad-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="410ad-129">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="410ad-130">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-130">LysSvc.exe</span></span>

  - <span data-ttu-id="410ad-131">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="410ad-132">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="410ad-133">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="410ad-134">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="410ad-135">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="410ad-136">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="410ad-137">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="410ad-138">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-138">RtcHost.exe</span></span>

  - <span data-ttu-id="410ad-139">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="410ad-140">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="410ad-141">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-141">XmppTGW.exe</span></span>

- <span data-ttu-id="410ad-142">Processus du service d’hôte Windows Fabric :</span><span class="sxs-lookup"><span data-stu-id="410ad-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="410ad-143">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-143">Fabric.exe</span></span>

  - <span data-ttu-id="410ad-144">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="410ad-145">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-145">FabricHost.exe</span></span>

- <span data-ttu-id="410ad-146">Processus d’IIS :</span><span class="sxs-lookup"><span data-stu-id="410ad-146">IIS processes:</span></span>

  - <span data-ttu-id="410ad-147">%SystemRoot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="410ad-148">%SystemRoot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="410ad-149">Processus du serveur dorsal SQL Server :</span><span class="sxs-lookup"><span data-stu-id="410ad-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="410ad-150">Notez que ces chemins d’accès sont spécifiques à la version de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="410ad-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="410ad-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="410ad-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="410ad-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="410ad-154">Processus du serveur SQL Server frontal :</span><span class="sxs-lookup"><span data-stu-id="410ad-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="410ad-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="410ad-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="410ad-157">Instance RTC de l’installation de Standard Edition</span><span class="sxs-lookup"><span data-stu-id="410ad-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="410ad-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="410ad-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="410ad-159">Répertoires et fichiers :</span><span class="sxs-lookup"><span data-stu-id="410ad-159">Directories and files:</span></span>

  - <span data-ttu-id="410ad-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="410ad-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="410ad-161">%SystemRoot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="410ad-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="410ad-162">%SystemRoot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="410ad-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="410ad-163">Notez que ces chemins d’accès sont spécifiques à Skype pour la version du serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="410ad-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="410ad-164">%programfiles%\Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="410ad-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="410ad-165">%programfiles%\Common Files\Skype Entreprise Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="410ad-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="410ad-166">%programfiles%\Common Files\Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="410ad-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="410ad-167">%programfiles%\Common Files\Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="410ad-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="410ad-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="410ad-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="410ad-p105">Magasin de partage de fichiers (spécifié dans le générateur de topologies). Les magasins de fichiers sont spécifiés dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="410ad-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="410ad-171">Fichiers journaux et de données SQL Server, dont ceux pour la base de données principale, le magasin d’utilisateurs, le magasin d’archivage, le magasin de surveillance et le magasin d’applications.</span><span class="sxs-lookup"><span data-stu-id="410ad-171">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="410ad-172">Les fichiers journaux et de base de données peuvent être spécifiés dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="410ad-172">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="410ad-173">Pour plus d’informations sur les fichiers journaux et de données pour chaque base de données, y compris les noms par défaut, reportez-vous à la section [emplacement des fichiers journaux et données SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="410ad-173">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="410ad-174">SQL Server données et fichiers journaux, y compris ceux de la base de données frontal Skype pour le magasin Business et magasin RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="410ad-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="410ad-175">Ils se trouvent normalement sous %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="410ad-175">They are normally under %localdrive%\CSData.</span></span>


