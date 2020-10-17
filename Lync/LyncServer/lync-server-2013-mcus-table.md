---
title: 'Lync Server 2013 : table des MCU'
description: 'Lync Server 2013 : table des MCU.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0b5d0bcbebb5efc1d767776b4581b18d9f2ed18
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556480"
---
# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="89d87-103">Table MCU dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89d87-103">Mcus table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89d87-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="89d87-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="89d87-105">La table des MCU est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="89d87-105">The Mcus table is a supporting table.</span></span> <span data-ttu-id="89d87-106">Chaque enregistrement stocke des informations sur un service de conférence.</span><span class="sxs-lookup"><span data-stu-id="89d87-106">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="89d87-107">Ces éléments peuvent inclure le service de conférence par messagerie instantanée et le service de conférence téléphonique (qui s’exécutent en tant que processus sur les serveurs frontaux), le service de conférence Web et le service de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="89d87-107">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89d87-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="89d87-108">Column</span></span></th>
<th><span data-ttu-id="89d87-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="89d87-109">Data Type</span></span></th>
<th><span data-ttu-id="89d87-110">Clé/index</span><span class="sxs-lookup"><span data-stu-id="89d87-110">Key/Index</span></span></th>
<th><span data-ttu-id="89d87-111">Détails</span><span class="sxs-lookup"><span data-stu-id="89d87-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89d87-112"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="89d87-112"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="89d87-113">int</span><span class="sxs-lookup"><span data-stu-id="89d87-113">int</span></span></p></td>
<td><p><span data-ttu-id="89d87-114">Primaire</span><span class="sxs-lookup"><span data-stu-id="89d87-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="89d87-115">Numéro unique identifiant ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="89d87-115">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d87-116"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="89d87-116"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="89d87-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="89d87-117">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d87-118"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="89d87-118"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="89d87-119">inyint</span><span class="sxs-lookup"><span data-stu-id="89d87-119">inyint</span></span></p></td>
<td><p><span data-ttu-id="89d87-120"> Etranger</span><span class="sxs-lookup"><span data-stu-id="89d87-120"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="89d87-121">Type de serveur de conférence, tel que conf : chat (pour IMs) ou conf : audio-vidéo.</span><span class="sxs-lookup"><span data-stu-id="89d87-121">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="89d87-122">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="89d87-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

