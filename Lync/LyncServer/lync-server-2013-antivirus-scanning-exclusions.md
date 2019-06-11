---
title: 'Lync Server 2013 : exclusions de l’analyse antivirus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f354b93bf21f054e9b5b24e3befd1787279bbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="031e4-102">Exclusions de l’analyse antivirus pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="031e4-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="031e4-103">_**Dernière modification de la rubrique:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="031e4-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="031e4-104">Pour vous assurer que le scanner antivirus n’interagit pas avec le fonctionnement de Lync Server 2013, vous devez exclure les processus et répertoires spécifiques pour chaque serveur Lync Server 2013 Server ou le rôle serveur sur lequel vous exécutez un scanneur antivirus.</span><span class="sxs-lookup"><span data-stu-id="031e4-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="031e4-105">Vous devez exclure les processus et les répertoires suivants :</span><span class="sxs-lookup"><span data-stu-id="031e4-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="031e4-106">Emplacement des dossiers et fichiers indiqués ci-dessous sont les emplacements par défaut de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="031e4-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="031e4-107">Pour les emplacements pour lesquels vous n’avez pas utilisé la valeur par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut spécifiés dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="031e4-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="031e4-108">Notez que certains programmes antivirus peuvent avoir besoin de chemins d’accès absolus, non relatifs, pour leur liste d’exclusions.</span><span class="sxs-lookup"><span data-stu-id="031e4-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="031e4-109">Processus Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="031e4-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="031e4-110">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="031e4-111">AcpMcuSvc. exe</span><span class="sxs-lookup"><span data-stu-id="031e4-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="031e4-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="031e4-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="031e4-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="031e4-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="031e4-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="031e4-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="031e4-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="031e4-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="031e4-120">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="031e4-121">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="031e4-122">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="031e4-123">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="031e4-124">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="031e4-125">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="031e4-126">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="031e4-127">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="031e4-128">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="031e4-129">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="031e4-130">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="031e4-131">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="031e4-132">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="031e4-133">Processus du service d’hôte Windows Fabric :</span><span class="sxs-lookup"><span data-stu-id="031e4-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="031e4-134">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="031e4-135">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="031e4-136">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="031e4-136">FabricHost.exe</span></span>

  - <span data-ttu-id="031e4-137">Processus d’IIS :</span><span class="sxs-lookup"><span data-stu-id="031e4-137">IIS processes:</span></span>
    
      - <span data-ttu-id="031e4-138">% systemroot%\\system32\\inetsrv\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="031e4-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="031e4-139">% systemroot%\\SysWOW64\\inetsrv\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="031e4-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="031e4-140">Processus du serveur dorsal SQL Server :</span><span class="sxs-lookup"><span data-stu-id="031e4-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="031e4-141">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="031e4-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="031e4-142">% ProgramFiles%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\Reporting\\services\\\\ReportServer bin ReportingServicesService. exe</span><span class="sxs-lookup"><span data-stu-id="031e4-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="031e4-143">% ProgramFiles%\\Microsoft SQL Server\\MSAS11. Emplacement\\\\OLAP\\de MSSQLSERVER MSMDSrv. exe</span><span class="sxs-lookup"><span data-stu-id="031e4-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="031e4-144">Processus du serveur SQL Server frontal :</span><span class="sxs-lookup"><span data-stu-id="031e4-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="031e4-145">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="031e4-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="031e4-146">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="031e4-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="031e4-147">Répertoires et fichiers :</span><span class="sxs-lookup"><span data-stu-id="031e4-147">Directories and files:</span></span>
    
      - <span data-ttu-id="031e4-148">% systemroot%\\system32\\LogFiles</span><span class="sxs-lookup"><span data-stu-id="031e4-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="031e4-149">% systemroot%\\SysWOW64\\LogFiles</span><span class="sxs-lookup"><span data-stu-id="031e4-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="031e4-150">code global du\\GAC\\\_de\\l’assembly% systemroot% Microsoft.net</span><span class="sxs-lookup"><span data-stu-id="031e4-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="031e4-151">% ProgramFiles%\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="031e4-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="031e4-152">% ProgramFiles%\\fichiers\\communs Microsoft Lync Server 2013\\FileSystemWatcher</span><span class="sxs-lookup"><span data-stu-id="031e4-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="031e4-153">Fichiers\\communs%\\ProgramFiles% Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="031e4-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="031e4-154">% SystemDrive%\\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="031e4-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="031e4-155">Magasin de partage de fichiers (spécifié dans le générateur de topologies).</span><span class="sxs-lookup"><span data-stu-id="031e4-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="031e4-156">Les magasins de fichiers sont spécifiés dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="031e4-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="031e4-157">Fichiers journaux et de données SQL Server, dont ceux pour la base de données principale, le magasin d’utilisateurs, le magasin d’archivage, le magasin de surveillance et le magasin d’applications.</span><span class="sxs-lookup"><span data-stu-id="031e4-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="031e4-158">Les fichiers journaux et de base de données peuvent être spécifiés dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="031e4-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="031e4-159">Pour plus d’informations sur les données et les fichiers journaux pour chaque base de données, y compris les noms par défaut, voir [données SQL Server et emplacement des fichiers journaux pour Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="031e4-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="031e4-160">Les fichiers de données et les fichiers journaux de SQL Server, y compris ceux de la base de données frontale, du magasin Lync et du magasin RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="031e4-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="031e4-161">Ils sont généralement sous% Lecteur_Local%\\CSData.</span><span class="sxs-lookup"><span data-stu-id="031e4-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

