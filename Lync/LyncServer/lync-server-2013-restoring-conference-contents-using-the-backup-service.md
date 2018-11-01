---
title: "Lync Server 2013 : Rest. du contenu d’une conf. avec le service de sauvegarde"
TOCTitle: Restauration du contenu d’une conférence avec le service de sauvegarde
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49891318
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration du contenu d’une conférence avec le service de sauvegarde dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Si les informations de conférence stockées dans le magasin de fichiers d’un pool frontal deviennent disponibles, vous devez restaurer ces informations pour permettre aux utilisateurs hébergés sur le pool de conserver leurs données de conférence. Si le pool frontal qui a perdu les données de conférence est couplé à un autre pool frontal, vous pouvez utiliser le service de sauvegarde pour restaurer les données.

Vous devez aussi effectuer cette tâche en cas de panne d’un pool entier et basculer ses utilisateurs sur un pool de sauvegarde. Quand ces utilisateurs sont rebasculés sur leur pool d’origine, vous devez également exécuter cette procédure pour recopier leur contenu de référence sur le pool d’origine.

Supposons que Pool1 est associé à Pool2 et que les données de conférence de Pool1 sont perdues. Vous pouvez utiliser l’applet de commande suivante pour appeler le service de sauvegarde afin de restaurer le contenu :

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

La restauration du contenu de conférence peut prendre un certain temps, qui est fonction de sa taille. Vous pouvez utiliser l’applet de commande suivante pour vérifier l’état du processus

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Le processus est terminé une fois que cette applet de commande a renvoyé une valeur d’état stable pour les données du module de conférence.

