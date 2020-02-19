---
title: Contrôle d’admission des appels avec une passerelle PSTN ou un PBX tiers
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
ms.openlocfilehash: 85a35bafa8f3311d19633f044ec4bde0437993db
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>Contrôle d’admission des appels dans Lync Server 2013 avec une passerelle PSTN ou un PBX tiers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Cette rubrique décrit des exemples de déploiement du contrôle d’admission des appels sur la liaison entre l’interface de la passerelle du serveur de médiation et une passerelle RTC (réseau téléphonique commuté) ou un PBX (Private Branch Exchange) tiers.

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Cas 1 : contrôle d’admission des appels entre le serveur de médiation et une passerelle PSTN

Le contrôle d’admission des appels peut être déployé sur la liaison de réseau étendu depuis l’interface de passerelle du serveur de médiation vers une passerelle PSTN ou PBX tierce.

**Cas 1 : contrôle d’admission des appels entre le serveur de médiation et une passerelle PSTN**

![Cas 1 : CAC entre la passerelle PSTN de serveur de médiation](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Cas 1 : CAC entre la passerelle PSTN de serveur de médiation")

Dans cet exemple, le contrôle d’admission des appels est appliqué entre le serveur de médiation et une passerelle PSTN. Si un utilisateur de client Lync sur le site réseau 1 passe un appel RTC via la passerelle PSTN dans le site réseau 2, le média transite par la liaison WAN. Par conséquent, deux vérifications de contrôle d’admission des appels sont effectuées pour chaque session PSTN :

  - Entre l’application cliente Lync et le serveur de médiation

  - Entre le serveur de médiation et la passerelle PSTN

Cela fonctionne pour les appels RTC entrants vers un client dans le site réseau 1 et pour les appels RTC sortants provenant d’une application cliente dans le site réseau 1.

<div>


> [!NOTE]
> Assurez-vous que le sous-réseau IP auquel appartient la passerelle PSTN est configuré et associé au site réseau 2.<BR>Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation est configuré et associé au site réseau 1.<BR>Pour plus d’informations, consultez <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">la rubrique associer un sous-réseau à un site réseau dans Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Cas 2 : CAC entre le serveur de médiation et un PBX tiers avec point de terminaison multimédia

Cette configuration est semblable au cas 1. Dans les deux cas, le serveur de médiation sait quel périphérique termine le média à l’extrémité opposée de la liaison de réseau étendu, et l’adresse IP de la passerelle PSTN ou du PBX avec le point de terminaison multimédia (MTP) est configurée sur le serveur de médiation comme tronçon suivant.

**Cas 2 : CAC entre le serveur de médiation et un PBX tiers avec MTP**

![Cas 2 : CAC entre PBX de serveur de médiation avec MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Cas 2 : CAC entre PBX de serveur de médiation avec MTP")

Dans cet exemple, CAC est appliqué entre le serveur de médiation et le PBX/MTP. Si un utilisateur client Lync sur le site réseau 1 passe un appel RTC via le PBX/MTP situé dans le site réseau 2, le média transite par la liaison de réseau étendu (WAN). Par conséquent, pour chaque session RTC, deux vérifications de contrôle d’admission des appels sont effectuées :

  - Entre l’application cliente Lync et le serveur de médiation

  - Entre le serveur de médiation et le PBX/MTP

Cela fonctionne pour les appels RTC entrants vers un client dans le site réseau 1 et les appels RTC sortants provenant d’un client dans le site réseau 1.

<div>


> [!NOTE]
> Assurez-vous que le sous-réseau IP auquel appartient le MTP est configuré et associé au site réseau 2.<BR>Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation est configuré et associé au site réseau 1.<BR>Pour plus d’informations, consultez <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">la rubrique associer un sous-réseau à un site réseau dans Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Cas 3 : CAC entre le serveur de médiation et un système PBX tiers sans point de terminaison multimédia

Le cas 3 est légèrement différent des deux premiers cas. S’il n’y a pas de MTP sur le PBX tiers, pour une demande de session sortante adressée au PBX tiers, le serveur de médiation ne sait pas où le média se termine dans la limite du PBX. Dans ce cas, le média est directement acheminé entre le serveur de médiation et le périphérique de point de terminaison tiers.

**Cas 3 : CAC entre le serveur de médiation et un PBX tiers sans MTP**

![Cas 3 : CAC entre PBX de serveur de médiation sans MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Cas 3 : CAC entre PBX de serveur de médiation sans MTP")

Dans cet exemple, si un utilisateur de client Lync sur le site réseau 1 passe un appel à un utilisateur via le PBX, le serveur de médiation peut effectuer des vérifications CAC uniquement sur la jambe proxy (entre l’application cliente Lync et le serveur de médiation). Étant donné que le serveur de médiation n’a pas d’informations sur l’appareil de point de terminaison pendant que la session est demandée, les vérifications du contrôle d’admission des appels ne peuvent pas être effectuées sur la liaison de réseau étendu (entre le serveur de médiation et le point de terminaison tiers) avant l’établissement de l’appel. Une fois la session établie, le serveur de médiation facilite la comptabilisation de la bande passante utilisée sur la jonction.

Pour les appels qui proviennent du point de terminaison tiers, les informations relatives à ce périphérique de point de terminaison sont disponibles au moment de la demande de session et la vérification du contrôle d’admission des appels peut être effectuée sur les deux côtés du serveur de médiation.

<div>


> [!NOTE]
> Assurez-vous que le sous-réseau IP auquel appartiennent les périphériques de point de terminaison est configuré et associé au site réseau 2.<BR>Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation est configuré et associé au site réseau 1.<BR>Pour plus d’informations, consultez <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">la rubrique associer un sous-réseau à un site réseau dans Lync Server 2013</A>.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

