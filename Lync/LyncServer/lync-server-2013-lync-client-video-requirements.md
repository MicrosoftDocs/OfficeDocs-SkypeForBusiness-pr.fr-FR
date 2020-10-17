---
title: 'Lync Server 2013 : configuration vidéo requise pour les clients Lync'
description: 'Lync Server 2013 : configuration vidéo requise pour les clients Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1d4a993650ec8102d8b66ea5aa936ad1613f20
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570480"
---
# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="e13b9-103">Configuration requise pour la vidéo client Lync pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e13b9-103">Lync client video requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e13b9-104">_**Dernière modification de la rubrique :** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="e13b9-104">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="e13b9-105">Cette section décrit la prise en charge du matériel vidéo pour les appels vidéo Lync 2013 et explique comment déterminer la qualité vidéo attendue pour différentes configurations d’ordinateur, de tablette et d’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="e13b9-105">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="e13b9-106">Caractéristiques et fonctionnalités des ordinateurs de bureau et tablette Windows</span><span class="sxs-lookup"><span data-stu-id="e13b9-106">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="e13b9-107">Lync 2013 introduit l’accélération matérielle pour le codage et le décodage vidéo en fonction de la norme H. 264/MPEG-4 part 10 Advanced Video Coding standard.</span><span class="sxs-lookup"><span data-stu-id="e13b9-107">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="e13b9-108">Cette fonctionnalité permet aux ordinateurs dont la vitesse d’horloge du processeur est faible d’encoder et de décoder des vidéos avec des résolutions supérieures.</span><span class="sxs-lookup"><span data-stu-id="e13b9-108">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="e13b9-109">La configuration requise pour le matériel vidéo dépend de la configuration de l’ordinateur et de la résolution vidéo souhaitée.</span><span class="sxs-lookup"><span data-stu-id="e13b9-109">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="e13b9-110">Configuration requise du matériel vidéo</span><span class="sxs-lookup"><span data-stu-id="e13b9-110">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e13b9-111">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="e13b9-111">Feature</span></span></th>
<th><span data-ttu-id="e13b9-112">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="e13b9-112">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e13b9-113">Décodage matériel accéléré H.264 à l’aide de l’accélération vidéo DirectX (DXVA)</span><span class="sxs-lookup"><span data-stu-id="e13b9-113">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e13b9-114">La carte graphique doit prendre en charge DirectX 9.0 et exposer le mode de décodage DXVA2_ModeH264_VLD_NoFGT.</span><span class="sxs-lookup"><span data-stu-id="e13b9-114">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="e13b9-115">Le pilote de carte graphique le plus récent doit être installé.</span><span class="sxs-lookup"><span data-stu-id="e13b9-115">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="e13b9-116">Pour plus d’informations sur les modes de décodage, voir <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A> .</span><span class="sxs-lookup"><span data-stu-id="e13b9-116">For details about decoding modes, see <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e13b9-117">Encodage matériel accéléré H.264 : chipset requis</span><span class="sxs-lookup"><span data-stu-id="e13b9-117">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="e13b9-118">Les solutions de codage vidéo avec accélération matérielle Intel suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="e13b9-118">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="e13b9-119">Chipsets Intel HD Graphics 2000, 2500, 3000, et 4000 de deuxième ou troisième générations (ou versions ultérieures) avec encodeurs vidéo matériel intégrés.</span><span class="sxs-lookup"><span data-stu-id="e13b9-119">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="e13b9-120">L’installation du pilote Intel HD Graphics 15.28.9.2884 ou le pilote le plus récent contenant les éléments suivants sont requis :</span><span class="sxs-lookup"><span data-stu-id="e13b9-120">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="e13b9-121">Pilote d’affichage 9.17.10.2884 ou le pilote le plus récent</span><span class="sxs-lookup"><span data-stu-id="e13b9-121">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="e13b9-122">Version de Hardware Media Foundation Transform (HMFT) 3.12.10.31 ou la dernière HMFT</span><span class="sxs-lookup"><span data-stu-id="e13b9-122">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="e13b9-123">Les solutions de codage vidéo avec accélération matérielle AMD suivantes sont prises en charge (nécessite des mises à jour CU1 pour Lync Server 2013) :</span><span class="sxs-lookup"><span data-stu-id="e13b9-123">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="e13b9-124">Le moteur de codec vidéo AMD, qui est disponible dans plusieurs cartes graphiques discrètes et dans des unités de traitement accélérées intégrées de processeurs accélérés de la série AMD.</span><span class="sxs-lookup"><span data-stu-id="e13b9-124">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="e13b9-125">Le pilote du moteur de codec vidéo AMD 9.12.0.0 ou une version ultérieure doit être installé.</span><span class="sxs-lookup"><span data-stu-id="e13b9-125">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e13b9-126">Encodage matériel accéléré H.264 : caméra requise</span><span class="sxs-lookup"><span data-stu-id="e13b9-126">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="e13b9-127">Caméras vidéo USB avec encodeur matériel H.264 intégré conforme à la spécification USB Video Class (UVC) version 1.5.</span><span class="sxs-lookup"><span data-stu-id="e13b9-127">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e13b9-128">Lync 2013 prend en charge les caméras UVC 1,5 avec Windows 8 ou Windows 8,1, qui inclut la prise en charge de UVC 1,5.</span><span class="sxs-lookup"><span data-stu-id="e13b9-128">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="e13b9-129">Dans la mesure où Windows 7 ne prend pas en charge UVC 1.5, Lync 2013 considère les caméras UVC 1.5 comme des caméras génériques sans prise en charge de l’encodage matériel.</span><span class="sxs-lookup"><span data-stu-id="e13b9-129">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="e13b9-130">Identification des fonctionnalités d’encodage et de décodage vidéo H.264</span><span class="sxs-lookup"><span data-stu-id="e13b9-130">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="e13b9-131">En règle générale, quatre facteurs principaux déterminent les capacités d’encodage et de décodage maximales d’une configuration donnée :</span><span class="sxs-lookup"><span data-stu-id="e13b9-131">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="e13b9-132">Prise en charge du décodage matériel accéléré avec DXVA</span><span class="sxs-lookup"><span data-stu-id="e13b9-132">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="e13b9-133">Prise en charge de l’encodage matériel accéléré</span><span class="sxs-lookup"><span data-stu-id="e13b9-133">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="e13b9-134">Nombre de cœurs physiques</span><span class="sxs-lookup"><span data-stu-id="e13b9-134">Number of physical cores</span></span>

  - <span data-ttu-id="e13b9-135">Indice de performance Windows (WEI)</span><span class="sxs-lookup"><span data-stu-id="e13b9-135">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="e13b9-136">L’Outil d’évaluation système Windows (WinSAT) détermine l’indice WEI.</span><span class="sxs-lookup"><span data-stu-id="e13b9-136">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="e13b9-137">Lorsque vous exécutez l’outil WinSAT, il génère un document XML formel. Assessment sur l’ordinateur dans le répertoire% windir% \\ \\ WinSAT \\ datastore.</span><span class="sxs-lookup"><span data-stu-id="e13b9-137">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="e13b9-138">Ce fichier XML contient les deux scores suivants qui sont essentiels pour déterminer les capacités d’encodage et de décodage :</span><span class="sxs-lookup"><span data-stu-id="e13b9-138">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="e13b9-139">La valeur VideoEncodeScore indique la capacité d’encodage vidéo logiciel de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e13b9-139">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="e13b9-140">La valeur GraphicsScore indique la capacité d’encodage matériel accéléré de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e13b9-140">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="e13b9-p106">Les trois tableaux suivants expliquent les capacités d’encodage et de décodage maximales pour différents types de PC en fonction de l’accélération matérielle prise en charge. Pour des résolutions de 640x360 et supérieures, la fréquence d’images maximale prise en charge est de 30 images par secondes (i/s). Pour des résolutions inférieures à 640x360, la fréquence d’images maximale prise en charge est de 15 i/s.</span><span class="sxs-lookup"><span data-stu-id="e13b9-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="e13b9-144">Ordinateur sans DXVA et sans encodeur matériel accéléré</span><span class="sxs-lookup"><span data-stu-id="e13b9-144">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e13b9-145">Résolution d’encodeur compatible</span><span class="sxs-lookup"><span data-stu-id="e13b9-145">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="e13b9-146">Résolution de décodeur compatible</span><span class="sxs-lookup"><span data-stu-id="e13b9-146">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="e13b9-147">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="e13b9-147">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e13b9-148">424x240</span><span class="sxs-lookup"><span data-stu-id="e13b9-148">424x240</span></span></p></td>
