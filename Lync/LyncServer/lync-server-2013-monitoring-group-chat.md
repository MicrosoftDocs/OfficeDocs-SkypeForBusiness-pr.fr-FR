---
title: 'Lync Server 2013 : surveillance de la conversation de groupe'
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
ms.openlocfilehash: a42589db677132170e9456c998d96fd2eb1de5d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="ea88b-102">Surveillance de la conversation de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea88b-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea88b-103">_**Dernière modification de la rubrique :** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="ea88b-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="ea88b-104">Nous vous recommandons vivement d’exécuter le [programme d’installation de mise à jour de serveur](https://support.microsoft.com/kb/968802) le plus récent disponible sur le centre de téléchargement Microsoft pour en améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="ea88b-104">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="ea88b-105">En supposant que vous exécutez la dernière mise à jour cumulative, utilisez le tableau test de contrainte suivant pour les mesures à comprendre si vos serveurs de conversation de groupe fonctionnent au niveau de l’intégrité.</span><span class="sxs-lookup"><span data-stu-id="ea88b-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="ea88b-106">Environnement de test et modèle utilisateur</span><span class="sxs-lookup"><span data-stu-id="ea88b-106">Test environment and user model</span></span>

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
<td><p><span data-ttu-id="ea88b-107">Trois serveurs de conversation de groupe dans un pool de conversation de groupe, chacun avec une mémoire de 8 Go et 8 processeurs.</span><span class="sxs-lookup"><span data-stu-id="ea88b-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea88b-108">Deux serveurs frontaux Lync Server 2013 dans Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="ea88b-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea88b-109">60 000 utilisateurs simultanés sur trois serveurs de conversation de groupe.</span><span class="sxs-lookup"><span data-stu-id="ea88b-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea88b-110">25 000 canaux hébergés par le pool de conversation de groupe.</span><span class="sxs-lookup"><span data-stu-id="ea88b-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea88b-111">Taille du canal :</span><span class="sxs-lookup"><span data-stu-id="ea88b-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea88b-112">Taille des petits canaux : 30</span><span class="sxs-lookup"><span data-stu-id="ea88b-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="ea88b-113">Taille moyenne des canaux : 150</span><span class="sxs-lookup"><span data-stu-id="ea88b-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="ea88b-114">Taille de canal large : 2500</span><span class="sxs-lookup"><span data-stu-id="ea88b-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea88b-115">Nombre de canaux :</span><span class="sxs-lookup"><span data-stu-id="ea88b-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea88b-116">Nombre petites canaux : 24 000</span><span class="sxs-lookup"><span data-stu-id="ea88b-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="ea88b-117">Nombre moyen canaux 800</span><span class="sxs-lookup"><span data-stu-id="ea88b-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="ea88b-118">Nombre grandes canaux 24</span><span class="sxs-lookup"><span data-stu-id="ea88b-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="ea88b-119">Nombre total de canaux 24 824</span><span class="sxs-lookup"><span data-stu-id="ea88b-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea88b-120">Canaux d’invitation :</span><span class="sxs-lookup"><span data-stu-id="ea88b-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea88b-121">La moitié des canaux ont été des canaux d’invitation</span><span class="sxs-lookup"><span data-stu-id="ea88b-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea88b-122">Nombre de canaux qu’un utilisateur rejoint :</span><span class="sxs-lookup"><span data-stu-id="ea88b-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea88b-123">Petit : 12</span><span class="sxs-lookup"><span data-stu-id="ea88b-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="ea88b-124">Moyenne : 2</span><span class="sxs-lookup"><span data-stu-id="ea88b-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="ea88b-125">Grande : 1</span><span class="sxs-lookup"><span data-stu-id="ea88b-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea88b-126">Taux de participation :</span><span class="sxs-lookup"><span data-stu-id="ea88b-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea88b-127">10 au total/seconde, 3,33/seconde par serveur</span><span class="sxs-lookup"><span data-stu-id="ea88b-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea88b-128">Taux de déconnexion :</span><span class="sxs-lookup"><span data-stu-id="ea88b-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea88b-129">10 au total/seconde, 3,33/seconde par serveur</span><span class="sxs-lookup"><span data-stu-id="ea88b-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea88b-130">Taux de conversation :</span><span class="sxs-lookup"><span data-stu-id="ea88b-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea88b-131">20 Total/seconde, 6.66/seconde par serveur</span><span class="sxs-lookup"><span data-stu-id="ea88b-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="ea88b-132">Les numéros de compteur de performances suivants seront susceptibles de varier lorsque différentes spécifications matérielles ou profils utilisateur sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="ea88b-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="ea88b-133">Compteur de performances à surveiller</span><span class="sxs-lookup"><span data-stu-id="ea88b-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea88b-134">Compteur de performance</span><span class="sxs-lookup"><span data-stu-id="ea88b-134">Performance Counter</span></span></th>
<th><span data-ttu-id="ea88b-135">Seuils</span><span class="sxs-lookup"><span data-stu-id="ea88b-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea88b-136">Processus (ChannelService)-&gt;% temps processeur</span><span class="sxs-lookup"><span data-stu-id="ea88b-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="ea88b-137">Min : 0</span><span class="sxs-lookup"><span data-stu-id="ea88b-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

