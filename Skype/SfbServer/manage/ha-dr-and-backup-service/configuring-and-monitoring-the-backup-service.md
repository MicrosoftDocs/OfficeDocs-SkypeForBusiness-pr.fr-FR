---
title: Configuration et surveillance du service de sauvegarde
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez utiliser Skype pour les commandes Business Server Management Shell pour configurer et surveiller le Service de sauvegarde.
ms.openlocfilehash: 3a41caecb4e123505da2d529ea74c22a5d0e28e7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199876"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Configuration et surveillance du Service de sauvegarde dans Skype pour Business Server

Vous pouvez utiliser la Skype pour les commandes Business Server Management Shell suivante pour configurer et surveiller le Service de sauvegarde. Pour restaurer les informations de conférence stockées dans le magasin de fichiers d’un pool frontal, voir [restaurer le contenu de conférence à l’aide du Service de sauvegarde](#restore-conference-contents-using-the-backup-service), ci-dessous.

> [!NOTE]  
> Groupe RTCUniversalServerAdmins est le seul groupe qui dispose d’autorisations pour exécuter **Get-csbackupservicestatus ne** par défaut. Pour utiliser cette applet de commande, ouvrez une session en tant que membre de ce groupe. Ou bien, vous pouvez accorder l’accès à cette commande à d’autres groupes (par exemple, CSAdministrator) à l’aide de l’applet de commande **Set-CsBackupServiceConfiguration** .

## <a name="to-see-the-backup-service-configuration"></a>Pour afficher la configuration du Service de sauvegarde

Exécutez l’applet de commande suivante :

    Get-CsBackupServiceConfiguration

La valeur par défaut pour SyncInterval est de deux minutes.

## <a name="to-set-the-backup-service-sync-interval"></a>Pour définir l’intervalle de synchronisation du Service de sauvegarde

Exécutez l’applet de commande suivante :

    Set-CsBackupServiceConfiguration -SyncInterval interval

Par exemple, la commande suivante définit l’intervalle sur trois minutes.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Bien que vous pouvez utiliser cette applet de commande pour modifier l’intervalle de synchronisation par défaut pour le Service de sauvegarde, vous ne, sauf si elle est absolument nécessaire, en tant que la synchronisation intervalle a un impact important sur les performances du Service de sauvegarde et de l’objectif de point de récupération (RPO).

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Pour obtenir l’état du Service de sauvegarde pour un pool donné

Exécutez l’applet de commande suivante :

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> L’état de synchronisation du Service de sauvegarde est défini rubans à partir d’un pool (P1) à son pool de sauvegarde (P2). L’état de synchronisation de P1 vers P2 peut être différent de celui de P2 à P1. Pour P1 vers P2, Service de sauvegarde est dans un état « stable » si toutes les modifications apportées dans P1 sont complètement répliquées sur P2 dans l’intervalle de synchronisation. Il n’est dans l’état « final » s’il y a aucune modification à être synchronisées à partir de P1 à P2. Les deux états indiquent un instantané du Service de sauvegarde au moment de que l’applet de commande est exécutée. Il n’implique pas que l’état renvoyé restera est par la suite. En particulier, l’état « final » continuera à contenir uniquement si P1 ne génère pas toutes les modifications après l’exécution de l’applet de commande. Cela est vrai dans le cas de basculement P1 vers P2 après que P1 est placé dans le mode lecture seule dans le cadre de la logique d’exécution **Invoke-cspoolfailover ne** .

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Pour obtenir des informations sur la relation de sauvegarde pour un pool donné

Exécutez l’applet de commande suivante :

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>Pour forcer une synchronisation du Service de sauvegarde

Exécutez l’applet de commande suivante :

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Restaurer le contenu de conférence à l’aide du Service de sauvegarde 

Si les informations de conférence stockées dans le magasin de fichiers d’un pool frontal devient indisponibles, vous devez restaurer ces informations afin que les utilisateurs hébergés sur le pool conservent leurs données de conférence. Si le pool frontal qui a perdu les données de conférence est associé à un autre pool frontal, vous pouvez utiliser le Service de sauvegarde à restaurer les données.

Vous devez également effectuer cette tâche si un pool entier a échoué et vous avez à faire basculer les utilisateurs à un pool de sauvegarde. Lorsque ces utilisateurs sont basculées retour vers leur pool d’origine, vous devez utiliser cette procédure pour copier leur contenu de conférence à leur pool de d’origine.

Supposons que Pool1 est associé à Pool2, et les données de conférence dans Pool1 sont perdues. Vous pouvez utiliser la cmdlet suivante pour appeler le Service de sauvegarde pour restaurer le contenu :

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Restaurer le contenu de conférence peut prendre un certain temps, en fonction de leur taille. Vous pouvez utiliser l’applet de commande suivante pour vérifier l’état du processus :

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Le processus est terminé une fois cette applet de commande renvoie une valeur d’état stable pour le module de conférence de données.
