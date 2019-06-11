---
title: 'Lync Server 2013: configuration de plages de ports pour vos clients Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03cd4c109760756dd265526bd9d5285fdc9fed30
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Configuration de plages de ports pour vos clients Microsoft Lync dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-04-22_

Par défaut, les applications clientes Lync peuvent utiliser n’importe quel port entre les ports 1024 et 65535 lorsqu’une session de communication est utilisée. en effet, les plages de port spécifiques ne sont pas activées automatiquement pour les clients. Toutefois, pour pouvoir utiliser la qualité de service, vous devez réaffecter les différents types de trafic (audio, vidéo, média, partage d’application et transfert de fichier) à une série de plages de ports uniques. Pour ce faire, vous pouvez utiliser l’applet de passe Set-CsConferencingConfiguration.

<div>


> [!NOTE]  
> Les utilisateurs finaux ne peuvent pas apporter ces modifications. Les modifications de port ne peuvent être effectuées que par les administrateurs utilisant l’applet de cmdlet Set-CsConferencingConfiguration.



</div>

Vous pouvez déterminer les plages de ports actuellement utilisées pour les sessions de communication en exécutant la commande suivante à partir de Microsoft Lync Server 2013 Management Shell:

    Get-CsConferencingConfiguration

Si vous avez apporté des modifications à vos paramètres de conférence depuis que vous avez installé Lync Server 2013, vous devez obtenir des informations sur les propriétés suivantes:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Si vous observez de près la sortie précédente, vous verrez deux points importants. Tout d’abord, la propriété ClientMediaPortRangeEnabled est définie sur false:

    ClientMediaPortRangeEnabled : False

C’est important, car lorsque cette propriété est définie sur false, les clients Lync utiliseront tout port disponible entre 1024 et 65535 lorsqu’une session de communication sera utilisée. C’est vrai, quels que soient les autres paramètres de port (par exemple, ClientMediaPort ou ClientVideoPort). Si vous souhaitez restreindre l’utilisation à un ensemble spécifique de ports (ce que vous voulez faire si vous envisagez d’implémenter la qualité de service), vous devez d’abord activer les plages de port de média client. Vous pouvez effectuer cette opération à l’aide de la commande Windows PowerShell suivante:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

La commande précédente permet d’activer les plages de port de média client pour la collection globale de paramètres de configuration de conférence. Toutefois, ces paramètres peuvent également être appliqués à l’étendue du site et/ou à l’étendue du service (pour le service du serveur de conférence uniquement). Pour activer les plages de port de média client pour un site ou un serveur spécifique, spécifiez l’identité de ce site ou serveur lors de l’appel de Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Vous pouvez également utiliser cette commande pour activer simultanément les plages de ports pour tous les paramètres de configuration de la Conférence:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

Le deuxième élément important que vous remarquerez est que la sortie de l’exemple indique que, par défaut, les plages de ports multimédias définies pour chaque type de trafic réseau sont identiques:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Pour implémenter QoS, chacune de ces plages de port doit être unique. Par exemple, vous pouvez configurer les plages de ports comme suit:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de trafic client</th>
<th>Début du port</th>
<th>Plage de ports</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>CX3-20</p></td>
</tr>
<tr class="even">
<td><p>Vidéo</p></td>
<td><p>58000</p></td>
<td><p>CX3-20</p></td>
</tr>
<tr class="odd">
<td><p>Partage d'application</p></td>
<td><p>42000</p></td>
<td><p>CX3-20</p></td>
</tr>
<tr class="even">
<td><p>Transfert de fichiers</p></td>
<td><p>42020</p></td>
<td><p>CX3-20</p></td>
</tr>
</tbody>
</table>


Dans le tableau ci-dessus, les plages de port client représentent un sous-ensemble des plages de ports configurées pour vos serveurs. Par exemple, sur les serveurs, le partage d’application a été configuré de manière à utiliser les ports 40803 à 49151; sur les ordinateurs clients, le partage d’application est configuré de manière à utiliser les ports 42000 à 42019. Pour simplifier l’administration de la qualité de service (QoS), il n’est pas nécessaire de représenter un sous-ensemble de ports utilisés sur le serveur. (Par exemple, sur les ordinateurs clients, vous pouvez configurer le partage d’application à utiliser, par exemple, les ports 10000 à 10019.) Néanmoins, nous vous conseillons de faire en sorte que les plages de port de votre client constituent un sous-ensemble de vos plages de port serveur.

Par ailleurs, vous avez peut-être remarqué que les ports 8348 étaient mis de côté pour le partage d’application sur les serveurs, mais que seuls 20 ports étaient mis de côté pour le partage d’application sur les clients. C’est également recommandé, mais il ne s’agit pas d’une règle matérielle et rapide. En règle générale, vous pouvez considérer chaque port disponible pour représenter une seule session de communication: Si vous disposez de ports 100 disponibles dans une plage de ports qui signifie que l’ordinateur en question peut participer, au plus, des sessions de communication 100 à tout moment. Étant donné que les serveurs seront susceptibles de participer dans de nombreuses conversations qu’aux clients, il est préférable d’ouvrir de nombreux ports supplémentaires sur les serveurs plutôt que sur les clients. La mise en place de 20 ports pour le partage d’application sur un client implique qu’un utilisateur peut participer à 20 sessions de partage d’application sur l’appareil spécifié, en même temps. Cela devrait s’avérer suffisant pour la plupart de vos utilisateurs.

Pour affecter les plages de port précédentes à votre collection globale de paramètres de configuration de conférence, vous pouvez utiliser la commande Lync Server Management Shell suivante:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Vous pouvez utiliser cette commande pour affecter les mêmes plages de ports à tous les paramètres de configuration de la Conférence:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Les utilisateurs individuels doivent se déconnecter de Lync, puis reconnectez-vous pour que les modifications prennent effet.

<div>


> [!NOTE]  
> Vous pouvez également activer les plages de port de média client, puis les affecter à l’aide d’une seule commande. Par exemple :<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

