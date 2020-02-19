---
title: 'Lync Server 2013 : configuration vidéo requise pour les clients Lync'
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
ms.openlocfilehash: 1e4a8e99c50bc62565ed597e65cef73a6aaddd08
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="376db-102">Configuration requise pour la vidéo client Lync pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="376db-102">Lync client video requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="376db-103">_**Dernière modification de la rubrique :** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="376db-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="376db-104">Cette section décrit la prise en charge du matériel vidéo pour les appels vidéo Lync 2013 et explique comment déterminer la qualité vidéo attendue pour différentes configurations d’ordinateur, de tablette et d’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="376db-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="376db-105">Caractéristiques et fonctionnalités des ordinateurs de bureau et tablette Windows</span><span class="sxs-lookup"><span data-stu-id="376db-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="376db-106">Lync 2013 introduit l’accélération matérielle pour le codage et le décodage vidéo en fonction de la norme H. 264/MPEG-4 part 10 Advanced Video Coding standard.</span><span class="sxs-lookup"><span data-stu-id="376db-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="376db-107">Cette fonctionnalité permet aux ordinateurs dont la vitesse d’horloge du processeur est faible d’encoder et de décoder des vidéos avec des résolutions supérieures.</span><span class="sxs-lookup"><span data-stu-id="376db-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="376db-108">La configuration requise pour le matériel vidéo dépend de la configuration de l’ordinateur et de la résolution vidéo souhaitée.</span><span class="sxs-lookup"><span data-stu-id="376db-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="376db-109">Configuration requise du matériel vidéo</span><span class="sxs-lookup"><span data-stu-id="376db-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="376db-110">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="376db-110">Feature</span></span></th>
<th><span data-ttu-id="376db-111">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="376db-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="376db-112">Décodage matériel accéléré H.264 à l’aide de l’accélération vidéo DirectX (DXVA)</span><span class="sxs-lookup"><span data-stu-id="376db-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="376db-113">La carte graphique doit prendre en charge DirectX 9.0 et exposer le mode de décodage DXVA2_ModeH264_VLD_NoFGT.</span><span class="sxs-lookup"><span data-stu-id="376db-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="376db-114">Le pilote de carte graphique le plus récent doit être installé.</span><span class="sxs-lookup"><span data-stu-id="376db-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="376db-115">Pour plus d’informations sur les modes de <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>décodage, voir.</span><span class="sxs-lookup"><span data-stu-id="376db-115">For details about decoding modes, see <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="376db-116">Encodage matériel accéléré H.264 : chipset requis</span><span class="sxs-lookup"><span data-stu-id="376db-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="376db-117">Les solutions de codage vidéo avec accélération matérielle Intel suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="376db-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="376db-118">Chipsets Intel HD Graphics 2000, 2500, 3000, et 4000 de deuxième ou troisième générations (ou versions ultérieures) avec encodeurs vidéo matériel intégrés.</span><span class="sxs-lookup"><span data-stu-id="376db-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="376db-119">L’installation du pilote Intel HD Graphics 15.28.9.2884 ou le pilote le plus récent contenant les éléments suivants sont requis :</span><span class="sxs-lookup"><span data-stu-id="376db-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="376db-120">Pilote d’affichage 9.17.10.2884 ou le pilote le plus récent</span><span class="sxs-lookup"><span data-stu-id="376db-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="376db-121">Version de Hardware Media Foundation Transform (HMFT) 3.12.10.31 ou la dernière HMFT</span><span class="sxs-lookup"><span data-stu-id="376db-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="376db-122">Les solutions de codage vidéo avec accélération matérielle AMD suivantes sont prises en charge (nécessite des mises à jour CU1 pour Lync Server 2013) :</span><span class="sxs-lookup"><span data-stu-id="376db-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="376db-123">Le moteur de codec vidéo AMD, qui est disponible dans plusieurs cartes graphiques discrètes et dans des unités de traitement accélérées intégrées de processeurs accélérés de la série AMD.</span><span class="sxs-lookup"><span data-stu-id="376db-123">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="376db-124">Le pilote du moteur de codec vidéo AMD 9.12.0.0 ou une version ultérieure doit être installé.</span><span class="sxs-lookup"><span data-stu-id="376db-124">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="376db-125">Encodage matériel accéléré H.264 : caméra requise</span><span class="sxs-lookup"><span data-stu-id="376db-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="376db-126">Caméras vidéo USB avec encodeur matériel H.264 intégré conforme à la spécification USB Video Class (UVC) version 1.5.</span><span class="sxs-lookup"><span data-stu-id="376db-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="376db-127">Lync 2013 prend en charge les caméras UVC 1,5 avec Windows 8 ou Windows 8,1, qui inclut la prise en charge de UVC 1,5.</span><span class="sxs-lookup"><span data-stu-id="376db-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="376db-128">Dans la mesure où Windows 7 ne prend pas en charge UVC 1.5, Lync 2013 considère les caméras UVC 1.5 comme des caméras génériques sans prise en charge de l’encodage matériel.</span><span class="sxs-lookup"><span data-stu-id="376db-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="376db-129">Identification des fonctionnalités d’encodage et de décodage vidéo H.264</span><span class="sxs-lookup"><span data-stu-id="376db-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="376db-130">En règle générale, quatre facteurs principaux déterminent les capacités d’encodage et de décodage maximales d’une configuration donnée :</span><span class="sxs-lookup"><span data-stu-id="376db-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="376db-131">Prise en charge du décodage matériel accéléré avec DXVA</span><span class="sxs-lookup"><span data-stu-id="376db-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="376db-132">Prise en charge de l’encodage matériel accéléré</span><span class="sxs-lookup"><span data-stu-id="376db-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="376db-133">Nombre de cœurs physiques</span><span class="sxs-lookup"><span data-stu-id="376db-133">Number of physical cores</span></span>

  - <span data-ttu-id="376db-134">Indice de performance Windows (WEI)</span><span class="sxs-lookup"><span data-stu-id="376db-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="376db-135">L’Outil d’évaluation système Windows (WinSAT) détermine l’indice WEI.</span><span class="sxs-lookup"><span data-stu-id="376db-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="376db-136">Lorsque vous exécutez l’outil WinSAT, il génère un document XML formel. Assessment sur l’ordinateur dans le répertoire%\\windir\\%\\WinSAT datastore.</span><span class="sxs-lookup"><span data-stu-id="376db-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="376db-137">Ce fichier XML contient les deux scores suivants qui sont essentiels pour déterminer les capacités d’encodage et de décodage :</span><span class="sxs-lookup"><span data-stu-id="376db-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="376db-138">La valeur VideoEncodeScore indique la capacité d’encodage vidéo logiciel de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="376db-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="376db-139">La valeur GraphicsScore indique la capacité d’encodage matériel accéléré de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="376db-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="376db-p106">Les trois tableaux suivants expliquent les capacités d’encodage et de décodage maximales pour différents types de PC en fonction de l’accélération matérielle prise en charge. Pour des résolutions de 640x360 et supérieures, la fréquence d’images maximale prise en charge est de 30 images par secondes (i/s). Pour des résolutions inférieures à 640x360, la fréquence d’images maximale prise en charge est de 15 i/s.</span><span class="sxs-lookup"><span data-stu-id="376db-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="376db-143">Ordinateur sans DXVA et sans encodeur matériel accéléré</span><span class="sxs-lookup"><span data-stu-id="376db-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="376db-144">Résolution d’encodeur compatible</span><span class="sxs-lookup"><span data-stu-id="376db-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="376db-145">Résolution de décodeur compatible</span><span class="sxs-lookup"><span data-stu-id="376db-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="376db-146">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="376db-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="376db-147">424x240</span><span class="sxs-lookup"><span data-stu-id="376db-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="376db-148">424x240 (640x360 à 15 i/s pour des scénarios de réception uniquement)</span><span class="sxs-lookup"><span data-stu-id="376db-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="376db-149">1 cœur et VideoEncodeScore ≥ 4,0</span><span class="sxs-lookup"><span data-stu-id="376db-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="376db-150">640x360</span><span class="sxs-lookup"><span data-stu-id="376db-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="376db-151">640x360</span><span class="sxs-lookup"><span data-stu-id="376db-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="376db-152">2 cœurs et VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="376db-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="376db-153">640x360</span><span class="sxs-lookup"><span data-stu-id="376db-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="376db-154">1280x720</span><span class="sxs-lookup"><span data-stu-id="376db-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="376db-155">2 cœurs et VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="376db-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="376db-156">640x360</span><span class="sxs-lookup"><span data-stu-id="376db-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="376db-157">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-158">4 cœurs et VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="376db-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="376db-159">1280x720</span><span class="sxs-lookup"><span data-stu-id="376db-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="376db-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="376db-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="376db-161">4 cœurs et VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="376db-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="376db-162">1280x720</span><span class="sxs-lookup"><span data-stu-id="376db-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="376db-163">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-164">4 cœurs et VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="376db-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="376db-165">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-167">S/O</span><span class="sxs-lookup"><span data-stu-id="376db-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="376db-168">Ordinateur avec DXVA mais sans encodeur matériel accéléré</span><span class="sxs-lookup"><span data-stu-id="376db-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="376db-169">Résolution d’encodeur compatible</span><span class="sxs-lookup"><span data-stu-id="376db-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="376db-170">Résolution de décodeur compatible</span><span class="sxs-lookup"><span data-stu-id="376db-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="376db-171">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="376db-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="376db-172">424x240</span><span class="sxs-lookup"><span data-stu-id="376db-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="376db-173">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-174">1 cœur et VideoEncodeScore ≥ 3,0</span><span class="sxs-lookup"><span data-stu-id="376db-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="376db-175">640x360</span><span class="sxs-lookup"><span data-stu-id="376db-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="376db-176">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-177">2 cœurs et VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="376db-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="376db-178">960x540</span><span class="sxs-lookup"><span data-stu-id="376db-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="376db-179">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-180">2 cœurs et VideoEncodeScore ≥ 6,0</span><span class="sxs-lookup"><span data-stu-id="376db-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="376db-181">1280x720</span><span class="sxs-lookup"><span data-stu-id="376db-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="376db-182">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-183">4 cœurs et VideoEncodeScore ≥ 6,7</span><span class="sxs-lookup"><span data-stu-id="376db-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="376db-184">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-186">4 cœurs et VideoEncodeScore ≥ 8,2</span><span class="sxs-lookup"><span data-stu-id="376db-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="376db-187">Le score WinSAT sur Windows 7 est limité à un maximum de 7,9.</span><span class="sxs-lookup"><span data-stu-id="376db-187">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="376db-188">Par conséquent, la fonctionnalité de codage pour un ordinateur dépourvu de codeur matériel accéléré ne peut être obtenue que sur Windows 8 ou Windows 8,1, où le score WinSAT maximal est de 9,9.</span><span class="sxs-lookup"><span data-stu-id="376db-188">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="376db-189">Ordinateur avec DXVA et avec un encodeur matériel accéléré Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="376db-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="376db-190">Résolution d’encodeur compatible</span><span class="sxs-lookup"><span data-stu-id="376db-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="376db-191">Résolution de décodeur compatible</span><span class="sxs-lookup"><span data-stu-id="376db-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="376db-192">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="376db-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="376db-193">1280x720</span><span class="sxs-lookup"><span data-stu-id="376db-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="376db-194">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-195">Intel HD Graphics deuxième et troisième générations</span><span class="sxs-lookup"><span data-stu-id="376db-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="376db-196">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="376db-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="376db-198">Intel HD Graphics deuxième et troisième générations avec GraphicsScore ≥ 5,0</span><span class="sxs-lookup"><span data-stu-id="376db-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="376db-199">Fonctionnalités de vidéo d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="376db-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="376db-200">Le tableau suivant décrit les capacités vidéo maximales pour les appareils mobiles pris en charge.</span><span class="sxs-lookup"><span data-stu-id="376db-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="376db-201">Pour plus d’informations sur la prise en charge des appareils mobiles, voir [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="376db-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="376db-202">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="376db-202">Feature</span></span></th>
