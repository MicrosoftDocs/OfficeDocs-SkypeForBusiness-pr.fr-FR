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
ms.openlocfilehash: 3c91ea4368d96e6a558a25eda86d163e4ced4cb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Recommandations en matière de déploiement pour le serveur de médiation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-12_

Cette rubrique décrit les recommandations en matière de planification pour le déploiement de médiation Server. Après avoir examiné ces recommandations, nous vous conseillons d’utiliser l’outil de planification pour créer et afficher des topologies de remplacement possibles, qui peuvent servir de modèles pour la topologie de déploiement finale que vous décidez de déployer.

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>Serveur de médiation autonome ou colocalisé

Le serveur de médiation est par défaut colocalisé sur le serveur principal ou le serveur frontal standard dans un pool frontal de sites centraux. Le nombre d’appels RTC (réseau téléphonique commuté) pouvant être gérés et le nombre d’ordinateurs requis dans le pool dépendront des éléments suivants :

  - Nombre d’homologues de passerelle que le pool de serveurs de médiation contrôle

  - des périodes de trafic aux heures de pointe via ces passerelles ;

  - Pourcentage d’appels dont le média ignore le serveur de médiation

Lors de la planification, veillez à prendre en compte les exigences de traitement multimédia pour les appels RTC et les conférences A/V qui ne sont pas configurées pour le recours au contenu multimédia, ainsi que le traitement requis pour gérer les interactions de signalisation en fonction du nombre d’appels vers des heures de disponibilité qui doivent être pris en charge. S’il n’y a pas assez d’UC, vous devez déployer un pool autonome de serveurs de médiation. les passerelles RTC, IP PBX et SBCs doivent être divisées en sous-ensembles contrôlés par les serveurs de médiation colocalisés dans un pool et les serveurs de médiation autonomes dans un ou plusieurs pools autonomes.

Si vous avez déployé des passerelles RTC, des PBX IP ou des contrôleurs de frontière de session (SBCs) qui ne prennent pas en charge les fonctionnalités appropriées pour interagir avec un pool de serveurs de médiation, y compris les suivants, ils devront être associés à un pool autonome composé de d’un serveur de médiation unique :

  - Effectuer l’équilibrage de charge DNS (Layer Domain Name System) entre les serveurs de médiation d’un pool (ou sinon, le trafic est uniformément routé vers tous les serveurs de médiation d’un pool)

  - Accepter le trafic de n’importe quel serveur de médiation dans un pool

Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour déterminer si collocating du serveur de médiation avec votre pool frontal peut gérer le chargement. Si votre environnement ne peut pas répondre à ces exigences, vous devez déployer un pool de serveurs de médiation autonome.

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>Aspects relatifs au site central et aux sites de succursale

Les serveurs de médiation sur le site central peuvent être utilisés pour acheminer les appels pour les PBX IP ou les passerelles RTC dans les sites de succursale. Toutefois, si vous déployez des Trunks SIP, vous devez déployer un serveur de médiation sur le site où chaque Trunk est arrêté. Le fait de disposer d’un serveur de médiation au niveau du site central pour les appels pour un PBX IP ou une passerelle RTC sur un site de succursale ne nécessite pas l’utilisation de la fonctionnalité de contournement de média. Toutefois, si vous pouvez activer la dérivation multimédia, cela réduit la latence du chemin multimédia et, par conséquent, entraîne une meilleure qualité multimédia, car le chemin multimédia n’est plus nécessaire pour suivre le chemin d’accès de signalisation. La déviation du trafic multimédia réduira également la charge de traitement sur le pool.

<div>


> [!NOTE]  
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC. Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco. La dérivation de média est uniquement prise en charge avec les produits et les versions indiqués sur le programme d’interopérabilité d’ouverture de communications unifiées-Lync Server à <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.



</div>

Si la résilience du site de succursale est requise, il est nécessaire d’avoir une branche ou une combinaison d’un serveur frontal, d’un serveur de médiation et d’une passerelle dans le site de succursale. (L’hypothèse de la résilience du site de succursale est que la présence et les conférences ne sont pas résilientes sur le site.) Pour obtenir des instructions sur la planification du site de succursale pour les appels vocaux, voir [planification de la résilience vocale dans Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

S’il s’agit d’interactions avec un PBX IP, si ce n’est 3960 pas le cas, vous pouvez découper les premiers mots du message d’accueil pour les appels entrants du PBX IP vers les points de terminaison de Lync. Ce comportement peut être plus sérieux si un serveur de médiation sur un site central effectue le routage des appels pour un PBX IP à l’endroit où l’itinéraire se termine sur un site de succursale, car une plus grande période est nécessaire pour que le signalement s’exécute. Si vous subissez ce comportement, le déploiement d’un serveur de médiation sur le site de la succursale est le seul moyen de réduire l’écrêtage des premiers mots.

Enfin, si votre site central possède un PBX TDM ou si votre PBX IP n’élimine pas la nécessité d’une passerelle RTC, vous devez déployer une passerelle sur l’itinéraire d’appel connexion du serveur de médiation et du PBX.

<div>


> [!NOTE]  
> Pour améliorer les performances multimédias d’un serveur de médiation autonome, activez RSS (Receive-Side Scaling) sur les cartes réseau de ces serveurs. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, consultez la section « améliorations apportées à l’échelle de <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>réception dans Windows Server ». Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

