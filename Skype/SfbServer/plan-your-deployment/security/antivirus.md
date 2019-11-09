---
title: Exclusions de l’analyse antivirus pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Vue d’ensemble de l’interopérabilité avec le scanner antivirus avec Skype entreprise Server.
ms.openlocfilehash: 69fb02d04f27b7444a3b8cadaacafc05654a1c9f
ms.sourcegitcommit: 1aa98e3865d5a0f7be5e1cba497dea4ac7b9c607
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074626"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="addac-103">Exclusions de l’analyse antivirus pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="addac-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="addac-104">Vue d’ensemble de l’interopérabilité avec le scanner antivirus avec Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="addac-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="addac-105">Pour vous assurer que le scanner antivirus n’interagit pas avec le fonctionnement de Skype entreprise Server, vous devez exclure des processus spécifiques et des annuaires pour chaque rôle serveur ou serveur Skype entreprise Server sur lequel vous exécutez un scanneur antivirus.</span><span class="sxs-lookup"><span data-stu-id="addac-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="addac-106">Vous devez exclure les processus et les répertoires suivants :</span><span class="sxs-lookup"><span data-stu-id="addac-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="addac-107">Dossiers et emplacements de fichiers indiqués ci-dessous sont les emplacements par défaut de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="addac-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="addac-108">Pour les emplacements pour lesquels vous n’avez pas utilisé la valeur par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut spécifiés dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="addac-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="addac-109">Notez que certains programmes antivirus peuvent avoir besoin de chemins d’accès absolus, non relatifs, pour leur liste d’exclusions.</span><span class="sxs-lookup"><span data-stu-id="addac-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="addac-110">Processus du serveur Skype entreprise :</span><span class="sxs-lookup"><span data-stu-id="addac-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="addac-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="addac-111">ABServer.exe</span></span>

  - <span data-ttu-id="addac-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="addac-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="addac-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="addac-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="addac-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="addac-114">ChannelService.exe</span></span>

  - <span data-ttu-id="addac-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="addac-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="addac-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="addac-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="addac-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="addac-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="addac-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="addac-118">DataProxy.exe</span></span>

  - <span data-ttu-id="addac-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="addac-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="addac-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="addac-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="addac-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="addac-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="addac-122">LyncBackupService. exe</span><span class="sxs-lookup"><span data-stu-id="addac-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="addac-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="addac-123">LysSvc.exe</span></span>

  - <span data-ttu-id="addac-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="addac-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="addac-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="addac-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="addac-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="addac-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="addac-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="addac-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="addac-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="addac-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="addac-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="addac-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="addac-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="addac-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="addac-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="addac-131">RtcHost.exe</span></span>

  - <span data-ttu-id="addac-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="addac-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="addac-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="addac-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="addac-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="addac-134">XmppTGW.exe</span></span>

- <span data-ttu-id="addac-135">Processus du service d’hôte Windows Fabric :</span><span class="sxs-lookup"><span data-stu-id="addac-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="addac-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="addac-136">Fabric.exe</span></span>

  - <span data-ttu-id="addac-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="addac-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="addac-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="addac-138">FabricHost.exe</span></span>

- <span data-ttu-id="addac-139">Processus d’IIS :</span><span class="sxs-lookup"><span data-stu-id="addac-139">IIS processes:</span></span>

  - <span data-ttu-id="addac-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="addac-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="addac-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="addac-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="addac-142">Processus du serveur dorsal SQL Server :</span><span class="sxs-lookup"><span data-stu-id="addac-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="addac-143">Notez que ces chemins d’accès sont spécifiques à la version de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="addac-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="addac-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="addac-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="addac-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="addac-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="addac-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="addac-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="addac-147">Processus du serveur SQL Server frontal :</span><span class="sxs-lookup"><span data-stu-id="addac-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="addac-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="addac-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="addac-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="addac-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="addac-150">Instance RTC de l’installation de Standard Edition</span><span class="sxs-lookup"><span data-stu-id="addac-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="addac-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="addac-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="addac-152">Répertoires et fichiers :</span><span class="sxs-lookup"><span data-stu-id="addac-152">Directories and files:</span></span>

  - <span data-ttu-id="addac-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="addac-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="addac-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="addac-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="addac-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="addac-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="addac-156">Notez que ces chemins sont spécifiques à la version de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="addac-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="addac-157">%programfiles%\Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="addac-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="addac-158">%programfiles%\Common Files\Skype Entreprise Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="addac-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="addac-159">%programfiles%\Common Files\Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="addac-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="addac-160">%programfiles%\Common Files\Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="addac-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="addac-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="addac-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="addac-p103">Magasin de partage de fichiers (spécifié dans le générateur de topologies). Les magasins de fichiers sont spécifiés dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="addac-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="addac-p104">Fichiers journaux et de données SQL Server, dont ceux pour la base de données principale, le magasin d’utilisateurs, le magasin d’archivage, le magasin de surveillance et le magasin d’applications. Les fichiers journaux et de base de données peuvent être spécifiés dans le générateur de topologies. Pour plus d’informations sur les fichiers journaux et de données pour chaque base de données, dont les noms par défaut, reportez-vous à la rubrique [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation relative au déploiement.</span><span class="sxs-lookup"><span data-stu-id="addac-p104">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="addac-167">Les fichiers de données et les fichiers journaux de SQL Server, y compris ceux de la base de données frontale, Skype entreprise Store et RtcDatabase Store.</span><span class="sxs-lookup"><span data-stu-id="addac-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="addac-168">Ils se trouvent normalement sous %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="addac-168">They are normally under %localdrive%\CSData.</span></span>


