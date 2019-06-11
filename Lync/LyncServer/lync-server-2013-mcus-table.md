---
title: 'Lync Server 2013 : Table Mcus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf0a34d24bf60770f2b1e2664a89993f5917d854
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="cebb0-102">Table Mcus dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cebb0-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cebb0-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cebb0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cebb0-104">La table MCU est une table de support.</span><span class="sxs-lookup"><span data-stu-id="cebb0-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="cebb0-105">Chaque enregistrement stocke les informations relatives à un service de conférence.</span><span class="sxs-lookup"><span data-stu-id="cebb0-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="cebb0-106">Il peut s’agir du service de conférence par messagerie instantanée et du service de conférence téléphonique (qui s’exécutent sous forme de processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="cebb0-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cebb0-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="cebb0-107">Column</span></span></th>
<th><span data-ttu-id="cebb0-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="cebb0-108">Data Type</span></span></th>
<th><span data-ttu-id="cebb0-109">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="cebb0-109">Key/Index</span></span></th>
<th><span data-ttu-id="cebb0-110">Détails</span><span class="sxs-lookup"><span data-stu-id="cebb0-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cebb0-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="cebb0-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="cebb0-112">int</span><span class="sxs-lookup"><span data-stu-id="cebb0-112">int</span></span></p></td>
<td><p><span data-ttu-id="cebb0-113">Principal</span><span class="sxs-lookup"><span data-stu-id="cebb0-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="cebb0-114">Numéro unique identifiant ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="cebb0-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cebb0-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="cebb0-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cebb0-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cebb0-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cebb0-117"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="cebb0-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="cebb0-118">inyint</span><span class="sxs-lookup"><span data-stu-id="cebb0-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="cebb0-119"> Externes</span><span class="sxs-lookup"><span data-stu-id="cebb0-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="cebb0-120">Le type de serveur de conférence, tel que conf: chat (pour les messages instantanés) ou conf: audio-vidéo.</span><span class="sxs-lookup"><span data-stu-id="cebb0-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="cebb0-121">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cebb0-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

