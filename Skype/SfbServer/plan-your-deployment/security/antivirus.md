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
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296972"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="5d3ad-103">Exclusions de l’analyse antivirus pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5d3ad-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="5d3ad-104">Vue d’ensemble de l’interopérabilité avec le scanner antivirus avec Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="5d3ad-105">Cet article contient des recommandations susceptibles de permettre à un administrateur de déterminer la cause d’une instabilité éventuelle sur un ordinateur exécutant une version prise en charge de Microsoft Windows lorsqu’il est utilisé avec un logiciel antivirus dans un domaine Active Directory environnement ou dans un environnement d’entreprise géré.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="5d3ad-106">Nous vous recommandons d’appliquer provisoirement ces procédures pour évaluer un système.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="5d3ad-107">Si les recommandations contenues dans cet article vous aideront à améliorer les performances ou la stabilité du système, contactez le fabricant de votre logiciel antivirus pour obtenir des instructions ou une version mise à jour du logiciel antivirus.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="5d3ad-108">Cet article contient des informations pour vous aider à réduire les paramètres de sécurité ou pour désactiver temporairement les fonctionnalités de sécurité sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="5d3ad-109">Vous pouvez apporter ces modifications afin de comprendre la nature d’un problème spécifique.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="5d3ad-110">Avant de procéder à ces modifications, nous vous recommandons d’évaluer les risques associés à l’implémentation de cette solution de contournement dans votre environnement particulier.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="5d3ad-111">Si vous implémentez cette solution de contournement, prenez toutes les mesures supplémentaires appropriées pour protéger l’ordinateur des fichiers qui ne sont plus analysés par votre logiciel antivirus.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="5d3ad-112">Pour vous assurer que le scanner antivirus n’interagit pas avec le fonctionnement de Skype entreprise Server, vous devez exclure des processus spécifiques et des annuaires pour chaque rôle serveur ou serveur Skype entreprise Server sur lequel vous exécutez un scanneur antivirus.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="5d3ad-113">Vous devez exclure les processus et les répertoires suivants :</span><span class="sxs-lookup"><span data-stu-id="5d3ad-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="5d3ad-114">Dossiers et emplacements de fichiers indiqués ci-dessous sont les emplacements par défaut de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="5d3ad-115">Pour les emplacements pour lesquels vous n’avez pas utilisé la valeur par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut spécifiés dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d3ad-116">Notez que certains programmes antivirus peuvent avoir besoin de chemins d’accès absolus, non relatifs, pour leur liste d’exclusions.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="5d3ad-117">Processus du serveur Skype entreprise:</span><span class="sxs-lookup"><span data-stu-id="5d3ad-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="5d3ad-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-118">ABServer.exe</span></span>

  - <span data-ttu-id="5d3ad-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="5d3ad-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="5d3ad-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-121">ChannelService.exe</span></span>

  - <span data-ttu-id="5d3ad-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="5d3ad-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="5d3ad-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="5d3ad-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-125">DataProxy.exe</span></span>

  - <span data-ttu-id="5d3ad-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="5d3ad-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="5d3ad-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="5d3ad-129">LyncBackupService. exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="5d3ad-130">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-130">LysSvc.exe</span></span>

  - <span data-ttu-id="5d3ad-131">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="5d3ad-132">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="5d3ad-133">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="5d3ad-134">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="5d3ad-135">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="5d3ad-136">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="5d3ad-137">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="5d3ad-138">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-138">RtcHost.exe</span></span>

  - <span data-ttu-id="5d3ad-139">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="5d3ad-140">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="5d3ad-141">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-141">XmppTGW.exe</span></span>

- <span data-ttu-id="5d3ad-142">Processus du service d’hôte Windows Fabric :</span><span class="sxs-lookup"><span data-stu-id="5d3ad-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="5d3ad-143">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-143">Fabric.exe</span></span>

  - <span data-ttu-id="5d3ad-144">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="5d3ad-145">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-145">FabricHost.exe</span></span>

- <span data-ttu-id="5d3ad-146">Processus d’IIS :</span><span class="sxs-lookup"><span data-stu-id="5d3ad-146">IIS processes:</span></span>

  - <span data-ttu-id="5d3ad-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="5d3ad-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="5d3ad-149">Processus du serveur dorsal SQL Server :</span><span class="sxs-lookup"><span data-stu-id="5d3ad-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d3ad-150">Notez que ces chemins d’accès sont spécifiques à la version de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="5d3ad-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="5d3ad-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="5d3ad-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="5d3ad-154">Processus du serveur SQL Server frontal :</span><span class="sxs-lookup"><span data-stu-id="5d3ad-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="5d3ad-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="5d3ad-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="5d3ad-157">Instance RTC de l’installation de Standard Edition</span><span class="sxs-lookup"><span data-stu-id="5d3ad-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="5d3ad-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="5d3ad-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="5d3ad-159">Répertoires et fichiers :</span><span class="sxs-lookup"><span data-stu-id="5d3ad-159">Directories and files:</span></span>

  - <span data-ttu-id="5d3ad-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="5d3ad-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="5d3ad-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="5d3ad-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="5d3ad-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="5d3ad-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d3ad-163">Notez que ces chemins sont spécifiques à la version de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="5d3ad-164">%programfiles%\Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d3ad-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="5d3ad-165">%programfiles%\Common Files\Skype Entreprise Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="5d3ad-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="5d3ad-166">%programfiles%\Common Files\Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d3ad-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="5d3ad-167">%programfiles%\Common Files\Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="5d3ad-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="5d3ad-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="5d3ad-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="5d3ad-p105">Magasin de partage de fichiers (spécifié dans le générateur de topologies). Les magasins de fichiers sont spécifiés dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="5d3ad-p106">Fichiers journaux et de données SQL Server, dont ceux pour la base de données principale, le magasin d’utilisateurs, le magasin d’archivage, le magasin de surveillance et le magasin d’applications. Les fichiers journaux et de base de données peuvent être spécifiés dans le générateur de topologies. Pour plus d’informations sur les fichiers journaux et de données pour chaque base de données, dont les noms par défaut, reportez-vous à la rubrique [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation relative au déploiement.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-p106">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="5d3ad-174">Les fichiers de données et les fichiers journaux de SQL Server, y compris ceux de la base de données frontale, Skype entreprise Store et RtcDatabase Store.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="5d3ad-175">Ils se trouvent normalement sous %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="5d3ad-175">They are normally under %localdrive%\CSData.</span></span>


