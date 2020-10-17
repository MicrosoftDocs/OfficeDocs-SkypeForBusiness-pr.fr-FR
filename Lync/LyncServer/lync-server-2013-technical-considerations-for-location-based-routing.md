---
title: 'Lync Server 2013 : considérations techniques relatives au routage des Location-Based'
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
ms.openlocfilehash: 80364f35ffaf361353815988bcae12f29bca019c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536181"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Considérations techniques relatives au routage des Location-Based dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Lors de la planification de la Location-Based routage, vous devez prendre en compte l’impact sur les scénarios suivants.

<div>

## <a name="disaster-recovery"></a>Récupération d'urgence

Pendant un basculement depuis le pool principal vers un pool de sauvegarde, ainsi que lors de la restauration des opérations normales vers le pool principal, Location-Based routage reste appliqué à tout moment lors d’une procédure de récupération d’urgence et de récupération d’urgence.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

La configuration du routage des Location-Based a une incidence sur la planification de l’endroit où vous déployez les passerelles associées à vos Survivable Branch Appliances. La passerelle associée à votre SBA doit se trouver dans le même site réseau que votre Survivable Branch Appliance ; dans le cas contraire, les utilisateurs hébergés sur votre Survivable Branch Appliance ne seront pas autorisés à effectuer des appels sortants si Location-Based routage est configuré. Lorsque la connexion de réseau étendu entre votre Survivable Branch appliance et le site central est inactive, Location-Based les restrictions de routage restent appliquées.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification du routage des Location-Based dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

