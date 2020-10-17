---
title: 'Lync Server 2013 : vue d’ensemble du routage des Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48fee2b9db45519ff4773b4dfe47b33745e5fb10
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520961"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Vue d’ensemble du routage des Location-Based dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Le routage des Location-Based introduit un nouveau jeu de règles qui modifie le routage des appels RTC nationaux et internationaux afin de prévenir toute déviation du péage. Le routage de Location-Based offre la possibilité d’étendre ces règles à des régions spécifiques, des passerelles spécifiques ou à un ensemble spécifique d’utilisateurs.

Les scénarios suivants illustrent les principaux types de restrictions Location-Based le routage peut appliquer :

  - Appels sortants : le routage de Location-Based peut appliquer des appels sortants à des sorties à partir d’une passerelle PSTN se trouvant dans la même région que l’appelant pour empêcher le contournement Toll, ce qui empêche les appels à sortir d’une passerelle PSTN située dans une autre région que l’appelant.

  - Appels entrants : le routage des Location-Based peut empêcher les appels RTC entrants de sonner les points de terminaison Lync si la passerelle PSTN achemine l’appel entrant ne se trouve pas dans la même région que l’utilisateur Lync appelé.

  - Régions inconnues : le routage des Location-Based limite les appels PSTN entrants et sortants vers et à partir d’utilisateurs situés dans des emplacements indéterminés (c’est-à-dire des utilisateurs distants se connectant à partir d’Internet ou situés dans des régions inconnues).

  - Régions internationales : le routage des Location-Based applique le routage des appels sortants via des passerelles RTC internationales s’il est impossible de trouver une passerelle locale vers l’emplacement de l’utilisateur.

<div>

## <a name="see-also"></a>Voir aussi


[Planification du routage des Location-Based dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

