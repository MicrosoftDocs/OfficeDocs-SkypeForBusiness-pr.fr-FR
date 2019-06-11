---
title: Sites Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1843ac4256e71723abf59fa272155ced2010e72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Sites Lync Server pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-16_

Dans Lync Server, vous définissez des *sites* sur votre réseau qui contiennent des composants serveur Lync. Un site désigne un ensemble d’ordinateurs connectés comme il se doit par un réseau haut débit à faible latence, par exemple, un réseau local unique (LAN) ou bien deux réseaux connectés via un réseau haut débit à fibre optique. Notez que les sites serveur Lync constituent un concept distinct des sites services de domaine Active Directory et des sites Microsoft Exchange Server. Les sites de votre serveur Lync n’ont pas besoin de correspondre à vos sites Active Directory.

<div>

## <a name="site-types"></a>Types de sites

Chaque site est un *site central*contenant au moins un pool frontal ou un serveur Standard Edition Server ou un *site de succursale*. Chaque site de filiale est associé à un seul site central, et les utilisateurs du site de succursale obtiennent la plupart des fonctionnalités de Lync Server sur les serveurs du site central associé.

Chaque site de filiale contient l’une des options suivantes:

  - Un *appareil de branchement survivant (SBA)*, qui est un serveur de Blades standard avec un bureau d’enregistrement de serveurs Lync et un serveur de médiation exécuté sur Windows Server. L’unité de branchement Survivable comporte également une passerelle RTC (réseau téléphonique commuté). L’unité de branchement survivant est conçue pour les sites de succursale entre 25 et 1000 utilisateurs.

  - Un *serveur de succursales survivant (SBS)*, qui est un serveur exécutant Windows Server qui répond à la configuration matérielle requise, et sur lequel sont installés le logiciel serveur du Bureau d’enregistrement et de médiation de Lync Server. Il doit se connecter à une passerelle PSTN ou à une jonction SIP à un fournisseur de services téléphoniques. Le serveur de succursales survivant est conçu pour les sites de succursale entre les utilisateurs 1000 et 5000.

  - Passerelle RTC et, éventuellement, *serveur de médiation*. Pour plus d’informations sur ces rôles de serveur, voir [rôles de serveur dans Lync server 2013](lync-server-2013-server-roles.md).

Une succursale disposant d’une liaison réseau étendu (WAN) fiable vers un site central peut utiliser la troisième option: une passerelle RTC et éventuellement un serveur de médiation. Les sites de succursales dotés de liens moins résilients doivent utiliser un appareil de succursales ou un serveur de succursales Survivables, qui fournit la résilience en cas de panne du réseau étendu. Par exemple, dans le cas d’un site disposant d’une unité de succursale ou d’un serveur de succursale survivant, les utilisateurs peuvent quand même passer et recevoir des appels voix d’entreprise si le WAN qui connecte le site de la succursale au site central est arrêté. Pour plus d’informations sur l’appareil de succursale survivant, le serveur de succursales survivant et la résilience, voir [planification de la résilience vocale d’entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) dans la documentation de planification.

</div>

<div>

## <a name="site-topologies"></a>Topologies de site

Votre déploiement doit inclure au moins un site central et peut inclure zéro sur plusieurs sites de succursales. Chaque site de filiale est affilié à un site central. Le site central fournit les services serveur Lync au site de succursale qui ne sont pas hébergés localement sur le site de la succursale, tels que la présence et la Conférence.

Si vous disposez de plusieurs sites, vous pouvez associer les pools front-end sur différents sites pour activer la fonction de reprise après sinistre. Pour plus d’informations, voir [prise en charge de la haute disponibilité et de la reprise après sinistre dans Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Rôles serveur dans Lync Server 2013](lync-server-2013-server-roles.md)  
[Prise en charge de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Planification de la résistance Voix Entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

