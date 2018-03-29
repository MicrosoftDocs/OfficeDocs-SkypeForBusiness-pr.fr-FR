---
title: Exclusions de l’analyse antivirus pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Vue d’ensemble de l’interopérabilité de moteur d’analyse antivirus avec Skype pour Business Server 2015.
ms.openlocfilehash: bb188b25c61269ee7c38829e1887a3443a0f77c4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a><span data-ttu-id="95aa2-103">Exclusions de l’analyse antivirus pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="95aa2-103">Antivirus scanning exclusions for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="95aa2-104">Vue d’ensemble de l’interopérabilité de moteur d’analyse antivirus avec Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="95aa2-104">Overview of antivirus scanner interoperation with Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="95aa2-105">Pour vous assurer que le moteur d’analyse antiviru n’interfère pas avec l’opération de Skype pour Business Server 2015, vous devez exclure les processus spécifiques et des répertoires pour chaque Skype pour Business Server 2015 serveur ou du rôle de serveur sur lequel vous exécutez un logiciel antivirus.</span><span class="sxs-lookup"><span data-stu-id="95aa2-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server 2015, you must exclude specific processes and directories for each Skype for Business Server 2015 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="95aa2-106">Vous devez exclure les processus et les répertoires suivants :</span><span class="sxs-lookup"><span data-stu-id="95aa2-106">The following processes and directories should be excluded:</span></span>
  
> [!NOTE]
> <span data-ttu-id="95aa2-107">Les emplacements de dossiers et de fichiers répertoriés ci-dessous sont les emplacements par défaut pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="95aa2-107">Folder and file locations listed below are the default locations for Skype for Business Server 2015.</span></span> <span data-ttu-id="95aa2-108">Pour les emplacements pour lesquels vous n’avez pas utilisé la valeur par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut spécifiés dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="95aa2-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="95aa2-109">Notez que certains programmes antivirus peuvent avoir besoin de chemins d’accès absolus, non relatifs, pour leur liste d’exclusions.</span><span class="sxs-lookup"><span data-stu-id="95aa2-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span> 
  
- <span data-ttu-id="95aa2-110">Skype pour les processus d’entreprise serveur 2015 :</span><span class="sxs-lookup"><span data-stu-id="95aa2-110">Skype for Business Server 2015 processes:</span></span>
    
  - <span data-ttu-id="95aa2-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-111">ABServer.exe</span></span>
    
  - <span data-ttu-id="95aa2-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-112">ASMCUSvc.exe</span></span>
    
  - <span data-ttu-id="95aa2-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-113">AVMCUSvc.exe</span></span>
    
  - <span data-ttu-id="95aa2-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-114">ChannelService.exe</span></span>
    
  - <span data-ttu-id="95aa2-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-115">ClsAgent.exe</span></span>
    
  - <span data-ttu-id="95aa2-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-116">ComplianceService.exe</span></span>
    
  - <span data-ttu-id="95aa2-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-117">DataMCUSvc.exe</span></span>
    
  - <span data-ttu-id="95aa2-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-118">DataProxy.exe</span></span>
    
  - <span data-ttu-id="95aa2-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-119">FileTransferAgent.exe</span></span>
    
  - <span data-ttu-id="95aa2-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-120">HealthAgent.exe</span></span>
    
  - <span data-ttu-id="95aa2-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-121">IMMCUSvc.exe</span></span>
    
  - <span data-ttu-id="95aa2-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-122">LysSvc.exe</span></span>
    
  - <span data-ttu-id="95aa2-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-123">MasterReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="95aa2-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-124">MediaRelaySvc.exe</span></span>
    
  - <span data-ttu-id="95aa2-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-125">MediationServerSvc.exe</span></span>
    
  - <span data-ttu-id="95aa2-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-126">MRASSvc.exe</span></span>
    
  - <span data-ttu-id="95aa2-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-127">OcsAppServerHost.exe</span></span>
    
  - <span data-ttu-id="95aa2-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-128">ReplicaReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="95aa2-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-129">ReplicationApp.exe</span></span>
    
  - <span data-ttu-id="95aa2-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-130">RtcHost.exe</span></span>
    
  - <span data-ttu-id="95aa2-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-131">RTCSrv.exe</span></span>
    
  - <span data-ttu-id="95aa2-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-132">XmppProxy.exe</span></span>
    
  - <span data-ttu-id="95aa2-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-133">XmppTGW.exe</span></span>
    
