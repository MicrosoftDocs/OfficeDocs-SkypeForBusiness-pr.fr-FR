---
title: 'Lync Server 2013 : configuration requise pour le routage des Location-Based pour les conférences'
description: 'Lync Server 2013 : configuration requise pour le routage des Location-Based pour les conférences.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbaa1af2690c3148d2ecfb173b13be288a21d80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542520"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configuration requise pour le routage des Location-Based pour les conférences dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-19_

Les conditions requises pour l’installation et la configuration de l’application de conférence de routage de Location-Based sont les suivantes :

  - La mise à jour cumulative 2 de Lync Server 2013 doit être déployée sur tous les serveurs ou pools de votre topologie.

<div>


> [!NOTE]  
> Si la mise à jour cumulative 2 ou ultérieure de Lync Server 2013 n’est pas installée sur un serveur ou un pool Lync dans votre topologie, la mise en œuvre de Location-Based routage des réunions Lync n’est pas garantie.



</div>

  - Le routage de Location-Based Lync Server 2013 est une condition préalable pour l’application de conférence de routage de Location-Based. Pour plus d’informations sur la configuration du routage de Location-Based Lync Server 2013, reportez-vous à la rubrique [configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).

  - La configuration requise d' Location-Based application de conférence de routage est identique à la configuration requise pour le routage Location-Based de Lync Server 2013. Pour plus d’informations, reportez-vous à la rubrique [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Serveurs pris en charge

L’application de conférence de routage de Location-Based nécessite le déploiement de la mise à jour cumulative 2 de Lync Server 2013 sur tous les serveurs de pool de Front-End et Standard Edition de votre topologie. Si la mise à jour cumulative 2 de Lync Server 2013 n’est pas installée sur certains serveurs Lync de votre topologie, les restrictions de routage Location-Based ne peuvent pas être appliquées entièrement sur les réunions Lync et les transferts d’appels consultatifs.

Le tableau suivant identifie les combinaisons de rôles serveur et de versions qui prennent en charge le routage des Location-Based.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Version du pool Front-End</p></td>
<td><p>Version du serveur de médiation</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="odd">
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Mise à jour cumulative 1 de Lync Server 2013</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative 1 de Lync Server 2013</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Non</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>Clients pris en charge

Les clients Lync qui prennent en charge Location-Based le routage des réunions Lync sont les mêmes que les clients qui prennent en charge Lync Server 2013 Location-Based le routage. Pour plus d’informations, reportez-vous à la rubrique [prise en charge des clients et des serveurs pour le routage Location-Based](lync-server-2013-client-and-server-support-for-location-based-routing.md).

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Exigences de serveur de médiation pour les transferts d’appel consultatifs

L’application de conférence de routage de Location-Based nécessite le déploiement de serveurs de médiation autonomes afin d’appliquer des restrictions de routage Location-Based sur les transferts d’appel consultatifs.

Pour appliquer Location-Based routage des transferts d’appel consultatifs, le serveur de médiation doit être associé à un seul serveur de médiation (PBX, passerelle SIP, etc.) dans les régions réseau où le routage Location-Based est requis. Si des homologues de serveur de médiation supplémentaires sont déployés dans la même région réseau, le serveur de médiation homologue doit être associé à un autre serveur de médiation. Cette exigence est détaillée de la manière suivante :

  - Serveur de médiation unique par plusieurs homologues de serveur de médiation lorsqu’un transfert d’appel consultatif est acheminé vers un homologue de serveur de médiation par le biais d’un serveur de médiation configuré avec plusieurs jonctions SIP vers plusieurs homologues (PBX et passerelles), le transfert d’appel consultatif est bloqué pour empêcher le contournement des appels téléphoniques PSTN si le transfert consultatif est autorisé via des jonctions SIP,
    
    Par exemple, dans le cas d’un serveur de médiation unique traitant un homologue de serveur de médiation de passerelle PSTN et un homologue de serveur de médiation de PBX, le comportement suivant sera observé :
    
      - Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PSTN à un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel n’est pas autorisé à empêcher le contournement de téléphone PSTN.
    
      - Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PBX dans le même site (site 1) vers un utilisateur de Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel est interdit même s’il n’est pas pris en compte dans le cadre d’un contournement de téléphone PSTN potentiel.

  - Serveurs de médiation distincts par homologue de serveur de médiation
    
    Lorsqu’un transfert consultatif est ciblé sur un homologue de serveur de médiation, le transfert consultatif est évalué par rapport à l’homologue de serveur de médiation unique desservi par le serveur de médiation. L’appel sera rejeté ou autorisé en fonction du potentiel qu’il peut supporter dans le cadre du contournement de téléphone RTC, indépendamment de tous les autres homologues de serveur de médiation dans le site, car ils sont desservis par des serveurs de médiation distincts.
    
    Par exemple, dans le cas d’un serveur de médiation distinct traitant un homologue de serveur de médiation de passerelle PSTN et un homologue de serveur de médiation de PBX, le comportement suivant sera observé :
    
      - Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PSTN à un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel n’est pas autorisé à empêcher le contournement de téléphone PSTN.
    
      - Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PBX dans le même site (site 1) vers un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel est autorisé, car il n’est pas soumis à un contournement de téléphone PSTN potentiel.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Fonctionnalités non prises en charge par l’application de conférence de routage Location-Based

Les fonctionnalités suivantes ne sont pas prises en charge par l’application de conférence de routage de Location-Based :

  - Conférence rendez-vous. Le routage des Location-Based ne peut pas être appliqué pour les conférences rendez-vous. Toute demande d’accès à une conférence donnée n’est pas restreinte par le routage des Location-Based même si l’organisateur de la Conférence est un utilisateur Lync activé pour le routage de Location-Based.

  - Il est recommandé de ne pas mettre en service les numéros d’accès aux conférences dans les régions Location-Based où des restrictions de routage doivent être appliquées.

</div>

</div>

<span> </span>

</div>

</div>

</div>

