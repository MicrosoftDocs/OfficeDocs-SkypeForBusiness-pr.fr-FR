---
title: 'Lync Server 2013 : vue multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a760e3113cf12eceaa9f60c829b4d6a4a714ea25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="a9a49-102">Vue multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9a49-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9a49-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a9a49-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a9a49-104">La vue Media stocke des informations sur un type de média utilisé au cours d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="a9a49-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="a9a49-105">Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="a9a49-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="a9a49-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9a49-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a9a49-p102">La vue Media ne doit pas être utilisée pour calculer la durée du média lors d’une session. Cette vue contient les détails de signalisation de l’échange multimédia lors d’une session. L’échange multimédia est effectué par la requête INVITE et StartTime indique l’heure à laquelle la requête INVITE a été envoyée. L’heure d’invitation ne signifie pas nécessairement l’heure de début du média, car le média démarre seulement une fois la session acceptée.</span><span class="sxs-lookup"><span data-stu-id="a9a49-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="a9a49-110">La vue multimédia contient toutes les colonnes de la [vue SessionDetails dans Lync Server 2013](lync-server-2013-sessiondetails-view.md) , en plus de celles répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a9a49-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9a49-111">Colonne</span><span class="sxs-lookup"><span data-stu-id="a9a49-111">Column</span></span></th>
<th><span data-ttu-id="a9a49-112">Type de données</span><span class="sxs-lookup"><span data-stu-id="a9a49-112">Data Type</span></span></th>
<th><span data-ttu-id="a9a49-113">Détails</span><span class="sxs-lookup"><span data-stu-id="a9a49-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9a49-114"><strong>Support</strong></span><span class="sxs-lookup"><span data-stu-id="a9a49-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="a9a49-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9a49-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9a49-116">Type de média.</span><span class="sxs-lookup"><span data-stu-id="a9a49-116">Media type.</span></span> <span data-ttu-id="a9a49-117">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialist-table.md">table médial dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a9a49-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9a49-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="a9a49-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a9a49-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="a9a49-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="a9a49-120">Heure d’envoi d’une demande multimédia.</span><span class="sxs-lookup"><span data-stu-id="a9a49-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9a49-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="a9a49-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a9a49-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="a9a49-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="a9a49-123">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="a9a49-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

