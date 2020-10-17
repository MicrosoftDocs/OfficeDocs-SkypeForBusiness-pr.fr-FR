---
title: 'Lync Server 2013 : estimation du trafic et de l’utilisation de la voix'
description: 'Lync Server 2013 : estimation du trafic et de l’utilisation de la voix.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc288e6da65e8e6f221a05c6c82f0588414c8af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555010"
---
# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a>Estimation du trafic et de l’utilisation de la voix pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-07_

L’outil de planification Microsoft Lync Server 2013 utilise la mesure suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports nécessaires à la prise en charge de ce trafic.

  - <span></span>  
    Pour **Faible trafic** (1 appel PSTN par utilisateur et par heure), 15 utilisateurs par port.

  - <span></span>  
    Pour **Trafic moyen** (2 appels PSTN par utilisateur et par heure), 10 utilisateurs par port.

  - <span></span>  
    Pour **Trafic important** (au moins 3 appels PSTN par utilisateur et par heure), 5 utilisateurs par port.

Le nombre de ports à son tour détermine le nombre de serveurs de médiation et de passerelles qui seront nécessaires. La taille des passerelles de réseau téléphonique commuté (PSTN) que la plupart des organisations envisagent de déployer peut aller de 2 à 960 ports. (Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.)

Par exemple, une organisation comportant 10 000 utilisateurs et dont le trafic est moyen requiert 1 000 ports. Le nombre de passerelles requis est égal au nombre total de ports requis, qui est déterminé par la capacité totale des passerelles.

</div>

<span> </span>

</div>

</div>

</div>

