---
title: 'Lync Server 2013 : configuration technique requise pour Response Group'
description: 'Lync Server 2013 : configuration technique requise pour Response Group.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3125ed8c732960e23970229e99bf5a8487eb96a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550320"
---
# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="407bd-103">Configuration technique requise pour Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="407bd-103">Technical requirements for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="407bd-104">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="407bd-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="407bd-105">Cette section décrit les exigences techniques suivantes pour l’application Response Group :</span><span class="sxs-lookup"><span data-stu-id="407bd-105">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="407bd-106">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="407bd-106">Hardware requirements</span></span>

  - <span data-ttu-id="407bd-107">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="407bd-107">Software requirements</span></span>

  - <span data-ttu-id="407bd-108">Conditions requises en matière de ports</span><span class="sxs-lookup"><span data-stu-id="407bd-108">Port requirements</span></span>

  - <span data-ttu-id="407bd-109">Conditions requises pour les fichiers audio</span><span class="sxs-lookup"><span data-stu-id="407bd-109">Audio file requirements</span></span>

  - <span data-ttu-id="407bd-110">Configuration requise de l’outil de configuration Response Group</span><span class="sxs-lookup"><span data-stu-id="407bd-110">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="407bd-111">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="407bd-111">Hardware Requirements</span></span>

<span data-ttu-id="407bd-112">L’application Response Group a les mêmes besoins en matière de matériel que les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="407bd-112">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="407bd-113">Pour plus d’informations sur la configuration matérielle requise, voir [Server Hardware Platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="407bd-113">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="407bd-114">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="407bd-114">Software Requirements</span></span>

<span data-ttu-id="407bd-115">L’application Response Group a les mêmes exigences en matière de système d’exploitation et de logiciels que les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="407bd-115">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="407bd-116">Pour plus d’informations sur la configuration logicielle requise, voir [serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="407bd-116">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="407bd-117">Si vous utilisez des fichiers audio Windows Media (. WMA) pour la musique et les annonces d’un groupe Response Group, tous les serveurs frontaux ou les éditions standard qui exécutent l’application Response Group doivent avoir installé le module d’exécution du format Windows Media pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="407bd-117">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="407bd-118">Pour Windows Server 2008 R2, le runtime du format Windows Media est installé dans le cadre de l’expérience Bureau Windows.</span><span class="sxs-lookup"><span data-stu-id="407bd-118">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="407bd-119">Pour plus d’informations sur les conditions requises pour l’audio, voir « Conditions requises pour les fichiers audio » plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="407bd-119">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="407bd-120">Configuration requise pour les ports</span><span class="sxs-lookup"><span data-stu-id="407bd-120">Port Requirements</span></span>

<span data-ttu-id="407bd-121">L’application Response Group utilise les ports suivants :</span><span class="sxs-lookup"><span data-stu-id="407bd-121">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="407bd-122">**Port 5071**     Utilisé pour les demandes d’écoute SIP</span><span class="sxs-lookup"><span data-stu-id="407bd-122">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="407bd-123">**Port 8404**     Utilisé pour les communications entre les serveurs</span><span class="sxs-lookup"><span data-stu-id="407bd-123">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="407bd-124">Ce port est utilisé pour le service de mise en correspondance et est requis lorsque l’application Response Group est déployée dans un pool comportant plusieurs serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="407bd-124">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="407bd-125">Ces ports sont des paramètres par défaut que vous pouvez modifier à l’aide de l’applet de commande <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="407bd-125">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="407bd-126">Pour plus d’informations sur cette applet de commande, voir la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="407bd-126">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="407bd-127">Conditions requises pour les fichiers audio</span><span class="sxs-lookup"><span data-stu-id="407bd-127">Audio File Requirements</span></span>

<span data-ttu-id="407bd-128">L’application Response Group prend en charge le format de fichier Wave (. wav) et le format de fichier audio Windows Media (. WMA) pour les messages Response Group, la musique d’attente ou les questions à réponse vocale interactive (IVR).</span><span class="sxs-lookup"><span data-stu-id="407bd-128">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="407bd-129">Le format de fichier audio Windows Media nécessite que le runtime de format Windows Media soit installé sur les serveurs frontaux exécutant Windows Server 2008 R2 et Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="407bd-129">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="407bd-130">Pour plus d’informations, voir « Configuration logicielle requise » plus haut dans cette section.</span><span class="sxs-lookup"><span data-stu-id="407bd-130">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="407bd-131">Formats de fichiers Wave pris en charge</span><span class="sxs-lookup"><span data-stu-id="407bd-131">Supported Wave File Formats</span></span>

<span data-ttu-id="407bd-132">Tous les fichiers son doivent répondre aux conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="407bd-132">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="407bd-133">fichier 8 bits ou 16 bits ;</span><span class="sxs-lookup"><span data-stu-id="407bd-133">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="407bd-134">format LPCM (Linear Pulse Code Modulation), A-Law ou mu-Law ;</span><span class="sxs-lookup"><span data-stu-id="407bd-134">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="407bd-135">mono ou stéréo ;</span><span class="sxs-lookup"><span data-stu-id="407bd-135">Mono or stereo</span></span>

  - <span data-ttu-id="407bd-136">4 Mo ou moins.</span><span class="sxs-lookup"><span data-stu-id="407bd-136">4MB or less</span></span>

<span data-ttu-id="407bd-137">Pour des performances de fichiers son optimales, il est recommandé d’utiliser un fichier son correspondant au profil suivant : 16 kHz, Mono, 16 bits.</span><span class="sxs-lookup"><span data-stu-id="407bd-137">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="407bd-138">Formats de fichiers audio Windows Media pris en charge</span><span class="sxs-lookup"><span data-stu-id="407bd-138">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="407bd-139">Si vous utilisez un fichier audio Windows Media, prévoyez d’utiliser de faibles vitesses de transmission et vérifiez les performances de votre système quand il est surchargé.</span><span class="sxs-lookup"><span data-stu-id="407bd-139">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="407bd-140">Vous pouvez utiliser Microsoft Expression Encoder 4 pour convertir un fichier au format audio Windows Media.</span><span class="sxs-lookup"><span data-stu-id="407bd-140">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="407bd-141">Pour télécharger Expression Encoder 4, reportez-vous à la rubrique [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) .</span><span class="sxs-lookup"><span data-stu-id="407bd-141">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="407bd-142">Configuration requise pour l'outil de configuration pour Response Group</span><span class="sxs-lookup"><span data-stu-id="407bd-142">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="407bd-143">L’outil de configuration Response Group prend en charge les combinaisons de systèmes d’exploitation et de navigateurs Web décrites dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="407bd-143">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="407bd-p107">Les versions 32 bits ou 64 bits des systèmes d'exploitation sont prises en charge. Seules les versions 32 bits d'Internet Explorer sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="407bd-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="407bd-146">Systèmes d’exploitation et navigateurs web pris en charge</span><span class="sxs-lookup"><span data-stu-id="407bd-146">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="407bd-147">Système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="407bd-147">Operating system</span></span></th>
<th><span data-ttu-id="407bd-148">Navigateur Web</span><span class="sxs-lookup"><span data-stu-id="407bd-148">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="407bd-149">Windows Vista avec Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="407bd-149">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="407bd-150">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="407bd-150">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="407bd-151">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-151">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="407bd-152">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-152">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407bd-153">Windows 7</span><span class="sxs-lookup"><span data-stu-id="407bd-153">Windows 7</span></span></p>
<p><span data-ttu-id="407bd-154">Windows 7 avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="407bd-154">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="407bd-155">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-155">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="407bd-156">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-156">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407bd-157">Windows Server 2008 avec Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="407bd-157">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="407bd-158">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="407bd-158">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="407bd-159">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-159">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="407bd-160">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-160">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407bd-161">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="407bd-161">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="407bd-162">Windows Server 2008 R2 avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="407bd-162">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="407bd-163">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-163">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="407bd-164">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-164">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="407bd-165">Console des agents Response Group</span><span class="sxs-lookup"><span data-stu-id="407bd-165">Response Group Agent Console</span></span>

<span data-ttu-id="407bd-166">La console des agents prend en charge les combinaisons de systèmes d’exploitation et de navigateurs indiquées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="407bd-166">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="407bd-p108">Les versions 32 bits ou 64 bits des systèmes d’exploitation sont prises en charge. Seules les versions 32 bits d’Internet Explorer sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="407bd-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="407bd-169">Systèmes d’exploitation et navigateurs web pris en charge</span><span class="sxs-lookup"><span data-stu-id="407bd-169">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="407bd-170">Système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="407bd-170">Operating system</span></span></th>
<th><span data-ttu-id="407bd-171">Navigateur Web</span><span class="sxs-lookup"><span data-stu-id="407bd-171">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="407bd-172">Windows Vista avec Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="407bd-172">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="407bd-173">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="407bd-173">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="407bd-174">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-174">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="407bd-175">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-175">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407bd-176">Windows 7</span><span class="sxs-lookup"><span data-stu-id="407bd-176">Windows 7</span></span></p>
<p><span data-ttu-id="407bd-177">Windows 7 avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="407bd-177">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="407bd-178">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-178">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="407bd-179">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-179">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="407bd-180">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="407bd-180">Firefox 10.0</span></span></p>
<p><span data-ttu-id="407bd-181">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="407bd-181">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407bd-182">Windows Server 2008 avec Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="407bd-182">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="407bd-183">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="407bd-183">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="407bd-184">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-184">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="407bd-185">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-185">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407bd-186">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="407bd-186">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="407bd-187">Windows Server 2008 R2 avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="407bd-187">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="407bd-188">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-188">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="407bd-189">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="407bd-189">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="407bd-190">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="407bd-190">Firefox 10.0</span></span></p>
<p><span data-ttu-id="407bd-191">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="407bd-191">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

