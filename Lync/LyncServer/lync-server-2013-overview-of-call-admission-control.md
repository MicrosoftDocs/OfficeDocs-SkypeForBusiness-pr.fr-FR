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
ms.openlocfilehash: f5b38fbb1ae1e209e5b5332e896d806d1ca24975
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-22_

Les communications en temps réel sont sensibles à la latence et à la perte de paquets qui peuvent se produire sur des réseaux encombrés. Le contrôle d’admission des appels détermine, en fonction de la bande passante réseau disponible, si des sessions de communication en temps réel, telles que des appels vocaux ou vidéo, peuvent être établies. La conception CAC de Lync Server 2013 propose quatre attributs principaux :

  - Le contrôle d’admission des appels est simple à déployer et à gérer sans recours à un équipement supplémentaire, tel que des routeurs configurés spécialement.

  - Il traite les scénarios d’utilisation des communications unifiées critiques, tels que les utilisateurs itinérants et les points de présence multiples. Les stratégies du contrôle d’admission des appels sont appliquées selon l’emplacement du point de terminaison et non pas de l’emplacement où est hébergé l’utilisateur.

  - Outre les appels vocaux, ce contrôle peut être appliqué à d’autres trafics, tels que les appels vidéo et les sessions de conférence audio/vidéo.

  - Il fournit suffisamment de flexibilité pour permettre la représentation de différents types de topologies réseau. Pour consulter des exemples, voir [composants et topologies pour CAC dans Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Si ou nouvelle session audio ou vidéo dépasse les limites de bande passante définies sur une liaison de réseau étendu, la session est bloquée ou (pour les appels téléphoniques uniquement) réacheminée sur RTC.

Le contrôle d’admission des appels contrôle le trafic en temps réel pour la voix et la vidéo uniquement. Il ne contrôle pas le trafic de données.

Les administrateurs définissent des stratégies CAC qui sont appliquées par le service de stratégie de bande passante qui est installé avec chaque pool frontal. Les paramètres CAC sont automatiquement propagés vers tous les serveurs front end de Lync Server de votre réseau.

Pour les appels qui échouent en raison des stratégies de contrôle d’admission des appels, l’ordre de priorité de réacheminement des appels est le suivant :

1.  Internet

2.  PSTN

3.  Messagerie vocale

L’enregistrement des détails des appels capture les informations concernant les appels réacheminés vers RTC ou la messagerie vocale. L’enregistrement des détails des appels ne capture pas les informations des appels non réacheminés sur Internet, car Internet est traité comme un autre chemin d’accès plutôt qu’une autre option.

<div>


> [!NOTE]  
> Les dépôts de messages vocaux ne seront pas refusés en raison des contraintes de bande passante.



</div>

Le service de stratégie de bande passante génère deux types de fichiers journaux au format CSV (valeurs séparées par des virgules). Le fichier journal du **nombre d’échecs de vérification** capture les informations lorsque les demandes de bande passante sont refusées. Le fichier journal d’**utilisation des liaisons** capture un instantané de la topologie réseau et de l’utilisation de la bande passante de la liaison de réseau étendu. Ces deux fichiers journaux peuvent vous aider à affiner vos stratégies de contrôle d’admission des appels en fonction de l’utilisation.

<div>

## <a name="call-admission-control-considerations"></a>Considérations relatives au contrôle d’admission des appels

L’administrateur choisit d’installer le service de stratégie de bande passante sur le premier pool configuré dans le site central. Puisqu’il existe un seul site central par région réseau, il existe un seul service de stratégie de bande passante par région réseau, lequel gère la stratégie de bande passante pour cette région, ses sites associés et les liens vers ces sites. Le service de stratégie de bande passante s’exécute dans le cadre des serveurs frontaux et, par conséquent, la haute disponibilité est intégrée au sein de ce pool. Le service de stratégie de bande passante qui s’exécute sur chaque serveur frontal se synchronise toutes les 15 secondes. Si le pool frontal ne fonctionne pas, les stratégies CAC ne sont plus appliquées pour ce site tant qu’il n’y a pas de pool frontal Cela signifie que tous les appels sont transmis pendant la durée d’interruption du service de stratégie de bande passante. Par conséquent, il existe un risque de surabonnement de bande passante pour vos liens durant cette période.

Le service de stratégie de bande passante fournit une haute disponibilité au sein d’un pool frontal. Toutefois, elle ne fournit pas de redondance entre les pools front-end. Le service de stratégie de bande passante ne peut pas basculer d’un pool frontal à un autre. Une fois que le service pour le pool frontal est restauré, le service de stratégie de bande passante reprend et peut appliquer de nouveau les contrôles de stratégie de bande passante.

<div>

## <a name="network-considerations"></a>Considérations relatives au réseau

Même si la restriction de bande passante pour l’audio et la vidéo est appliquée par le service de stratégie de bande passante dans Lync Server 2013, cette restriction n’est pas appliquée sur le routeur réseau (couches 2 et 3). Lync Server 2010 CAC ne peut pas empêcher une application de données (par exemple, l’utilisation de la bande passante réseau entière sur une liaison réseau étendu, y compris la bande passante réservée aux appels audio et vidéo par votre stratégie CAC). Pour protéger la bande passante nécessaire sur votre réseau, vous pouvez déployer un protocole de qualité de service (QoS) tel que les services différenciés (DiffServ). Par conséquent, la meilleure pratique consiste à coordonner les stratégies de bande passante du contrôle d’admission des données que vous définissez avec les paramètres QoS que vous pouvez déployer.

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>Chemins d’accès des médias et de la signalisation sur réseau privé virtuel (VPN)

Si votre entreprise prend en charge les médias via VPN, assurez-vous que les flux multimédia et de signalisation passent tous deux via le VPN ou qu’ils sont routés par le biais d’Internet. Par défaut, les flux multimédia et de signalisation passent par le tunnel VPN.

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>Contrôle d’admission des appels des utilisateurs extérieurs

Le contrôle d’admission des appels n’est pas appliqué aux utilisateurs distants où le trafic réseau circule via Internet. Dans la mesure où le trafic multimédia traverse Internet, qui n’est pas géré par Lync Server, le CAC ne peut pas être appliqué. Les vérifications CAC seront exécutées, toutefois, sur la partie de l’appel qui circule par le biais du réseau d’entreprise.

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>Contrôle d’admission des appels des connexions RTC

Le contrôle d’admission des appels est applicable sur le serveur de médiation, qu’il s’agisse d’un réseau IP/PBX, d’une passerelle PSTN ou d’une connexion SIP. Dans la mesure où le serveur de médiation est un agent utilisateur dorsal (B2BUA), il arrête le média. Il a deux côtés de connexion : le côté connecté à Lync Server et un côté passerelle, qui est connecté à des passerelles RTC, des PBX IP/PBX ou des lignes SIP. Pour plus d’informations sur les connexions RTC, voir [planification de la connectivité PSTN dans Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

Le CAC peut être appliqué sur les deux côtés du serveur de médiation, sauf si la dérivation multimédia est activée. Si l’option de contournement du contenu multimédia est activée, le trafic multimédia ne traverse pas le serveur de médiation mais est transmis directement entre le client et la passerelle Lync. Dans ce cas, le contrôle d’admission des appels n’est pas nécessaire. Pour plus d’informations, reportez-vous à la section [planification de la dérivation multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

La figure suivante illustre la façon dont le contrôle d’admission des appels est appliqué sur les connexions RTC avec ou sans la déviation du trafic multimédia activée.

**Application du contrôle d’admission des appels sur des connexions RTC**

![Application de connexion de contournement de média CAC vocal](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Application de connexion de contournement de média CAC vocal")

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>Compatibilité du contrôle d’admission des appels avec les versions antérieures d’Office Communications Server

Le contrôle d’admission des appels ne peut être activé que sur les points de terminaison activés pour Lync Server 2010 et les versions ultérieures.

Le contrôle d’admission des appels ne peut pas être activé sur des points de terminaison exécutant Office Communicator 2007 R2 ou une version antérieure.

**Application de CAC sur différentes versions de Lync Server**

![Diagramme de comparaison de version CAC](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagramme de comparaison de version CAC")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

