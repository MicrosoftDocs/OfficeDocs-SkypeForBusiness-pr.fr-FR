---
title: 'Lync Server 2013 : Restauration du contenu d’une conférence avec le service de sauvegarde'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 873ca354ca592eb6bc317b579a0a6f5008e6a172
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>Restauration du contenu d’une conférence avec le service de sauvegarde dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Si les informations de la Conférence stockées dans le magasin de fichiers d’un pool frontal deviennent indisponibles. vous devez restaurer ces informations de sorte que les utilisateurs hébergés sur le pool conservent leurs données de conférence. Si le pool frontal qui a perdu les données de conférence est associé à un autre pool frontal, vous pouvez utiliser le service de sauvegarde pour restaurer les données.

Vous devez également effectuer cette tâche si un pool entier a échoué et que vous devez faire basculer ses utilisateurs vers un pool de sauvegarde. Lorsque les utilisateurs ont basculé vers leur pool d’origine, vous devez utiliser cette procédure pour copier le contenu de la Conférence sur leur pool d’origine.

Supposez que Pool1 est associé à Pool2, et les données de conférence en Pool1 sont perdues. Vous pouvez utiliser l’applet de commande suivante pour appeler le service de sauvegarde et restaurer le contenu :

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

La restauration du contenu de la Conférence risque de prendre un certain temps en fonction de la taille de celle-ci. Pour vérifier l’état du processus, vous pouvez utiliser l’applet de commande suivante :

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Le processus est réalisé lorsque cette cmdlet renvoie une valeur d’état stable pour le module de conférence de données.

</div>

<span> </span>

</div>

</div>

</div>

