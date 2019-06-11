---
title: 'Affichage Lync Server 2013: ConferenceMessageCount'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0324c9913a607057c4e1cd161a9040b83d6bd29b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a>Affichage ConferenceMessageCount dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

Le mode ConferenceMessageCount stocke les informations sur le nombre de messages envoyés par un utilisateur à une conférence. Cet affichage a été présenté dans Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Le mode ConferenceMessageCount contient toutes les colonnes de la <A href="lync-server-2013-conferencesessiondetails-view.md">vue ConferenceSessionDetails dans Lync Server 2013</A> , en plus des colonnes répertoriées ci-dessous.



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’utilisateur qui a envoyé le message.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur qui a envoyé les messages. Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>identificateur</p></td>
<td><p>Client de l’utilisateur qui a envoyé les messages. Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserMessageCount</strong></p></td>
<td><p>type</p></td>
<td><p>Nombre de messages envoyés par l’utilisateur au cours de la session de conférence.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

