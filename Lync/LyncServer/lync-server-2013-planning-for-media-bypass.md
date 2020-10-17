---
title: 'Lync Server 2013 : planification de la déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5d9687069e82cde803f7a01873db482ea2afa2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521991"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Planification de la déviation du trafic multimédia dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Le contournement de média fait référence à la suppression du serveur de médiation du chemin d’accès des médias, dans la mesure du possible, pour les appels dont la signalisation traverse le serveur de médiation.

Le contournement de média peut améliorer la qualité de la voix en diminuant la latence, les traductions inutiles, la perte de paquets possible et le nombre de points de défaillance éventuels. L’extensibilité peut être améliorée du fait que l’élimination du traitement multimédia pour les appels contournés réduit la charge sur le serveur de médiation. Cette réduction du chargement complète la capacité du serveur de médiation à contrôler plusieurs passerelles.

Lorsqu’un site de succursale sans serveur de médiation est connecté à un site central par une ou plusieurs liaisons de réseau étendu avec une bande passante limitée, la déviation du trafic multimédia diminue l’exigence de bande passante en permettant aux médias d’un client sur un site de succursale de circuler directement vers la passerelle locale sans avoir préalablement transiter de la liaison de réseau étendu à un serveur de médiation

En soulageant le serveur de médiation du traitement multimédia, la déviation du trafic multimédia peut également réduire le nombre de serveurs de médiation requis par une infrastructure voix entreprise.

La figure suivante montre des médias de base et des voies de signalisation dans des topologies avec et sans contournement de média.

**Médias et voies de signalisation avec et sans contournement de média**

![Application de la connexion de contournement de média CAC vocal](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Application de la connexion de contournement de média CAC vocal")

En règle générale, essayez d’activer le contournement de média quand cela est possible.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Vue d’ensemble de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Modes de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>Sections connexes

[Déploiement des fonctionnalités avancées de voix entreprise dans Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Options globales de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

