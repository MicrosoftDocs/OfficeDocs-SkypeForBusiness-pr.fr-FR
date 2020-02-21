---
title: 'Lync Server 2013 : configuration des exemples de scénarios vidéo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 128703a39563124f6abfc4ae44143d274fd3a7c5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="1df5b-102">Configuration d’exemples de scénarios vidéo pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1df5b-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1df5b-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1df5b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1df5b-104">Lync 2013 ajoute de nouvelles fonctionnalités de vidéo pour la prise en charge de la vidéo et de la Galerie (HD) 1920 x 1080.</span><span class="sxs-lookup"><span data-stu-id="1df5b-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="1df5b-105">Les mesures basées sur les données client indiquent que la bande passante vidéo classique n’a pas été légèrement comparée à Lync 2010, mais que la bande passante de flux vidéo maximale a augmenté en raison de la prise en charge Full HD (pour plus d’informations, consultez la section « utilisation du réseau multimédia » dans la [bande passante réseau requise pour le trafic multimédia dans Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span><span class="sxs-lookup"><span data-stu-id="1df5b-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="1df5b-106">Les administrateurs peuvent donc restreindre la bande passante vidéo pour certains utilisateurs (par exemple, utilisateurs dans une succursale dotée d’une capacité réseau inférieure) et offrir la meilleure qualité vidéo possible pour les autres utilisateurs (par exemple, cadres).</span><span class="sxs-lookup"><span data-stu-id="1df5b-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="1df5b-p102">Le tableau suivant fournit la liste des paramètres recommandés pour configurer la vidéo pour différentes capacités réseau. Ces paramètres limiteront dans certains cas l’envoi et la réception de vidéos de résolution plus élevée (voir la colonne la plus à droite). La vidéo en mode Galerie n’est pas disponible si la configuration minimale est utilisée en raison de la faible bande passante réseau de réception maximale.</span><span class="sxs-lookup"><span data-stu-id="1df5b-p102">The following table provides a list of recommended settings for configuring video for different network capacities. These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column). The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="1df5b-110">Paramètres vidéo recommandés</span><span class="sxs-lookup"><span data-stu-id="1df5b-110">Recommended Video Settings</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th><span data-ttu-id="1df5b-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="1df5b-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="1df5b-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="1df5b-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="1df5b-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="1df5b-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="1df5b-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="1df5b-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="1df5b-115">Résolution vidéo attendue pour une vidéo de bonne qualité</span><span class="sxs-lookup"><span data-stu-id="1df5b-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1df5b-116">Idéale</span><span class="sxs-lookup"><span data-stu-id="1df5b-116">Best</span></span></p></td>
<td><p><span data-ttu-id="1df5b-117">True</span><span class="sxs-lookup"><span data-stu-id="1df5b-117">True</span></span></p></td>
<td><p><span data-ttu-id="1df5b-118">True</span><span class="sxs-lookup"><span data-stu-id="1df5b-118">True</span></span></p></td>
<td><p><span data-ttu-id="1df5b-119">8000</span><span class="sxs-lookup"><span data-stu-id="1df5b-119">8000</span></span></p></td>
<td><p><span data-ttu-id="1df5b-120">8000</span><span class="sxs-lookup"><span data-stu-id="1df5b-120">8000</span></span></p></td>
<td><p><span data-ttu-id="1df5b-121">Égal à égal : résolution vidéo 1920 x 1080 maximum</span><span class="sxs-lookup"><span data-stu-id="1df5b-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="1df5b-122">Mode Galerie : jusqu’à deux vidéos de résolution 1920 x 1080 ou plusieurs vidéos de résolution inférieure</span><span class="sxs-lookup"><span data-stu-id="1df5b-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1df5b-123">Good</span><span class="sxs-lookup"><span data-stu-id="1df5b-123">Good</span></span></p></td>
<td><p><span data-ttu-id="1df5b-124">True</span><span class="sxs-lookup"><span data-stu-id="1df5b-124">True</span></span></p></td>
<td><p><span data-ttu-id="1df5b-125">True</span><span class="sxs-lookup"><span data-stu-id="1df5b-125">True</span></span></p></td>
<td><p><span data-ttu-id="1df5b-126">2500</span><span class="sxs-lookup"><span data-stu-id="1df5b-126">2500</span></span></p></td>
<td><p><span data-ttu-id="1df5b-127">2500</span><span class="sxs-lookup"><span data-stu-id="1df5b-127">2500</span></span></p></td>
<td><p><span data-ttu-id="1df5b-128">Égal à égal : résolution vidéo 1280 x 720 maximum</span><span class="sxs-lookup"><span data-stu-id="1df5b-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="1df5b-129">Mode Galerie : jusqu’à cinq vidéos de résolution 640 x 360</span><span class="sxs-lookup"><span data-stu-id="1df5b-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1df5b-130">Moyenne</span><span class="sxs-lookup"><span data-stu-id="1df5b-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="1df5b-131">True</span><span class="sxs-lookup"><span data-stu-id="1df5b-131">True</span></span></p></td>
<td><p><span data-ttu-id="1df5b-132">True</span><span class="sxs-lookup"><span data-stu-id="1df5b-132">True</span></span></p></td>
<td><p><span data-ttu-id="1df5b-133">1000</span><span class="sxs-lookup"><span data-stu-id="1df5b-133">1000</span></span></p></td>
<td><p><span data-ttu-id="1df5b-134">1000</span><span class="sxs-lookup"><span data-stu-id="1df5b-134">1000</span></span></p></td>
<td><p><span data-ttu-id="1df5b-135">Égal à égal : résolution vidéo 960 x 540 maximum</span><span class="sxs-lookup"><span data-stu-id="1df5b-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="1df5b-136">Mode Galerie : jusqu’à cinq vidéos de résolution 424 x 240</span><span class="sxs-lookup"><span data-stu-id="1df5b-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1df5b-137">Minimale</span><span class="sxs-lookup"><span data-stu-id="1df5b-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="1df5b-138">Vrai</span><span class="sxs-lookup"><span data-stu-id="1df5b-138">True</span></span></p></td>
<td><p><span data-ttu-id="1df5b-139">False</span><span class="sxs-lookup"><span data-stu-id="1df5b-139">False</span></span></p></td>
<td><p><span data-ttu-id="1df5b-140">350</span><span class="sxs-lookup"><span data-stu-id="1df5b-140">350</span></span></p></td>
<td><p><span data-ttu-id="1df5b-141">350</span><span class="sxs-lookup"><span data-stu-id="1df5b-141">350</span></span></p></td>
<td><p><span data-ttu-id="1df5b-142">Égal à égal : résolution vidéo 424 x 240 maximum</span><span class="sxs-lookup"><span data-stu-id="1df5b-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="1df5b-143">Mode Galerie : non disponible</span><span class="sxs-lookup"><span data-stu-id="1df5b-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1df5b-144">Vous pouvez utiliser les informations du tableau précédent pour déployer les nouvelles fonctionnalités de conférence vidéo HD et en mode Galerie pour certains utilisateurs dans votre organisation, tout en autorisant des résolutions vidéo différentes pour d’autres.</span><span class="sxs-lookup"><span data-stu-id="1df5b-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="1df5b-p103">Dans l’exemple suivant, l’administrateur déploie les nouvelles fonctionnalités vidéo avec la meilleure qualité vidéo disponible pour les seuls cadres. Pour les employés d’une succursale dotée d’une faible capacité réseau, seule la configuration minimale du tableau précédent est déployée. Pour tous les autres employés, la configuration « Satisfaisante » est déployée.</span><span class="sxs-lookup"><span data-stu-id="1df5b-p103">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives. For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed. For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="1df5b-p104">Pour déployer les nouvelles fonctionnalités pour les cadres, l’administrateur crée la stratégie de conférence ExecutiveVideo avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="1df5b-p104">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="1df5b-150">VideoBitRateKB est défini sur 8 000 Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="1df5b-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="1df5b-151">TotalReceiveVideoBitRateKB est défini sur 8 000 Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="1df5b-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="1df5b-152">AllowMultiview est défini sur True.</span><span class="sxs-lookup"><span data-stu-id="1df5b-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="1df5b-153">EnableMultiviewJoin est défini sur True.</span><span class="sxs-lookup"><span data-stu-id="1df5b-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="1df5b-p105">Pour les employés de la succursale, l’administrateur crée la stratégie de conférence BranchOfficeVideo avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="1df5b-p105">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="1df5b-156">VideoBitRateKB est défini sur 350 Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="1df5b-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="1df5b-157">TotalReceiveVideoBitRateKB est défini sur 350 Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="1df5b-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="1df5b-158">AllowMultiview est défini sur True.</span><span class="sxs-lookup"><span data-stu-id="1df5b-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="1df5b-159">EnableMultiviewJoin est défini sur False.</span><span class="sxs-lookup"><span data-stu-id="1df5b-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="1df5b-p106">Pour tous les autres employés, l’administrateur crée la stratégie de conférence StandardVideo avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="1df5b-p106">For all other employees, the administrator creates a conferencing policy named StandardVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="1df5b-162">VideoBitRateKB est défini sur 2 500 Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="1df5b-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="1df5b-163">TotalReceiveVideoBitRateKB est défini sur 2 500 Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="1df5b-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="1df5b-164">AllowMultiview est défini sur True.</span><span class="sxs-lookup"><span data-stu-id="1df5b-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="1df5b-165">EnableMultiviewJoin est défini sur True.</span><span class="sxs-lookup"><span data-stu-id="1df5b-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="1df5b-166">L’administrateur affecte les stratégies de conférence aux utilisateurs comme suit :</span><span class="sxs-lookup"><span data-stu-id="1df5b-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="1df5b-167">La stratégie de conférence ExecutiveVideo est affectée aux cadres.</span><span class="sxs-lookup"><span data-stu-id="1df5b-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="1df5b-168">La stratégie de conférence BranchOfficeVideo est affectée à tous les employés de la succursale.</span><span class="sxs-lookup"><span data-stu-id="1df5b-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="1df5b-169">La stratégie de conférence StandardVideo est affectée à tous les autres employés.</span><span class="sxs-lookup"><span data-stu-id="1df5b-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="1df5b-170">Il en résulte l’expérience utilisateur suivante :</span><span class="sxs-lookup"><span data-stu-id="1df5b-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="1df5b-171">Toutes les conférences organisées par les utilisateurs prennent en charge le mode Galerie, mais les employés de la succursale ne peuvent pas l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="1df5b-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="1df5b-172">Pour toutes les conférences incluant plusieurs participants, les cadres peuvent envoyer la vidéo HD intégrale 1920 x 1080 (si leur matériel et leur liaison réseau la prennent en charge) et peuvent recevoir la vidéo HD intégrale 1920 x 1080 si les clients des autres participants la prennent en charge.</span><span class="sxs-lookup"><span data-stu-id="1df5b-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="1df5b-173">S’ils bénéficient de résolutions inférieures par rapport aux cadres dans le cadre des conférences à plusieurs participants, les employés qui ne sont pas des cadres obtiennent tout de même une résolution satisfaisante.</span><span class="sxs-lookup"><span data-stu-id="1df5b-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="1df5b-174">Les employés de la filiale obtiendront une bonne qualité vidéo dans les appels à deux parties lorsque Lync affiche la taille de la fenêtre vidéo par défaut ; Toutefois, si la fenêtre Lync est agrandie en plein écran, la résolution vidéo n’augmente pas.</span><span class="sxs-lookup"><span data-stu-id="1df5b-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="1df5b-175">Pour les conférences à plusieurs, les employés de la succursale ne verront qu’une seule vidéo active.</span><span class="sxs-lookup"><span data-stu-id="1df5b-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

