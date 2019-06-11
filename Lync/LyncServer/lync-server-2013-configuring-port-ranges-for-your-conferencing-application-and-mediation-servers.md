---
title: 'Lync Server 2013: configuration de plages de ports pour vos serveurs de conférence, d’application et de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5402da56fa646c6ae6e2247baa70a5ef03b851cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="58492-102">Configuration de plages de ports dans Lync Server 2013 pour vos serveurs de conférence, d’application et de médiation</span><span class="sxs-lookup"><span data-stu-id="58492-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58492-103">_**Dernière modification de la rubrique:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="58492-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="58492-104">Pour implémenter la qualité de service, vous devez configurer des plages de port identiques pour le partage audio, vidéo et d’application sur vos serveurs de conférence, d’application et de médiation. de plus, ces plages de port ne doivent pas se chevaucher de quelque manière que ce soit.</span><span class="sxs-lookup"><span data-stu-id="58492-104">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="58492-105">Par exemple, vous pouvez utiliser les ports 10000 à 10999 pour la vidéo sur vos serveurs de conférence.</span><span class="sxs-lookup"><span data-stu-id="58492-105">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="58492-106">Cela signifie que vous devez également réserver les ports 10000 à 10999 pour la vidéo sur vos serveurs d’application et de médiation.</span><span class="sxs-lookup"><span data-stu-id="58492-106">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="58492-107">Si ce n’est pas le cas, QoS ne fonctionnera pas comme prévu.</span><span class="sxs-lookup"><span data-stu-id="58492-107">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="58492-108">De même, supposons que vous réservez les ports 10000 à 10999 pour la vidéo, mais que vous réservez les ports 10500 à 11999 pour le son.</span><span class="sxs-lookup"><span data-stu-id="58492-108">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="58492-109">Cela peut générer des problèmes de qualité de service, car les plages de port se chevauchent.</span><span class="sxs-lookup"><span data-stu-id="58492-109">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="58492-110">Avec la qualité de service (QoS), chaque modalité doit avoir un ensemble unique de ports: Si vous utilisez les ports 10000 à 10999 pour la vidéo, vous devez utiliser une autre plage (par exemple, 11000 à 11999 pour le son).</span><span class="sxs-lookup"><span data-stu-id="58492-110">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="58492-111">Par défaut, les plages de port audio et vidéo ne se chevauchent pas dans Microsoft Lync Server 2013; Toutefois, les plages de port affectées au partage d’application s’empiètent sur les plages de ports audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="58492-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="58492-112">(Qui, à son tour, signifie qu’aucune de ces plages n’est unique.) Vous pouvez vérifier les plages de port existantes pour vos serveurs de conférences, d’applications et de médiation en exécutant les trois commandes suivantes à partir de Lync Server 2013 Management Shell:</span><span class="sxs-lookup"><span data-stu-id="58492-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="58492-113">Comme vous pouvez le voir dans les commandes précédentes, chaque type de port (audio, vidéo et partage d’application) assigne deux valeurs de propriété distinctes: le début du port et le nombre de ports.</span><span class="sxs-lookup"><span data-stu-id="58492-113">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="58492-114">Le début du port indique le premier port utilisé pour cette modalité; par exemple, si le port audio démarre est égal à 50000, cela signifie que le premier port utilisé pour le trafic audio est le port 50000.</span><span class="sxs-lookup"><span data-stu-id="58492-114">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="58492-115">Si le nombre de ports audio est 2 (qui n’est pas une valeur valide, mais qui est utilisé ici à des fins d’illustration), cela signifie que 2 ports uniquement sont attribués pour le son.</span><span class="sxs-lookup"><span data-stu-id="58492-115">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio.</span></span> <span data-ttu-id="58492-116">Si le premier port est port 50000 et qu’il existe au total deux ports, cela signifie que le second port doit être le port 50001 (les plages de port doivent être contiguës).</span><span class="sxs-lookup"><span data-stu-id="58492-116">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="58492-117">Par conséquent, la plage de port pour le son correspond aux ports 50000 à 50001 inclus.</span><span class="sxs-lookup"><span data-stu-id="58492-117">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="58492-118">Notez également que le serveur d’applications et le serveur de médiation ne prennent pas en charge la QoS pour le son. vous n’avez pas besoin de changer les ports vidéo ou de partage d’application dans vos serveurs d’applications ou serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="58492-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="58492-119">Si vous exécutez les trois commandes précédentes, vous verrez que les valeurs de port par défaut de Lync Server 2013 sont configurées comme suit:</span><span class="sxs-lookup"><span data-stu-id="58492-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58492-120">Propriété</span><span class="sxs-lookup"><span data-stu-id="58492-120">Property</span></span></th>
<th><span data-ttu-id="58492-121">Serveur de conférence</span><span class="sxs-lookup"><span data-stu-id="58492-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="58492-122">Serveur d’applications</span><span class="sxs-lookup"><span data-stu-id="58492-122">Application Server</span></span></th>
<th><span data-ttu-id="58492-123">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="58492-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58492-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="58492-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="58492-125">49152</span><span class="sxs-lookup"><span data-stu-id="58492-125">49152</span></span></p></td>
<td><p><span data-ttu-id="58492-126">49152</span><span class="sxs-lookup"><span data-stu-id="58492-126">49152</span></span></p></td>
<td><p><span data-ttu-id="58492-127">49152</span><span class="sxs-lookup"><span data-stu-id="58492-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58492-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="58492-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="58492-129">8348</span><span class="sxs-lookup"><span data-stu-id="58492-129">8348</span></span></p></td>
<td><p><span data-ttu-id="58492-130">8348</span><span class="sxs-lookup"><span data-stu-id="58492-130">8348</span></span></p></td>
<td><p><span data-ttu-id="58492-131">8348</span><span class="sxs-lookup"><span data-stu-id="58492-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58492-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="58492-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="58492-133">57501</span><span class="sxs-lookup"><span data-stu-id="58492-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58492-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="58492-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="58492-135">8034</span><span class="sxs-lookup"><span data-stu-id="58492-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58492-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="58492-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="58492-137">49152</span><span class="sxs-lookup"><span data-stu-id="58492-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58492-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="58492-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="58492-139">16383</span><span class="sxs-lookup"><span data-stu-id="58492-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58492-140">Comme indiqué précédemment, lors de la configuration des ports du serveur Lync pour la qualité de service (QoS), vous devez vous assurer que: 1 et 2) les plages de port ne se chevauchent pas.</span><span class="sxs-lookup"><span data-stu-id="58492-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="58492-141">Si vous examinez de près le tableau précédent, vous verrez que les plages de port sont identiques entre les trois types de serveurs.</span><span class="sxs-lookup"><span data-stu-id="58492-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="58492-142">Par exemple, le port audio de début est défini sur le port 49152 sur chaque type de serveur et le nombre total de ports réservés pour le son dans chaque serveur est également identique: 8348.</span><span class="sxs-lookup"><span data-stu-id="58492-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="58492-143">Toutefois, le chevauchement des plages de port: les ports audio commencent au port 49152, mais les ports sont-ils mis de côté pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="58492-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="58492-144">Pour optimiser l’utilisation de la qualité du service, le partage d’application doit être reconfiguré pour utiliser une plage de ports unique.</span><span class="sxs-lookup"><span data-stu-id="58492-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="58492-145">Par exemple, vous pouvez configurer le partage d’application pour qu’il commence au port 40803 et utilise les ports 8348.</span><span class="sxs-lookup"><span data-stu-id="58492-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="58492-146">(Pourquoi 8348 ports?</span><span class="sxs-lookup"><span data-stu-id="58492-146">(Why 8348 ports?</span></span> <span data-ttu-id="58492-147">Si vous ajoutez ces valeurs ensemble--40803 + 8348, cela signifie que le partage d’application utilisera les ports 40803 via le port 49150.</span><span class="sxs-lookup"><span data-stu-id="58492-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="58492-148">Étant donné que les ports audio ne commencent pas jusqu’au port 49152, il n’y a plus de plages de ports qui se chevauchent.)</span><span class="sxs-lookup"><span data-stu-id="58492-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="58492-149">Après avoir sélectionné la nouvelle plage de ports pour le partage d’application, vous pouvez apporter votre modification à l’aide de l’applet de passe Set-CsConferencingServer.</span><span class="sxs-lookup"><span data-stu-id="58492-149">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="58492-150">Il n’est pas nécessaire de procéder à cette modification sur les serveurs d’applications ou sur les serveurs de médiation, car ces serveurs ne gèrent pas le trafic de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="58492-150">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="58492-151">Vous ne devez modifier les valeurs de port sur ces serveurs que si vous décidez de réaffecter les ports utilisés pour le trafic audio.</span><span class="sxs-lookup"><span data-stu-id="58492-151">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="58492-152">Pour modifier les valeurs de port du partage d’application sur un serveur de conférence unique, exécutez une commande similaire à celle-ci à partir de Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="58492-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="58492-153">Si vous voulez apporter ces modifications sur tous vos serveurs de conférence, vous pouvez exécuter cette commande à la place:</span><span class="sxs-lookup"><span data-stu-id="58492-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="58492-154">Après avoir modifié les paramètres de port que vous devez arrêter, puis redémarrez chaque service affecté par ces changements.</span><span class="sxs-lookup"><span data-stu-id="58492-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="58492-155">Il n’est pas obligatoire que vos serveurs de conférence, serveurs d’applications et serveurs de médiation partagent exactement la même plage de port; la seule exigence requise est que vous réservez des plages de port uniques sur tous vos serveurs.</span><span class="sxs-lookup"><span data-stu-id="58492-155">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="58492-156">Toutefois, l’administration sera généralement plus facile si vous utilisez le même ensemble de ports sur tous vos serveurs.</span><span class="sxs-lookup"><span data-stu-id="58492-156">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

