---
title: Configuration et surveillance du service de sauvegarde
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vous pouvez utiliser les commandes de Skype entreprise Server Management Shell pour configurer et surveiller le service de sauvegarde.
ms.openlocfilehash: 80b15b2306807fe5bfc36449e16953466e3af75c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818215"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Configuration et analyse du service de sauvegarde dans Skype entreprise Server

Vous pouvez utiliser les commandes Skype entreprise Server Management Shell suivantes pour configurer et surveiller le service de sauvegarde. Pour restaurer des informations de conférence stockées dans le magasin de fichiers d’un pool frontal, voir [restaurer le contenu de la Conférence à l’aide du service de sauvegarde](#restore-conference-contents-using-the-backup-service), ci-dessous.

> [!NOTE]  
> Le groupe RTCUniversalServerAdmins est le seul groupe qui dispose des autorisations d’exécution par défaut de **Get-CsBackupServiceStatus** . Pour utiliser cette applet de connexion, connectez-vous en tant que membre du groupe. Ou, vous pouvez accorder l’accès à cette commande à d’autres groupes (par exemple, CSAdministrator) à l’aide de l’applet de commande **Set-CsBackupServiceConfiguration** .

## <a name="to-see-the-backup-service-configuration"></a>Pour afficher la configuration du service de sauvegarde

Exécutez l’applet de commande suivante :

    Get-CsBackupServiceConfiguration

La valeur par défaut de SyncInterval est de deux minutes.

## <a name="to-set-the-backup-service-sync-interval"></a>Pour définir l’intervalle de synchronisation du service de sauvegarde

Exécutez l’applet de commande suivante :

    Set-CsBackupServiceConfiguration -SyncInterval interval

Par exemple, la valeur suivante définit l’intervalle à 3 minutes.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Même si vous pouvez utiliser cette applet de action pour modifier l’intervalle de synchronisation par défaut du service de sauvegarde, vous ne devez pas le faire sauf si cela est absolument nécessaire, car l’intervalle de synchronisation a un impact important sur les performances du service de sauvegarde et de l’objectif de point de récupération (RPO).

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Pour obtenir l’état du service de sauvegarde pour un pool particulier

Exécutez l’applet de commande suivante :

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> L’état de synchronisation du service de sauvegarde est défini de façon unidirectionnelle à partir d’un pool (P1) vers son pool de sauvegarde (P2). L’état de synchronisation de P1 à P2 peut être différent de celui de P2 à P1. Pour P1 à P2, le service de sauvegarde est dans un état « permanent » si toutes les modifications apportées à P1 sont entièrement répliquées dans le cadre de l’intervalle de synchronisation. Il est dans l’état « final » s’il n’y a plus de modifications à synchroniser entre P1 et P2. Les deux États indiquent une capture instantanée du service de sauvegarde au moment de l’exécution de l’applet de connexion. Cela ne signifie pas que l’état renvoyé sera le plus tard possible. En particulier, l’état « final » reste en attente uniquement si P1 ne génère aucune modification après l’exécution de l’applet de suspension. C’est vrai en cas d’échec de P1 sur P2 après que P1 est passé dans le mode lecture seule dans le cadre de la logique d’exécution d' **Invoke-CsPoolfailover** .

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Pour obtenir des informations sur la relation de sauvegarde d’un pool particulier

Exécutez l’applet de commande suivante :

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>Pour forcer la synchronisation du service de sauvegarde

Exécutez l’applet de commande suivante :

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Restaurer le contenu d’une conférence à l’aide du service de sauvegarde 

Si les informations de la Conférence stockées dans le magasin de fichiers d’un pool frontal deviennent indisponibles, vous devez restaurer ces informations de sorte que les utilisateurs hébergés sur le pool conservent leurs données de conférence. Si le pool frontal qui a perdu les données de conférence est associé à un autre pool frontal, vous pouvez utiliser le service de sauvegarde pour restaurer les données.

Vous devez également effectuer cette tâche si un pool entier a échoué et que vous devez faire basculer ses utilisateurs vers un pool de sauvegarde. Lorsque les utilisateurs ont basculé vers leur pool d’origine, vous devez utiliser cette procédure pour copier le contenu de la Conférence sur leur pool d’origine.

Supposez que Pool1 est associé à Pool2, et les données de conférence en Pool1 sont perdues. Vous pouvez utiliser l’applet de commande suivante pour appeler le service de sauvegarde et restaurer le contenu :

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

La restauration du contenu de la Conférence risque de prendre un certain temps en fonction de la taille de celle-ci. Pour vérifier l’état du processus, vous pouvez utiliser l’applet de commande suivante :

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Le processus est réalisé lorsque cette cmdlet renvoie une valeur d’état stable pour le module de conférence de données.
