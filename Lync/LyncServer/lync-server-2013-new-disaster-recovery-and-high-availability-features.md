---
title: 'Lync Server 2013 : nouvelles fonctionnalités de haute disponibilité et de récupération d’urgence'
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
ms.openlocfilehash: 7845f919f04985e67d6825b8722904a9158606b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Nouvelles fonctionnalités de haute disponibilité et de récupération d’urgence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-20_

Comme dans Lync Server 2010, le schéma haute disponibilité (HA) principal pour Lync Server 2013 repose sur la redondance des serveurs via la mise en pool. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.

Lync Server 2013 ajoute de nouvelles mesures de récupération d’urgence en vous permettant de coupler des pools frontaux situés dans deux centres de données. Si l’un des pools appariés n’est plus opérationnel, un administrateur peut effectuer le basculement des utilisateurs de ce pool vers l’autre pool de la paire afin de garantir une continuité du service. Cette fonctionnalité ne nécessite aucune solution réseau ou matérielle coûteuse comme les réseaux de stockage ou les disques partagés.

Lync Server 2013 ajoute également la haute disponibilité du serveur principal. Il s’agit d’une topologie facultative dans laquelle vous déployez deux serveurs principaux pour un pool frontal et configurez la mise en miroir SQL synchrone pour toutes les bases de données Lync exécutées sur les serveurs principaux. Vous pouvez décider de déployer ou non un serveur témoin pour le miroir.

<div>

## <a name="see-also"></a>Voir aussi


[Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

