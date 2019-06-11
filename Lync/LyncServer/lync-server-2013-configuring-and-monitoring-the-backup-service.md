---
title: 'Lync Server 2013 : Configuration et surveillance du service de sauvegarde'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66a800014b3327e83426c9f758b7d5359c1ce6c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Configuration et surveillance du service de sauvegarde dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Vous pouvez utiliser les commandes Lync Server Management Shell suivantes pour configurer et surveiller le service de sauvegarde.

<div>


> [!NOTE]  
> Le groupe RTCUniversalServerAdmins est le seul groupe qui dispose des autorisations d’exécution par défaut de <STRONG>Get-CsBackupServiceStatus</STRONG> . Pour utiliser cette applet de connexion, connectez-vous en tant que membre du groupe. Ou, vous pouvez accorder l’accès à cette commande à d’autres groupes (par exemple, CSAdministrator) à l’aide de l’applet de commande <STRONG>Set-CsBackupServiceConfiguration</STRONG> .



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>Pour afficher la configuration du service de sauvegarde

Exécutez l’applet de commande suivante :

    Get-CsBackupServiceConfiguration

La valeur par défaut de SyncInterval est de deux minutes.

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>Pour définir l’intervalle de synchronisation du service de sauvegarde

Exécutez l’applet de commande suivante :

    Set-CsBackupServiceConfiguration -SyncInterval interval

Par exemple, la valeur suivante définit l’intervalle à 3 minutes.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> Même si vous pouvez utiliser cette applet de action pour modifier l’intervalle de synchronisation par défaut du service de sauvegarde, vous ne devez pas le faire sauf si cela est absolument nécessaire, car l’intervalle de synchronisation a un impact important sur les performances du service de sauvegarde et de l’objectif de point de récupération (RPO).



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Pour obtenir l’état du service de sauvegarde pour un pool particulier

Exécutez l’applet de commande suivante :

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> L’état de synchronisation du service de sauvegarde est défini de façon unidirectionnelle à partir d’un pool (P1) vers son pool de sauvegarde (P2). L’état de synchronisation de P1 à P2 peut être différent de celui de P2 à P1. Pour P1 à P2, le service de sauvegarde est dans un état «permanent» si toutes les modifications apportées à P1 sont entièrement répliquées dans le cadre de l’intervalle de synchronisation. Il est dans l’état «final» s’il n’y a plus de modifications à synchroniser entre P1 et P2. Les deux États indiquent une capture instantanée du service de sauvegarde au moment de l’exécution de l’applet de connexion. Cela ne signifie pas que l’état renvoyé sera le plus tard possible. En particulier, l’état «final» reste en attente uniquement si P1 ne génère aucune modification après l’exécution de l’applet de suspension. C’est vrai en cas d’échec de P1 sur P2 après que P1 est passé dans le mode lecture seule dans le cadre de la logique d’exécution d' <STRONG>Invoke-CsPoolfailover</STRONG> .



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Pour obtenir des informations sur la relation de sauvegarde d’un pool particulier

Exécutez l’applet de commande suivante :

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>Pour forcer la synchronisation du service de sauvegarde

Exécutez l’applet de commande suivante :

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

