---
title: 'Lync Server 2013 : données d’affichage de QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f6d2b30654272baf0ce8db712461acb3e4f13a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="25979-102">QoE afficher les détails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25979-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25979-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="25979-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="25979-104">Les affichages couvrent les scénarios les plus courants pour le renvoi de données à partir de la base de données de QoE SQL.</span><span class="sxs-lookup"><span data-stu-id="25979-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="25979-105">Il s’agit des vues recommandées utilisées pour créer des rapports personnalisés au lieu d’accéder directement aux tables de base de données ; Cela est dû au fait que les vues ont plus de chances de conserver une compatibilité descendante avec les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="25979-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25979-106">Nom de la vue</span><span class="sxs-lookup"><span data-stu-id="25979-106">View Name</span></span></th>
<th><span data-ttu-id="25979-107">Description</span><span class="sxs-lookup"><span data-stu-id="25979-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25979-108"><a href="lync-server-2013-audiostreamdetail-view.md">Vue AudioStreamDetail dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25979-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="25979-109">Stocke les informations sur chaque flux audio dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="25979-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25979-110"><a href="lync-server-2013-medialine-view.md">Vue MediaLine dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25979-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="25979-111">Stocke des informations sur chaque ligne de média dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="25979-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="25979-112">Une session audio contient généralement une ligne de média audio.</span><span class="sxs-lookup"><span data-stu-id="25979-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="25979-113">Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo ; toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence ou la Vue Galerie est utilisé.</span><span class="sxs-lookup"><span data-stu-id="25979-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25979-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Vue NetworkConfigurationSettings dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25979-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="25979-115">Stocke des informations sur la configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="25979-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25979-116"><a href="lync-server-2013-session-view.md">Vue de session dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25979-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="25979-117">Stocke des informations sur les sessions disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="25979-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25979-118"><a href="lync-server-2013-useragent-view.md">Vue UserAgent dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25979-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="25979-119">Stocke des informations sur les agents utilisateurs qui ont participé à des sessions disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="25979-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25979-120"><a href="lync-server-2013-videostreamdetail-view.md">Vue VideoStreamDetail dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25979-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="25979-121">Stocke des informations sur chaque flux vidéo dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="25979-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