- <span data-ttu-id="95aa2-134">Processus du service d’hôte Windows Fabric :</span><span class="sxs-lookup"><span data-stu-id="95aa2-134">Windows Fabric Host Service processes:</span></span>
    
  - <span data-ttu-id="95aa2-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-135">Fabric.exe</span></span>
    
  - <span data-ttu-id="95aa2-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-136">FabricDCA.exe</span></span>
    
  - <span data-ttu-id="95aa2-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-137">FabricHost.exe</span></span>
    
- <span data-ttu-id="95aa2-138">Processus d’IIS :</span><span class="sxs-lookup"><span data-stu-id="95aa2-138">IIS processes:</span></span>
    
  - <span data-ttu-id="95aa2-139">%SystemRoot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-139">%systemroot%\system32\inetsrv\w3wp.exe</span></span>
    
  - <span data-ttu-id="95aa2-140">%SystemRoot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>
    
- <span data-ttu-id="95aa2-141">Processus du serveur dorsal SQL Server :</span><span class="sxs-lookup"><span data-stu-id="95aa2-141">SQL Server Back-End processes:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="95aa2-142">Notez que ces chemins d’accès sont spécifiques à la version de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95aa2-142">Note that these paths are specific to SQL Server version.</span></span> 
  
  - <span data-ttu-id="95aa2-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="95aa2-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>
    
  - <span data-ttu-id="95aa2-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>
    
- <span data-ttu-id="95aa2-146">Processus du serveur SQL Server frontal :</span><span class="sxs-lookup"><span data-stu-id="95aa2-146">SQL Server Front-End processes:</span></span>
    
  - <span data-ttu-id="95aa2-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="95aa2-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="95aa2-149">Instance RTC de l’installation de Standard Edition</span><span class="sxs-lookup"><span data-stu-id="95aa2-149">Standard Edition Installation RTC Instance</span></span> 
    
  - <span data-ttu-id="95aa2-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="95aa2-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>
    
- <span data-ttu-id="95aa2-151">Répertoires et fichiers :</span><span class="sxs-lookup"><span data-stu-id="95aa2-151">Directories and files:</span></span>
    
  - <span data-ttu-id="95aa2-152">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="95aa2-152">%systemroot%\System32\LogFiles</span></span>
    
  - <span data-ttu-id="95aa2-153">%SystemRoot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="95aa2-153">%systemroot%\SysWow64\LogFiles</span></span>
    
  - <span data-ttu-id="95aa2-154">%SystemRoot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="95aa2-154">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>
    
  - <span data-ttu-id="95aa2-155">%programfiles%\Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="95aa2-155">%programfiles%\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="95aa2-156">%programfiles%\Common Files\Skype Entreprise Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="95aa2-156">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>
    
  - <span data-ttu-id="95aa2-157">%programfiles%\Common Files\Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="95aa2-157">%programfiles%\Common Files\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="95aa2-158">%programfiles%\Common Files\Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="95aa2-158">%programfiles%\Common Files\Skype for Business Online</span></span>
    
  - <span data-ttu-id="95aa2-159">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="95aa2-159">%SystemDrive%\RtcReplicaRoot</span></span>
    
  - <span data-ttu-id="95aa2-p103">Magasin de partage de fichiers (spécifié dans le générateur de topologies). Les magasins de fichiers sont spécifiés dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="95aa2-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>
    
  - <span data-ttu-id="95aa2-162">Fichiers journaux et de données SQL Server, dont ceux pour la base de données principale, le magasin d’utilisateurs, le magasin d’archivage, le magasin de surveillance et le magasin d’applications.</span><span class="sxs-lookup"><span data-stu-id="95aa2-162">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="95aa2-163">Les fichiers journaux et de base de données peuvent être spécifiés dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="95aa2-163">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="95aa2-164">Pour plus d’informations sur les fichiers journaux et de données pour chaque base de données, y compris les noms par défaut, reportez-vous à la section [Placement des fichiers journaux et données de SQL Server](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="95aa2-164">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>
    
  - <span data-ttu-id="95aa2-165">SQL Server données et fichiers journaux, y compris ceux de la base de données frontale, Skype pour entreprise banque et banque de RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="95aa2-165">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="95aa2-166">Ils se trouvent normalement sous %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="95aa2-166">They are normally under %localdrive%\CSData.</span></span>
    

