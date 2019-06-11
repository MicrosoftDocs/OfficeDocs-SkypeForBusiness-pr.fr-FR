---
title: 'Lync Server 2013: vue multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ec4b80cc790068029a286a54d26a59a35fc125
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="2316d-102">Vue multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2316d-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2316d-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2316d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2316d-104">Le mode multimédia stocke les informations relatives à un type de média utilisé dans une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="2316d-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="2316d-105">Une session serait représentée par plusieurs enregistrements dans la table, si plusieurs types de média sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="2316d-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="2316d-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2316d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2316d-107">Le mode multimédia ne doit pas être utilisé pour calculer la durée du média pour une session.</span><span class="sxs-lookup"><span data-stu-id="2316d-107">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="2316d-108">Cet affichage contient les détails de signalisation d’échange de médias dans une session.</span><span class="sxs-lookup"><span data-stu-id="2316d-108">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="2316d-109">L’échange de média est effectué par la demande d’invitation, et la durée de StartTime indique l’heure d’envoi de l’invitation. La durée d’invitation ne correspond pas nécessairement à l’heure de début du média, car le contenu multimédia ne démarre qu’après acceptation de la session.</span><span class="sxs-lookup"><span data-stu-id="2316d-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="2316d-110">La vue multimédia contient toutes les colonnes de la [vue SessionDetails dans Lync Server 2013](lync-server-2013-sessiondetails-view.md) , en plus de celles répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2316d-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2316d-111">Colonne</span><span class="sxs-lookup"><span data-stu-id="2316d-111">Column</span></span></th>
<th><span data-ttu-id="2316d-112">Type de données</span><span class="sxs-lookup"><span data-stu-id="2316d-112">Data Type</span></span></th>
<th><span data-ttu-id="2316d-113">Détails</span><span class="sxs-lookup"><span data-stu-id="2316d-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2316d-114"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="2316d-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="2316d-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2316d-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2316d-116">Type de média.</span><span class="sxs-lookup"><span data-stu-id="2316d-116">Media type.</span></span> <span data-ttu-id="2316d-117">Pour plus d’informations, reportez-vous <a href="lync-server-2013-medialist-table.md">à la table de médiane dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2316d-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2316d-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="2316d-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2316d-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2316d-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="2316d-120">Temps d’envoi d’une demande de média.</span><span class="sxs-lookup"><span data-stu-id="2316d-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2316d-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="2316d-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2316d-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2316d-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="2316d-123">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="2316d-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

