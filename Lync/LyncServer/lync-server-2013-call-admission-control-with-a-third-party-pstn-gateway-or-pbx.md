---
title: Contrôle d’admisson des appels avec une passerelle RTC ou un système PBX tiers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09aae207844fed12c840918a533fb181ca36634e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>Contrôle d’admisson des appels dans Lync Server 2013 avec une passerelle RTC ou un système PBX tiers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Cette rubrique donne des exemples de déploiement du contrôle d’admission des appels sur la liaison entre l’interface de la passerelle du serveur de médiation et une passerelle RTC (réseau téléphonique commuté) ou un système PBX (Private Branch Exchange) tiers.

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Exemple 1 : Contrôle d’admission des appels entre le serveur de médiation et une passerelle RTC

Le contrôle d’admission des appels peut être déployé sur une liaison de réseau étendu depuis l’interface de la passerelle du serveur de médiation vers une passerelle RTC ou un système PBX tiers.

**Exemple 1 : Contrôle d’admission des appels entre le serveur de médiation et une passerelle RTC**

![Cas 1 : CAC entre passerelle PSTN de serveur de médiation](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Cas 1 : CAC entre passerelle PSTN de serveur de médiation")

Dans cet exemple, la fonction CAC est appliquée entre le serveur de médiation et une passerelle PSTN. Si un utilisateur du client Lync au niveau du site réseau 1 passe un appel RTC par le biais de la passerelle RTC dans le site réseau 2, le média passe par la liaison WAN. Par conséquent, deux vérifications de contrôle d’admission des appels sont effectuées pour chaque session RTC :

  - Entre l’application cliente Lync et le serveur de médiation

  - Entre le serveur de médiation et la passerelle RTC

Cet exemple s’applique aux appels RTC entrants vers un client dans Site réseau 1, ainsi qu’aux appels RTC sortants issus d’une application cliente dans Site réseau n1.

<div>


> [!NOTE]
> Assurez-vous que le sous-réseau IP auquel appartient la passerelle RTC est configuré et associé au Site réseau 2.<BR>Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation, et qu’il est associé au site réseau 1.<BR>Pour plus d’informations, consultez <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associer un sous-réseau à un site réseau dans Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Cas 2 : CAC entre le serveur de médiation et un PBX tiers avec point de terminaison du média

Cette configuration est semblable à l’exemple 1. Dans les deux cas, le serveur de médiation détermine quel appareil arrête les éléments multimédias à l’extrémité opposée du lien réseau étendu, et l’adresse IP de la passerelle PSTN ou du PBX avec point de terminaison de média (MTP) est configurée sur le serveur de médiation comme tronçon suivant.

**Exemple 2 : Contrôle d’admission des appels entre le serveur de médiation et un système PBX tiers avec point de terminaison multimédia (MTP)**

![Cas 2 : CAC entre PBX de serveur de médiation avec MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Cas 2 : CAC entre PBX de serveur de médiation avec MTP")

Dans cet exemple, le CAC est appliqué entre le serveur de médiation et le PBX/MTP. Si un utilisateur du client Lync sur le site réseau 1 effectue un appel RTC par le biais du PBX/MTP situé dans le site réseau 2, le média passe par la liaison WAN. Par conséquent, pour chaque session RTC, deux vérifications de contrôle d’admission des appels sont effectuées :

  - Entre l’application cliente Lync et le serveur de médiation

  - Entre le serveur de médiation et le PBX/MTP

Cet exemple s’applique aux appels RTC entrants vers un client dans Site réseau n° 1, ainsi qu’aux appels RTC sortants issus d’un client dans Site réseau n° 1.

<div>


> [!NOTE]
> Assurez-vous que le sous-réseau IP auquel appartient le MTP est configuré et associé au Site réseau 2.<BR>Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation, et qu’il est associé au site réseau 1.<BR>Pour plus d’informations, consultez <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associer un sous-réseau à un site réseau dans Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Cas 3 : CAC entre le serveur de médiation et un PBX tiers sans point de terminaison multimédia

L’exemple 3 est légèrement différent des deux premiers. S’il n’y a pas de MTP sur le système PBX tiers, pour une demande de session sortante pour le PBX tiers, le serveur de médiation ne connaît pas l’endroit où le contenu multimédia sera arrêté dans la limite du PBX. Dans ce cas, les éléments multimédias sont acheminés directement entre le serveur de médiation et l’appareil de point de terminaison tiers.

**Exemple 3 : Contrôle d’admission des appels entre le serveur de médiation et un système PBX tiers sans point de terminaison multimédia (MTP)**

![Cas 3 : CAC entre PBX de serveur de médiation sans MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Cas 3 : CAC entre PBX de serveur de médiation sans MTP")

Dans cet exemple, si un utilisateur du client Lync au niveau du site réseau 1 place un appel vers un utilisateur via le système PBX, le serveur de médiation est en mesure d’effectuer des vérifications CAC uniquement sur le tronçon proxy (entre l’application cliente et le serveur de médiation Lync). Dans la mesure où le serveur de médiation ne contient pas d’informations sur l’appareil de point de terminaison lors de la demande de la session, les vérifications CAC ne peuvent pas être effectuées sur la liaison réseau étendu (entre le serveur de médiation et le point de terminaison tiers) avant l’établissement. Toutefois, une fois la session établie, le serveur de médiation facilite le contrôle de la bande passante utilisée sur le Trunk.

Pour les appels provenant du point de terminaison tiers, les informations relatives à cet appareil de point de terminaison sont disponibles au moment de la demande de session et de la vérification du CAC peut être effectuée sur les deux côtés du serveur de médiation.

<div>


> [!NOTE]
> Assurez-vous que le sous-réseau IP auquel appartiennent les périphériques de point de terminaison est configuré et associé au Site réseau 2.<BR>Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation, et qu’il est associé au site réseau 1.<BR>Pour plus d’informations, consultez <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associer un sous-réseau à un site réseau dans Lync Server 2013</A>.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