<th><span data-ttu-id="376db-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="376db-203">Windows Phone</span></span></th>
<th><span data-ttu-id="376db-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="376db-204">iPhone</span></span></th>
<th><span data-ttu-id="376db-205">iPad</span><span class="sxs-lookup"><span data-stu-id="376db-205">iPad</span></span></th>
<th><span data-ttu-id="376db-206">Android</span><span class="sxs-lookup"><span data-stu-id="376db-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="376db-207">Résolution maximale de H. 264</span><span class="sxs-lookup"><span data-stu-id="376db-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="376db-208">VGA</span><span class="sxs-lookup"><span data-stu-id="376db-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="376db-209">QVGA : iPhone-n</span><span class="sxs-lookup"><span data-stu-id="376db-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="376db-210">VGA : iPhone 5</span><span class="sxs-lookup"><span data-stu-id="376db-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="376db-211">720p : iPhone 5S et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="376db-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="376db-212">VGA : iPad 2 et version ultérieure/iPad mini 1 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="376db-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="376db-213">720p : iPad air/iPad mini 2/iPad Pro et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="376db-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="376db-214">Jusqu’à VGA en fonction du modèle d’appareil</span><span class="sxs-lookup"><span data-stu-id="376db-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="376db-215">Résolution de décodage maximale H. 264</span><span class="sxs-lookup"><span data-stu-id="376db-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="376db-216">VGA</span><span class="sxs-lookup"><span data-stu-id="376db-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="376db-217">QVGA : iPhone-n</span><span class="sxs-lookup"><span data-stu-id="376db-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="376db-218">VGA : iPhone 5</span><span class="sxs-lookup"><span data-stu-id="376db-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="376db-219">720p : iPhone 5S et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="376db-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="376db-220">VGA : iPad 2 et version ultérieure/iPad mini 1 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="376db-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="376db-221">720p : iPad air/iPad mini 2/iPad Pro et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="376db-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="376db-222">Jusqu’à VGA en fonction du modèle d’appareil</span><span class="sxs-lookup"><span data-stu-id="376db-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

