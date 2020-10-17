---
title: 'Lync Server 2013 : prise en charge de plusieurs tronçons'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2581ee5f67c6af1c5afd0622f7893ccc2486b51d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507041"
---
# <a name="multiple-trunk-support-in-lync-server-2013"></a>Prise en charge de plusieurs tronçons dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

La fonctionnalité Lync Server 2013 prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Ces associations sont établies en définissant une jonction, qui est une association logique entre un pool de serveurs de médiation et une passerelle de réseau téléphonique commuté (RTC), un contrôleur de frontière de session (SBC) ou un PBX IP. Utilisez le générateur de topologie pour associer des passerelles aux serveurs de médiation (c’est-à-dire, des jonctions).

  - Pour attribuer ou supprimer une jonction dans Lync Server 2013, vous devez d’abord définir une jonction dans le générateur de topologies. Une jonction se compose de l’Association suivante : nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.

  - Pour configurer plusieurs jonctions, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation. Cela procure une résistance supplémentaire à l’infrastructure voix entreprise, ce qui est particulièrement utile dans les scénarios d’interopérabilité PBX (Private Branch Exchange).

Lorsqu’une jonction est définie, elle doit être associée à un itinéraire. Pour associer une jonction à un itinéraire, vous définissez un nom simple pour la jonction dans le générateur de topologie. Ce nom simple est utilisé comme nom de jonction dans le panneau de configuration Lync Server, où des jonctions peuvent être associées à des itinéraires. Le nom de jonction simple est utilisé comme nom de passerelle à partir de Lync Server Management Shell.

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

L’administrateur doit sélectionner une jonction par défaut associée à un serveur de médiation. Dans le générateur de topologies, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés**. Spécifiez la passerelle par défaut pour le serveur de médiation.

Le diagramme suivant illustre les différentes jonctions qui sont définies pour chaque serveur de médiation et passerelle.

**Routage de jonction M-N**

![Plusieurs affectations de jonctions.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Plusieurs affectations de jonctions.")

</div>

<span> </span>

</div>

</div>

</div>

