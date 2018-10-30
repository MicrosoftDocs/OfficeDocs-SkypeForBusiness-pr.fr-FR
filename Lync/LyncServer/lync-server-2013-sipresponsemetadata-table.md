---
title: Table SIPResponseMetaData dans Lync Server 2013
TOCTitle: Table SIPResponseMetaData dans Lync Server 2013
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205294(v=OCS.15)
ms:contentKeyID: 49298880
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table SIPResponseMetaData dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table SIPResponseMetaDataTable contient la liste des codes de réponse SIP et les classification et définition de chacun de ces codes. Ceux-ci sont générés en réponse aux événements affectant les périphériques SIP et les sessions de communication SIP. Par exemple, le code de réponse 403 est généré quand un périphérique SIP effectue une requête, mais que le serveur refuse d’honorer cette requête.

Cette table est une nouveauté de Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Clé/Index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Valeur numérique qui représente le code de réponse SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Class</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Classification générale pour le code de réponse. Les classifications comprennent :</p>
<ul>
<li><p>1 – Réponses informatives</p></li>
<li><p>2 – Réponses réussies</p></li>
<li><p>3 – Réponses de redirection</p></li>
<li><p>4 – Réponses d’échec de client</p></li>
<li><p>5 -- Réponses d’échec de serveur</p></li>
<li><p>6 – Réponse d’échec global</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Description du code de réponse SIP. Par exemple, le code de réponse 181 a la description suivante :</p>
<p>L’appel est en cours de transfert</p></td>
</tr>
</tbody>
</table>

