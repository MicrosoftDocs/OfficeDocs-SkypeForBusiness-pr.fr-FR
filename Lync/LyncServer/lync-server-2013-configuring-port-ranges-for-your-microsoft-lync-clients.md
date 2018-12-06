---
title: Configuration des plages de ports pour vos clients Microsoft Lync
TOCTitle: Configuration des plages de ports pour vos clients Microsoft Lync
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204760(v=OCS.15)
ms:contentKeyID: 49296677
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des plages de ports pour vos clients Microsoft Lync

 

_**Dernière rubrique modifiée :** 2015-03-09_

Par défaut, les applications clientes Lync impliquées dans une session de communication peuvent utiliser n’importe quel port entre 1024 et 65535. En effet, certaines plages de ports ne sont pas automatiquement activées pour les clients. Toutefois, pour pouvoir utiliser la qualité de service, vous devrez réaffecter les différents types de trafic (audio, vidéo, multimédia, partage d’applications et transfert de fichiers) à une série de plages de ports uniques. Pour cela, utilisez l’applet de commande Set-CsConferencingConfiguration.

Vous pouvez déterminer les plages de ports actuellement utilisées pour les sessions de communication en exécutant la commande suivante dans Microsoft Lync Server 2013 Management Shell :

    Get-CsConferencingConfiguration

Supposons que vous n’avez apporté aucune modification à vos paramètres de conférence depuis l’installation de Lync Server 2013, vous devez obtenir des informations comprenant ces valeurs de propriété :

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Deux éléments importants sont à noter dans la sortie précédente. Tout d’abord, la propriété ClientMediaPortRangeEnabled est définie sur False :

    ClientMediaPortRangeEnabled : False

Ce détail a son importance car, quand la propriété est définie sur False, les clients Lync impliqués dans une session de communication utilisent tout port disponible entre les ports 1024 et 65535. Cela se vérifie quels que soient les autres paramètres des ports (par exemple, ClientMediaPort ou ClientVideoPort). Si vous voulez limiter l’utilisation à un ensemble spécifique de ports (par exemple, si vous planifiez l’implémentation de la qualité de service), vous devez alors d’abord activer des plages de ports multimédias clients. Pour ce faire, utilisez la commande Windows PowerShell suivante :

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

La commande précédente active les plages de ports multimédias clients pour la collection globale des paramètres de configuration de conférence. Toutefois, ces paramètres peuvent aussi être appliqués au niveau du site et/ou au niveau du service (pour le service de serveurs de conférence uniquement). Pour activer des plages de ports multimédias clients pour un site ou serveur spécifique, indiquez l’identité de ce site ou serveur quand vous appelez Set-CsConferencingConfiguration :

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Vous pouvez aussi utiliser cette commande pour activer simultanément des plages de ports pour tous vos paramètres de configuration de conférence :

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

La deuxième chose importante à remarquer dans cette sortie est que les plages de ports multimédias définies pour chaque type de trafic réseau sont généralement identiques :

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Pour implémenter la qualité de service, chacune de ces plages de ports doit être unique. Par exemple, vous pouvez configurer les plages de ports de la façon suivante :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de trafic client</th>
<th>Port de début</th>
<th>Plage de ports</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Vidéo</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Partage d’application</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Transfert de fichiers</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


Dans la table précédente, les plages de ports clients représentent un sous-ensemble des plages de ports configurées pour vos serveurs. Par exemple, le partage d’application sur les serveurs a été configuré pour utiliser les ports 40803 à 49151, alors que sur les ordinateurs clients, il est configuré pour utiliser les ports 42000 à 42019. Le but de cette configuration est avant tout de simplifier la gestion de la qualité de service : les ports clients n’ont pas besoin de représenter un sous-ensemble des ports utilisés sur le serveur. (Par exemple, sur les ordinateurs clients vous pouvez configurer le partage d’application pour qu’il utilise les ports 10000 à 10019). Toutefois, il est recommandé que vos plages de ports clients soient un sous-ensemble des plages de ports de vos serveurs.

Par ailleurs, vous avez peut-être remarqué que 8348 ports sont réservés au partage d’application sur les serveurs, contre seulement 20 ports pour le partage d’application sur les clients. Cette configuration est également recommandée, mais il ne s’agit pas d’une règle inflexible. En général, tout port disponible peut être envisagé pour représenter une seule session de communication : si vous avez 100 ports disponibles dans une plage de ports, l’ordinateur concerné peut potentiellement participer à 100 sessions de communication maximum à tout moment. Les serveurs étant susceptibles de participer à bien plus de conversations que les clients, il paraît logique d’ouvrir davantage de ports sur les serveurs que sur les clients. Les 20 ports réservés au partage d’application sur un client signifient qu’un utilisateur peut potentiellement participer à 20 sessions de partage d’application simultanées sur l’appareil spécifié. C’est amplement suffisant pour la grande majorité de vos utilisateurs.

Pour affecter les plages de ports précédentes à votre collection globale de paramètres de configuration de conférence, vous pouvez utiliser la commande Lync Server Management Shell suivante :

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Ou bien, utilisez cette commande pour affecter ces mêmes plages de ports à tous vos paramètres de configuration de conférence :

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Les utilisateurs individuels doivent se déconnecter de Lync, puis se reconnecter pour que ces modifications puissent prendre effet.

> [!NOTE]  
> Vous pouvez aussi activer les plages de ports multimédias clients, puis les affecter à l’aide d’une seule commande. Par exemple :<br />
<code>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</code>
