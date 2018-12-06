---
title: 'Lync Server 2013 : Configuration et surveillance du service de sauvegarde'
TOCTitle: Configuration et surveillance du service de sauvegarde
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205252(v=OCS.15)
ms:contentKeyID: 49298780
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration et surveillance du service de sauvegarde dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Les commandes Lync Server Management Shell suivantes vous permettent de configurer et de surveiller le service de sauvegarde.

> [!NOTE]  
> Le groupe RTCUniversalServerAdmins est le seul ayant des autorisations pour exécuter <strong>Get-CsBackupServiceStatus</strong> par défaut. Pour utiliser cette applet de commande, connectez-vous comme membre de ce groupe. Vous pouvez sinon accorder aux autres groupes (par exemple, le groupe CSAdministrator) l’accès à cette commande à l’aide de l’applet de commande <strong>Set-CsBackupServiceConfiguration</strong>.

## Pour afficher la configuration du service de sauvegarde

Exécutez l’applet de commande suivante :

    Get-CsBackupServiceConfiguration

La valeur par défaut pour SyncInterval est de deux minutes.

## Pour définir l’intervalle de synchronisation du service de sauvegarde

Exécutez l’applet de commande suivante :

    Set-CsBackupServiceConfiguration -SyncInterval interval

Par exemple, ce qui suit définit l’intervalle sur trois minutes :

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

> [!IMPORTANT]  
> Même si vous pouvez utiliser cette applet de commande pour modifier l’intervalle de synchronisation par défaut pour le service de sauvegarde, ne le modifiez pas à moins que ce soit absolument nécessaire, car l’intervalle de synchronisation a une forte incidence sur les performances du service de sauvegarde et sur la perte de données maximale admissible (RPO, Recovery Point Objective).

## Pour obtenir le statut du service de sauvegarde pour un pool donné

Exécutez l’applet de commande suivante :

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> Le statut de synchronisation du service de sauvegarde est défini de façon unidirectionnelle à partir d’un pool (P1) sur son pool de stockage (P2). Le statut de synchronisation de P1 à P2 peut différer de celui de P2 à P1. Dans le cas de P1 à P2, le service de sauvegarde est dans un état « stable » si toutes les modifications faites dans P1 sont entièrement répliquées sur P2 pendant l’intervalle de synchronisation. Son état passe à « final » s’il n’y a plus aucune modification à synchroniser de P1 à P2. Les deux états indiquent une copie instantanée du service de sauvegarde quand l’applet de commande s’exécute. Cela ne veut pas dire que l’état renvoyé ne change plus ensuite. L’état « final » plus particulièrement reste le même seulement si P1 ne génère pas de modification après l’exécution de l’applet de commande. C’est le cas lors du basculement de P1 à P2 après que P1 est placé en mode de lecture seule suite à l’exécution d’<strong>Invoke-CsPoolfailover</strong>.

## Pour obtenir des informations sur la relation de sauvegarde pour un pool donné

Exécutez l’applet de commande suivante :

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## Pour forcer une synchronisation du service de sauvegarde

Exécutez l’applet de commande suivante :

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

