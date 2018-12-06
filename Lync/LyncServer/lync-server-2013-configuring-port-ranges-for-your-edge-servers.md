---
title: Configuration des plages de ports pour vos serveurs Edge
TOCTitle: Configuration des plages de ports pour vos serveurs Edge
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204996(v=OCS.15)
ms:contentKeyID: 49297591
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des plages de ports pour vos serveurs Edge

 

_**Dernière rubrique modifiée :** 2015-07-24_

Avec les serveurs Edge, il n’est pas nécessaire de configurer des plages de ports distinctes pour l’audio, la vidéo et le partage d’application ; de même, les plages de ports utilisées pour les serveurs Edge n’ont pas besoin de correspondre à celles utilisées avec vos serveurs de conférence, d’applications et de médiation. En revanche, pour faciliter l’administration, vous pouvez modifier les plages de ports de vos serveurs Edge afin qu’elles correspondent à celles de vos autres serveurs. Par exemple, supposons que vous ayez configuré vos serveurs de conférence, d’applications et de médiation afin d’utiliser ces plages de ports :


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


Comme vous pouvez le voir, vos plages de ports pour l’audio, la vidéo et le partage d’application commencent au port 40803 et englobent un total de 24 732 ports. Si vous préférez, vous pouvez configurer un serveur Edge donné afin d’utiliser ces valeurs de ports globales en exécutant une commande similaire à celle-ci depuis Lync Server Management Shell :

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Ou utilisez la commande suivante pour configurer simultanément tous les serveurs Edge de votre organisation :

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Vous pouvez vérifier les paramètres de port actuels de vos serveurs Edge à l’aide de cette commande Lync Server Management Shell :

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

