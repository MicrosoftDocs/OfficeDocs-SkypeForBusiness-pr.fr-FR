---
title: 'Lync Server 2013 : prise en charge de la haute disponibilité et de la récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d3be41dd4ca3f942d5b57e1954cecf105fcc714
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Prise en charge de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-25_

Lync Server 2013 offre une haute disponibilité grâce à la redondance des serveurs via la mise en pool. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs. Pour plus d’informations sur les rôles serveur, consultez la rubrique [rôles serveur dans Lync server 2013](lync-server-2013-server-roles.md).

Lync Server 2013 fournit également des mesures de récupération d’urgence en activant le jumelage des pools. Si vous déployez cette topologie, vous désignez des paires de pools frontaux, chaque pool d’une paire étant situé dans un centre de données distinct et dans une zone géographique distincte. Si un pool ou un site n’est plus opérationnel, vous pouvez rediriger les utilisateurs de ce pool afin qu’ils se servent de l’autre pool de la paire, avec une interruption minimale du service.

Lync Server 2013 prend également en charge la haute disponibilité du serveur principal. Il s’agit d’une topologie facultative dans laquelle vous déployez deux serveurs principaux pour un pool frontal et configurez la mise en miroir SQL Server synchrone pour toutes les bases de données Lync exécutées sur les serveurs principaux.

Pour plus d’informations sur l’appariement des pools et la mise en miroir du serveur principal, voir [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

<div>

## <a name="see-also"></a>Voir aussi


[Rôles serveur dans Lync Server 2013](lync-server-2013-server-roles.md)  
[Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

