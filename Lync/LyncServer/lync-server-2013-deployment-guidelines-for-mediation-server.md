---
title: 'Lync Server 2013 : instructions de déploiement pour le serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afcbfec56f4cfee3def2a0ef6deb82934534dbb2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Instructions de déploiement pour le serveur de médiation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-12_

Cette rubrique décrit les instructions de planification pour le déploiement d’un serveur de médiation. Après avoir examiné ces instructions, nous vous recommandons d’utiliser l’outil de planification pour créer et afficher d’autres topologies possibles, qui peuvent servir de modèles pour ce que la topologie personnalisée finale que vous décidez de déployer ressemblerait.

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>Serveur de médiation colocalisé ou autonome ?

Le serveur de médiation est colocalisé par défaut sur le serveur Standard Edition Server ou frontal dans un pool frontal sur les sites centraux. Le nombre d’appels RTC (réseau téléphonique commuté) pouvant être gérés et le nombre d’ordinateurs requis dans le pool dépendent des éléments suivants :

  - Le nombre d’homologues de passerelle contrôlés par le pool de serveurs de médiation ;

  - Les périodes de trafic à haut volume via ces passerelles ;

  - Le pourcentage d’appels qui sont des appels dont le média contournent le serveur de médiation.

Lors de la planification, veillez à prendre en compte les exigences en matière de traitement des médias pour les appels PSTN et les conférences A/V qui ne sont pas configurées pour la déviation du trafic multimédia, ainsi que le traitement nécessaire pour gérer les interactions de signalisation pour le nombre d’appels d’heure de pointe qui doivent être pris en charge. S’il n’y a pas assez d’UC, vous devez déployer un pool autonome de serveurs de médiation ; les passerelles PSTN, IP-PBX et SBCs doivent être divisées en sous-ensembles contrôlés par les serveurs de médiation colocalisés dans un pool et les serveurs de médiation autonomes dans un ou plusieurs pools autonomes.

Si vous avez déployé des passerelles PSTN, des systèmes IP-PBX ou des contrôleurs de frontière de session (SBC) qui ne prennent pas en charge les fonctionnalités correctes pour interagir avec un pool de serveurs de médiation, y compris les éléments suivants, ils devront être associés à un pool autonome composé d’un serveur de médiation unique :

  - Effectuer l’équilibrage de charge DNS (Domain Name System) de couche réseau entre les serveurs de médiation d’un pool (ou acheminer uniformément le trafic de manière uniforme vers tous les serveurs de médiation d’un pool)

  - Accepter le trafic d’un serveur de médiation dans un pool

Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour évaluer si colocaliser le serveur de médiation avec votre pool frontal peut gérer la charge. Si votre environnement ne remplit pas les conditions requises, vous devez alors déployer un pool de serveurs de médiation autonome.

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>Considérations relatives au site central et aux sites de succursale

Les serveurs de médiation sur le site central peuvent être utilisés pour router les appels sur les sites de succursale pour les passerelles PSTN ou les IP-PBX. Si vous déployez des jonctions SIP, cependant, vous devez déployer un serveur de médiation sur le site où s’arrête chaque jonction. Le fait de disposer d’un serveur de médiation sur le site central qui route les appels sur un site de succursale pour un IP/PBX ou une passerelle PSTN ne requiert pas l’utilisation du contournement de média. Toutefois, si vous pouvez l’activer, vous pourrez réduire la latence du chemin d’accès des médias et par conséquent, obtenir une qualité des médias améliorée du fait que le chemin d’accès des médias n’est plus nécessaire pour suivre le chemin de signalisation. Le contournement de média réduira également la charge de traitement sur le pool.

<div>


> [!NOTE]  
> Le contournement de média ne fonctionnera pas avec chaque passerelle PSTN, système IP-PBX et SBC. Microsoft a testé un ensemble de passerelles PSTN et de contrôleurs SBC avec des partenaires agréés et a effectué quelques tests avec les systèmes IP-PBX de Cisco. La déviation du trafic multimédia n’est prise en charge qu’avec les produits et les versions mentionnés dans le <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>programme d’interopérabilité ouvert pour les communications unifiées – Lync Server à.



</div>

Si la résistance de site de succursale est requise, un Survivable Branch Appliance ou une combinaison d’un serveur frontal, d’un serveur de médiation et d’une passerelle doit être déployé sur le site de succursale. (L’hypothèse de résistance de site de succursale est que la présence et la Conférence ne sont pas résilientes sur le site.) Pour obtenir des conseils sur la planification de site de succursale pour la voix, voir [Planning for Branch-site Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

Pour les interactions avec un système IP-PBX, si le système IP-PBX ne prend pas correctement en charge les interactions de médias précoces avec plusieurs boîtes de dialogue précoces et RFC 3960, il peut y avoir un découpage des premiers mots du message d’accueil pour les appels entrants depuis le PBX IP vers des points de terminaison Lync. Ce comportement peut s’aggraver si un serveur de médiation sur le site central achemine les appels pour un IP-PBX là où s’arrête l’itinéraire sur un site de succursale, car la signalisation a besoin de plus de temps pour se terminer. Si vous êtes confronté à ce problème, le déploiement d’un serveur de médiation sur le site de succursale constitue le seul moyen de réduire le découpage des premiers mots.

Pour finir, si votre site central comporte un TDM PBX ou que votre IP-PBX ne supprime pas le besoin d’une passerelle PSTN, vous devez alors déployer une passerelle sur l’itinéraire d’appel qui se connecte au serveur de médiation et au PBX.

<div>


> [!NOTE]  
> Pour améliorer les performances multimédias d’un serveur de médiation autonome, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau de ces serveurs. RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur. Pour plus d’informations, reportez-vous à la section « améliorations de l' <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>évolutivité côté réception dans Windows Server » à l’adresse. Pour plus d’informations sur l’activation de RSS, consultez la documentation de votre carte réseau.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

