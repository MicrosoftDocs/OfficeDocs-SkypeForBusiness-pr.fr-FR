---
title: 'Lync Server 2013 : configuration et surveillance du service de sauvegarde'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a14e7a451b6d28df2663498e64cf2fb85c818352
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Configuration et surveillance du service de sauvegarde dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Vous pouvez utiliser les commandes Lync Server Management Shell suivantes pour configurer et surveiller le service de sauvegarde.

<div>


> [!NOTE]  
> Le groupe RTCUniversalServerAdmins est le seul groupe disposant des autorisations pour exécuter <STRONG>Get-CsBackupServiceStatus</STRONG> par défaut. Pour utiliser cette applet de commande, ouvrez une session en tant que membre de ce groupe. Ou, vous pouvez accorder l’accès à cette commande à d’autres groupes (par exemple, CSAdministrator) à l’aide de la cmdlet <STRONG>Set-applet csbackupserviceconfiguration ne</STRONG> .



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>Pour afficher la configuration du service de sauvegarde

Exécutez la cmdlet suivante :

    Get-CsBackupServiceConfiguration

La valeur par défaut pour SyncInterval est de deux minutes.

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>Pour définir l’intervalle de synchronisation du service de sauvegarde

Exécutez la cmdlet suivante :

    Set-CsBackupServiceConfiguration -SyncInterval interval

Par exemple, le code suivant définit l’intervalle à trois minutes.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> Bien que vous puissiez utiliser cette applet de commande pour modifier l’intervalle de synchronisation par défaut pour le service de sauvegarde, vous ne devez pas le faire sauf si cela est absolument nécessaire, car l’intervalle de synchronisation a un fort impact sur les performances du service de sauvegarde et l’objectif de point de récupération (RPO).



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Pour obtenir l’état du service de sauvegarde pour un pool particulier

Exécutez la cmdlet suivante :

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> L’état de synchronisation du service de sauvegarde est défini de façon unidirectionnelle à partir d’un pool (P1) vers son pool de sauvegarde (P2). L’état de synchronisation de P1 à P2 peut être différent de celui de P2 à P1. Pour P1 à P2, le service de sauvegarde est dans un état « stable » si toutes les modifications apportées à P1 sont entièrement répliquées sur P2 dans l’intervalle de synchronisation. Il se trouve dans l’état « final » s’il n’y a plus de modifications à synchroniser de P1 à P2. Les deux États indiquent un instantané du service de sauvegarde au moment de l’exécution de la cmdlet. Cela ne signifie pas que l’état renvoyé restera le même. En particulier, l’état « final » reste en conservation uniquement si P1 ne génère pas de modifications après l’exécution de la cmdlet. Cela est vrai en cas de défaillance de P1 sur P2 après que P1 est placé dans le mode lecture seule dans le cadre de la logique d’exécution <STRONG>Invoke-applet cspoolfailover ne</STRONG> .



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Pour obtenir des informations sur la relation de sauvegarde pour un pool particulier

Exécutez la cmdlet suivante :

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>Pour forcer une synchronisation du service de sauvegarde

Exécutez la cmdlet suivante :

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

