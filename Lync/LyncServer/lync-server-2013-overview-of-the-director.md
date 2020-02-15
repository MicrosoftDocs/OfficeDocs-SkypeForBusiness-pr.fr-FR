---
title: 'Lync Server 2013 : vue d’ensemble du directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55875699e2411527d9202565ae5d31cc72e776f7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Vue d’ensemble du directeur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Un directeur est un serveur exécutant Lync Server 2013 qui authentifie les demandes des utilisateurs, mais qui n’héberge pas de comptes d’utilisateur. Vous pouvez également déployer un directeur dans les deux scénarios suivants :

  - Si vous activez l’accès des utilisateurs externes en déployant des serveurs Edge, vous devez également déployer un directeur. Dans ce scénario, le directeur authentifie les utilisateurs externes, puis transmet leur trafic aux serveurs internes. Lorsqu’un directeur est utilisé pour authentifier les utilisateurs externes, il allège la charge des serveurs de pools frontaux à l’exécution de l’authentification de ces utilisateurs. Il permet également d’isoler les pools frontaux internes du trafic malveillant, tels que les attaques par déni de service. Si le réseau est saturé par du trafic externe non valide dans le cadre d’une telle attaque, tout ce trafic s’arrête au niveau du directeur.

  - Si vous déployez plusieurs pools frontaux sur un site central, en ajoutant un directeur à ce site, vous pouvez rationaliser les demandes d’authentification et améliorer les performances. Dans ce scénario, toutes les demandes sont d’abord adressées au directeur, qui les achemine vers le pool frontal correct.

</div>

<span> </span>

</div>

</div>

</div>

