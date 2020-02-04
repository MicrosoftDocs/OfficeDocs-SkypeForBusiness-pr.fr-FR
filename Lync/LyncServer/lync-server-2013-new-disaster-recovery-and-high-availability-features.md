---
title: 'Lync Server 2013 : Nouvelles fonctionnalités de haute disponibilité et de récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aabac29c5e866c4bfeff8ad79d392578d52ba650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Nouvelles fonctionnalités de haute disponibilité et de récupération d’urgence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-20_

Comme dans Lync Server 2010, le schéma principal de haute disponibilité pour Lync Server 2013 repose sur la redondance du serveur via le regroupement. Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.

Lync Server 2013 ajoute de nouvelles mesures de reprise après sinistre en vous permettant de jumeler les pools front-end situés dans deux centres de données. Si l’une des listes de réserve s’affiche, un administrateur peut basculer sur les utilisateurs de ce pool vers l’autre pool de la paire pour garantir la continuation du service. Cette fonctionnalité n’exige pas de solutions réseau ou matérielles onéreuses, telles que les réseaux de stockage ou les disques partagés.

Lync Server 2013 ajoute également la haute disponibilité du serveur principal. Il s’agit d’une topologie facultative dans laquelle vous déployez deux serveurs dorsaux pour un pool frontal, et configurez la mise en miroir SQL synchrone pour toutes les bases de données Lync exécutées sur les serveurs dorsaux. Vous pouvez décider de déployer un témoin pour le miroir.

<div>

## <a name="see-also"></a>Voir aussi


[Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

