---
title: Relations de serveur de sauvegarde de sauvegarde Lync Server 2013
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
ms.openlocfilehash: 9ac47dcda07d7c0ca368cc572ccfafe2c6c95b2f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Relations de serveur d’inscriptions de sauvegarde dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-28_

En plus de fournir une fonctionnalité de récupération d’urgence, deux pools associés jouent le rôle de serveur d’inscriptions de sauvegarde l’un pour l’autre. Dans Lync Server 2013, les relations de serveur d’inscriptions de sauvegarde entre les pools frontaux sont toujours 1:1 et réciproques. Cela signifie que si P1 est la sauvegarde de P2, alors P2 doit être la sauvegarde de P1, et aucun des deux ne peut servir de sauvegarde pour un autre pool frontal. Il s’agit d’une modification de Lync Server 2010, dans laquelle les relations de sauvegarde de pool frontal peuvent être nombreuses.

Même si les relations de sauvegarde entre deux pools frontaux doivent être 1:1 et symétriques, chaque pool frontal peut toujours être le serveur d’inscriptions de sauvegarde pour un nombre d’appliances Survivable Branch appliance, tout comme dans Lync Server 2010.

Notez que Lync Server 2013 n’étend pas la prise en charge de la récupération d’urgence aux utilisateurs hébergés sur un Survivable Branch appliance. Si un pool frontal qui sert de sauvegarde pour un Survivable Branch Appliance tombe en panne, les utilisateurs connectés au Survivable Branch Appliance tombent en mode résistance même après que les utilisateurs hébergés sur le pool frontal ont basculé vers le pool de serveurs frontaux de sauvegarde.

</div>

<span> </span>

</div>

</div>

</div>

