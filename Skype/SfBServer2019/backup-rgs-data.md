---
title: Backing up Service Response Group (RGS) data in Skype Entreprise Server 2019
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: Découvrez comment back up Service Response Group (RGS) data in Skype Entreprise Server 2019.
ms.openlocfilehash: 7e3e4116a281584da7afc1807fe58e79d2528183
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581158"
---
# <a name="back-up-response-group-service-rgs-data"></a>Back up Service Response Group (RGS) data

Avec la Skype Entreprise Server cumulative de juillet 2019, nous avons inclus la possibilité d’inclure des données RGS dans le cadre de la sauvegarde standard.

## <a name="rgs-data-replication"></a>Réplication des données RGS

Pour essayer la fonctionnalité de réplication des données RGS, suivez les étapes ci-dessous :

1. Installez la mise à jour cumulative de juillet sur tous les fronts de votre pool couplé.
1. Installez la base de données RGS sur les deux membres du pool couplé :
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Exécutez l’cmdlet suivante sur les deux pools pour répliquer les données RGS existantes dans les tables de sauvegarde afin que les données soient reprises par RGSBackupService :
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. Activez RGSBackupService (cela activera RGSBackupService globalement. Si ce paramètre est vrai, RGSBackupService commence à synchroniser les données RGS sur les pools couplés (les deux pools doivent être CU1). Patientez quelques minutes avant de commencer. Initialement, l’état de RGS BackupService sera NotInitialized.) :
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. Pour vérifier BackupServiceStatus :
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Pour vérifier La réplication des données entre les pools, utilisez ces cmdlets (ces cmdlets n’indiquent que les données du pool du propriétaire) :
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. Pour vérifier les données RGS du pool propriétaire et ses données de sauvegarde :
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Vérifiez la fonctionnalité de flux de travail en appelant audio le flux de travail.
1. Faire échouer votre pool de propriétaires RGS.
1. Vérifiez la fonctionnalité de flux de travail en appelant audio le flux de travail.
1. Faire échouer le pool.
1. Mettez à jour les données RGS sur le pool source et effectuez un autre changement pour vérifier que les modifications sont reflétées sur le pool de sauvegarde. RGS doit se comporter de la même manière qu’avant le failover.

> [!TIP]
> Il est recommandé d’effectuer ces étapes sur un bloc de données et d’effectuer fréquemment des failovers et des rappels. Tous les nouveaux RGS créés après cette mise à jour de mise à jour de mise à jour doivent également être répliqués.

## <a name="rgs-cmdlets"></a>Cmdlets RGS

- Pour vérifier BackupServiceStatus (l’état d’exportation doit être dans l’état Final ou Stable. L’état d’importation doit être dans l’état Normal. RGSBackupservice doit être activé.) :
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- Pour synchroniser entièrement les données RGS sur le pool de sauvegarde (cela synchronisera les données RGS complètes sur le pool de sauvegarde.) :
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- Pour synchroniser entièrement le filestore RGS sur le pool de sauvegarde (cela synchronisera les données RGS complètes sur le pool de sauvegarde.) :
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- Pour synchroniser les données delta RGS sur le pool de sauvegarde (cela synchronisera les données delta sur le pool de sauvegarde pour RGS uniquement) :
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- Pour synchroniser toutes les données de module, y compris RGS :
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- Pour désactiver RGSBackupService (cela désactive RGSBackupService globalement. Si ce paramètre est vrai, RGSBackupService est désactivé sur tous les pools couplés.) :
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
