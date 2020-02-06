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
# <a name="back-up-response-group-service-rgs-data"></a>Sauvegarder les données de service de Response Group (RGS)

Avec la mise à jour cumulative de Skype entreprise Server 2019 de juillet, nous avons inclus la possibilité d’inclure des données RGS dans le cadre de la sauvegarde standard.

## <a name="rgs-data-replication"></a>Réplication des données RGS

Pour tester la fonctionnalité de réplication de données de RGS, suivez les étapes ci-dessous :

1. Installez la mise à jour cumulative de juillet sur toutes les FEs de votre liste de serveurs couplés.
1. Installez la base de données RGS sur les deux membres du pool couplé :
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Exécutez l’applet de commande suivante sur les deux pools pour répliquer les données d’affichage de données existantes dans les tables de sauvegarde de manière à ce que les données puissent être collectées par RGSBackupService :
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. Activez RGSBackupService (cela permettra RGSBackupService globalement. Si ce paramètre est défini sur true, RGSBackupService commence la synchronisation des données RGS sur les pools couplés (les deux réserves doivent être CU1). Attendez quelques minutes avant de commencer. À l’origine, le statut de l’BackupService (RGS) est NotInitialized.)
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. Pour vérifier BackupServiceStatus :
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Pour vérifier DataReplication d’ensemble de pools, utilisez ces applets de contrôle (ces applets de contrôle n’affichent que les données de pool de propriétaire) :
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. Pour vérifier les données de la réserve de propriétaires et ses données de sauvegarde :
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Vérifiez la fonctionnalité de flux de travail en effectuant un appel audio au flux de travail.
1. Basculer votre liste de propriétaires de RGS.
1. Vérifiez la fonctionnalité de flux de travail en effectuant un appel audio au flux de travail.
1. Basculez le pool.
1. Mise à jour des données RGS sur une liste de sources et exécution d’un autre basculement pour vérifier que les modifications sont reflétées dans le pool de sauvegarde. RGS doit se comporter de la même façon que le comportement du basculement.

> [!TIP]
> Nous vous recommandons de suivre ces étapes sur une grande quantité de données et de procéder à des basculements et failbacks. Tout nouveau RGS créé après cette mise à jour de CU doit également être répliqué.

## <a name="rgs-cmdlets"></a>Cmdlets RGS

- Pour vérifier BackupServiceStatus (l’état d’exportation doit être dans l’état final ou stable. L’état de l’importation doit être au mode normal. RGSBackupservice doit être activé.) :
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- Pour synchroniser les données de RGS sur le pool de sauvegardes, vous devez synchroniser l’ensemble des données RGS sur le pool de sauvegarde.) :
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- Pour synchroniser entièrement le magasin de données RGS sur le pool de sauvegardes, vous pouvez synchroniser la totalité des données RGS sur le pool de sauvegarde.) :
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- Pour synchroniser les données dans le pool de sauvegardes, vous pouvez synchroniser les données Delta sur le pool de sauvegarde pour RGS uniquement.
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- Pour synchroniser toutes les données de module, y compris RGS :
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- Pour désactiver RGSBackupService (cette opération désactive globalement RGSBackupService. Si ce paramètre est défini sur true, RGSBackupService sera désactivé sur tous les pools couplés.) :
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
