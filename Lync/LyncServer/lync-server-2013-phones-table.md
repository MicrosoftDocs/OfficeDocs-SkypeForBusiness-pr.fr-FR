---
title: 'Lync Server 2013 : table des téléphones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cf680ddd7e980cbcbd1437657d4a6ef87e17e46
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="a8c03-102">Table téléphones dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8c03-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8c03-103">_**Dernière modification de la rubrique :** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="a8c03-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="a8c03-104">La table téléphones est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a8c03-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="a8c03-105">Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP qui ont des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="a8c03-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8c03-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="a8c03-106">Column</span></span></th>
<th><span data-ttu-id="a8c03-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="a8c03-107">Data Type</span></span></th>
<th><span data-ttu-id="a8c03-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="a8c03-108">Key/Index</span></span></th>
<th><span data-ttu-id="a8c03-109">Détails</span><span class="sxs-lookup"><span data-stu-id="a8c03-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8c03-110"><strong>PhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="a8c03-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="a8c03-111">int</span><span class="sxs-lookup"><span data-stu-id="a8c03-111">int</span></span></p></td>
<td><p><span data-ttu-id="a8c03-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="a8c03-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a8c03-113">Numéro unique identifiant ce téléphone.</span><span class="sxs-lookup"><span data-stu-id="a8c03-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8c03-114"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="a8c03-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a8c03-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a8c03-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a8c03-116">Numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="a8c03-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8c03-117"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="a8c03-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="a8c03-118">dateTime</span><span class="sxs-lookup"><span data-stu-id="a8c03-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a8c03-119">Horodatage (réservé à un usage interne).</span><span class="sxs-lookup"><span data-stu-id="a8c03-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="a8c03-120">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8c03-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

