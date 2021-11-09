---
title: Configuration et surveillance du service de sauvegarde
ms.reviewer: ''
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Vous pouvez utiliser les Skype Entreprise Server Management Shell pour configurer et surveiller le service de sauvegarde.
ms.openlocfilehash: 0881d40ca639edf825b0af104981ceddcab6e87a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832018"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Configuration et surveillance du service de sauvegarde dans Skype Entreprise Server

Vous pouvez utiliser les commandes suivantes Skype Entreprise Server Management Shell pour configurer et surveiller le service de sauvegarde. Pour restaurer les informations de conférence stockées dans le magasin de fichiers d’un pool frontal, voir Restaurer le contenu de la conférence à l’aide du [service](#restore-conference-contents-using-the-backup-service)de sauvegarde, ci-dessous.

> [!NOTE]  
> Le groupe RTCUniversalServerAdmins est le seul groupe autorisé à exécuter **Get-CsBackupServiceStatus** par défaut. Pour utiliser cette cmdlet, connectez-vous en tant que membre de ce groupe. Vous pouvez également accorder l’accès à cette commande à d’autres groupes  (par exemple, CSAdministrator) à l’aide de l';

## <a name="to-see-the-backup-service-configuration"></a>Pour voir la configuration du service de sauvegarde

Exécutez la l’applet commande suivant :<br/><br/>Get-CsBackupServiceConfiguration

La valeur par défaut de SyncInterval est de deux minutes.

## <a name="to-set-the-backup-service-sync-interval"></a>Pour définir l’intervalle de synchronisation du service de sauvegarde

Exécutez la l’applet commande suivant :<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval

Par exemple, l’exemple suivant définit l’intervalle sur trois minutes.<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Bien que vous pouvez utiliser cette cmdlet pour modifier l’intervalle de synchronisation par défaut pour le service de sauvegarde, vous ne devez pas le faire sauf si cela est absolument nécessaire, car l’intervalle de synchronisation a un impact considérable sur les performances du service de sauvegarde et l’objectif de point de récupération (RPO).

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Pour obtenir l’état du service de sauvegarde pour un pool particulier

Exécutez la l’applet commande suivant :<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<pool-FQDN>

> [!NOTE]  
> L’état de synchronisation du service de sauvegarde est défini de manière unidirectionnelle à partir d’un pool (P1) vers son pool de sauvegarde (P2). L’état de synchronisation de P1 à P2 peut être différent de celui de P2 à P1. Pour P1 à P2, le service de sauvegarde est dans un état « stable » si toutes les modifications apportées dans P1 sont entièrement répliquées sur P2 au cours de l’intervalle de synchronisation. Il est dans l’état « final » s’il n’y a plus de modifications à synchroniser de P1 à P2. Les deux états indiquent un instantané du service de sauvegarde au moment de l’exécution de la cmdlet. Cela ne signifie pas que l’état renvoyé restera tel quel par la suite. En particulier, l’état « final » continuera de se maintenir uniquement si P1 ne génère aucune modification après l’exécution de l’cmdlet. Cela est vrai dans le cas d’un passage de P1 à P2 après que P1 est placé en mode lecture seule dans le cadre de la logique d’exécution **Invoke-CsPoolfailover.**

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Pour obtenir des informations sur la relation de sauvegarde pour un pool particulier

Exécutez la l’applet commande suivant :<br/><br/>Get-CsPoolBackupRelationship -PoolFQDN \<poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>Pour forcer la synchronisation d’un service de sauvegarde

Exécutez la l’applet commande suivant :<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<poolFqdn> [-BackupModule {All| PresenceFocus| DataConf| CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Restaurer le contenu des conférences à l’aide du service de sauvegarde 

Si les informations de conférence stockées dans le magasin de fichiers d’un pool frontal deviennent indisponibles, vous devez restaurer ces informations afin que les utilisateurs qui y sont stockés conservent leurs données de conférence. Si le pool frontal qui a perdu des données de conférence est associé à un autre pool frontal, vous pouvez utiliser le service de sauvegarde pour restaurer les données.

Vous devez aussi effectuer cette tâche en cas de panne d’un pool entier et basculer ses utilisateurs sur un pool de sauvegarde. Quand ces utilisateurs sont rebasculés sur leur pool d’origine, vous devez également exécuter cette procédure pour recopier leur contenu de référence sur le pool d’origine.

Supposons que Pool1 est couplé à Pool2 et que les données de conférence de Pool1 sont perdues. Vous pouvez utiliser l’cmdlet suivante pour appeler le service de sauvegarde afin de restaurer le contenu :<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

La restauration du contenu de conférence peut prendre un certain temps, qui est fonction de sa taille. Vous pouvez utiliser l’applet de commande suivante pour vérifier l’état du processus<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

Le processus est terminé une fois que cette applet de commande a retourné une valeur d’état stable pour les données du module de conférence.
