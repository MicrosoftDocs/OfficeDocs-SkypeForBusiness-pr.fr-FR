---
title: Backing up Service Response Group (RGS) data in Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Découvrez comment back up Service Response Group (RGS) dans Skype Entreprise Server 2019.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824068"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="5e721-103">Back up Service Response Group (RGS) data</span><span class="sxs-lookup"><span data-stu-id="5e721-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="5e721-104">Avec la mise à jour cumulative de juillet 2019 de Skype Entreprise Server, nous avons inclus la possibilité d’inclure des données RGS dans le cadre de la sauvegarde standard.</span><span class="sxs-lookup"><span data-stu-id="5e721-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="5e721-105">Réplication des données RGS</span><span class="sxs-lookup"><span data-stu-id="5e721-105">RGS data replication</span></span>

<span data-ttu-id="5e721-106">Pour essayer la fonctionnalité de réplication des données RGS, suivez les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="5e721-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="5e721-107">Installez la mise à jour cumulative de juillet sur tous les fronts de votre pool couplé.</span><span class="sxs-lookup"><span data-stu-id="5e721-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="5e721-108">Installez la base de données RGS sur les deux membres du pool couplé :</span><span class="sxs-lookup"><span data-stu-id="5e721-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="5e721-109">Exécutez l’cmdlet suivante sur les deux pools pour répliquer les données RGS existantes dans les tables de sauvegarde afin que les données soient reprises par RGSBackupService :</span><span class="sxs-lookup"><span data-stu-id="5e721-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="5e721-110">Activez RGSBackupService (cela activera RGSBackupService globalement.</span><span class="sxs-lookup"><span data-stu-id="5e721-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="5e721-111">Si ce paramètre est vrai, RGSBackupService commence à synchroniser les données RGS sur les pools couplés (les deux pools doivent être CU1).</span><span class="sxs-lookup"><span data-stu-id="5e721-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="5e721-112">Patientez quelques minutes avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="5e721-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="5e721-113">Initialement, l’état de RGS BackupService sera NotInitialized.) :</span><span class="sxs-lookup"><span data-stu-id="5e721-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="5e721-114">Pour vérifier BackupServiceStatus :</span><span class="sxs-lookup"><span data-stu-id="5e721-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="5e721-115">Pour vérifier La réplication des données entre les pools, utilisez ces cmdlets (ces cmdlets n’indiquent que les données du pool du propriétaire) :</span><span class="sxs-lookup"><span data-stu-id="5e721-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="5e721-116">Pour vérifier les données RGS du pool propriétaire et ses données de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="5e721-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="5e721-117">Vérifiez la fonctionnalité de flux de travail en appelant audio le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="5e721-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="5e721-118">Faire échouer votre pool de propriétaires RGS.</span><span class="sxs-lookup"><span data-stu-id="5e721-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="5e721-119">Vérifiez la fonctionnalité de flux de travail en appelant audio le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="5e721-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="5e721-120">Faire échouer le pool.</span><span class="sxs-lookup"><span data-stu-id="5e721-120">Failback the pool.</span></span>
1. <span data-ttu-id="5e721-121">Mettez à jour les données RGS sur le pool source et effectuez un autre changement pour vérifier que les modifications sont reflétées sur le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="5e721-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="5e721-122">RGS doit se comporter de la même manière qu’avant le failover.</span><span class="sxs-lookup"><span data-stu-id="5e721-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="5e721-123">Il est recommandé d’effectuer ces étapes sur un bloc de données et d’effectuer fréquemment des failovers et des rappels.</span><span class="sxs-lookup"><span data-stu-id="5e721-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="5e721-124">Tous les nouveaux RGS créés après cette mise à jour de mise à jour de mise à jour doivent également être répliqués.</span><span class="sxs-lookup"><span data-stu-id="5e721-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="5e721-125">Cmdlets RGS</span><span class="sxs-lookup"><span data-stu-id="5e721-125">RGS cmdlets</span></span>

- <span data-ttu-id="5e721-126">Pour vérifier BackupServiceStatus (l’état d’exportation doit être dans l’état Final ou Stable.</span><span class="sxs-lookup"><span data-stu-id="5e721-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="5e721-127">L’état d’importation doit être dans l’état Normal.</span><span class="sxs-lookup"><span data-stu-id="5e721-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="5e721-128">RGSBackupservice doit être activé.) :</span><span class="sxs-lookup"><span data-stu-id="5e721-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="5e721-129">Pour synchroniser entièrement les données RGS sur le pool de sauvegarde (cela synchronisera les données RGS complètes sur le pool de sauvegarde.) :</span><span class="sxs-lookup"><span data-stu-id="5e721-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="5e721-130">Pour synchroniser entièrement le filestore RGS sur le pool de sauvegarde (cela synchronisera les données RGS complètes sur le pool de sauvegarde.) :</span><span class="sxs-lookup"><span data-stu-id="5e721-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="5e721-131">Pour synchroniser les données delta RGS sur le pool de sauvegarde (cela synchronisera les données delta sur le pool de sauvegarde pour RGS uniquement) :</span><span class="sxs-lookup"><span data-stu-id="5e721-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="5e721-132">Pour synchroniser toutes les données de module, y compris RGS :</span><span class="sxs-lookup"><span data-stu-id="5e721-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="5e721-133">Pour désactiver RGSBackupService (cela désactive RGSBackupService globalement.</span><span class="sxs-lookup"><span data-stu-id="5e721-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="5e721-134">Si ce paramètre est vrai, RGSBackupService est désactivé sur tous les pools couplés.) :</span><span class="sxs-lookup"><span data-stu-id="5e721-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
