---
title: Sites Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3e420a1fad89692133df4422138b43d4d7210e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Sites Lync Server pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-16_

Dans Lync Server, vous définissez des *sites* sur votre réseau qui contiennent des composants Lync Server. Un site désigne un ensemble d’ordinateurs connectés comme il se doit par un réseau haut débit à faible latence, par exemple, un réseau local unique (LAN) ou bien deux réseaux connectés via un réseau haut débit à fibre optique. Notez que les sites Lync Server constituent un concept distinct des sites des services de domaine Active Directory et des sites Microsoft Exchange Server. Vos sites Lync Server n’ont pas besoin de correspondre à vos sites Active Directory.

<div>

## <a name="site-types"></a>Types de site

Chaque site est soit un *site central*, qui contient au moins un pool frontal ou un serveur Standard Edition, soit un *site de succursale*. Chaque site de succursale est associé à un site central exactement et les utilisateurs du site de succursale bénéficient de la plupart de leurs fonctionnalités Lync Server à partir des serveurs sur le site central associé.

Chaque site de succursale contient l’un des éléments suivants :

  - *Survivable Branch Appliance (SBA)*, qui est un serveur lame standard avec un serveur d’inscriptions Lync Server et un serveur de médiation s’exécutant sur Windows Server. Le Survivable Branch Appliance contient également une passerelle RTC (réseau téléphonique commuté). Le Survivable Branch Appliance est conçu pour les sites de succursale comportant entre 25 et 1000 utilisateurs.

  - Un *serveur Survivable Branch Server (SBS)*, qui est un serveur exécutant Windows Server qui répond à la configuration matérielle requise et sur lequel le logiciel de serveur d’inscriptions et de médiation Lync Server est installé. Il doit se connecter à une passerelle PSTN ou à une jonction SIP à un fournisseur de service téléphonique. Le serveur Survivable Branch Server est conçu pour les sites de succursale comptant entre 1 000 et 5 000 utilisateurs.

  - Une passerelle PSTN et, éventuellement, un *serveur de médiation*. Pour plus d’informations sur ce rôle et sur d’autres rôles serveur, voir [rôles serveur dans Lync server 2013](lync-server-2013-server-roles.md).

Une succursale avec une liaison de réseau étendu (WAN) résistante vers un site central peut utiliser la troisième option, à savoir une passerelle PSTN et éventuellement un serveur de médiation. Les sites de succursale avec des liens moins résistants doivent utiliser un Survivable Branch Appliance ou un serveur Survivable Branch Server, qui assure la résilience en cas de défaillance du réseau étendu. Par exemple, dans un site disposant d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server déployé, les utilisateurs peuvent toujours effectuer et recevoir des appels voix entreprise si le réseau étendu qui connecte le site de succursale au site central est inactif. Pour plus d’informations sur le Survivable Branch appliance, le serveur Survivable Branch Server et la résilience, voir [Planning for Enterprise Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) dans la documentation de planification.

</div>

<div>

## <a name="site-topologies"></a>Topologies de site

Le déploiement doit comprendre au moins un site central et peut inclure aucun ou plusieurs sites de succursale. Chaque site de succursale est affilié à un site central. Le site central fournit les services Lync Server au site de succursale qui ne sont pas hébergés localement sur le site de succursale, comme la présence et la Conférence.

Si vous disposez de plusieurs sites, vous pouvez regrouper par paires les pools frontaux sur différents sites pour activer les fonctionnalités de récupération d’urgence. Pour plus d’informations, consultez la rubrique [prise en charge de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Rôles serveur dans Lync Server 2013](lync-server-2013-server-roles.md)  
[Prise en charge de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Planification de la résistance voix entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

