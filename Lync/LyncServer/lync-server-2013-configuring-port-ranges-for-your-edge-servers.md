---
title: 'Lync Server 2013 : configuration des plages de ports pour vos serveurs Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1d1dc6c35cac0a375b9229a0a9e04664bfe868a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Configuration des plages de ports pour vos serveurs Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-07-24_

Avec les serveurs Edge, il n’est pas nécessaire de configurer des plages de ports distinctes pour l’audio, la vidéo et le partage d’application ; de même, les plages de ports utilisées pour les serveurs Edge n’ont pas besoin de correspondre à celles utilisées avec vos serveurs de conférence, d’applications et de médiation. Avant de poursuivre notre exemple, il est important de souligner que, lorsque cette option existe, nous vous recommandons de ne pas modifier les plages de ports, car cela peut avoir un impact négatif sur certains scénarios si vous quittez la plage de ports 50000.

Par exemple, supposons que vous ayez configuré vos serveurs de conférence, d’applications et de médiation afin d’utiliser ces plages de ports :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de paquet</th>
<th>Port de début</th>
<th>Nombre de ports réservés</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Partage d’application</p></td>
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


Comme vous pouvez le voir, les plages de ports pour l’audio, la vidéo et le partage d’application commencent au port 40803 et englobent un total de 24732 ports. Si vous préférez, vous pouvez configurer un serveur Edge donné afin d’utiliser ces valeurs de ports globales en exécutant une commande similaire à celle-ci depuis Lync Server Management Shell :

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Ou utilisez la commande suivante pour configurer simultanément tous les serveurs Edge de votre organisation :

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Vous pouvez vérifier les paramètres de port actuels de vos serveurs Edge à l’aide de cette commande Lync Server Management Shell :

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Encore une fois, pendant que nous fournissons ces options, nous vous recommandons vivement de laisser des choses comme pour la configuration de port.

</div>

<span> </span>

</div>

</div>

</div>

