---
title: 'Lync Server 2013 : surveillance de la conversation de groupe'
description: 'Lync Server 2013 : surveillance de la conversation de groupe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625e45f455e8dba50a5fa64240b62cb010623d16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562030"
---
# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="06ff1-103">Surveillance de la conversation de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06ff1-103">Monitoring group chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06ff1-104">_**Dernière modification de la rubrique :** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="06ff1-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="06ff1-105">Nous vous recommandons vivement d’exécuter le [programme d’installation de mise à jour de serveur](https://support.microsoft.com/kb/968802) le plus récent disponible sur le centre de téléchargement Microsoft pour en améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="06ff1-105">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="06ff1-106">En supposant que vous exécutez la dernière mise à jour cumulative, utilisez le tableau test de contrainte suivant pour les mesures à comprendre si vos serveurs de conversation de groupe fonctionnent au niveau de l’intégrité.</span><span class="sxs-lookup"><span data-stu-id="06ff1-106">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="06ff1-107">Environnement de test et modèle utilisateur</span><span class="sxs-lookup"><span data-stu-id="06ff1-107">Test environment and user model</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06ff1-108">Trois serveurs de conversation de groupe dans un pool de conversation de groupe, chacun avec une mémoire de 8 Go et 8 processeurs.</span><span class="sxs-lookup"><span data-stu-id="06ff1-108">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06ff1-109">Deux serveurs frontaux Lync Server 2013 dans Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="06ff1-109">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06ff1-110">60 000 utilisateurs simultanés sur trois serveurs de conversation de groupe.</span><span class="sxs-lookup"><span data-stu-id="06ff1-110">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06ff1-111">25 000 canaux hébergés par le pool de conversation de groupe.</span><span class="sxs-lookup"><span data-stu-id="06ff1-111">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06ff1-112">Taille du canal :</span><span class="sxs-lookup"><span data-stu-id="06ff1-112">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="06ff1-113">Taille des petits canaux : 30</span><span class="sxs-lookup"><span data-stu-id="06ff1-113">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="06ff1-114">Taille moyenne des canaux : 150</span><span class="sxs-lookup"><span data-stu-id="06ff1-114">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="06ff1-115">Taille de canal large : 2500</span><span class="sxs-lookup"><span data-stu-id="06ff1-115">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06ff1-116">Nombre de canaux :</span><span class="sxs-lookup"><span data-stu-id="06ff1-116">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="06ff1-117">Nombre petites canaux : 24 000</span><span class="sxs-lookup"><span data-stu-id="06ff1-117">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="06ff1-118">Nombre moyen canaux 800</span><span class="sxs-lookup"><span data-stu-id="06ff1-118">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="06ff1-119">Nombre grandes canaux 24</span><span class="sxs-lookup"><span data-stu-id="06ff1-119">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="06ff1-120">Nombre total de canaux 24 824</span><span class="sxs-lookup"><span data-stu-id="06ff1-120">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06ff1-121">Canaux d’invitation :</span><span class="sxs-lookup"><span data-stu-id="06ff1-121">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="06ff1-122">La moitié des canaux ont été des canaux d’invitation</span><span class="sxs-lookup"><span data-stu-id="06ff1-122">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06ff1-123">Nombre de canaux qu’un utilisateur rejoint :</span><span class="sxs-lookup"><span data-stu-id="06ff1-123">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="06ff1-124">Petit : 12</span><span class="sxs-lookup"><span data-stu-id="06ff1-124">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="06ff1-125">Moyenne : 2</span><span class="sxs-lookup"><span data-stu-id="06ff1-125">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="06ff1-126">Grande : 1</span><span class="sxs-lookup"><span data-stu-id="06ff1-126">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06ff1-127">Taux de participation :</span><span class="sxs-lookup"><span data-stu-id="06ff1-127">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="06ff1-128">10 au total/seconde, 3,33/seconde par serveur</span><span class="sxs-lookup"><span data-stu-id="06ff1-128">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06ff1-129">Taux de déconnexion :</span><span class="sxs-lookup"><span data-stu-id="06ff1-129">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="06ff1-130">10 au total/seconde, 3,33/seconde par serveur</span><span class="sxs-lookup"><span data-stu-id="06ff1-130">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06ff1-131">Taux de conversation :</span><span class="sxs-lookup"><span data-stu-id="06ff1-131">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="06ff1-132">20 Total/seconde, 6.66/seconde par serveur</span><span class="sxs-lookup"><span data-stu-id="06ff1-132">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="06ff1-133">Les numéros de compteur de performances suivants seront susceptibles de varier lorsque différentes spécifications matérielles ou profils utilisateur sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="06ff1-133">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="06ff1-134">Compteur de performances à surveiller</span><span class="sxs-lookup"><span data-stu-id="06ff1-134">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06ff1-135">Compteur de performance</span><span class="sxs-lookup"><span data-stu-id="06ff1-135">Performance Counter</span></span></th>
<th><span data-ttu-id="06ff1-136">Seuils</span><span class="sxs-lookup"><span data-stu-id="06ff1-136">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06ff1-137">Processus (ChannelService)- &gt; % temps processeur</span><span class="sxs-lookup"><span data-stu-id="06ff1-137">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="06ff1-138">Min : 0</span><span class="sxs-lookup"><span data-stu-id="06ff1-138">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

