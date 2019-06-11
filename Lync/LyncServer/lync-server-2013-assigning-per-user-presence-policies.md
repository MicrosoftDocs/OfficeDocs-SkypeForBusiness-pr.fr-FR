---
title: 'Lync Server 2013: attribution de stratégies de présence par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 905065e231869b4b6075fc1894e51c91df8f0aee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Attribution de stratégies de présence par utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-11_

Une politique de présence est un ensemble de limites et de restrictions qui influent sur la présence. Le tableau suivant décrit les paramètres de stratégie de présence disponibles dans Lync Server 2013.

### <a name="presence-policy-settings"></a>Paramètres de la stratégie de présence

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
<th>Nom d’affichage</th>
<th>Description</th>
<th>Type</th>
<th>Valeur</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>Nombre maximal d’abonnements aux catégories d’abonnés</p></td>
<td><p>Limite le nombre d’abonnements à des catégories d’abonnés. Par exemple, lorsque Communicator s’abonne à la présence d’un utilisateur, il obtient un abonnement de catégorie pour chaque carte de visite, données de calendrier, notes, services et catégories d’États.</p>
<p>La valeur 0 indique que l’utilisateur ou le contact ne peut pas s’abonner à d’autres utilisateurs.</p>
<div>

> [!NOTE]  
> Ce paramètre peut avoir une incidence considérable sur les performances s’il est défini sur un numéro élevé et l’utilisateur moyen a un grand nombre d’utilisateurs s’abonnant à sa présence.


</div></td>
<td><p>Entier</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>Nombre maximal d’alertes d’abonnement de présence en file d’attente</p></td>
<td><p>Limite le nombre d’entrées dans la table abonnés invites. Ce paramètre détermine le nombre maximal d’invites qui peuvent être mis en file d’attente pour un utilisateur donné. Par exemple, lorsque l’utilisateur A s’abonner à la présence de l’utilisateur B, il reçoit une invite indiquant que l’utilisateur A est désormais abonné à l’utilisateur B et une invite d’accusé de réception est créée dans la table des abonnés invités de l’utilisateur B. Après que l’utilisateur a accepté, ou accuse de réception, l’abonnement, l’invite d’accusé de réception est supprimée de la table des abonnés invites de l’utilisateur B.</p>
<p>La valeur 0 indique que l’utilisateur n’est pas invité à s’abonner à sa présence.</p></td>
<td><p>Entier ou jeton</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


Par défaut, la stratégie et le **service** **par défaut** : stratégies de présence moyenne sont installés lors du déploiement de Lync Server. Le tableau suivant décrit les paramètres spécifiques des deux stratégies de présence.

### <a name="presence-policies"></a>Politiques de présence

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
<td><p>Politique pour les utilisateurs typiques. Il s’agit de la stratégie de présence par défaut.</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>Service: moyen</p></td>
<td><p>Stratégie pour les applications qui requièrent davantage d’utilisateurs pour s’abonner à la présence de l’objet.</p></td>
<td><p>1000</p></td>
<td><p>0,4</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

