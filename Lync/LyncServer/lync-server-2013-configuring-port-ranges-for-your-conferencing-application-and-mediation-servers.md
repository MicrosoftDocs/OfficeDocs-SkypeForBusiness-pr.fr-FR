---
title: 'Lync Server 2013 : configuration des plages de ports pour vos serveurs de conférence, d’application et de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3df859017ca54d32ad56580c842f748114166d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535061"
---
# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="7b627-102">Configuration des plages de ports dans Lync Server 2013 pour vos serveurs de conférence, d’application et de médiation</span><span class="sxs-lookup"><span data-stu-id="7b627-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b627-103">_**Dernière modification de la rubrique :** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="7b627-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="7b627-p101">Pour implémenter la qualité de service (QoS), vous devez configurer des plages de ports identiques pour l’audio, la vidéo et le partage d’applications sur vos serveurs de conférence, d’applications et de médiation. En outre, ces plages de ports ne doivent absolument pas se chevaucher. Pour prendre un exemple simple, supposons que vous utilisiez les ports 10000 à 10999 pour la vidéo sur vos serveurs de conférence. Cela signifie que vous devez également réserver les ports 10000 à 10999 pour la vidéo sur vos serveurs d’applications et de médiation. Sinon, la qualité de service ne fonctionnera pas comme prévu.</span><span class="sxs-lookup"><span data-stu-id="7b627-p101">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way. To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers. That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers. If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="7b627-p102">De même, supposons que vous réserviez les ports 10000 à 10999 pour la vidéo mais que vous réserviez ensuite les ports 10500 à 11999 pour l’audio. Cela peut créer des problèmes de qualité de service, car les plages de ports se chevauchent. Avec la qualité de service, chaque modalité doit posséder un ensemble unique de ports : si vous utilisez les ports 10000 à 10999 pour la vidéo, vous devez utiliser une autre plage (par exemple, 11000 à 11999 pour l’audio).</span><span class="sxs-lookup"><span data-stu-id="7b627-p102">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio. This can create problems for Quality of Service, because the port ranges overlap. With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="7b627-111">Par défaut, les plages de ports audio et vidéo ne se chevauchent pas dans Microsoft Lync Server 2013 ; Toutefois, les plages de ports affectées au partage d’application se chevauchent avec les plages de ports audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="7b627-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="7b627-112">(Ce qui signifie, à son tour, qu’aucune de ces plages n’est unique.) Vous pouvez vérifier les plages de ports existantes pour vos serveurs de conférence, d’application et de médiation en exécutant les trois commandes suivantes dans Lync Server 2013 Management Shell :</span><span class="sxs-lookup"><span data-stu-id="7b627-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="7b627-p104">Comme vous pouvez le voir dans les commandes précédentes, chaque type de port (audio, vidéo et partage d’application) se voit affecter deux valeurs de propriétés distinctes : le port de début et le nombre de ports. Le port de début indique le premier port utilisé pour la modalité concernée. Par exemple, si le port de début audio est 50000, cela signifie que le premier port utilisé pour le trafic audio est le port 50000. Si le nombre de ports audio est égal à 2 (il s’agit ici d’une valeur non valide utilisée uniquement à titre d’illustration), cela signifie que seuls 2 ports sont alloués pour l’audio. Si le premier port est le port 50000 et s’il existe deux ports au total, cela signifie que le second port doit être le port 50001 (les plages de ports doivent être contigües). Ainsi, la plage de ports pour l’audio doit inclure les ports 50000 à 50001.</span><span class="sxs-lookup"><span data-stu-id="7b627-p104">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count. The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000. If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio. If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous). As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="7b627-118">Notez également que le serveur d’applications et le serveur de médiation ne prennent en charge la qualité de service que pour l’audio. Vous n’avez pas besoin de modifier les ports vidéo ou de partage d’application sur vos serveurs d’applications ou vos serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="7b627-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="7b627-119">Si vous exécutez les trois commandes précédentes, vous verrez que les valeurs de port par défaut pour Lync Server 2013 sont configurées comme suit :</span><span class="sxs-lookup"><span data-stu-id="7b627-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b627-120">Propriété</span><span class="sxs-lookup"><span data-stu-id="7b627-120">Property</span></span></th>
<th><span data-ttu-id="7b627-121">Serveur de conférence</span><span class="sxs-lookup"><span data-stu-id="7b627-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="7b627-122">Serveur d’applications</span><span class="sxs-lookup"><span data-stu-id="7b627-122">Application Server</span></span></th>
<th><span data-ttu-id="7b627-123">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="7b627-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b627-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="7b627-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="7b627-125">49152</span><span class="sxs-lookup"><span data-stu-id="7b627-125">49152</span></span></p></td>
<td><p><span data-ttu-id="7b627-126">49152</span><span class="sxs-lookup"><span data-stu-id="7b627-126">49152</span></span></p></td>
<td><p><span data-ttu-id="7b627-127">49152</span><span class="sxs-lookup"><span data-stu-id="7b627-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b627-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="7b627-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="7b627-129">8348</span><span class="sxs-lookup"><span data-stu-id="7b627-129">8348</span></span></p></td>
<td><p><span data-ttu-id="7b627-130">8348</span><span class="sxs-lookup"><span data-stu-id="7b627-130">8348</span></span></p></td>
<td><p><span data-ttu-id="7b627-131">8348</span><span class="sxs-lookup"><span data-stu-id="7b627-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b627-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="7b627-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="7b627-133">57501</span><span class="sxs-lookup"><span data-stu-id="7b627-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b627-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="7b627-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="7b627-135">8034</span><span class="sxs-lookup"><span data-stu-id="7b627-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b627-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="7b627-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="7b627-137">49152</span><span class="sxs-lookup"><span data-stu-id="7b627-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b627-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="7b627-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="7b627-139">16383</span><span class="sxs-lookup"><span data-stu-id="7b627-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b627-140">Comme indiqué précédemment, lors de la configuration des ports Lync Server pour la qualité de service, vous devez vous assurer que : 1) les paramètres des ports audio sont identiques sur les serveurs de conférence, d’applications et de médiation. et, 2) les plages de ports ne se chevauchent pas.</span><span class="sxs-lookup"><span data-stu-id="7b627-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="7b627-141">Si vous examinez attentivement le tableau précédent, vous voyez que les plages de ports sont identiques sur les trois types de serveur.</span><span class="sxs-lookup"><span data-stu-id="7b627-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="7b627-142">Par exemple, le port audio de début est fixé au port 49152 sur chaque type de serveur et le nombre total de ports réservés à l’audio sur chaque serveur est également identique : 8 348.</span><span class="sxs-lookup"><span data-stu-id="7b627-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="7b627-143">Toutefois, les plages de ports se chevauchent : les ports audio débutent au port 49152 mais c’est le cas également pour les ports réservés au partage d’application.</span><span class="sxs-lookup"><span data-stu-id="7b627-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="7b627-144">Pour permettre une qualité de service optimale, le partage d’application doit être reconfiguré afin d’utiliser une plage de ports unique.</span><span class="sxs-lookup"><span data-stu-id="7b627-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="7b627-145">Par exemple, vous pouvez configurer le partage d’application pour démarrer au port 40803 et utiliser 8 348 ports.</span><span class="sxs-lookup"><span data-stu-id="7b627-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="7b627-146">Pourquoi 8 348 ports ?</span><span class="sxs-lookup"><span data-stu-id="7b627-146">(Why 8348 ports?</span></span> <span data-ttu-id="7b627-147">Si vous ajoutez ces valeurs ensemble--40803 + 8348--cela signifie que le partage d’application utilisera les ports 40803 via le port 49150.</span><span class="sxs-lookup"><span data-stu-id="7b627-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="7b627-148">Comme les ports audio ne commencent pas avant le port 49152, vous n’avez plus de plages de ports qui se chevauchent.</span><span class="sxs-lookup"><span data-stu-id="7b627-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="7b627-p106">Après avoir sélectionné la nouvelle plage de ports pour le partage d’application, vous pouvez effectuer votre modification à l’aide de l’applet de commande Set-CsConferencingServer. Cette modification n’a pas à être effectuée sur vos serveurs d’applications ou vos serveurs de médiation, car ces serveurs ne gèrent pas le trafic du partage d’application. Vous ne devez changer les valeurs de ports de ces serveurs que si vous décidez de réaffecter les ports utilisés pour le trafic audio.</span><span class="sxs-lookup"><span data-stu-id="7b627-p106">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet. This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic. You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="7b627-152">Pour modifier les valeurs de port du partage d’application sur un serveur de conférence unique, exécutez une commande semblable à celle-ci à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="7b627-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="7b627-153">Si vous voulez effectuer ces modifications sur tous vos serveurs de conférence, vous pouvez exécuter cette commande à la place :</span><span class="sxs-lookup"><span data-stu-id="7b627-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="7b627-154">Après avoir modifié les paramètres des ports, vous devez arrêter, puis redémarrer chaque service affecté par les modifications.</span><span class="sxs-lookup"><span data-stu-id="7b627-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="7b627-p107">Il n’est pas obligatoire que vos serveurs de conférence, serveurs d’applications et serveurs de médiation partagent la même plage de ports. Le seul impératif est de réserver les plages de ports uniques sur tous vos serveurs. Toutefois, l’administration est généralement plus facile si vous utilisez le même ensemble de ports sur tous vos serveurs.</span><span class="sxs-lookup"><span data-stu-id="7b627-p107">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers. However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

