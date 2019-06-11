---
title: 'Lync Server 2013: configuration de plages de ports pour vos serveurs Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73827b9c16903a6b3cf06f0c56446c0409fb9cd4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Configuration de plages de ports pour vos serveurs Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-07-24_

Avec les serveurs Edge, vous n’avez pas besoin de configurer des plages de port distinctes pour le partage audio, vidéo et d’application. de même, les plages de port utilisées pour les serveurs Edge ne doivent pas nécessairement correspondre aux plages de port utilisées avec vos serveurs de conférence, d’application et de médiation. Avant de continuer, nous vous conseillons d’insister sur le fait que, si vous dépassez cette option, nous vous conseillons de ne pas modifier les plages de ports, car cela peut nuire à certains scénarios si vous vous éloignez de la plage de ports 50000.

Par exemple, supposons que vous ayez configuré vos serveurs de conférence, d’application et de médiation pour utiliser ces plages de ports:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de paquet</th>
<th>Port de démarrage</th>
<th>Nombre de ports réservés</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Partage d'application</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>Vidéo</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>Totaux</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Comme vous pouvez le constater, vos plages de port pour le partage audio, vidéo et d’application commencent au port 40803 et incluent au total des ports 24732. Si vous le souhaitez, vous pouvez configurer un serveur Edge donné pour utiliser ces valeurs de port globales en exécutant une commande similaire à celle-ci dans Lync Server Management Shell:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Vous pouvez utiliser la commande suivante pour configurer simultanément tous les serveurs Edge de votre organisation:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Vous pouvez vérifier les paramètres de port actuels pour vos serveurs Edge à l’aide de la commande Lync Server Management Shell suivante:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Là encore, nous vous conseillons vivement de conserver les éléments tels que la configuration de port.

</div>

<span> </span>

</div>

</div>

</div>

