---
title: 'Lync Server 2013 : paramètres réseau pour les fonctionnalités avancées de voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ce4983f7744158c9c9ff56cdfdde818fdc8e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Network settings for the advanced Enterprise Voice features in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-10_

Lync Server comporte trois fonctionnalités avancées de voix entreprise : contrôle d’admission des appels (CAC), services d’urgence (E9-1-1) et contournement de média. Ces fonctionnalités partagent certaines exigences de configuration pour les zones du réseau, les sites réseau et l’Association de chaque sous-réseau dans la topologie du serveur Lync avec un site réseau. Pour plus d’informations sur la planification du déploiement de ces fonctionnalités, voir :

  - [Planification du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)

  - [Planification des services d’urgence (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

Pour plus d’informations sur le déploiement de chacune de ces fonctionnalités, reportez-vous à la rubrique [déploiement de fonctionnalités avancées d’entreprise voix dans Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) dans la documentation de déploiement.

Cette rubrique fournit une vue d’ensemble des exigences de configuration communes aux trois fonctions vocales avancées d’entreprise.

<div>

## <a name="network-regions"></a>Régions réseau

Une région réseau est un concentrateur réseau ou un segment réseau principal utilisé uniquement dans la configuration du service Contrôle d’admission des appels, du système E9-1-1 et de la déviation du trafic multimédia.

<div>


> [!NOTE]  
> Les régions réseau ne sont pas identiques aux régions de conférence rendez-vous de Lync Server, qui sont nécessaires pour associer des numéros d’accès de conférence rendez-vous à un ou plusieurs plans de numérotation Lync Server. Pour plus d’informations sur les régions de conférence rendez-vous, consultez la rubrique Configuration requise pour les conférences rendez <A href="lync-server-2013-dial-in-conferencing-requirements.md">-vous dans Lync Server 2013</A> dans la documentation de planification.



</div>

Le CAC nécessite que toutes les régions du réseau aient un site central Lync Server associé qui gère le trafic multimédia au sein de la région (autrement dit, il prend des décisions basées sur les stratégies que vous avez configurées en ce qui concerne l’existence ou non d’une session audio ou vidéo en temps réel). être établi). Les sites Lync Server central ne représentent pas des emplacements géographiques, mais plutôt des groupes logiques de serveurs configurés en tant que pool ou ensemble de pools. Pour plus d’informations sur les sites centraux, voir [topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md) dans la documentation de planification. Voir également [topologies prises en charge dans Lync Server 2013](lync-server-2013-supported-topologies.md) dans la documentation sur la prise en charge.

Pour configurer une région réseau, vous pouvez utiliser l’onglet **régions** de la section **Configuration réseau** du panneau de configuration de Lync Server ou exécuter les applets de commande **New-CsNetworkRegion** ou **Set-CsNetworkRegion** Lync Server Management Shell. Pour obtenir des instructions, consultez la rubrique [créer ou modifier une région réseau dans Lync server 2013](lync-server-2013-create-or-modify-a-network-region.md) dans la documentation de déploiement, ou consultez la documentation Lync Server Management Shell.

Les mêmes définitions de zones réseau sont partagées par les trois fonctions vocales d’entreprise avancées. Si vous avez créé des régions réseau pour une fonctionnalité, vous n’avez pas besoin d’en créer de nouvelles pour les autres fonctionnalités. Cependant, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le système E9-1-1 (qui ne nécessite pas de site central associé) et que vous déployez ultérieurement le contrôle d’admission des appels, vous devez modifier chacune des définitions de région réseau pour spécifier un site central.

Pour associer un site central Lync Server à une région réseau, vous spécifiez le nom du site central, soit à l’aide de la section **Configuration réseau** du panneau de configuration de Lync Server, soit en exécutant les applets de commande **New-CsNetworkRegion** ou **Set-CsNetworkRegion** Lync Server Management Shell. Pour obtenir des instructions, consultez la rubrique [créer ou modifier une région réseau dans Lync server 2013](lync-server-2013-create-or-modify-a-network-region.md) dans la documentation de déploiement, ou consultez la documentation Lync Server Management Shell.

</div>

<div>

## <a name="network-sites"></a>Sites réseau

Un site réseau représente un emplacement géographique, tel qu’une succursale, un bureau régional ou un bureau principal. Chaque site réseau doit être associé à une région réseau spécifique.

<div>


> [!NOTE]  
> Les sites réseau sont utilisés uniquement par les fonctionnalités avancées de voix entreprise. Ils ne sont pas les mêmes que ceux que vous configurez dans la topologie de votre serveur Lync. Pour plus d’informations sur les sites de succursale, voir <A href="lync-server-2013-reference-topologies.md">topologies de référence dans Lync Server 2013</A> dans la documentation de planification. Voir également <A href="lync-server-2013-supported-topologies.md">topologies prises en charge dans Lync Server 2013</A> dans la documentation sur la prise en charge.



</div>

Pour configurer un site réseau et l’associer à une région du réseau, vous pouvez utiliser la section **Configuration réseau** du panneau de configuration de Lync Server ou exécuter les applets de commande **New-CsNetworkSite** ou **Set-CsNetworkSite** de Lync Server Management Shell. Pour plus d’informations, reportez-vous à [créer ou modifier un site réseau dans Lync server 2013](lync-server-2013-create-or-modify-a-network-site.md) dans la documentation de déploiement, ou vous référer à la documentation Lync Server Management Shell.

</div>

<div>

## <a name="identify-ip-subnets"></a>Identifier les sous-réseaux IP

Pour chaque site réseau, vous devrez collaborer avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Si votre administrateur réseau a déjà organisé les sous-réseaux IP en régions réseau et sites réseau, votre travail est considérablement simplifié.

Dans notre exemple, le site New York de la région Amérique du Nord peut se voir affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, qui travaille généralement à Détroit, se rend dans les bureaux de New York pour suivre une formation, allume son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages allouées à New York (par exemple, 172.29.80.103).

<div>


> [!WARNING]  
> Les sous-réseaux IP spécifiés pendant la configuration du réseau sur le serveur doivent correspondre au format fourni par les ordinateurs clients afin d’être correctement utilisés pour la déviation du trafic multimédia. Un client Lync accepte son adresse IP locale et masque l’adresse IP avec le masque de sous-réseau associé. Lors de la détermination de l’ID de contournement associé à chaque client, le serveur d’inscriptions comparera la liste des sous-réseaux IP associés à chaque site réseau avec le sous-réseau fourni par le client pour obtenir une correspondance exacte. Pour cette raison, il est important que les sous-réseaux entrés lors de la configuration du réseau sur le serveur soient des sous-réseaux réels et non des sous-réseaux virtuels. (Si vous déployez le contrôle d’admission des appels, mais pas la déviation du trafic multimédia, le contrôle d’admission des appels fonctionnera correctement même si vous configurez des sous-réseaux virtuels.)<BR>Par exemple, si un client Lync se connecte à partir d’un ordinateur doté d’une adresse IP 172.29.81.57 avec un masque de sous-réseau IP de 255.255.255.0, il demande l’ID de contournement associé au sous-réseau 172.29.81.0. Si le sous-réseau est défini comme 172.29.0.0/16, même si le client appartient au sous-réseau virtuel, le serveur d’inscriptions ne considérera pas cela comme une correspondance, car le serveur d’inscriptions recherche spécifiquement le sous-réseau 172.29.81.0. Par conséquent, il est important que l’administrateur entre les sous-réseaux exactement comme fourni par les clients Lync (qui sont configurés avec des sous-réseaux lors de la configuration du réseau, de manière statique ou par le protocole DHCP).)



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>Association de sous-réseaux à des sites réseau

Chaque sous-réseau dans le réseau d’entreprise doit être associé à un site réseau (c’est-à-dire que chaque sous-réseau doit être associé à un emplacement géographique). Grâce à cette association de sous-réseaux, les fonctionnalités avancées de voix entreprise permettent de localiser les points de terminaison géographiquement. Par exemple, la localisation des points de terminaison permet au contrôle d’admission des appels de réguler le flux de données audio et vidéo en temps réel qui transitent vers et depuis le site réseau.

Pour associer des sous-réseaux aux sites réseau, vous pouvez utiliser la section **Configuration réseau** du panneau de configuration de Lync Server ou utiliser Lync Server Management Shell. Pour obtenir des instructions, reportez-vous à la section [associez un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) dans la documentation de déploiement, ou consultez la documentation Lync Server Management Shell.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Planification des services d’urgence (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

