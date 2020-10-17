---
title: 'Lync Server 2013 : déploiement de sites de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed57a78637639d5e6402f88b7909114f3aabce7a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531291"
---
# <a name="deploying-branch-sites-in-lync-server-2013"></a>Déploiement de sites de succursale dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Les utilisateurs de site de succursale obtiennent la plupart de leurs fonctionnalités Lync Server 2013 à partir du serveur sur le site central auquel le site de succursale est associé. Chaque site de succursale est associé à exactement un site central. Pour transmettre les appels vers et depuis le réseau téléphonique commuté public, le site de succursale peut avoir besoin de ce qui suit :

  - une passerelle PSTN et si possible un serveur de médiation ;

  - une jonction SIP ;

  - une infrastructure vocale existante avec PBX (autocommutateur privé) ;

  - Un Survivable Branch Appliance

  - Un serveur Survivable Branch Server

Les sites de succursale disposant d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server sont plus résiliences en cas de défaillance du réseau étendu ou du site central que les sites de succursale sans l’une de ces solutions. Par exemple, dans un site disposant d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server déployé, les utilisateurs peuvent toujours effectuer et recevoir des appels RTC si le réseau qui connecte le site de succursale au site central est inactif. Une autre façon d’obtenir la résistance des sites de succursale consiste à utiliser une passerelle PSTN ou une jonction SIP avec un déploiement de Lync Server complet sur le site de succursale.

Pour plus d’informations sur le déploiement de site de succursale le plus approprié pour votre organisation, notamment les conditions préalables et les autres considérations de planification, reportez-vous à [Planning for PSTN Connectivity in Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) et [Planning for Branch-site Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) dans la documentation de planification.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Fourniture de la connectivité PSTN sur un site de succursale dans Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

