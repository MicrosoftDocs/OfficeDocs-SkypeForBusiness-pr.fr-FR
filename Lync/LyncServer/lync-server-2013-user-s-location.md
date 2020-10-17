---
title: 'Lync Server 2013 : emplacement de l’utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 854e887605cc1d3d2b6d394228ebd3e8059644ee
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518831"
---
# <a name="users-location-in-lync-server-2013"></a>Emplacement de l’utilisateur dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Location-Based le routage exploite les mêmes régions réseau, sites et sous-réseaux qu’il est défini dans Lync Server et utilisé par E9-1-1, le contrôle d’admission des appels et la déviation du trafic multimédia pour appliquer des restrictions de routage des appels afin d’empêcher le contournement Toll. L’emplacement d’un utilisateur est déterminé par le sous-réseau IP des points de terminaison Lync de l’utilisateur qui sont connectés. Chaque sous-réseau IP est associé à un site réseau, qui est regroupé en régions réseau définies par l’administrateur. Le routage des Location-Based est appliqué en fonction du site réseau de l’utilisateur.

Les règles de routage des Location-Based sont appliquées en fonction du site réseau, ce qui signifie qu’un ensemble de règles donné est appliqué à tous les points de terminaison activés pour le routage Location-Based qui sont situés dans le même site réseau. Les administrateurs peuvent appliquer des Location-Based le routage aux sites réseau qui en ont besoin.

Les stratégies de routage des communications vocales peuvent être définies par site réseau pour définir une passerelle PSTN particulière qui doit être utilisée par tous les utilisateurs situés dans le site réseau pour appeler des numéros de téléphone PSTN. Ces stratégies de routage des communications vocales prévalent sur le routage défini par la stratégie de voix de l’utilisateur lorsque celui-ci se trouve dans un site réseau activé pour le routage des Location-Based et qu’il empêche le routage des appels via d’autres passerelles RTC qui sont activées pour le routage de Location-Based. Lorsqu’un utilisateur Lync passe un appel RTC, la stratégie de voix de l’utilisateur détermine si l’utilisateur peut être autorisé à passer l’appel. Si la stratégie de voix de l’utilisateur autorise l’utilisateur à passer l’appel, Location-Based routage détermine la passerelle PSTN à partir de laquelle l’appel doit être effectué. Location-Based routage effectue cette détermination en fonction de l’emplacement de l’utilisateur.

Un emplacement d’utilisateur peut être classé comme suit :

  - L’utilisateur se trouve dans un site réseau connu activé pour le routage des Location-Based et son numéro a (numérotation directe vers l’intérieur) se termine sur une passerelle RTC placée dans le même site réseau (c.-à-d. Office). Le routage des appels sortants s’effectue par le biais de la stratégie de routage des communications vocales du site réseau dans lequel se trouve l’utilisateur. Les appels RTC entrants vers l’utilisateur sont acheminés vers les points de terminaison situés dans le même site réseau que la passerelle RTC.

  - L’utilisateur se trouve dans un site réseau connu qui est différent du site réseau où se trouve la passerelle PSTN. (par exemple, l’utilisateur est parcouru à un autre bureau d’entreprise). Le routage des appels sortants utilise la stratégie de routage des communications vocales du site réseau dans lequel se trouve l’utilisateur. Les appels RTC entrants vers l’utilisateur ne sont pas acheminés vers les points de terminaison situés dans des sites différents de celui de la passerelle PSTN afin d’empêcher le contournement payant PSTN.

  - Lorsqu’un utilisateur se trouve dans un site réseau inconnu du déploiement Lync Server, le routage des appels sortants est basé sur la stratégie de voix attribuée à l’utilisateur sur les passerelles PSTN qui ne sont pas liées à des restrictions de routage Location-Based. Les appels RTC entrants ne sont pas acheminés vers les points de terminaison situés dans des sites réseau inconnus pour empêcher le contournement payant PSTN.

<div>

## <a name="see-also"></a>Voir aussi


[Conseils pour le routage des Location-Based dans Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

