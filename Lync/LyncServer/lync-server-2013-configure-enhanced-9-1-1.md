---
title: 'Lync Server 2013 : configurer Enhanced 9-1-1'
description: 'Lync Server 2013 : configurer Enhanced 9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc7a2a9ed10e7f29f53a4dfff6dff926ded18d38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553330"
---
# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a>Configurer Enhanced 9-1-1 dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

Enhanced 9-1-1 (E9-1-1) est une fonctionnalité de notification d’urgence qui associe le numéro de téléphone de l’appelant à une adresse géographique ou postale. Au moyen de ces informations, le centre d’appels de la sécurité publique (PSAP) peut immédiatement contacter les services d’urgence et les dépêcher sur place pour porter secours à l’appelant.

Pour prendre en charge E9-1-1, Lync Server 2013 doit être en mesure d’associer correctement un emplacement à un client et de s’assurer que ces informations sont utilisées pour acheminer l’appel d’urgence vers le PSAPI le plus proche.

Pour plus d’informations sur la planification d’un déploiement E9-1-1, reportez-vous à la rubrique [Planning for Emergency Services (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).

<div>


> [!IMPORTANT]  
> Lync Server 2013 prend uniquement en charge E9-1-1 aux États-Unis. Pour déployer E9-1-1, vous devez configurer une connexion SIP à un fournisseur de services E9-1-1 certifié, ou déployer une passerelle ELIN (Emergency Location Identification Number) vers un fournisseur de services E9-1-1 basé sur le réseau téléphonique commuté (RTC). Pour plus d’informations, voir <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">enhanced 9-1-1 (E9-1-1) et serveur de médiation dans Lync server 2013</A>. Pour plus d’informations sur la configuration des connexions de jonction, voir <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with Media Bypass in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration d’un itinéraire des communications vocales E9-1-1 dans Lync Server 2013](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [Créer des stratégies d’emplacement dans Lync Server 2013](lync-server-2013-create-location-policies.md)

  - [Configurer les informations de site pour E9-1-1 dans Lync Server 2013](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [Configuration de la base de données d’emplacements dans Lync Server 2013](lync-server-2013-configure-the-location-database.md)

  - [Configurer les fonctionnalités avancées d’E9-1-1 dans Lync Server 2013](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

