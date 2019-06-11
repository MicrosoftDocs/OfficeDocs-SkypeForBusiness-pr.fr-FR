---
title: 'Lync Server 2013: configuration requise pour le routage sur site pour les conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 925b71497012d7e6ed9c19042a079a7b30630c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configuration requise pour le routage sur site pour les conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-07-19_

Voici les exigences requises pour l’installation et la configuration de l’application de conférence de routage basée sur l’emplacement:

  - La mise à jour cumulative 2 Lync Server 2013 doit être déployée sur tous les serveurs ou pools de votre topologie.

<div>


> [!NOTE]  
> Si une mise à jour cumulative 2 ou une version ultérieure de Lync Server 2013 n’est pas installée sur un serveur ou un pool Lync dans votre topologie, il n’est pas possible de garantir l’exécution du routage de réunion Lync dans l’emplacement.



</div>

  - Le routage de géolocalisation Lync Server 2013 est une configuration requise pour l’application de conférence de routage basée sur l’emplacement. Pour plus d’informations sur la configuration du routage de l’emplacement de Lync Server 2013, voir [configuration du routage en fonction](lync-server-2013-configuring-location-based-routing.md)de l’emplacement.

  - Les exigences de l’application conférences de routage de géolocalisation sont les mêmes que celles requises pour le routage en fonction de l’emplacement de Lync Server 2013. Pour plus d’informations, reportez-vous à la rubrique [planification pour le routage sur site](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Serveurs pris en charge

L’application de conférence de routage basée sur l’emplacement nécessite le déploiement de la mise à jour cumulative 2 de Lync Server 2013 sur toutes les listes frontales et les serveurs Standard Edition dans votre topologie. Si la mise à jour cumulative 2 de Lync Server 2013 n’est pas installée sur certains serveurs Lync dans votre topologie, les restrictions de routage basées sur les emplacements ne peuvent pas être entièrement appliquées lors des réunions Lync et des transferts d’appel.

Le tableau suivant identifie la combinaison de rôles et de versions du serveur prenant en charge le routage par emplacement.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Version de pool frontal</p></td>
<td><p>Version de serveur de médiation</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="odd">
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Mise à jour cumulative 1 de Lync Server 2013</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative 1 de Lync Server 2013</p></td>
<td><p>Indifférente</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>Indifférente</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Indifférente</p></td>
<td><p>Non</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>Clients pris en charge

Les clients Lync prenant en charge le routage par emplacement des réunions Lync sont les mêmes que ceux prenant en charge le routage sur l’emplacement Lync Server 2013. Pour plus d’informations, consultez [prise en charge des clients et du serveur pour le routage](lync-server-2013-client-and-server-support-for-location-based-routing.md)géolocalisation.

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Configuration requise pour le serveur de médiation pour les transferts d’appels

L’application de conférence de routage basée sur l’emplacement nécessite le déploiement de serveurs de médiation autonomes pour appliquer les restrictions de routage basées sur les emplacements aux transferts d’appel consultatif.

Pour appliquer le routage des appels de consultation selon l’emplacement, le serveur de médiation doit être associé à un seul homologue du serveur de médiation (par exemple, PBX, passerelle SIP, etc.) dans les régions réseau où le routage de l’emplacement est requis. Si d’autres homologues du serveur de médiation sont déployés dans la même région réseau, l’homologue du serveur de médiation doit être associé à un serveur de médiation différent. Cette obligation est détaillée comme suit:

  - Serveur de médiation unique par plusieurs homologues du serveur de médiation lorsque le transfert d’un appel consultatif est acheminé vers un homologue du serveur de médiation par le biais d’un serveur de médiation configuré avec plusieurs ISL SIP pour plusieurs homologues (PBX et passerelles), le Conseil le transfert d’appel est bloqué pour empêcher le contournement du protocole RTC si le transfert d’appel est autorisé par le biais de lignes SIP, mais rejeté par d’autres ISL SIP.
    
    Par exemple, dans le cas d’un serveur de médiation unique qui dessert un homologue du serveur de médiation de la passerelle RTC et un homologue du serveur de médiation PBX, le comportement suivant est observé:
    
      - Lorsqu’un utilisateur Lync à partir d’un site donné (par exemple, le site 1) tente de transférer un appel avec un point de terminaison RTC à un utilisateur Lync à partir d’un site différent (par exemple, site 2) par le biais du transfert de consultation, l’appel n’est pas autorisé à éviter le contournement du numéro RTC.
    
      - Lorsqu’un utilisateur Lync à partir d’un site donné (par exemple, le site 1) tente de transférer un appel avec un point de terminaison PBX au sein d’un même site (site 1) pour un utilisateur Lync à partir d’un site différent (par exemple, site 2) par le biais d’un virement RTC potentiel, l’appel est rejeté même l en contournement.

  - Séparation des serveurs de médiation par le pair du serveur de médiation
    
    Lorsque le transfert consultatif est ciblé auprès d’un homologue de serveur de médiation, le transfert de la consultation est évalué par rapport à l’homologue du serveur de médiation unique desservi par le serveur de médiation. L’appel sera interdit ou autorisé en fonction de son potentiel dans le cadre du contournement du numéro RTC, quels que soient les autres homologues du site dans le cadre de leur service par des serveurs de médiation distincts.
    
    Par exemple, dans le cas d’un serveur de médiation distinct prenant en service un homologue de serveur de médiation de passerelle RTC et un homologue de serveur de médiation PBX, le comportement suivant est observé:
    
      - Lorsqu’un utilisateur Lync à partir d’un site donné (par exemple, le site 1) tente de transférer un appel avec un point de terminaison RTC à un utilisateur Lync à partir d’un site différent (par exemple, site 2) par le biais du transfert de consultation, l’appel n’est pas autorisé à éviter le contournement du numéro RTC.
    
      - Lorsqu’un utilisateur Lync à partir d’un site donné (par exemple, le site 1) tente de transférer un appel à l’aide d’un point de terminaison PBX dans le même site (site 1) pour un utilisateur Lync à partir d’un site différent (par exemple, site 2) par le biais du transfert de consultation, l’appel est autorisé à ne pas occasionner de contournement assurance.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Fonctionnalités non prises en charge par l’application de conférence de routage basée sur l’emplacement

Les fonctionnalités suivantes ne sont pas prises en charge par l’application de conférence de routage basée sur l’emplacement:

  - Conférence rendez-vous. Le routage en fonction de l’emplacement ne peut pas être appliqué pour la Conférence rendez-vous. Toute demande d’accès à une conférence donnée n’est pas limitée par le routage de l’emplacement, même si l’organisateur de la Conférence est un utilisateur de Lync prenant en charge le routage de l’emplacement.

  - Nous vous conseillons de ne pas mettre en place des numéros d’accès aux conférences dans les régions dans lesquelles les restrictions de routage basées sur l’emplacement doivent être appliquées.

</div>

</div>

<span> </span>

</div>

</div>

</div>

