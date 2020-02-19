---
title: Configuration requise pour l’infrastructure réseau de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea383a77ff8d6089e2a01d7fb00df434f6d805e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Configuration requise pour l’infrastructure réseau pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

La carte réseau de chaque serveur de la topologie Lync Server 2013 doit prendre en charge au moins 1 Gigabit par seconde (Gbits/s). En général, vous devez connecter tous les rôles serveur au sein de la topologie Lync Server à l’aide d’une faible latence et d’un réseau local à bande passante élevée (LAN). La taille du réseau local dépend de la taille de la topologie :

  - Dans les topologies Standard Edition, les serveurs doivent se trouver dans un réseau prenant en charge 1 Gbits/s ou équivalent.

  - Dans les topologies de pool frontal, la plupart des serveurs doivent se trouver dans un réseau prenant en charge plus de 1 Gbits/s, en particulier lors de la prise en charge de la conférence audio/vidéo (A/V) et du partage d’applications.

Pour l’intégration d’un réseau téléphonique commuté (PSTN), vous pouvez intégrer à l’aide de lignes T1/E1 ou de jonctions SIP.

<div>

## <a name="audiovideo-network-requirements"></a>Configuration requise pour le réseau audio/vidéo

La configuration réseau requise pour l’audio/vidéo (A/V) dans un déploiement Lync Server inclut les éléments suivants :

  - Si vous déployez un serveur Edge unique ou un pool de serveurs Edge à l’aide de l’équilibrage de charge DNS, vous pouvez configurer le pare-feu externe en tant que NAT. Vous ne pouvez pas configurer le pare-feu interne en tant que NAT. Pour plus d’informations sur ces conditions requises, voir [determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) dans la documentation de planification.
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous avez un pool de serveurs Edge et que vous utilisez un programme d’équilibrage de la charge matérielle, vous devez utiliser des adresses IP publiques sur chaque serveur Edge et vous ne pouvez pas utiliser la traduction d’adresses réseau pour les serveurs ou le pool sur votre périphérique NAT (par exemple, le pare-feu ou un autre périphérique d’infrastructure qui serait Inbou trafic ND ou trafic sortant). Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Résumé des ports-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</A> dans la documentation sur la planification de l’accès des utilisateurs externes.

    
    </div>

  - Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure.

  - Si vous utilisez la sécurité du protocole Internet (IPsec), nous vous recommandons de désactiver IPsec sur les plages de ports utilisées pour le trafic A/V. Pour plus d’informations, reportez-vous à la rubrique [IPSec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) dans la documentation de planification.

Pour garantir une qualité des médias optimale, procédez comme suit :

  - Configurez vos liens réseau pour qu’ils prennent en charge un débit de 65 kilobits par seconde (Kbits/s) par flux audio et 500 Kbits/s par flux vidéo, s’ils sont activés, pendant les périodes d’utilisation maximale. Une session audio ou vidéo bidirectionnelle est composée de deux flux.

  - Pour faire face à des pics inattendus dans le trafic au-dessus de ce niveau et une utilisation accrue au fil du temps, les points de terminaison Lync Server Media peuvent s’adapter à des conditions de réseau variables et prendre en charge des charges de trois fois le débit (voir paragraphe précédent) pour l’audio et la vidéo, tout en restant conservation de la qualité acceptable. Toutefois, ne partez pas du principe que cette adaptabilité prend en charge un réseau sous-configuré. Dans un réseau sous-configuré, la capacité des points de terminaison multimédia Lync Server à traiter dynamiquement des conditions réseau variables (par exemple, une perte de paquets élevée temporaire) est réduite.

  - Pour les liaisons réseau où la mise en service est extrêmement coûteuse et difficile, vous devrez peut-être envisager la mise en service d’un volume de trafic inférieur. Dans ce scénario, l’élasticité des points de terminaison de Lync Server Media absorbe la différence entre le volume de trafic et le niveau de trafic maximal, au prix d’une réduction de la qualité de la voix. De plus, il y a une diminution de la hauteur suffisante autrement pour absorber les pics soudains dans le trafic.

  - Pour les liens qui ne peuvent pas être correctement configurés à court terme (par exemple, un site avec des liaisons de réseau étendu très médiocres), envisagez de désactiver la vidéo pour certains utilisateurs.

  - Approvisionnez votre réseau pour garantir un retard de bout en bout de 150 millisecondes (MS) en dessous de la charge maximale. La latence est l’une des altérations de réseau que les composants multimédias de Lync Server ne peuvent pas réduire, et il est important de trouver et d’éliminer les points faibles.

  - Pour les serveurs exécutant un logiciel antivirus, incluez tous les serveurs exécutant Lync Server dans la liste des exceptions afin de fournir des performances et une qualité audio optimales.

</div>

<div>

## <a name="conferencing-network-requirements"></a>Configuration requise pour le réseau de conférence

La bande passante utilisée pour télécharger le contenu de conférence à partir du serveur IIS (Internet Information Services) dépend de la taille du contenu téléchargé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

