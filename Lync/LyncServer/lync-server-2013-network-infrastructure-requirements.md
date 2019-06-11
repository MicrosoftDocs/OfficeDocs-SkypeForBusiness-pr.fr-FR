---
title: Configurations requises pour l’infrastructure réseau de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc1f74705469bf3a024d84848942eae972e0a629
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Configuration requise pour l’infrastructure réseau pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-18_

La carte réseau de chaque serveur dans la topologie Lync Server 2013 doit prendre en charge au moins 1 Gbit/s (Gbps). En règle générale, vous devez connecter tous les rôles de serveur dans la topologie du serveur Lync à l’aide d’un réseau local (LAN) à faible latence et de haut débit. La taille du réseau local dépend de la taille de la topologie:

  - Dans les topologies Standard Edition, les serveurs doivent se trouver dans un réseau qui prend en charge Ethernet 1 Gbit ou équivalent.

  - Dans les topologies de pool frontal, la plupart des serveurs doivent se trouver dans un réseau qui prend en charge plus de 1 Gbit/s, en particulier lors de la prise en charge du partage d’applications et de conférences audio/vidéo (A/V).

Dans le cas de l'intégration au réseau téléphonique commuté (RTC ou, en anglais, PSTN pour Public Switched Telephone Network), vous pouvez utiliser les lignes T1/E1 ou les jonctions SIP.

<div>

## <a name="audiovideo-network-requirements"></a>Configuration requise du réseau audio/vidéo

La configuration réseau requise pour les appels audio/vidéo (A/V) dans un déploiement Lync Server inclut les éléments suivants:

  - Si vous déployez un serveur Edge unique ou un pool Edge à l’aide de l’équilibrage de charge DNS, vous pouvez configurer le pare-feu externe en tant que NAT. Vous ne pouvez pas configurer le pare-feu interne en tant que NAT. Pour plus d’informations sur ces exigences, voir [déterminer la configuration requise pour le pare-feu A/V et la configuration de port pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) dans la documentation de planification.
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous disposez d’un pool Edge et que vous utilisez un dispositif d’équilibrage de la charge matérielle, vous devez utiliser des adresses IP publiques sur chacun des serveurs de périphérie et vous ne pouvez pas utiliser la traduction d’adresses réseau pour les serveurs ou le pool sur votre appareil NAT (par exemple, le pare-feu ou un autre appareil d’infrastructure qui aurait pour tar Inbou trafic ND ou sortant). Pour plus d’informations, reportez-vous à la section Résumé de port-bordure consolidée mise en plan <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">avec des équilibreurs de charge matérielle dans Lync Server 2013</A> dans la documentation relative à l’accès des utilisateurs externes.

    
    </div>

  - Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure.

  - Si vous utilisez le protocole IPSec, nous vous recommandons de le désactiver sur les plages de ports utilisées pour le trafic A/V. Pour plus d’informations, reportez-vous à la section [exceptions IPSec dans Lync Server 2013](lync-server-2013-ipsec-exceptions.md) dans la documentation de planification.

Pour garantir une qualité multimédia optimale, procédez comme suit:

  - Mise en service de vos liens réseau pour prendre en charge le débit de 65 kilobits par seconde (kbps) par flux audio et 500 kbps par flux vidéo, s’il est activé, pendant les périodes d’utilisation maximale. Une session audio ou vidéo bidirectionnelle est composée de deux flux.

  - Pour gérer les pics inattendus du trafic au-dessus de ce niveau et augmenter l’utilisation au fil du temps, les points de terminaison Lync Server Media peuvent s’adapter à des conditions de réseau variables et prendre en charge des charges de trois fois le débit (voir le paragraphe précédent) pour les appels audio et vidéo, tout en restant conservation de la qualité acceptable. Toutefois, ne supposez pas que cette capacité d’adaptation prend en charge un réseau sous-approvisionné. Dans un réseau sous-approvisionné, la capacité des points de terminaison Lync Server Media d’une manière dynamique avec des conditions de réseau variables (par exemple, une perte de paquets de grande durée temporaire) est réduite.

  - Pour les liens réseau dans lesquels la mise en service est extrêmement onéreuse et difficile, il est possible que vous deviez envisager la mise en service pour un volume inférieur de trafic. Dans ce scénario, l’élasticité des points de terminaison de Lync Server Media absorbe la différence entre le volume de trafic et le niveau de trafic de pointe, au coût d’une diminution de la qualité de la voix. Par ailleurs, il y a une diminution de l’impasse de la hauteur pour absorber les crêtes soudaines du trafic.

  - Pour les liens qui ne peuvent pas être configurés correctement en courte durée (par exemple, un site avec de très mauvaises liaisons WAN), envisagez de désactiver la vidéo pour certains utilisateurs.

  - Mise en service de votre réseau pour garantir un délai de bout en bout maximal (latence) de 150 millisecondes (MS) en faible charge. La latence correspond à une déficience du réseau qui empêche les composants multimédias de Lync Server de réduire, et il est important de rechercher et d’éliminer les points faibles.

  - Pour les serveurs exécutant un logiciel antivirus, incluez tous les serveurs exécutant Lync Server dans la liste des exceptions afin de fournir des performances et une qualité audio optimales.

</div>

<div>

## <a name="conferencing-network-requirements"></a>Configuration réseau requise

La bande passante utilisée pour télécharger le contenu de la Conférence à partir du serveur IIS (Internet Information Services) dépend de la taille du contenu chargé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

