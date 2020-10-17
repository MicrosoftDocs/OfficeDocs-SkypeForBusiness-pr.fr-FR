---
title: 'Lync Server 2013 : configuration des plages de ports pour vos clients Microsoft Lync'
description: 'Lync Server 2013 : configuration des plages de ports pour vos clients Microsoft Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e7fcabf81f8e0110010b1a4fb8e697fb0da986c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569990"
---
# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Configuration des plages de ports pour vos clients Microsoft Lync dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-04-22_

Par défaut, les applications clientes Lync peuvent utiliser n’importe quel port entre les ports 1024 et 65535 lorsqu’une session de communication est impliquée ; Cela est dû au fait que les plages de ports spécifiques ne sont pas automatiquement activées pour les clients. Pour utiliser la qualité de service, toutefois, vous devrez réaffecter les différents types de trafic (audio, vidéo, multimédia, partage d’application et transfert de fichiers) à une série de plages de ports uniques. Cette opération peut être réalisée à l’aide de la cmdlet Set-CsConferencingConfiguration.

<div>


> [!NOTE]  
> Les utilisateurs finaux ne peuvent pas procéder à ces modifications. Les modifications de port peuvent être effectuées uniquement par les administrateurs à l’aide de l’applet de commande Set-CsConferencingConfiguration.



</div>

Vous pouvez déterminer les plages de ports actuellement utilisées pour les sessions de communication en exécutant la commande suivante à partir de Microsoft Lync Server 2013 Management Shell :

    Get-CsConferencingConfiguration

En supposant que vous n’avez apporté aucune modification à vos paramètres de conférence depuis que vous avez installé Lync Server 2013, vous devez obtenir des informations qui incluent les valeurs de ces propriétés :

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Si vous examinez attentivement la sortie précédente, vous verrez deux éléments d’importance. Tout d’abord, la propriété paramètres clientmediaportrangeenabled est définie sur false :

    ClientMediaPortRangeEnabled : False

Cela est important car, lorsque cette propriété est définie sur false, les clients Lync utiliseront n’importe quel port disponible entre les ports 1024 et 65535 lorsqu’ils sont impliqués dans une session de communication. Cela est vrai indépendamment des autres paramètres de port (par exemple, ClientMediaPort ou ClientVideoPort). Si vous souhaitez restreindre l’utilisation à un ensemble spécifique de ports (ce que vous devez faire si vous envisagez d’implémenter la qualité de service), vous devez d’abord activer les plages de ports du client multimédia. Cela peut être réalisé à l’aide de la commande Windows PowerShell suivante :

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

La commande précédente permet d’activer des plages de ports multimédias client pour la collection globale des paramètres de configuration de conférence ; Toutefois, ces paramètres peuvent également être appliqués à l’étendue du site et/ou à l’étendue du service (pour le service de serveur de conférence uniquement). Pour activer des plages de ports multimédias client pour un site ou un serveur spécifique, spécifiez l’identité de ce site ou serveur lors de l’appel de Set-CsConferencingConfiguration :

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Vous pouvez également utiliser cette commande pour activer simultanément les plages de ports pour tous vos paramètres de configuration de conférence :

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

La deuxième chose d’importance que vous remarquerez est que le résultat de l’exemple indique que, par défaut, les plages de ports multimédias définies pour chaque type de trafic réseau sont identiques :

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Pour mettre en œuvre la qualité de service, chacune de ces plages de ports doit être unique. Par exemple, vous pouvez configurer les plages de ports comme suit :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de trafic client</th>
<th>Démarrage du port</th>
<th>Plage de ports</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="even">
<td><p>Vidéo</p></td>
<td><p>58000</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="odd">
<td><p>Partage d'application</p></td>
<td><p>42000</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="even">
<td><p>Transfert de fichiers</p></td>
<td><p>42020</p></td>
<td><p>vingtaine</p></td>
</tr>
</tbody>
</table>


Dans le tableau précédent, les plages de ports client représentent un sous-ensemble des plages de ports configurées pour vos serveurs. Par exemple, sur les serveurs, le partage d’application a été configuré pour utiliser les ports 40803 à 49151 ; sur les ordinateurs clients, le partage d’application est configuré pour utiliser les ports 42000 à 42019. Cela est également essentiel pour faciliter l’administration de QoS : les ports clients n’ont pas besoin de représenter un sous-ensemble des ports utilisés sur le serveur. (Par exemple, sur les ordinateurs clients, vous pouvez configurer le partage d’application à utiliser, par exemple, les ports 10000 à 10019.) Toutefois, il est recommandé de faire en sorte que les plages de ports clients soient un sous-ensemble des plages de ports de votre serveur.

De plus, vous avez peut-être remarqué que les ports 8348 ont été mis de côté pour le partage d’application sur les serveurs, mais seulement 20 ports ont été mis de côté pour le partage d’application sur les clients. Cela est également recommandé, mais il ne s’agit pas d’une règle matérielle et rapide. En règle générale, vous pouvez considérer chaque port disponible pour qu’il représente une seule session de communication : Si vous disposez de 100 ports disponibles dans une plage de ports, cela signifie que l’ordinateur en question peut, au plus, se voir attribuer 100 sessions de communication à tout moment. Étant donné que les serveurs feront probablement partie d’autres conversations que les clients, il est logique d’ouvrir beaucoup plus de ports sur les serveurs que sur les clients. Le fait de ne pas mettre en place 20 ports pour le partage d’application sur un client signifie qu’un utilisateur peut participer à 20 sessions de partage d’application sur l’appareil spécifié, tout en même temps. Cela doit s’avérer suffisant pour la grande majorité de vos utilisateurs.

Pour affecter les plages de ports précédentes à votre collection globale de paramètres de configuration de conférence, vous pouvez utiliser la commande Lync Server Management Shell suivante :

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Vous pouvez utiliser cette commande pour affecter ces mêmes plages de ports à tous vos paramètres de configuration de conférence :

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Les utilisateurs individuels doivent se déconnecter de Lync, puis se reconnecter pour que ces modifications prennent effet.

<div>


> [!NOTE]  
> Vous pouvez également activer les plages de ports multimédias client, puis affecter ces plages de ports à l’aide d’une seule commande. Par exemple :<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

