---
title: 'Lync Server 2013 : Considérations techniques relatives au routage géodépendant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 978590484cbb6bd3c23fac26422c186847662e49
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Considérations techniques relatives au routage géodépendant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Lors de la planification du routage par emplacement, vous devez prendre en compte l’impact sur les situations suivantes.

<div>

## <a name="disaster-recovery"></a>Récupération d’urgence

Lors d’un basculement entre le pool principal et un pool de sauvegarde, ainsi que lors de la restauration d’opérations normales sur le pool principal, le routage de l’emplacement reste appliqué à tout moment dans le cadre d’une procédure de sinistre et de récupération.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

La configuration de l’acheminement en fonction de l’emplacement a un impact sur la planification de l’endroit où vous déployez les passerelles associées à vos appareils distants. La passerelle associée à votre SBA doit se trouver dans le même site réseau que votre application de succursale Survivable ; dans le cas contraire, les utilisateurs hébergés sur votre unité de branchement Survivable ne sont pas autorisés à effectuer des appels sortants si le routage par emplacement est configuré. Lorsque la connexion WAN entre votre appareil de branchement Survivable et le site central est en panne, des restrictions de routage basées sur l’emplacement ne sont pas appliquées.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification du routage géodépendant dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

