---
title: 'Lync Server 2013 : Règles de conversion'
TOCTitle: Règles de conversion
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398520(v=OCS.15)
ms:contentKeyID: 49297542
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Règles de conversion dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lync Server 2013Voix Entreprise exige que toutes les chaînes de numérotation adoptent le format standard E.164 pour des besoins de recherche de numéros inverse. Dans Microsoft Lync Server 2010, les règles de conversion sont uniquement prises en charge pour les numéros appelés. En revanche, dans Microsoft Lync Server 2013, elles sont désormais aussi prises en charge pour les numéros appelés. L’*homologue de jonction* (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 au format de numérotation local, vous pouvez définir une ou plusieurs règles de conversion pour manipuler l’URI demandé avant de l’acheminer vers l’homologue de jonction. Par exemple, vous pouvez rédiger une règle pour supprimer la valeur « +44 » au début de la chaîne de numérotation et la remplacer par « 0144 ».

En effectuant une conversion de l’itinéraire sortant sur le serveur, vous pouvez réduire les exigences de configuration sur chaque homologue de jonction afin de convertir les numéros de téléphone dans un format de numérotation local. Lorsque vous planifiez la quantité et le type de passerelles à associer avec un cluster de serveur de médiation spécifique, il peut s’avérer utile de regrouper les homologues de jonction avec les exigences de numérotation locale similaires. En effet, cela peut réduire le nombre de règles de conversion requises et le temps nécessaire pour les rédiger.

> [!IMPORTANT]  
> L’association d’une ou plusieurs règles de conversion avec une configuration de jonction Voix Entreprise doit être utilisée comme alternative à la configuration des règles de conversion sur un homologue de jonction. N’associez pas de règles de conversion avec une configuration de jonction Voix Entreprise si vous avez configuré les règles de conversion sur l’homologue de jonction, car les deux règles risqueraient de provoquer un conflit.

## Exemples de règles de conversion

Les exemples de règles de conversion suivantes vous montrent comment développer des règles sur le serveur pour convertir des numéros du format E.164 au format local pour un homologue de jonction.

Pour plus d’informations sur l’implémentation des règles de conversion, reporrtez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Chiffres de début</th>
<th>Longueur</th>
<th>Chiffres à supprimer</th>
<th>Chiffres à ajouter</th>
<th>Modèle de correspondance</th>
<th>Conversion</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Numérotation longue distance conventionnelle aux États-Unis</p>
<p>(supprimer le signe ’+’)</p></td>
<td><p>+1</p></td>
<td><p>12 exactement</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+(1\d{10})$</p></td>
<td><p>$1</p></td>
<td><p>+14255551010 devient 14255551010</p></td>
</tr>
<tr class="even">
<td><p>Numérotation longue distance internationale aux États-Unis</p>
<p>(supprimer le signe ’+’ et ajouter 011)</p></td>
<td><p>+</p></td>
<td><p>11 au moins</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+(\d{9}\d+)$</p></td>
<td><p>011$1</p></td>
<td><p>+441235551010 devient 011441235551010</p></td>
</tr>
</tbody>
</table>

