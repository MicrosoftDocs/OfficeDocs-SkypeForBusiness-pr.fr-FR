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
ms.openlocfilehash: 4b67f1472bbb8225bf952b5b678bcae8401d211d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508971"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="5f102-102">Exclusions d’analyse antivirus pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f102-103">_**Dernière modification de la rubrique :** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="5f102-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="5f102-104">Pour vous assurer que le scanneur antivirus n’interfère pas avec le fonctionnement de Lync Server 2013, vous devez exclure des processus et des répertoires spécifiques pour chaque rôle serveur ou serveur Lync Server 2013 sur lequel vous exécutez un scanneur antivirus.</span><span class="sxs-lookup"><span data-stu-id="5f102-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="5f102-105">Les répertoires et processus suivants doivent être exclus :</span><span class="sxs-lookup"><span data-stu-id="5f102-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f102-106">Emplacements de fichiers et de dossiers répertoriés ci-dessous sont les emplacements par défaut pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f102-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="5f102-107">Pour tout emplacement pour lequel vous n’avez pas utilisé le paramètre par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut mentionnés dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5f102-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5f102-108">Notez que certains programmes antivirus peuvent nécessiter des chemins d’accès absolus, non relatifs, pour leur liste d’exclusion.</span><span class="sxs-lookup"><span data-stu-id="5f102-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="5f102-109">Processus Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="5f102-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="5f102-110">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="5f102-111">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="5f102-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="5f102-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="5f102-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="5f102-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="5f102-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="5f102-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="5f102-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="5f102-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="5f102-120">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="5f102-121">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="5f102-122">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="5f102-123">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="5f102-124">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="5f102-125">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="5f102-126">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="5f102-127">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="5f102-128">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="5f102-129">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="5f102-130">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="5f102-131">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="5f102-132">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="5f102-133">Processus du service d’hôte de fabric Windows :</span><span class="sxs-lookup"><span data-stu-id="5f102-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="5f102-134">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="5f102-135">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="5f102-136">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-136">FabricHost.exe</span></span>

  - <span data-ttu-id="5f102-137">Processus IIS :</span><span class="sxs-lookup"><span data-stu-id="5f102-137">IIS processes:</span></span>
    
      - <span data-ttu-id="5f102-138">% systemroot% \\ system32 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="5f102-139">% systemroot% \\ SysWOW64 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="5f102-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="5f102-140">Processus de Back-End SQL Server :</span><span class="sxs-lookup"><span data-stu-id="5f102-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="5f102-141">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11.SQLServr.exe de MSSQLSERVER \\ MSSQL \\ \\</span><span class="sxs-lookup"><span data-stu-id="5f102-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="5f102-142">% ProgramFiles% \\ Microsoft SQL Server \\ MSRS11.ReportingServicesService.exe bin de l’outil MSSQLSERVER \\ Reporting Services \\ \\ \\</span><span class="sxs-lookup"><span data-stu-id="5f102-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="5f102-143">% ProgramFiles% \\ Microsoft SQL Server \\ MSAS11.MSMDSrv.exe de la \\ Corbeille OLAP de MSSQLSERVER \\ \\</span><span class="sxs-lookup"><span data-stu-id="5f102-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="5f102-144">Processus de Front-End SQL Server :</span><span class="sxs-lookup"><span data-stu-id="5f102-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="5f102-145">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. \\SQLServr.exe MSSQL \\ Binn \\ LYNCLOCAL</span><span class="sxs-lookup"><span data-stu-id="5f102-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="5f102-146">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. \\SQLServr.exe MSSQL \\ Binn \\ RTCLOCAL</span><span class="sxs-lookup"><span data-stu-id="5f102-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="5f102-147">Répertoires et fichiers :</span><span class="sxs-lookup"><span data-stu-id="5f102-147">Directories and files:</span></span>
    
      - <span data-ttu-id="5f102-148">% systemroot% \\ system32 \\ LogFiles</span><span class="sxs-lookup"><span data-stu-id="5f102-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="5f102-149">% systemroot% \\ SysWOW64 \\ LogFiles</span><span class="sxs-lookup"><span data-stu-id="5f102-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="5f102-150">% systemroot% \\ Microsoft.NET \\ \\ GAC GAC \_</span><span class="sxs-lookup"><span data-stu-id="5f102-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="5f102-151">% ProgramFiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="5f102-152">% ProgramFiles% de \\ fichiers communs le \\ \\ nœud observateur Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="5f102-153">\\fichiers communs% ProgramFiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="5f102-154">% SystemDrive% \\ RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="5f102-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="5f102-155">Magasin de partages de fichiers (spécifié dans le Générateur de topologies).</span><span class="sxs-lookup"><span data-stu-id="5f102-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="5f102-156">Les magasins de fichiers sont spécifiés dans le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="5f102-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="5f102-157">Données et fichiers journaux de SQL server, y compris ceux de la base de données principale, magasin utilisateur, magasin d’archivage, magasin de surveillance et magasin d’applications.</span><span class="sxs-lookup"><span data-stu-id="5f102-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="5f102-158">Les fichiers journaux et de base de données peuvent être spécifiés dans le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="5f102-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="5f102-159">Pour plus d’informations sur les données et les fichiers journaux de chaque base de données, y compris les noms par défaut, voir [SQL Server Data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5f102-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="5f102-160">Les fichiers de données et les fichiers journaux SQL Server, y compris ceux de la base de données frontale, Lync Store et RtcDatabase Store.</span><span class="sxs-lookup"><span data-stu-id="5f102-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="5f102-161">Ils sont normalement sous% Lecteur_Local% \\ CSData.</span><span class="sxs-lookup"><span data-stu-id="5f102-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

