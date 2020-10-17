---
title: 'Lync Server 2013 : règles de traduction'
description: 'Lync Server 2013 : règles de traduction.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65ee21459123ea09f54eb52e65a4d9ecba61c386
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549040"
---
# <a name="translation-rules-in-lync-server-2013"></a>Règles de conversion dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Lync Server 2013 Enterprise Voice nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 dans le but d’effectuer une recherche inversée des numéros (RNL). Dans Microsoft Lync Server 2010, les règles de traduction sont prises en charge uniquement pour les numéros appelés. Nouveauté de Microsoft Lync Server 2013, les règles de traduction sont également prises en charge pour les numéros d’appel. L' *homologue de jonction* (c’est-à-dire, la passerelle associée, le PBX ou la jonction SIP) peut exiger que les numéros soient au format de numérotation local. Pour convertir des nombres au format E. 164 en un format de numérotation local, vous pouvez définir une ou plusieurs règles de traduction pour manipuler l’URI de la demande avant de l’acheminer vers l’homologue de jonction. Par exemple, vous pouvez rédiger une règle de traduction pour remplacer « +44 » au début de la chaîne de numérotation par « 0144 ».

En effectuant une traduction de l’itinéraire sortant sur le serveur, vous pouvez réduire la configuration requise sur chaque homologue de jonction afin de convertir les numéros de téléphone dans un format de numérotation local. Lorsque vous planifiez les passerelles, ainsi que le nombre de passerelles, à associer à un cluster de serveurs de médiation spécifique, il peut être utile de regrouper des homologues de jonction avec des exigences de numérotation locale similaires. Cela peut réduire le nombre de règles de traduction requises et le temps nécessaire pour les écrire.

<div>


> [!IMPORTANT]  
> L’Association d’une ou de plusieurs règles de traduction à une configuration de jonction voix entreprise doit être utilisée à la place de la configuration des règles de traduction sur l’homologue de jonction. N’associez pas de règles de conversion à une configuration de jonction voix entreprise si vous avez configuré des règles de traduction sur l’homologue de jonction, car les deux règles peuvent entrer en conflit.



</div>

<div>

## <a name="example-translation-rules"></a>Exemples de règles de traduction

Les exemples de règles de conversion suivants montrent comment vous pouvez développer des règles sur le serveur pour traduire des nombres d’un format E. 164 vers un format local pour l’homologue de jonction.

Pour plus d’informations sur la façon d’implémenter des règles de traduction, voir [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.


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
<p>(supprimer le signe « + »)</p></td>
<td><p>+ 1</p></td>
<td><p>Exactement 12</p></td>
<td><p>0,1</p></td>
<td><p>0</p></td>
<td><p>^\+(1 \ d {10} ) $</p></td>
<td><p>$1</p></td>
<td><p>+ 14255551010 devient 14255551010</p></td>
</tr>
<tr class="even">
<td><p>Numérotation longue distance pour les États-Unis internationaux</p>
<p>(supprimer' + 'et ajouter 011)</p></td>
<td><p>+</p></td>
<td><p>Au moins 11</p></td>
<td><p>0,1</p></td>
<td><p>011</p></td>
<td><p>^\+(\d {9} \d +) $</p></td>
<td><p>011 $1</p></td>
<td><p>+ 441235551010 devient 011441235551010</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

