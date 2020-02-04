---
title: 'Lync Server 2013 : règles de traduction'
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
ms.openlocfilehash: d4ae330633acb04a35abe19356f4b00ff09ef41a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Règles de traduction dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Lync Server 2013 voix entreprise nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 pour pouvoir exécuter la recherche de numéro inverse (RNL). Dans Microsoft Lync Server 2010, les règles de traduction sont uniquement prises en charge pour les numéros appelés. Les règles de traduction suivantes sont également prises en charge dans Microsoft Lync Server 2013 pour les numéros d’appel. L’*homologue de jonction* (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 au format de numérotation local, vous pouvez définir une ou plusieurs règles de conversion pour manipuler l’URI demandé avant de l’acheminer vers l’homologue de jonction. Par exemple, vous pouvez rédiger une règle pour supprimer la valeur « +44 » au début de la chaîne de numérotation et la remplacer par « 0144 ».

En effectuant une conversion de l’itinéraire sortant sur le serveur, vous pouvez réduire les exigences de configuration sur chaque homologue de jonction afin de convertir les numéros de téléphone dans un format de numérotation local. Lorsque vous planifiez les passerelles et le nombre de passerelles à associer à un cluster de serveurs de médiation spécifique, il est possible que les homologues de groupe puissent s’avérer utiles pour la numérotation locale. En effet, cela peut réduire le nombre de règles de conversion requises et le temps nécessaire pour les rédiger.

<div>


> [!IMPORTANT]  
> L’Association d’une ou plusieurs règles de traduction à une configuration de Trunk voix entreprise doit être utilisée comme alternative à la configuration de règles de traduction sur l’homologue de Trunk. N’associez pas de règles de traduction à une configuration de Trunk vocale d’entreprise si vous avez configuré des règles de traduction sur l’homologue de Trunk, car les deux règles peuvent entrer en conflit.



</div>

<div>

## <a name="example-translation-rules"></a>Exemples de règles de conversion

Les exemples de règles de conversion suivantes vous montrent comment développer des règles sur le serveur pour convertir des numéros du format E.164 au format local pour un homologue de jonction.

Pour plus d’informations sur l’implémentation des règles de traduction, voir [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.


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
<td><p>0,4</p></td>
<td><p>^\+(1{10}</p></td>
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
<td><p>^\+(\d{9}\d +) $</p></td>
<td><p>011$1</p></td>
<td><p>+441235551010 devient 011441235551010</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

