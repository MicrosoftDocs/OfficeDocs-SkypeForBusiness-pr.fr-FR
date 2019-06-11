---
title: 'Lync Server 2013 : Déploiement de sites de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c96a8c99b6f80e7e70f3129e502d33b93a73f42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>Déploiement de sites de succursale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Les utilisateurs du site de succursale obtiennent la plupart des fonctionnalités de Lync Server 2013 du serveur sur le site central auquel le site de succursale est associé. Chaque site de filiale est associé à un seul site central. Pour passer des appels vers et à partir du réseau téléphonique public commuté (RTC), un site de succursale peut comporter l’une des opérations suivantes:

  - Passerelle RTC et éventuellement un serveur méditation

  - Un Trunk SIP

  - Une infrastructure vocale existante avec un échange de succursale privée (PBX)

  - Appareil de branchement survivant

  - Serveur de succursales survivant

Les sites de succursales disposant d’une unité de branchement plus survivant ou d’un serveur de succursales survivant sont plus résilients en cas d’échecs de réseaux larges ou de sites de succursales sans l’une de ces solutions. Par exemple, dans le cas d’un site disposant d’une branche ou d’un serveur de succursale survivant, les utilisateurs peuvent toujours passer et recevoir des appels RTC si le réseau qui se connecte au site central est arrêté. Une autre méthode pour obtenir la résilience du site d’une succursale consiste à utiliser une passerelle PSTN ou une ligne SIP avec un déploiement de Lync Server à grande échelle sur le site de la succursale.

Pour en savoir plus sur le déploiement de sites de succursale approprié pour votre organisation, notamment les conditions préalables et d’autres considérations en matière de planification, voir [planification de la connectivité PSTN dans Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) et [planification de la résilience vocale dans Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) dans la documentation de planification.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Connectivité RTC sur un site de succursale dans Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

