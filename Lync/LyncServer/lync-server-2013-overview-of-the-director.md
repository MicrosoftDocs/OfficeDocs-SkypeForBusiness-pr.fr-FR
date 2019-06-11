---
title: 'Lync Server 2013 : Vue d’ensemble du directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e1c36cd556dcf641acb4571b5bb349466eb278d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Vue d’ensemble du directeur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-08_

Un directeur est un serveur exécutant Lync Server 2013 qui authentifie les demandes des utilisateurs, mais qui n’utilise pas les comptes d’utilisateurs. Vous pouvez également déployer un réalisateur dans les deux scénarios suivants:

  - Si vous autorisez l’accès par des utilisateurs externes en déployant des serveurs de périphérie, vous devez également déployer un directeur. Dans ce scénario, le directeur authentifie les utilisateurs externes, puis transmet leur trafic aux serveurs internes. Lorsqu’un directeur est utilisé pour authentifier des utilisateurs externes, il allège la surcharge des serveurs du pool frontal en effectuant une authentification de ces utilisateurs. Il permet également d’isoler les listes frontales internes du trafic malveillant, par exemple pour les attaques par déni de service. Si le réseau est inondé de trafic externe non valide lors d’une telle attaque, il se termine au directeur.

  - Si vous déployez plusieurs pools front-end sur un site central, en ajoutant un réalisateur à ce site, vous pouvez rationaliser les demandes d’authentification et améliorer les performances. Dans ce scénario, toutes les demandes sont d’abord adressées au directeur, qui les route vers le pool frontal approprié.

</div>

<span> </span>

</div>

</div>

</div>

