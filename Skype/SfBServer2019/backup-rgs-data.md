---
title: Sauvegarder les données de service de Response Group (RGS) dans Skype entreprise Server 2019
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
description: Découvrez comment sauvegarder des données de service de Response Group (RGS) dans Skype entreprise Server 2019.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824068"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="ceb1d-103">Sauvegarder les données de service de Response Group (RGS)</span><span class="sxs-lookup"><span data-stu-id="ceb1d-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="ceb1d-104">Avec la mise à jour cumulative de Skype entreprise Server 2019 de juillet, nous avons inclus la possibilité d’inclure des données RGS dans le cadre de la sauvegarde standard.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="ceb1d-105">Réplication des données RGS</span><span class="sxs-lookup"><span data-stu-id="ceb1d-105">RGS data replication</span></span>

<span data-ttu-id="ceb1d-106">Pour tester la fonctionnalité de réplication de données de RGS, suivez les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="ceb1d-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="ceb1d-107">Installez la mise à jour cumulative de juillet sur toutes les FEs de votre liste de serveurs couplés.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="ceb1d-108">Installez la base de données RGS sur les deux membres du pool couplé :</span><span class="sxs-lookup"><span data-stu-id="ceb1d-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="ceb1d-109">Exécutez l’applet de commande suivante sur les deux pools pour répliquer les données d’affichage de données existantes dans les tables de sauvegarde de manière à ce que les données puissent être collectées par RGSBackupService :</span><span class="sxs-lookup"><span data-stu-id="ceb1d-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="ceb1d-110">Activez RGSBackupService (cela permettra RGSBackupService globalement.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="ceb1d-111">Si ce paramètre est défini sur true, RGSBackupService commence la synchronisation des données RGS sur les pools couplés (les deux réserves doivent être CU1).</span><span class="sxs-lookup"><span data-stu-id="ceb1d-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="ceb1d-112">Attendez quelques minutes avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="ceb1d-113">À l’origine, le statut de l’BackupService (RGS) est NotInitialized.)</span><span class="sxs-lookup"><span data-stu-id="ceb1d-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="ceb1d-114">Pour vérifier BackupServiceStatus :</span><span class="sxs-lookup"><span data-stu-id="ceb1d-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="ceb1d-115">Pour vérifier DataReplication d’ensemble de pools, utilisez ces applets de contrôle (ces applets de contrôle n’affichent que les données de pool de propriétaire) :</span><span class="sxs-lookup"><span data-stu-id="ceb1d-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="ceb1d-116">Pour vérifier les données de la réserve de propriétaires et ses données de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="ceb1d-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="ceb1d-117">Vérifiez la fonctionnalité de flux de travail en effectuant un appel audio au flux de travail.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="ceb1d-118">Basculer votre liste de propriétaires de RGS.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="ceb1d-119">Vérifiez la fonctionnalité de flux de travail en effectuant un appel audio au flux de travail.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="ceb1d-120">Basculez le pool.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-120">Failback the pool.</span></span>
1. <span data-ttu-id="ceb1d-121">Mise à jour des données RGS sur une liste de sources et exécution d’un autre basculement pour vérifier que les modifications sont reflétées dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="ceb1d-122">RGS doit se comporter de la même façon que le comportement du basculement.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="ceb1d-123">Nous vous recommandons de suivre ces étapes sur une grande quantité de données et de procéder à des basculements et failbacks.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="ceb1d-124">Tout nouveau RGS créé après cette mise à jour de CU doit également être répliqué.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="ceb1d-125">Cmdlets RGS</span><span class="sxs-lookup"><span data-stu-id="ceb1d-125">RGS cmdlets</span></span>

- <span data-ttu-id="ceb1d-126">Pour vérifier BackupServiceStatus (l’état d’exportation doit être dans l’état final ou stable.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="ceb1d-127">L’état de l’importation doit être au mode normal.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="ceb1d-128">RGSBackupservice doit être activé.) :</span><span class="sxs-lookup"><span data-stu-id="ceb1d-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="ceb1d-129">Pour synchroniser les données de RGS sur le pool de sauvegardes, vous devez synchroniser l’ensemble des données RGS sur le pool de sauvegarde.) :</span><span class="sxs-lookup"><span data-stu-id="ceb1d-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="ceb1d-130">Pour synchroniser entièrement le magasin de données RGS sur le pool de sauvegardes, vous pouvez synchroniser la totalité des données RGS sur le pool de sauvegarde.) :</span><span class="sxs-lookup"><span data-stu-id="ceb1d-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="ceb1d-131">Pour synchroniser les données dans le pool de sauvegardes, vous pouvez synchroniser les données Delta sur le pool de sauvegarde pour RGS uniquement.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="ceb1d-132">Pour synchroniser toutes les données de module, y compris RGS :</span><span class="sxs-lookup"><span data-stu-id="ceb1d-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="ceb1d-133">Pour désactiver RGSBackupService (cette opération désactive globalement RGSBackupService.</span><span class="sxs-lookup"><span data-stu-id="ceb1d-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="ceb1d-134">Si ce paramètre est défini sur true, RGSBackupService sera désactivé sur tous les pools couplés.) :</span><span class="sxs-lookup"><span data-stu-id="ceb1d-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
