---
title: 'Lync Server 2013 : Emplacement de l’utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e9eac8fce71d99e0817c57841e2539ed6423f2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Emplacement de l’utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-09_

Le routage basé sur géolocalisation exploite les mêmes régions, sites et sous-réseaux tels qu’ils sont définis dans Lync Server utilisé par E9-1-1, CAC et Media bypass pour appliquer des restrictions de routage des appels pour empêcher le contournement du numéro RTC. L’emplacement d’un utilisateur est déterminé par le sous-réseau IP du ou des points de terminaison Lync de l’utilisateur qui sont connectés. Chaque sous-réseau IP est associé à un site réseau, regroupé au sein de régions réseau définies par l’administrateur. Le routage géodépendant est appliqué sur la base du site réseau de l’utilisateur.

Les règles de routage basées sur le niveau de géolocalisation sont appliquées au niveau de chaque site du réseau, ce qui signifie qu’un ensemble de règles donné sera appliqué à tous les points de terminaison activés pour le routage par emplacement situés au sein du même site réseau. Les administrateurs peuvent appliquer le routage sur site aux sites réseau qui en ont besoin.

Il est possible de définir les stratégies de routage vocal sur une base de site réseau par site pour définir une passerelle PSTN particulière qui doit être utilisée par tous les utilisateurs situés dans le site réseau pour appeler des numéros de téléphone PSTN. Ces stratégies de routage de la voix prévaudront sur le routage défini par la stratégie vocale de l’utilisateur lorsque celui-ci se trouve dans un site réseau activé pour le routage de l’emplacement et qu’il empêche le routage des appels via d’autres passerelles RTC activées pour Routage basé sur l’emplacement. Lorsqu’un utilisateur de Lync place un appel RTC, la stratégie vocale de l’utilisateur détermine si l’utilisateur peut être autorisé à effectuer l’appel. Si la stratégie vocale de l’utilisateur permet à l’utilisateur de passer l’appel, le routage basé sur l’emplacement détermine la passerelle RTC à partir de laquelle l’appel doit être effectué. Le routage basé sur l’emplacement effectue cette détermination en fonction de l’emplacement de l’utilisateur.

L’emplacement d’un utilisateur peut être classé comme suit :

  - L’utilisateur se trouve dans un site réseau connu activé pour le routage géolocalisation et il se termine par un numéro sur une passerelle RTC placée sur le même site (par exemple, Office). Le routage des appels sortants est effectué via la stratégie de routage des communications vocales du site réseau dans lequel l’utilisateur est situé. Les appels RTC entrants destinés à l’utilisateur sont acheminés vers les points de terminaison situés dans le même site réseau que la passerelle RTC.

  - L’utilisateur est situé dans un site réseau connu différent du site réseau dans lequel la passerelle RTC est située (l’utilisateur a été déplacé vers une autre agence). Le routage des appels sortants utilise la stratégie de routage des communications vocales du site réseau dans lequel l’utilisateur est situé. Les appels RTC entrants destinés à l’utilisateur ne sont pas acheminés vers les points de terminaison situés dans d’autres sites que la passerelle RTC pour empêcher le contournement des frais de réseau téléphonique commuté.

  - Lorsqu’un utilisateur se trouve dans un site réseau qui n’est pas connu du déploiement de Lync Server, le routage des appels sortants sera basé sur la stratégie vocale attribuée à l’utilisateur sur les passerelles RTC qui ne sont pas liées aux restrictions de routage basées sur l’emplacement. Les appels RTC entrants ne sont pas acheminés vers les points de terminaison situés dans des sites réseau inconnus pour empêcher le contournement des frais de réseau téléphonique commuté.

<div>

## <a name="see-also"></a>Voir aussi


[Instructions de routage géodépendant dans Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