<td><p><span data-ttu-id="e13b9-149">424x240 (640x360 à 15 i/s pour des scénarios de réception uniquement)</span><span class="sxs-lookup"><span data-stu-id="e13b9-149">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="e13b9-150">1 cœur et VideoEncodeScore ≥ 4,0</span><span class="sxs-lookup"><span data-stu-id="e13b9-150">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e13b9-151">640x360</span><span class="sxs-lookup"><span data-stu-id="e13b9-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="e13b9-152">640x360</span><span class="sxs-lookup"><span data-stu-id="e13b9-152">640x360</span></span></p></td>
<td><p><span data-ttu-id="e13b9-153">2 cœurs et VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="e13b9-153">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e13b9-154">640x360</span><span class="sxs-lookup"><span data-stu-id="e13b9-154">640x360</span></span></p></td>
<td><p><span data-ttu-id="e13b9-155">1280x720</span><span class="sxs-lookup"><span data-stu-id="e13b9-155">1280x720</span></span></p></td>
<td><p><span data-ttu-id="e13b9-156">2 cœurs et VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="e13b9-156">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e13b9-157">640x360</span><span class="sxs-lookup"><span data-stu-id="e13b9-157">640x360</span></span></p></td>
<td><p><span data-ttu-id="e13b9-158">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-158">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-159">4 cœurs et VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="e13b9-159">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e13b9-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="e13b9-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="e13b9-161">1280x720</span><span class="sxs-lookup"><span data-stu-id="e13b9-161">1280x720</span></span></p></td>
<td><p><span data-ttu-id="e13b9-162">4 cœurs et VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="e13b9-162">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e13b9-163">1280x720</span><span class="sxs-lookup"><span data-stu-id="e13b9-163">1280x720</span></span></p></td>
<td><p><span data-ttu-id="e13b9-164">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-164">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-165">4 cœurs et VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="e13b9-165">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e13b9-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-167">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-167">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-168">N/A</span><span class="sxs-lookup"><span data-stu-id="e13b9-168">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="e13b9-169">Ordinateur avec DXVA mais sans encodeur matériel accéléré</span><span class="sxs-lookup"><span data-stu-id="e13b9-169">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e13b9-170">Résolution d’encodeur compatible</span><span class="sxs-lookup"><span data-stu-id="e13b9-170">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="e13b9-171">Résolution de décodeur compatible</span><span class="sxs-lookup"><span data-stu-id="e13b9-171">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="e13b9-172">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="e13b9-172">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e13b9-173">424x240</span><span class="sxs-lookup"><span data-stu-id="e13b9-173">424x240</span></span></p></td>
<td><p><span data-ttu-id="e13b9-174">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-174">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-175">1 cœur et VideoEncodeScore ≥ 3,0</span><span class="sxs-lookup"><span data-stu-id="e13b9-175">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e13b9-176">640x360</span><span class="sxs-lookup"><span data-stu-id="e13b9-176">640x360</span></span></p></td>
<td><p><span data-ttu-id="e13b9-177">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-177">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-178">2 cœurs et VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="e13b9-178">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e13b9-179">960x540</span><span class="sxs-lookup"><span data-stu-id="e13b9-179">960x540</span></span></p></td>
<td><p><span data-ttu-id="e13b9-180">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-180">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-181">2 cœurs et VideoEncodeScore ≥ 6,0</span><span class="sxs-lookup"><span data-stu-id="e13b9-181">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e13b9-182">1280x720</span><span class="sxs-lookup"><span data-stu-id="e13b9-182">1280x720</span></span></p></td>
<td><p><span data-ttu-id="e13b9-183">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-183">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-184">4 cœurs et VideoEncodeScore ≥ 6,7</span><span class="sxs-lookup"><span data-stu-id="e13b9-184">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e13b9-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-186">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-186">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-187">4 cœurs et VideoEncodeScore ≥ 8,2</span><span class="sxs-lookup"><span data-stu-id="e13b9-187">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e13b9-188">Le score WinSAT sur Windows 7 est limité à un maximum de 7,9.</span><span class="sxs-lookup"><span data-stu-id="e13b9-188">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="e13b9-189">Par conséquent, la fonctionnalité de codage pour un ordinateur dépourvu de codeur matériel accéléré ne peut être obtenue que sur Windows 8 ou Windows 8,1, où le score WinSAT maximal est de 9,9.</span><span class="sxs-lookup"><span data-stu-id="e13b9-189">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="e13b9-190">Ordinateur avec DXVA et avec un encodeur matériel accéléré Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="e13b9-190">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e13b9-191">Résolution d’encodeur compatible</span><span class="sxs-lookup"><span data-stu-id="e13b9-191">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="e13b9-192">Résolution de décodeur compatible</span><span class="sxs-lookup"><span data-stu-id="e13b9-192">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="e13b9-193">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="e13b9-193">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e13b9-194">1280x720</span><span class="sxs-lookup"><span data-stu-id="e13b9-194">1280x720</span></span></p></td>
<td><p><span data-ttu-id="e13b9-195">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-195">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-196">Intel HD Graphics deuxième et troisième générations</span><span class="sxs-lookup"><span data-stu-id="e13b9-196">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e13b9-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-198">1920x1080</span><span class="sxs-lookup"><span data-stu-id="e13b9-198">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="e13b9-199">Intel HD Graphics deuxième et troisième générations avec GraphicsScore ≥ 5,0</span><span class="sxs-lookup"><span data-stu-id="e13b9-199">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="e13b9-200">Fonctionnalités de vidéo d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="e13b9-200">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="e13b9-201">Le tableau suivant décrit les capacités vidéo maximales pour les appareils mobiles pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e13b9-201">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="e13b9-202">Pour plus d’informations sur la prise en charge des appareils mobiles, voir [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e13b9-202">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e13b9-203">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="e13b9-203">Feature</span></span></th>
<th><span data-ttu-id="e13b9-204">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="e13b9-204">Windows Phone</span></span></th>
<th><span data-ttu-id="e13b9-205">iPhone</span><span class="sxs-lookup"><span data-stu-id="e13b9-205">iPhone</span></span></th>
<th><span data-ttu-id="e13b9-206">iPad</span><span class="sxs-lookup"><span data-stu-id="e13b9-206">iPad</span></span></th>
<th><span data-ttu-id="e13b9-207">Android</span><span class="sxs-lookup"><span data-stu-id="e13b9-207">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e13b9-208">Résolution maximale de H. 264</span><span class="sxs-lookup"><span data-stu-id="e13b9-208">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="e13b9-209">VGA</span><span class="sxs-lookup"><span data-stu-id="e13b9-209">VGA</span></span></p></td>
<td><p><span data-ttu-id="e13b9-210">QVGA : iPhone-n</span><span class="sxs-lookup"><span data-stu-id="e13b9-210">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="e13b9-211">VGA : iPhone 5</span><span class="sxs-lookup"><span data-stu-id="e13b9-211">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="e13b9-212">720p : iPhone 5S et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="e13b9-212">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="e13b9-213">VGA : iPad 2 et version ultérieure/iPad mini 1 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="e13b9-213">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="e13b9-214">720p : iPad air/iPad mini 2/iPad Pro et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="e13b9-214">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="e13b9-215">Jusqu’à VGA en fonction du modèle d’appareil</span><span class="sxs-lookup"><span data-stu-id="e13b9-215">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e13b9-216">Résolution de décodage maximale H. 264</span><span class="sxs-lookup"><span data-stu-id="e13b9-216">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="e13b9-217">VGA</span><span class="sxs-lookup"><span data-stu-id="e13b9-217">VGA</span></span></p></td>
<td><p><span data-ttu-id="e13b9-218">QVGA : iPhone-n</span><span class="sxs-lookup"><span data-stu-id="e13b9-218">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="e13b9-219">VGA : iPhone 5</span><span class="sxs-lookup"><span data-stu-id="e13b9-219">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="e13b9-220">720p : iPhone 5S et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="e13b9-220">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="e13b9-221">VGA : iPad 2 et version ultérieure/iPad mini 1 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="e13b9-221">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="e13b9-222">720p : iPad air/iPad mini 2/iPad Pro et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="e13b9-222">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="e13b9-223">Jusqu’à VGA en fonction du modèle d’appareil</span><span class="sxs-lookup"><span data-stu-id="e13b9-223">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

