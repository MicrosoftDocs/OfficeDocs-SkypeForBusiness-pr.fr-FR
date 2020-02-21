---
title: 'Lync Server 2013 : exclusions d’analyse antivirus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6f3e9afc3bd17f5cba4caa7619cb562be069942
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="204dc-102">Exclusions d’analyse antivirus pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="204dc-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="204dc-103">_**Dernière modification de la rubrique :** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="204dc-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="204dc-104">Pour vous assurer que le scanneur antivirus n’interfère pas avec le fonctionnement de Lync Server 2013, vous devez exclure des processus et des répertoires spécifiques pour chaque rôle serveur ou serveur Lync Server 2013 sur lequel vous exécutez un scanneur antivirus.</span><span class="sxs-lookup"><span data-stu-id="204dc-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="204dc-105">Les répertoires et processus suivants doivent être exclus :</span><span class="sxs-lookup"><span data-stu-id="204dc-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="204dc-106">Emplacements de fichiers et de dossiers répertoriés ci-dessous sont les emplacements par défaut pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="204dc-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="204dc-107">Pour tout emplacement pour lequel vous n’avez pas utilisé le paramètre par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut mentionnés dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="204dc-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="204dc-108">Notez que certains programmes antivirus peuvent nécessiter des chemins d’accès absolus, non relatifs, pour leur liste d’exclusion.</span><span class="sxs-lookup"><span data-stu-id="204dc-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="204dc-109">Processus Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="204dc-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="204dc-110">AB. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="204dc-111">AcpMcuSvc. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="204dc-112">ASMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="204dc-113">AVMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="204dc-114">ChannelService. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="204dc-115">ClsAgent. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="204dc-116">ComplianceService. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="204dc-117">DataMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="204dc-118">DataProxy. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="204dc-119">FileTransferAgent. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="204dc-120">IMMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="204dc-121">LysSvc. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="204dc-122">MasterReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="204dc-123">MediaRelaySvc. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="204dc-124">MediationServerSvc. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="204dc-125">MRASSvc. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="204dc-126">OcsAppServerHost. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="204dc-127">ReplicaReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="204dc-128">ReplicationApp. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="204dc-129">RtcHost. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="204dc-130">RTCSrv. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="204dc-131">XmppProxy. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="204dc-132">XmppTGW. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="204dc-133">Processus du service d’hôte de fabric Windows :</span><span class="sxs-lookup"><span data-stu-id="204dc-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="204dc-134">Fabric. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="204dc-135">FabricDCA. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="204dc-136">FabricHost. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-136">FabricHost.exe</span></span>

  - <span data-ttu-id="204dc-137">Processus IIS :</span><span class="sxs-lookup"><span data-stu-id="204dc-137">IIS processes:</span></span>
    
      - <span data-ttu-id="204dc-138">% systemroot%\\system32\\inetsrv\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="204dc-139">% systemroot%\\SysWOW64\\inetsrv\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="204dc-140">Processus principaux SQL Server :</span><span class="sxs-lookup"><span data-stu-id="204dc-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="204dc-141">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="204dc-142">% ProgramFiles%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\Reporting\\services\\\\ReportServer bin ReportingServicesService. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="204dc-143">% ProgramFiles%\\Microsoft SQL Server\\MSAS11. MSSQLSERVER\\OLAP\\bin\\MSMDSrv. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="204dc-144">Processus frontaux SQL Server :</span><span class="sxs-lookup"><span data-stu-id="204dc-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="204dc-145">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="204dc-146">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="204dc-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="204dc-147">Répertoires et fichiers :</span><span class="sxs-lookup"><span data-stu-id="204dc-147">Directories and files:</span></span>
    
      - <span data-ttu-id="204dc-148">% systemroot%\\system32\\LogFiles</span><span class="sxs-lookup"><span data-stu-id="204dc-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="204dc-149">% systemroot%\\SysWOW64\\LogFiles</span><span class="sxs-lookup"><span data-stu-id="204dc-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="204dc-150">% systemroot%\\Microsoft.NET\\\\GAC GAC\_</span><span class="sxs-lookup"><span data-stu-id="204dc-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="204dc-151">% ProgramFiles%\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="204dc-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="204dc-152">% ProgramFiles%\\de fichiers\\communs le nœud observateur\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="204dc-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="204dc-153">Fichiers\\communs%\\ProgramFiles% Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="204dc-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="204dc-154">% SystemDrive%\\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="204dc-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="204dc-155">Magasin de partages de fichiers (spécifié dans le Générateur de topologies).</span><span class="sxs-lookup"><span data-stu-id="204dc-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="204dc-156">Les magasins de fichiers sont spécifiés dans le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="204dc-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="204dc-157">Données et fichiers journaux de SQL server, y compris ceux de la base de données principale, magasin utilisateur, magasin d’archivage, magasin de surveillance et magasin d’applications.</span><span class="sxs-lookup"><span data-stu-id="204dc-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="204dc-158">Les fichiers journaux et de base de données peuvent être spécifiés dans le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="204dc-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="204dc-159">Pour plus d’informations sur les données et les fichiers journaux de chaque base de données, y compris les noms par défaut, voir [SQL Server Data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="204dc-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="204dc-160">Les fichiers de données et les fichiers journaux SQL Server, y compris ceux de la base de données frontale, Lync Store et RtcDatabase Store.</span><span class="sxs-lookup"><span data-stu-id="204dc-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="204dc-161">Ils sont normalement sous% Lecteur_Local%\\CSData.</span><span class="sxs-lookup"><span data-stu-id="204dc-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

