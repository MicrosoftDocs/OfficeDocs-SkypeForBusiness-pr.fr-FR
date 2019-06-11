---
title: 'Lync Server 2013: prise en charge de plusieurs Trunks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156db04ceb26809c7043f30e9e01ea0071e0a31d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a>Prise en charge de plusieurs Trunks dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

La fonctionnalité Lync Server 2013 prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Pour ce faire, vous devez définir une ligne Trunk, qui est une association logique entre une grappe de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur de bordure de session (SBC) ou un PBX IP. Utilisez le générateur de topologie pour associer des passerelles aux serveurs de médiation (c’est-à-dire, des Trunks).

  - Pour attribuer ou supprimer un Trunk dans Lync Server 2013, vous devez commencer par définir un Trunk dans le générateur de topologie. Un Trunk est composé de l’Association suivante: nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.

  - Pour configurer plusieurs Trunks, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation. Cela fournit une résilience supplémentaire à l’infrastructure voix entreprise, qui est particulièrement utile dans les scénarios d’interopération de PBX (Private Branch Exchange).

Lorsqu’une jonction est définie, elle doit être associée à un itinéraire. Pour associer un Trunk à un itinéraire, vous devez définir un nom simple pour le Trunk dans le générateur de topologie. Ce nom simple est utilisé en tant que nom du Trunk dans le panneau de configuration de Lync Server, dans lequel les lignes peuvent être associées aux itinéraires. Le nom de Trunk simple est utilisé comme nom de passerelle de Lync Server Management Shell.

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

L’administrateur doit sélectionner une Trunk par défaut associée à un serveur de médiation. Dans le générateur de topologie, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés**. Spécifiez la passerelle par défaut du serveur de médiation.

Le diagramme suivant illustre les différentes liaisons définies pour chaque serveur et passerelle de médiation.

**Routage de l’interligne M-N**

![Plusieurs affectations de Trunk.] (images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Plusieurs affectations de Trunk.")

</div>

<span> </span>

</div>

</div>

</div>

