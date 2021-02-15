---
title: Exclusions de l’analyse antivirus pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Vue d’ensemble de l’interopérabilité du scanneur antivirus avec Skype Entreprise Server.
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832264"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="46ec1-103">Exclusions de l’analyse antivirus pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="46ec1-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="46ec1-104">Vue d’ensemble de l’interopérabilité du scanneur antivirus avec Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="46ec1-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="46ec1-105">Pour vous assurer que le scanneur antivirus n’interfère pas avec le fonctionnement de Skype Entreprise Server, vous devez exclure des processus et des répertoires spécifiques pour chaque serveur ou rôle serveur Skype Entreprise Server sur lequel vous exécutez un scanneur antivirus.</span><span class="sxs-lookup"><span data-stu-id="46ec1-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="46ec1-106">Les répertoires et processus suivants doivent être exclus :</span><span class="sxs-lookup"><span data-stu-id="46ec1-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="46ec1-107">Les emplacements de dossiers et de fichiers répertoriés ci-dessous sont les emplacements par défaut pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="46ec1-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="46ec1-108">Pour tout emplacement pour lequel vous n’avez pas utilisé le paramètre par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut mentionnés dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="46ec1-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46ec1-109">Notez que certains programmes antivirus peuvent avoir besoin de chemins d’accès absolus, et non relatifs, pour leur liste d’exclusions.</span><span class="sxs-lookup"><span data-stu-id="46ec1-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="46ec1-110">Processus Skype Entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="46ec1-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="46ec1-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-111">ABServer.exe</span></span>

  - <span data-ttu-id="46ec1-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="46ec1-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="46ec1-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-114">ChannelService.exe</span></span>

  - <span data-ttu-id="46ec1-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="46ec1-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="46ec1-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="46ec1-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-118">DataProxy.exe</span></span>

  - <span data-ttu-id="46ec1-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="46ec1-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="46ec1-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="46ec1-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="46ec1-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-123">LysSvc.exe</span></span>

  - <span data-ttu-id="46ec1-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="46ec1-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="46ec1-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="46ec1-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="46ec1-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="46ec1-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="46ec1-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="46ec1-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-131">RtcHost.exe</span></span>

  - <span data-ttu-id="46ec1-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="46ec1-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="46ec1-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-134">XmppTGW.exe</span></span>

- <span data-ttu-id="46ec1-135">Processus du service hôte Windows Fabric :</span><span class="sxs-lookup"><span data-stu-id="46ec1-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="46ec1-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-136">Fabric.exe</span></span>

  - <span data-ttu-id="46ec1-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="46ec1-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-138">FabricHost.exe</span></span>

- <span data-ttu-id="46ec1-139">Processus IIS :</span><span class="sxs-lookup"><span data-stu-id="46ec1-139">IIS processes:</span></span>

  - <span data-ttu-id="46ec1-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="46ec1-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="46ec1-142">SQL Server Back-End processus :</span><span class="sxs-lookup"><span data-stu-id="46ec1-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="46ec1-143">Notez que ces chemins d’accès sont spécifiques SQL Server version.</span><span class="sxs-lookup"><span data-stu-id="46ec1-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="46ec1-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="46ec1-145">%ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="46ec1-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="46ec1-147">SQL Server Front-End processus :</span><span class="sxs-lookup"><span data-stu-id="46ec1-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="46ec1-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="46ec1-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="46ec1-150">Instance RTC d’installation Standard Edition</span><span class="sxs-lookup"><span data-stu-id="46ec1-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="46ec1-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="46ec1-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="46ec1-152">Répertoires et fichiers :</span><span class="sxs-lookup"><span data-stu-id="46ec1-152">Directories and files:</span></span>

  - <span data-ttu-id="46ec1-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="46ec1-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="46ec1-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="46ec1-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="46ec1-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="46ec1-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="46ec1-156">Notez que ces chemins d’accès sont spécifiques à la version de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="46ec1-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="46ec1-157">%programfiles%\Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="46ec1-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="46ec1-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="46ec1-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="46ec1-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="46ec1-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="46ec1-160">%programfiles%\Common Files\Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="46ec1-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="46ec1-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="46ec1-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="46ec1-p103">Magasin de partages de fichiers (spécifié dans le Générateur de topologies). Les magasins de fichiers sont spécifiés dans le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="46ec1-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="46ec1-164">Données et fichiers journaux de SQL server, y compris ceux de la base de données principale, magasin utilisateur, magasin d’archivage, magasin de surveillance et magasin d’applications.</span><span class="sxs-lookup"><span data-stu-id="46ec1-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="46ec1-165">Les fichiers journaux et de base de données peuvent être spécifiés dans le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="46ec1-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="46ec1-166">Pour plus de détails sur les données et fichiers journaux pour chaque base de données, y compris les noms par défaut, voir [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="46ec1-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="46ec1-167">SQL Server données et fichiers journaux, y compris ceux de la base de données frontale, du magasin Skype Entreprise et du magasin RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="46ec1-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="46ec1-168">Ils sont normalement sous %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="46ec1-168">They are normally under %localdrive%\CSData.</span></span>


