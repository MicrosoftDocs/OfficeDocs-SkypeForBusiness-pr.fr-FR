---
title: 'Lync Server 2013 : configuration des plages de ports pour vos serveurs Edge'
description: 'Lync Server 2013 : configuration des plages de ports pour vos serveurs Edge.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c085a5dbc32bbf56842984eae2ef8896ab895c65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548250"
---
# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="3809d-103">Configuration des plages de ports pour vos serveurs Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3809d-103">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3809d-104">_**Dernière modification de la rubrique :** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="3809d-104">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="3809d-105">Avec les serveurs Edge, il n’est pas nécessaire de configurer des plages de ports distinctes pour l’audio, la vidéo et le partage d’application ; de même, les plages de ports utilisées pour les serveurs Edge n’ont pas besoin de correspondre à celles utilisées avec vos serveurs de conférence, d’applications et de médiation.</span><span class="sxs-lookup"><span data-stu-id="3809d-105">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="3809d-106">Avant de poursuivre notre exemple, il est important de souligner que, lorsque cette option existe, nous vous recommandons de ne pas modifier les plages de ports, car cela peut avoir un impact négatif sur certains scénarios si vous quittez la plage de ports 50000.</span><span class="sxs-lookup"><span data-stu-id="3809d-106">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="3809d-107">Par exemple, supposons que vous ayez configuré vos serveurs de conférence, d’applications et de médiation afin d’utiliser ces plages de ports :</span><span class="sxs-lookup"><span data-stu-id="3809d-107">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3809d-108">Type de paquet</span><span class="sxs-lookup"><span data-stu-id="3809d-108">Packet Type</span></span></th>
<th><span data-ttu-id="3809d-109">Port de début</span><span class="sxs-lookup"><span data-stu-id="3809d-109">Starting Port</span></span></th>
<th><span data-ttu-id="3809d-110">Nombre de ports réservés</span><span class="sxs-lookup"><span data-stu-id="3809d-110">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3809d-111">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="3809d-111">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="3809d-112">40803</span><span class="sxs-lookup"><span data-stu-id="3809d-112">40803</span></span></p></td>
<td><p><span data-ttu-id="3809d-113">8348</span><span class="sxs-lookup"><span data-stu-id="3809d-113">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3809d-114">Audio</span><span class="sxs-lookup"><span data-stu-id="3809d-114">Audio</span></span></p></td>
<td><p><span data-ttu-id="3809d-115">49152</span><span class="sxs-lookup"><span data-stu-id="3809d-115">49152</span></span></p></td>
<td><p><span data-ttu-id="3809d-116">8348</span><span class="sxs-lookup"><span data-stu-id="3809d-116">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3809d-117">Vidéo</span><span class="sxs-lookup"><span data-stu-id="3809d-117">Video</span></span></p></td>
<td><p><span data-ttu-id="3809d-118">57500</span><span class="sxs-lookup"><span data-stu-id="3809d-118">57500</span></span></p></td>
<td><p><span data-ttu-id="3809d-119">8034</span><span class="sxs-lookup"><span data-stu-id="3809d-119">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3809d-120"><strong>Totaux</strong></span><span class="sxs-lookup"><span data-stu-id="3809d-120"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="3809d-121">24730</span><span class="sxs-lookup"><span data-stu-id="3809d-121">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3809d-122">Comme vous pouvez le voir, les plages de ports pour l’audio, la vidéo et le partage d’application commencent au port 40803 et englobent un total de 24732 ports.</span><span class="sxs-lookup"><span data-stu-id="3809d-122">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="3809d-123">Si vous préférez, vous pouvez configurer un serveur Edge donné afin d’utiliser ces valeurs de ports globales en exécutant une commande similaire à celle-ci depuis Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="3809d-123">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="3809d-124">Ou utilisez la commande suivante pour configurer simultanément tous les serveurs Edge de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="3809d-124">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="3809d-125">Vous pouvez vérifier les paramètres de port actuels de vos serveurs Edge à l’aide de cette commande Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="3809d-125">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="3809d-126">Encore une fois, pendant que nous fournissons ces options, nous vous recommandons vivement de laisser des choses comme pour la configuration de port.</span><span class="sxs-lookup"><span data-stu-id="3809d-126">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

