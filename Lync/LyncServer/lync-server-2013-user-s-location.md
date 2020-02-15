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
ms.openlocfilehash: bbb581f049e8d45d16ace385fc26908d3d8301b9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Emplacement de l’utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Le routage géodépendant s’appuie sur les mêmes régions réseau, sites et sous-réseaux que ceux définis dans Lync Server utilisé par E9-1-1, le contrôle d’admission des appels et la déviation du trafic multimédia pour appliquer des restrictions de routage des appels afin d’empêcher le contournement des appels RTC. L’emplacement d’un utilisateur est déterminé par le sous-réseau IP des points de terminaison Lync de l’utilisateur qui sont connectés. Chaque sous-réseau IP est associé à un site réseau, qui est regroupé en régions réseau définies par l’administrateur. Le routage géodépendant est appliqué en fonction du site réseau de l’utilisateur.

Les règles de routage basées sur l’emplacement sont appliquées pour chaque site réseau, ce qui signifie qu’un ensemble de règles donné est appliqué à tous les points de terminaison activés pour le routage géodépendant qui sont situés au sein du même site réseau. Les administrateurs peuvent appliquer le routage géodépendant aux sites réseau qui en ont besoin.

Les stratégies de routage des communications vocales peuvent être définies par site réseau pour définir une passerelle PSTN particulière qui doit être utilisée par tous les utilisateurs situés dans le site réseau pour appeler des numéros de téléphone PSTN. Ces stratégies de routage des communications vocales prévalent sur le routage défini par la stratégie de voix de l’utilisateur lorsque celui-ci se trouve dans un site réseau pour lequel le routage géodépendant est activé, et empêche le routage des appels via d’autres passerelles RTC activées pour Routage géodépendant. Lorsqu’un utilisateur Lync passe un appel RTC, la stratégie de voix de l’utilisateur détermine si l’utilisateur peut être autorisé à passer l’appel. Si la stratégie de voix de l’utilisateur permet à l’utilisateur de passer l’appel, le routage géodépendant détermine la passerelle PSTN à partir de laquelle l’appel doit être effectué. Le routage géodépendant effectue cette détermination en fonction de l’emplacement de l’utilisateur.

Un emplacement d’utilisateur peut être classé comme suit :

  - L’utilisateur se trouve dans un site réseau connu activé pour le routage géodépendant et son numéro DID (numérotation directe vers l’intérieur) se termine sur une passerelle RTC placée dans le même site réseau (c.-à-d. Office). Le routage des appels sortants s’effectue par le biais de la stratégie de routage des communications vocales du site réseau dans lequel se trouve l’utilisateur. Les appels RTC entrants vers l’utilisateur sont acheminés vers les points de terminaison situés dans le même site réseau que la passerelle RTC.

  - L’utilisateur se trouve dans un site réseau connu qui est différent du site réseau où se trouve la passerelle PSTN. (par exemple, l’utilisateur est parcouru à un autre bureau d’entreprise). Le routage des appels sortants utilise la stratégie de routage des communications vocales du site réseau dans lequel se trouve l’utilisateur. Les appels RTC entrants vers l’utilisateur ne sont pas acheminés vers les points de terminaison situés dans des sites différents de celui de la passerelle PSTN afin d’empêcher le contournement payant PSTN.

  - Lorsqu’un utilisateur se trouve dans un site réseau inconnu du déploiement de Lync Server, le routage des appels sortants est basé sur la stratégie de voix attribuée à l’utilisateur sur les passerelles PSTN qui ne sont pas liées à des restrictions de routage basées sur l’emplacement. Les appels RTC entrants ne sont pas acheminés vers les points de terminaison situés dans des sites réseau inconnus pour empêcher le contournement payant PSTN.

<div>

## <a name="see-also"></a>Voir aussi


[Conseils pour le routage géodépendant dans Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

