---
title: 'Lync Server 2013 : attribution de stratégies de présence par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4ae464e37c7d4061c9a7311d7df427b7a66db1c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Affectation de stratégies de présence par utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-11_

Une stratégie de présence est un ensemble de limites et de restrictions qui affectent la présence. Le tableau suivant décrit les paramètres de stratégie de présence disponibles dans Lync Server 2013.

### <a name="presence-policy-settings"></a>Paramètres de stratégie de présence

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom XML</th>
<th>Nom d'affichage</th>
<th>Description</th>
<th>Type</th>
<th>Valeur</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>Nombre maximum d’abonnements aux catégories d’abonnés</p></td>
<td><p>Limite le nombre d’abonnements aux catégories d’abonnés Par exemple, lorsque Communicator s’abonne à la présence d’un utilisateur, il obtient un abonnement aux catégories pour chaque carte de visite, données de calendrier, notes, services et catégories d’état.</p>
<p>Un paramètre de 0 signifie que l’objet contact ou utilisateur ne peut pas être souscrit par d’autres.</p>
<div>

> [!NOTE]  
> Ce paramètre peut avoir un impact significatif sur les performances s’il est défini sur une valeur élevée, et l’utilisateur moyen a un grand nombre d’utilisateurs qui s’abonnent à sa présence.


</div></td>
<td><p>Entier</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>Nombre maximal d’alertes d’abonnement de présence mises en file d’attente</p></td>
<td><p>Limite le nombre d’entrées dans la table des abonnés alertés. Ce paramètre détermine le nombre maximum d’alertes pouvant être mises en file d’attente pour un utilisateur donné. Par exemple, lorsque l’utilisateur A s’abonne à la présence de l’utilisateur B, ce dernier reçoit une alerte l’informant que l’utilisateur A est abonné à l’utilisateur B, et un accusé de réception est créé dans la table des abonnés alertés de l’utilisateur B. Lorsque l’utilisateur B accepte ou accuse réception de l’abonnement, l’alerte d’accusé de réception est supprimée de la table des abonnées alertés de l’utilisateur B.</p>
<p>Un paramètre de 0 signifie que l’utilisateur n’est pas alerté lorsque quelqu’un s’abonne à sa présence.</p></td>
<td><p>Entier ou jeton</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


Par défaut, la stratégie et le **service** **par défaut** : les stratégies de présence moyennes sont installées lorsque vous déployez Lync Server. Le tableau suivant décrit les paramètres spécifiques des deux stratégies de présence.

### <a name="presence-policies"></a>Stratégies de présence

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de la stratégie</th>
<th>Description</th>
<th>CategorySubscriptions</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Stratégie par défaut</p></td>
<td><p>Stratégies pour les utilisateurs types. Il s’agit de la stratégie de présence par défaut.</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>Service : moyen</p></td>
<td><p>Stratégie pour les applications qui ont besoin que plusieurs utilisateurs s’abonnent à la présence de l’objet.</p></td>
<td><p>1000</p></td>
<td><p>0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

