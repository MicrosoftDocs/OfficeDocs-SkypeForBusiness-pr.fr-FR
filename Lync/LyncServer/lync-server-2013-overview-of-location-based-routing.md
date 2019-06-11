---
title: 'Lync Server 2013: vue d’ensemble du routage par emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b3a5cb2e89376a356daf54c6e5bc443ab52207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Vue d’ensemble du routage basé sur l’emplacement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Le routage géodépendant introduit de nouvelles règles modifiant le routage des appels RTC nationaux et internationaux pour empêcher le contournement des frais de réseau téléphonique commuté. Il offre la flexibilité nécessaire pour appliquer ces règles à certaines régions, passerelles ou groupes d’utilisateurs uniquement.

Les scénarios suivants illustrent les principaux types de routage de restrictions qui peuvent garantir:

  - Appels de sortie: le routage de géolocalisation peut imposer des appels sortants vers la sortie à partir d’une passerelle RTC qui se trouve dans la même région que celle où l’appelant doit éviter le contournement du réseau PSTN, qui empêche les appels à la sortie d’une passerelle RTC située dans une autre région que le visiteur.

  - Appels entrants – le routage de géolocalisation peut empêcher les appels RTC entrants de sonner sur des points de terminaison Lync si la passerelle RTC qui achemine l’appel entrant ne se trouve pas dans la même région que l’utilisateur Lync appelé.

  - Régions inconnues: le routage géolocalisation limite les appels RTC entrants et sortants vers et depuis les utilisateurs qui se trouvent dans des endroits indéterminés (c’est-à-dire, des utilisateurs distants qui se connectent à partir d’Internet ou qui se trouvent dans des régions inconnues).

  - Régions internationales: le routage de géolocalisation applique le routage des appels sortants par le biais des passerelles RTC internationales si une passerelle locale à l’emplacement de l’utilisateur est introuvable.

<div>

## <a name="see-also"></a>Voir aussi


[Planification du routage géodépendant dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

