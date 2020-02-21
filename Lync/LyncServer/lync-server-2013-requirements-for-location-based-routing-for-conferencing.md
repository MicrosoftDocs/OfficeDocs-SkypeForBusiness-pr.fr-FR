---
title: 'Lync Server 2013 : configuration requise pour le routage géodépendant pour les conférences'
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
ms.openlocfilehash: 567cebd5fcf1fc2a60fa110754f916525052e57d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configuration requise pour le routage géodépendant pour les conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-19_

Les conditions requises pour l’installation et la configuration de l’application de conférence de routage basée sur l’emplacement sont les suivantes :

  - La mise à jour cumulative 2 de Lync Server 2013 doit être déployée sur tous les serveurs ou pools de votre topologie.

<div>


> [!NOTE]  
> Si la mise à jour cumulative 2 ou ultérieure de Lync Server 2013 n’est pas installée sur un pool ou un serveur Lync dans votre topologie, l’application du routage géodépendant des réunions Lync n’est pas garantie.



</div>

  - Le routage géodépendant de Lync Server 2013 est une condition préalable pour l’application de conférence de routage basée sur l’emplacement. Pour plus d’informations sur la configuration du routage géodépendant de Lync Server 2013, reportez-vous à la rubrique [Configuring location-based Routing](lync-server-2013-configuring-location-based-routing.md).

  - La configuration requise de l’application de conférence de routage basée sur l’emplacement est identique à celle requise pour le routage géodépendant de Lync Server 2013. Pour plus d’informations, reportez-vous à la rubrique [Planning for location-based Routing](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Serveurs pris en charge

L’application de conférence de routage basée sur l’emplacement nécessite le déploiement de la mise à jour cumulative 2 de Lync Server 2013 sur tous les pools frontaux et les serveurs Standard Edition de votre topologie. Si la mise à jour cumulative 2 de Lync Server 2013 n’est pas installée sur certains serveurs Lync de votre topologie, les restrictions de routage géodépendant ne peuvent pas être appliquées entièrement sur les réunions Lync et les transferts d’appels consultatifs.

Le tableau suivant identifie les combinaisons de rôles serveur et de versions qui prennent en charge le routage géodépendant.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Version du pool frontal</p></td>
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
<td><p>N'importe lequel</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Non</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>Clients pris en charge

Les clients Lync qui prennent en charge le routage géodépendant des réunions Lync sont les mêmes que ceux qui prennent en charge le routage géodépendant de Lync Server 2013. Pour plus d’informations, reportez-vous à la rubrique [prise en charge des clients et des serveurs pour le routage géodépendant](lync-server-2013-client-and-server-support-for-location-based-routing.md).

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Exigences de serveur de médiation pour les transferts d’appel consultatifs

L’application de conférence de routage basée sur l’emplacement nécessite le déploiement de serveurs de médiation autonomes afin d’appliquer des restrictions de routage géodépendant sur les transferts d’appel consultatifs.

Pour appliquer le routage basé sur l’emplacement des transferts d’appel consultatifs, le serveur de médiation doit être associé à un seul serveur de médiation (PBX, passerelle SIP, etc.) dans les régions réseau où le routage géodépendant est requis. Si des homologues de serveur de médiation supplémentaires sont déployés dans la même région réseau, le serveur de médiation homologue doit être associé à un autre serveur de médiation. Cette exigence est détaillée de la manière suivante :

  - Serveur de médiation unique par plusieurs homologues de serveur de médiation lorsqu’un transfert d’appel consultatif est acheminé vers un homologue de serveur de médiation via un serveur de médiation configuré avec plusieurs jonctions SIP vers plusieurs pairs (PBX et passerelles), le Conseil consultatif le transfert d’appel est bloqué pour empêcher la déviation du trafic téléphonique PSTN si le transfert d’appel consultatif est autorisé via certaines jonctions SIP, mais interdit par le biais d’autres jonctions SIP.
    
    Par exemple, dans le cas d’un serveur de médiation unique traitant un homologue de serveur de médiation de passerelle PSTN et un homologue de serveur de médiation de PBX, le comportement suivant sera observé :
    
      - Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PSTN à un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel n’est pas autorisé à empêcher le contournement de téléphone PSTN.
    
      - Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PBX dans le même site (site 1) vers un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel est interdit même s’il n’est pas en mesure d’engendrer une probabilité RTC potentielle. l contournement.

  - Serveurs de médiation distincts par homologue de serveur de médiation
    
    Lorsqu’un transfert consultatif est ciblé sur un homologue de serveur de médiation, le transfert consultatif est évalué par rapport à l’homologue de serveur de médiation unique desservi par le serveur de médiation. L’appel sera rejeté ou autorisé en fonction du potentiel qu’il peut supporter dans le cadre du contournement de téléphone RTC, indépendamment de tous les autres homologues de serveur de médiation dans le site, car ils sont desservis par des serveurs de médiation distincts.
    
    Par exemple, dans le cas d’un serveur de médiation distinct traitant un homologue de serveur de médiation de passerelle PSTN et un homologue de serveur de médiation de PBX, le comportement suivant sera observé :
    
      - Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PSTN à un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel n’est pas autorisé à empêcher le contournement de téléphone PSTN.
    
      - Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PBX dans le même site (site 1) vers un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel est autorisé, car il n’est pas soumis à un contournement de numéro de téléphone PSTN potentiel. ant.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Fonctionnalités non prises en charge par l’application de conférence de routage basée sur l’emplacement

Les fonctionnalités suivantes ne sont pas prises en charge par l’application de conférence de routage basée sur l’emplacement :

  - Conférence rendez-vous. Le routage géodépendant ne peut pas être appliqué pour les conférences rendez-vous. Toute demande d’accès à une conférence donnée n’est pas limitée par le routage géodépendant même si l’organisateur de la Conférence est un utilisateur Lync activé pour le routage géodépendant.

  - Il est recommandé de ne pas mettre en service les numéros d’accès aux conférences dans les régions où des restrictions de routage géodépendant doivent être appliquées.

</div>

</div>

<span> </span>

</div>

</div>

</div>

