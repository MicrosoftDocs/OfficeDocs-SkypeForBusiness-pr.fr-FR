---
title: Relations des serveurs d’inscriptions de sauvegarde dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44111dbdec945e525b1ef54d910e1cf7f3b5a5d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Relations des serveurs d’inscriptions de sauvegarde dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-28_

En plus de fournir une fonctionnalité de récupération d’urgence, deux pools associés jouent le rôle de serveur d’inscriptions de sauvegarde l’un pour l’autre. Dans Lync Server 2013, les relations de registre de secours entre les pools frontal sont toujours 1:1 et réciproques. En d’autres termes, si P1 est la sauvegarde pour P2, P2 doit être la sauvegarde de P1, et aucune de ses autres listes frontales ne peut être sauvegardée. Il s’agit d’une modification de Lync Server 2010, qui peut être un grand nombre d’une relation de sauvegarde de pool frontal.

Même si les relations de sauvegarde entre les deux pools front-end doivent être 1:1 et symétriques, chaque pool frontal peut également être le Bureau d’enregistrement de sauvegarde pour n’importe quel nombre d’appareils plus survivant, comme dans Lync Server 2010.

Notez que Lync Server 2013 n’étend pas l’assistance de reprise après sinistre aux utilisateurs hébergés sur un appareil de succursales survivant. Dans le cas d’un pool frontal qui sert de sauvegarde pour une unité de branchement Survivable, les utilisateurs connectés à l’unité de branchement Survivable peuvent passer en mode de résilience, même si les utilisateurs hébergés sur le pool frontal ont basculé vers le pool frontal de sauvegarde.

</div>

<span> </span>

</div>

</div>

</div>

