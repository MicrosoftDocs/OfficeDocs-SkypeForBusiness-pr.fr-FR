---
title: 'Configuration requise pour le client Lync Server 2013:'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56743abd386cb59b177806eed3d441aaf587ccce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="15d48-102">Configuration vidéo requise pour le client Lync pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d48-102">Lync client video requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15d48-103">_**Dernière modification de la rubrique:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="15d48-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="15d48-104">Cette section décrit la prise en charge de matériel vidéo pour les appels vidéo Lync 2013 et explique comment déterminer la qualité vidéo prévue pour différentes configurations d’ordinateur, de tablette et de périphérique mobile.</span><span class="sxs-lookup"><span data-stu-id="15d48-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="15d48-105">Configurations et capacités requises pour les ordinateurs de bureau et les tablettes Windows</span><span class="sxs-lookup"><span data-stu-id="15d48-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="15d48-106">Lync 2013 introduit l’accélération matérielle pour le codage et le décodage vidéo en fonction de la norme de codage vidéo de H. 264/MPEG-4 partie 10 avancée.</span><span class="sxs-lookup"><span data-stu-id="15d48-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="15d48-107">Cette fonctionnalité permet aux ordinateurs dont la vitesse d’horloge du processeur est faible d’encoder et de décoder des vidéos avec des résolutions supérieures.</span><span class="sxs-lookup"><span data-stu-id="15d48-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="15d48-108">La configuration requise pour le matériel vidéo dépend de la configuration de l’ordinateur et de la résolution vidéo souhaitée.</span><span class="sxs-lookup"><span data-stu-id="15d48-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="15d48-109">Configuration matérielle requise pour la vidéo</span><span class="sxs-lookup"><span data-stu-id="15d48-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15d48-110">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="15d48-110">Feature</span></span></th>
<th><span data-ttu-id="15d48-111">Condition requise</span><span class="sxs-lookup"><span data-stu-id="15d48-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15d48-112">Décodage matériel accéléré H.264 à l’aide de l’accélération vidéo DirectX (DXVA)</span><span class="sxs-lookup"><span data-stu-id="15d48-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="15d48-113">La carte graphique doit prendre en charge DirectX 9.0 et exposer le mode de décodage DXVA2_ModeH264_VLD_NoFGT.</span><span class="sxs-lookup"><span data-stu-id="15d48-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="15d48-114">Le pilote de carte graphique le plus récent doit être installé.</span><span class="sxs-lookup"><span data-stu-id="15d48-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="15d48-115">Pour plus d’informations sur les modes de <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>décodage, voir.</span><span class="sxs-lookup"><span data-stu-id="15d48-115">For details about decoding modes, see <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d48-116">Encodage matériel accéléré H.264 : chipset requis</span><span class="sxs-lookup"><span data-stu-id="15d48-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="15d48-117">Les solutions d’encodage vidéo matériel accéléré Intel suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="15d48-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="15d48-118">Chipsets vidéo Intel HD 2000, 2500, 3000 et 4000 (ou versions ultérieures) avec les codes vidéo intégrés.</span><span class="sxs-lookup"><span data-stu-id="15d48-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="15d48-119">L’installation du pilote 15.28.9.2884 Intel HD Graphics ou version ultérieure contenant les éléments suivants est requise :</span><span class="sxs-lookup"><span data-stu-id="15d48-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="15d48-120">pilote d’affichage 9.17.10.2884 ou version ultérieure ;</span><span class="sxs-lookup"><span data-stu-id="15d48-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="15d48-121">HMFT (Hardware Media Foundation Transform) 3.12.10.31 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="15d48-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="15d48-122">Les solutions de codage vidéo accélérées sur le matériel AMD suivantes sont prises en charge (nécessite des mises à jour CU1 pour Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="15d48-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="15d48-p103">AMD Video Codec Engine, disponible dans plusieurs cartes graphiques discrètes et les unités de traitement accéléré intégrées des processeurs accélérés AMD série A. Le pilote 9.12.0.0 AMD Video Codec Engine ou une version ultérieure doit être installé.</span><span class="sxs-lookup"><span data-stu-id="15d48-p103">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors. The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d48-125">Encodage matériel accéléré H.264 : caméra requise</span><span class="sxs-lookup"><span data-stu-id="15d48-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="15d48-126">Caméras vidéo USB avec encodeur matériel H.264 intégré conforme à la spécification USB Video Class (UVC) version 1.5.</span><span class="sxs-lookup"><span data-stu-id="15d48-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="15d48-127">Lync 2013 prend en charge les appareils photo 1,5 UVC avec Windows 8 ou Windows 8,1, qui inclut la prise en charge de UVC 1,5.</span><span class="sxs-lookup"><span data-stu-id="15d48-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="15d48-128">Dans la mesure où Windows 7 n’inclut pas la prise en charge de UVC 1,5, Lync 2013 considère les appareils photo 1,5 UVC comme des caméras normales sans prise en charge du codage matériel.</span><span class="sxs-lookup"><span data-stu-id="15d48-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="15d48-129">Détermination des capacités de codage et de décodage vidéo de H. 264</span><span class="sxs-lookup"><span data-stu-id="15d48-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="15d48-130">En règle générale, quatre facteurs principaux déterminent les capacités d’encodage et de décodage maximales d’une configuration donnée :</span><span class="sxs-lookup"><span data-stu-id="15d48-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="15d48-131">Prise en charge du décodage matériel accéléré avec DXVA</span><span class="sxs-lookup"><span data-stu-id="15d48-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="15d48-132">Prise en charge de l’encodage matériel accéléré</span><span class="sxs-lookup"><span data-stu-id="15d48-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="15d48-133">Nombre de cœurs physiques</span><span class="sxs-lookup"><span data-stu-id="15d48-133">Number of physical cores</span></span>

  - <span data-ttu-id="15d48-134">Indice de performance Windows (WEI)</span><span class="sxs-lookup"><span data-stu-id="15d48-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="15d48-135">L’Outil d’évaluation système Windows (WinSAT) détermine l’indice WEI.</span><span class="sxs-lookup"><span data-stu-id="15d48-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="15d48-136">Lorsque vous exécutez l’outil de vérification WINS, il génère un document XML d’évaluation formel sur l’ordinateur dans le répertoire\\%\\windir\\% performance WinSAT.</span><span class="sxs-lookup"><span data-stu-id="15d48-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="15d48-137">Ce fichier XML contient les deux scores suivants qui sont essentiels pour déterminer les capacités d’encodage et de décodage :</span><span class="sxs-lookup"><span data-stu-id="15d48-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="15d48-138">La valeur VideoEncodeScore indique la capacité d’encodage vidéo logiciel de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="15d48-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="15d48-139">La valeur GraphicsScore indique la capacité d’encodage matériel accéléré de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="15d48-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="15d48-p106">Les trois tableaux suivants expliquent les capacités d’encodage et de décodage maximales pour différents types de PC en fonction de l’accélération matérielle prise en charge. Pour des résolutions de 640x360 et supérieures, la fréquence d’images maximale prise en charge est de 30 images par secondes (i/s). Pour des résolutions inférieures à 640x360, la fréquence d’images maximale prise en charge est de 15 i/s.</span><span class="sxs-lookup"><span data-stu-id="15d48-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="15d48-143">Ordinateur sans DXVA et sans encodeur matériel accéléré</span><span class="sxs-lookup"><span data-stu-id="15d48-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15d48-144">Résolution d’encodeur compatible</span><span class="sxs-lookup"><span data-stu-id="15d48-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="15d48-145">Résolution de décodeur compatible</span><span class="sxs-lookup"><span data-stu-id="15d48-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="15d48-146">Condition requise</span><span class="sxs-lookup"><span data-stu-id="15d48-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15d48-147">424x240</span><span class="sxs-lookup"><span data-stu-id="15d48-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="15d48-148">424x240 (640x360 à 15 i/s pour des scénarios de réception uniquement)</span><span class="sxs-lookup"><span data-stu-id="15d48-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="15d48-149">1 cœur et VideoEncodeScore ≥ 4,0</span><span class="sxs-lookup"><span data-stu-id="15d48-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d48-150">640x360</span><span class="sxs-lookup"><span data-stu-id="15d48-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="15d48-151">640x360</span><span class="sxs-lookup"><span data-stu-id="15d48-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="15d48-152">2 cœurs et VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="15d48-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d48-153">640x360</span><span class="sxs-lookup"><span data-stu-id="15d48-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="15d48-154">1280x720</span><span class="sxs-lookup"><span data-stu-id="15d48-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="15d48-155">2 cœurs et VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="15d48-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d48-156">640x360</span><span class="sxs-lookup"><span data-stu-id="15d48-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="15d48-157">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-158">4 cœurs et VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="15d48-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d48-159">1280x720</span><span class="sxs-lookup"><span data-stu-id="15d48-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="15d48-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="15d48-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="15d48-161">4 cœurs et VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="15d48-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d48-162">1280x720</span><span class="sxs-lookup"><span data-stu-id="15d48-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="15d48-163">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-164">4 cœurs et VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="15d48-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d48-165">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-167">N/A</span><span class="sxs-lookup"><span data-stu-id="15d48-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="15d48-168">Ordinateur avec DXVA mais sans encodeur matériel accéléré</span><span class="sxs-lookup"><span data-stu-id="15d48-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15d48-169">Résolution d’encodeur compatible</span><span class="sxs-lookup"><span data-stu-id="15d48-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="15d48-170">Résolution de décodeur compatible</span><span class="sxs-lookup"><span data-stu-id="15d48-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="15d48-171">Condition requise</span><span class="sxs-lookup"><span data-stu-id="15d48-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15d48-172">424x240</span><span class="sxs-lookup"><span data-stu-id="15d48-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="15d48-173">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-174">1 cœur et VideoEncodeScore ≥ 3,0</span><span class="sxs-lookup"><span data-stu-id="15d48-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d48-175">640x360</span><span class="sxs-lookup"><span data-stu-id="15d48-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="15d48-176">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-177">2 cœurs et VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="15d48-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d48-178">960x540</span><span class="sxs-lookup"><span data-stu-id="15d48-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="15d48-179">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-180">2 cœurs et VideoEncodeScore ≥ 6,0</span><span class="sxs-lookup"><span data-stu-id="15d48-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d48-181">1280x720</span><span class="sxs-lookup"><span data-stu-id="15d48-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="15d48-182">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-183">4 cœurs et VideoEncodeScore ≥ 6,7</span><span class="sxs-lookup"><span data-stu-id="15d48-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d48-184">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-186">4 cœurs et VideoEncodeScore ≥ 8,2</span><span class="sxs-lookup"><span data-stu-id="15d48-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="15d48-p107">Le score WinSAT sur Windows 7 est limité à un maximum de 7,9. C’est pourquoi la capacité d’encodage d’un ordinateur sans encodeur matériel accéléré ne peut être obtenue que sur Windows 8 ou Windows 8.1, pour lequel le score WinSAT est de 9,9 au maximum.</span><span class="sxs-lookup"><span data-stu-id="15d48-p107">The WinSAT score on Windows 7 is limited to a maximum of 7.9. Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="15d48-189">Ordinateur avec DXVA et avec un encodeur matériel accéléré Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="15d48-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15d48-190">Résolution d’encodeur compatible</span><span class="sxs-lookup"><span data-stu-id="15d48-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="15d48-191">Résolution de décodeur compatible</span><span class="sxs-lookup"><span data-stu-id="15d48-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="15d48-192">Condition requise</span><span class="sxs-lookup"><span data-stu-id="15d48-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15d48-193">1280x720</span><span class="sxs-lookup"><span data-stu-id="15d48-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="15d48-194">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-195">Intel HD Graphics deuxième et troisième générations</span><span class="sxs-lookup"><span data-stu-id="15d48-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d48-196">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="15d48-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="15d48-198">Intel HD Graphics deuxième et troisième générations avec GraphicsScore ≥ 5,0</span><span class="sxs-lookup"><span data-stu-id="15d48-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="15d48-199">Fonctionnalités vidéo sur les appareils mobiles</span><span class="sxs-lookup"><span data-stu-id="15d48-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="15d48-200">Le tableau ci-dessous décrit les fonctionnalités vidéo maximales pour les appareils mobiles pris en charge.</span><span class="sxs-lookup"><span data-stu-id="15d48-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="15d48-201">Pour plus d’informations sur la prise en charge des appareils mobiles, voir [planification pour les clients mobiles dans Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="15d48-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="15d48-202">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="15d48-202">Feature</span></span></th>
<th><span data-ttu-id="15d48-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="15d48-203">Windows Phone</span></span></th>
<th><span data-ttu-id="15d48-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="15d48-204">iPhone</span></span></th>
<th><span data-ttu-id="15d48-205">iPad</span><span class="sxs-lookup"><span data-stu-id="15d48-205">iPad</span></span></th>
<th><span data-ttu-id="15d48-206">Android</span><span class="sxs-lookup"><span data-stu-id="15d48-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15d48-207">Résolution d’encodage maximale H.264</span><span class="sxs-lookup"><span data-stu-id="15d48-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="15d48-208">VGA</span><span class="sxs-lookup"><span data-stu-id="15d48-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="15d48-209">QVGA : iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="15d48-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="15d48-210">VGA : iPhone 5</span><span class="sxs-lookup"><span data-stu-id="15d48-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="15d48-211">720p : iPhone 5S et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="15d48-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="15d48-212">VGA : iPad 2 et version ultérieure/iPad mini 1 et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="15d48-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="15d48-213">720p : iPad Air/iPad mini 2/iPad Pro et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="15d48-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="15d48-214">Jusqu’à VGA en fonction du modèle d’appareil</span><span class="sxs-lookup"><span data-stu-id="15d48-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d48-215">Résolution de décodage maximale H.264</span><span class="sxs-lookup"><span data-stu-id="15d48-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="15d48-216">VGA</span><span class="sxs-lookup"><span data-stu-id="15d48-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="15d48-217">QVGA : iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="15d48-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="15d48-218">VGA : iPhone 5</span><span class="sxs-lookup"><span data-stu-id="15d48-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="15d48-219">720p : iPhone 5S et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="15d48-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="15d48-220">VGA : iPad 2 et version ultérieure/iPad mini 1 et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="15d48-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="15d48-221">720p : iPad Air/iPad mini 2/iPad Pro et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="15d48-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="15d48-222">Jusqu’à VGA en fonction du modèle d’appareil</span><span class="sxs-lookup"><span data-stu-id="15d48-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

