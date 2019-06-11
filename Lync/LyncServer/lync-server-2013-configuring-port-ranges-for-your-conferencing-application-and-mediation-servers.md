---
title: 'Lync Server 2013: configuration de plages de ports pour vos serveurs de conférence, d’application et de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5402da56fa646c6ae6e2247baa70a5ef03b851cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configuration de plages de ports dans Lync Server 2013 pour vos serveurs de conférence, d’application et de médiation

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-04-30_

Pour implémenter la qualité de service, vous devez configurer des plages de port identiques pour le partage audio, vidéo et d’application sur vos serveurs de conférence, d’application et de médiation. de plus, ces plages de port ne doivent pas se chevaucher de quelque manière que ce soit. Par exemple, vous pouvez utiliser les ports 10000 à 10999 pour la vidéo sur vos serveurs de conférence. Cela signifie que vous devez également réserver les ports 10000 à 10999 pour la vidéo sur vos serveurs d’application et de médiation. Si ce n’est pas le cas, QoS ne fonctionnera pas comme prévu.

De même, supposons que vous réservez les ports 10000 à 10999 pour la vidéo, mais que vous réservez les ports 10500 à 11999 pour le son. Cela peut générer des problèmes de qualité de service, car les plages de port se chevauchent. Avec la qualité de service (QoS), chaque modalité doit avoir un ensemble unique de ports: Si vous utilisez les ports 10000 à 10999 pour la vidéo, vous devez utiliser une autre plage (par exemple, 11000 à 11999 pour le son).

Par défaut, les plages de port audio et vidéo ne se chevauchent pas dans Microsoft Lync Server 2013; Toutefois, les plages de port affectées au partage d’application s’empiètent sur les plages de ports audio et vidéo. (Qui, à son tour, signifie qu’aucune de ces plages n’est unique.) Vous pouvez vérifier les plages de port existantes pour vos serveurs de conférences, d’applications et de médiation en exécutant les trois commandes suivantes à partir de Lync Server 2013 Management Shell:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> Comme vous pouvez le voir dans les commandes précédentes, chaque type de port (audio, vidéo et partage d’application) assigne deux valeurs de propriété distinctes: le début du port et le nombre de ports. Le début du port indique le premier port utilisé pour cette modalité; par exemple, si le port audio démarre est égal à 50000, cela signifie que le premier port utilisé pour le trafic audio est le port 50000. Si le nombre de ports audio est 2 (qui n’est pas une valeur valide, mais qui est utilisé ici à des fins d’illustration), cela signifie que 2 ports uniquement sont attribués pour le son. Si le premier port est port 50000 et qu’il existe au total deux ports, cela signifie que le second port doit être le port 50001 (les plages de port doivent être contiguës). Par conséquent, la plage de port pour le son correspond aux ports 50000 à 50001 inclus.<BR>Notez également que le serveur d’applications et le serveur de médiation ne prennent pas en charge la QoS pour le son. vous n’avez pas besoin de changer les ports vidéo ou de partage d’application dans vos serveurs d’applications ou serveurs de médiation.



</div>

Si vous exécutez les trois commandes précédentes, vous verrez que les valeurs de port par défaut de Lync Server 2013 sont configurées comme suit:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Propriété</th>
<th>Serveur de conférence</th>
<th>Serveur d’applications</th>
<th>serveur de médiation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


Comme indiqué précédemment, lors de la configuration des ports du serveur Lync pour la qualité de service (QoS), vous devez vous assurer que: 1 et 2) les plages de port ne se chevauchent pas. Si vous examinez de près le tableau précédent, vous verrez que les plages de port sont identiques entre les trois types de serveurs. Par exemple, le port audio de début est défini sur le port 49152 sur chaque type de serveur et le nombre total de ports réservés pour le son dans chaque serveur est également identique: 8348. Toutefois, le chevauchement des plages de port: les ports audio commencent au port 49152, mais les ports sont-ils mis de côté pour le partage d’application. Pour optimiser l’utilisation de la qualité du service, le partage d’application doit être reconfiguré pour utiliser une plage de ports unique. Par exemple, vous pouvez configurer le partage d’application pour qu’il commence au port 40803 et utilise les ports 8348. (Pourquoi 8348 ports? Si vous ajoutez ces valeurs ensemble--40803 + 8348, cela signifie que le partage d’application utilisera les ports 40803 via le port 49150. Étant donné que les ports audio ne commencent pas jusqu’au port 49152, il n’y a plus de plages de ports qui se chevauchent.)

Après avoir sélectionné la nouvelle plage de ports pour le partage d’application, vous pouvez apporter votre modification à l’aide de l’applet de passe Set-CsConferencingServer. Il n’est pas nécessaire de procéder à cette modification sur les serveurs d’applications ou sur les serveurs de médiation, car ces serveurs ne gèrent pas le trafic de partage d’application. Vous ne devez modifier les valeurs de port sur ces serveurs que si vous décidez de réaffecter les ports utilisés pour le trafic audio.

Pour modifier les valeurs de port du partage d’application sur un serveur de conférence unique, exécutez une commande similaire à celle-ci à partir de Lync Server Management Shell:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Si vous voulez apporter ces modifications sur tous vos serveurs de conférence, vous pouvez exécuter cette commande à la place:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Après avoir modifié les paramètres de port que vous devez arrêter, puis redémarrez chaque service affecté par ces changements.

Il n’est pas obligatoire que vos serveurs de conférence, serveurs d’applications et serveurs de médiation partagent exactement la même plage de port; la seule exigence requise est que vous réservez des plages de port uniques sur tous vos serveurs. Toutefois, l’administration sera généralement plus facile si vous utilisez le même ensemble de ports sur tous vos serveurs.

</div>

<span> </span>

</div>

</div>

</div>

