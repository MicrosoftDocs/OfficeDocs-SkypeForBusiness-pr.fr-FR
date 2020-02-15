---
title: 'Lync Server 2013 : vue d’ensemble du routage géodépendant'
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
ms.openlocfilehash: 7bc7320ffd8bb4d12483a882b588205d26e7e164
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Vue d’ensemble du routage géodépendant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Le routage géodépendant introduit un nouveau jeu de règles qui modifie le routage des appels RTC nationaux et internationaux afin de prévenir toute déviation du péage. Le routage géodépendant permet d’étendre la flexibilité de ces règles à des régions spécifiques, des passerelles spécifiques ou à un ensemble spécifique d’utilisateurs.

Les scénarios suivants illustrent les principaux types de restrictions que le routage géodépendant peut appliquer :

  - Appels sortants : le routage géodépendant peut forcer les appels sortants à sortir d’une passerelle PSTN se trouvant dans la même région que l’appelant est d’empêcher le contournement des appels PSTN, ce qui empêche les appels à sortir d’une passerelle PSTN située dans une autre région que le appelant.

  - Appels entrants : le routage géodépendant peut empêcher les appels RTC entrants de sonner les points de terminaison Lync si la passerelle PSTN achemine l’appel entrant ne se trouve pas dans la même région que l’utilisateur Lync appelé.

  - Régions inconnues : le routage géodépendant limite les appels RTC entrants et sortants à destination et en provenance des utilisateurs situés dans des emplacements indéterminés (c’est-à-dire des utilisateurs distants se connectant à partir d’Internet ou se trouvant dans des régions inconnues).

  - Régions internationales : le routage géodépendant impose le routage des appels sortants via des passerelles RTC internationales s’il est impossible de trouver une passerelle locale vers l’emplacement de l’utilisateur.

<div>

## <a name="see-also"></a>Voir aussi


[Planification du routage géodépendant dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

