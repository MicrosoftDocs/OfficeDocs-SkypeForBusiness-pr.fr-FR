---
title: 'Lync Server 2013 : vue d’ensemble du contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4ad2be78d3e2af4c5b016b02e152ba0430d2a1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-22_

Les communications en temps réel sont sensibles à la latence et à la perte de paquets susceptibles de survenir sur des réseaux saturés. Le contrôle d’admission des appels détermine, en fonction de la bande passante réseau disponible, si des sessions de communication en temps réel, telles que des appels vocaux ou vidéo, peuvent être établies. La conception CAC dans Lync Server 2013 propose quatre attributs principaux :

  - Le contrôle d’admission des appels est simple à déployer et à gérer sans recours à un équipement supplémentaire, tel que des routeurs configurés spécialement.

  - Il traite les scénarios d’utilisation des communications unifiées critiques, tels que les utilisateurs itinérants et les points de présence multiples. Les stratégies du contrôle d’admission des appels sont appliquées selon l’emplacement du système d’extrémité et non pas de l’emplacement où est hébergé l’utilisateur.

  - Outre les appels vocaux, ce contrôle peut être appliqué à d’autres trafics, tels que les appels vidéo et les sessions de conférence audio/vidéo.

  - Il fournit suffisamment de flexibilité pour permettre la représentation de différents types de topologies réseau. Pour obtenir des exemples, voir [composants et topologies pour CAC dans Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Si ou nouvelle session audio ou vidéo dépasse les limites de bande passante définies sur une liaison WAN, la session est bloquée ou (pour les appels téléphoniques uniquement) réacheminée sur PSTN.

Le contrôle d’admission des appels contrôle le trafic en temps réel pour la voix et la vidéo uniquement. Il ne contrôle pas le trafic de données.

Les administrateurs définissent les stratégies de contrôle d’admission des stratégies, qui sont appliquées par le service de stratégie de bande passante installé avec chaque pool frontal. Les paramètres CAC sont automatiquement propagés sur tous les serveurs frontaux Lync Server de votre réseau.

Pour les appels qui échouent en raison des stratégies de contrôle d’admission des appels, l’ordre de priorité de réacheminement des appels est le suivant :

1.  Internet

2.  RTC

3.  Messagerie vocale

L’enregistrement des détails des appels capture les informations concernant les appels qui sont réacheminés vers PSTN ou la messagerie vocale. L’enregistrement des détails des appels ne capture pas les informations des appels non réacheminés sur Internet, car Internet est traité comme un autre chemin d’accès plutôt qu’une autre option.

<div>


> [!NOTE]  
> Les dépôts de messages vocaux ne seront pas refusés en raison des contraintes de bande passante.



</div>

Le service de stratégie de bande passante génère deux types de fichiers journaux au format CSV (valeurs séparées par des virgules). Le fichier journal du **nombre d’échecs de vérification** capture les informations lorsque les demandes de bande passante sont refusées. Le fichier journal d’**utilisation des liaisons** capture un instantané de la topologie réseau et de l’utilisation de la bande passante de la liaison WAN. Ces deux fichiers journaux peuvent vous aider à affiner vos stratégies de contrôle d’admission des appels en fonction de l’utilisation.

<div>

## <a name="call-admission-control-considerations"></a>Considérations relatives au contrôle d’admission des appels

L’administrateur choisit d’installer le service de stratégie de bande passante sur le premier pool configuré dans le site central. Puisqu’il existe un seul site central par région réseau, il existe un seul service de stratégie de bande passante par région réseau, lequel gère la stratégie de bande passante pour cette région, ses sites associés et les liens vers ces sites. Le service de stratégie de bande passante s’exécute sur les serveurs frontaux et, par conséquent, la haute disponibilité est intégrée au sein de ce pool. Le service de stratégie de bande passante s’exécutant sur chaque serveur frontal se synchronise toutes les 15 secondes. Si le pool frontal échoue, les stratégies de contrôle d’admission des stratégies ne sont plus appliquées pour ce site jusqu’à ce que le pool frontal et, par conséquent, le service de stratégie de bande passante soit à nouveau opérationnel. Cela signifie que tous les appels sont transmis pendant la durée d’interruption du service de stratégie de bande passante. Par conséquent, il existe un risque de surabonnement de bande passante pour vos liens durant cette période.

Le service de stratégie de bande passante offre une haute disponibilité au sein d’un pool frontal ; Toutefois, il ne fournit pas de redondance dans les pools frontaux. Le service de stratégie de bande passante ne peut pas basculer d’un pool frontal à un autre. Une fois le service sur le pool frontal restauré, le service de stratégie de bande passante reprend et peut appliquer de nouveau les contrôles de stratégie de bande passante.

<div>

## <a name="network-considerations"></a>Considérations relatives au réseau

Bien que la restriction de bande passante pour l’audio et la vidéo soit appliquée par le service de stratégie de bande passante dans Lync Server 2013, cette restriction n’est pas appliquée au niveau du routeur réseau (couches 2 et 3). Lync Server 2010 le contrôle d’admission des appels ne peut pas empêcher une application de données de consommer toute la bande passante réseau sur une liaison de réseau étendu, y compris la bande passante réservée à la stratégie de contrôle d’admission des appels audio et vidéo. Pour protéger la bande passante nécessaire sur votre réseau, vous pouvez déployer un protocole de qualité de service (QoS) tel que les services différenciés (DiffServ). Par conséquent, il est recommandé de coordonner les stratégies de bande passante de contrôle d’admission des coordonnées définies avec tous les paramètres de qualité de service que vous pouvez déployer.

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>Chemins d’accès des médias et de la signalisation sur réseau privé virtuel (VPN)

Si votre entreprise prend en charge les médias via VPN, assurez-vous que les flux multimédia et de signalisation passent tous deux via le VPN ou qu’ils sont routés par le biais d’Internet. Par défaut, les flux multimédia et de signalisation passent par le tunnel VPN.

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>Contrôle d’admission des appels des utilisateurs extérieurs

Le contrôle d’admission des appels ne s’applique pas aux utilisateurs distants où le trafic réseau transite par Internet. Étant donné que le trafic multimédia traverse Internet, qui n’est pas géré par Lync Server, le contrôle d’admission des médias ne peut pas être appliqué. Le contrôle d’admission des appels effectuera néanmoins des vérifications sur la portion d’appel qui transite par le réseau de l’entreprise.

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>Contrôle d’admission des appels des connexions PSTN

Le contrôle d’admission des appels est applicable sur le serveur de médiation, qu’il soit connecté à un IP/PBX, à une passerelle PSTN ou à une jonction SIP. Étant donné que le serveur de médiation est un agent utilisateur dos à dos (B2BUA), il met fin au support. Il comporte deux côtés de connexion : un côté connecté à Lync Server et un côté passerelle, qui est connecté à des passerelles PSTN, IP/PBX ou à des jonctions SIP. Pour plus d’informations sur les connexions PSTN, voir [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

Le contrôle d’admission des médias peut être appliqué sur les deux côtés du serveur de médiation sauf si la déviation du trafic multimédia est activée. Si la déviation du trafic multimédia est activée, le trafic multimédia ne traverse pas le serveur de médiation mais transite directement entre le client Lync et la passerelle. Dans ce cas, le contrôle d’admission des appels n’est pas nécessaire. Pour plus d’informations, reportez-vous à la rubrique [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

La figure suivante illustre la façon dont le contrôle d’admission des appels est appliqué sur les connexions PSTN avec ou sans le contournement de média activé.

**Application du contrôle d’admission des appels sur des connexions PSTN**

![Application de la connexion de contournement de média CAC vocal](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Application de la connexion de contournement de média CAC vocal")

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>Compatibilité du contrôle d’admission des appels avec les versions précédentes d’Office Communications Server

Le contrôle d’admission des appels peut être activé uniquement sur les points de terminaison qui sont activés pour Lync Server 2010 et les versions ultérieures.

Le contrôle d’admission des appels ne peut pas être activé sur les points de terminaison exécutant Office Communicator 2007 R2 ou une version antérieure.

**Application du contrôle d’admission des appels sur des versions de Lync Server différentes**

![Diagramme de comparaison des versions de la version CAC](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagramme de comparaison des versions de la version CAC")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

