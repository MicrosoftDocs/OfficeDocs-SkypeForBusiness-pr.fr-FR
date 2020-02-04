---
title: 'Lync Server 2013 : Configuration technique requise pour Response Group'
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
ms.openlocfilehash: b7ab381a70a8a6d69170959fbaf488982887d765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="aa4de-102">Configuration technique requise pour Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa4de-102">Technical requirements for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa4de-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="aa4de-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="aa4de-104">Cette section décrit les exigences techniques suivantes pour l’application Response Group :</span><span class="sxs-lookup"><span data-stu-id="aa4de-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="aa4de-105">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="aa4de-105">Hardware requirements</span></span>

  - <span data-ttu-id="aa4de-106">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="aa4de-106">Software requirements</span></span>

  - <span data-ttu-id="aa4de-107">Conditions requises en matière de ports</span><span class="sxs-lookup"><span data-stu-id="aa4de-107">Port requirements</span></span>

  - <span data-ttu-id="aa4de-108">Configuration requise pour le fichier audio</span><span class="sxs-lookup"><span data-stu-id="aa4de-108">Audio file requirements</span></span>

  - <span data-ttu-id="aa4de-109">Configuration requise pour l’outil de configuration de Response Group</span><span class="sxs-lookup"><span data-stu-id="aa4de-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="aa4de-110">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="aa4de-110">Hardware Requirements</span></span>

<span data-ttu-id="aa4de-111">L’application de Response Group a les mêmes exigences matérielles que les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="aa4de-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="aa4de-112">Pour plus d’informations sur la configuration matérielle requise, voir [plates-formes matérielles pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="aa4de-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="aa4de-113">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="aa4de-113">Software Requirements</span></span>

<span data-ttu-id="aa4de-114">Comme serveur frontal, l’application de Response Group a les mêmes exigences relatives au système d’exploitation et aux configurations logicielles requises.</span><span class="sxs-lookup"><span data-stu-id="aa4de-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="aa4de-115">Pour plus d’informations sur la configuration logicielle requise, voir [prise en charge du système d’exploitation serveur et outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="aa4de-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="aa4de-116">Si vous utilisez des fichiers Windows Media audio (. WMA) pour la musique et les annonces du groupe réponse, tous les serveurs frontaux ou les éditions standard qui exécutent l’application Response Group doivent avoir installé le runtime du format Windows Media pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="aa4de-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="aa4de-117">Pour Windows Server 2008 R2, le runtime Windows Media Format Runtime est installé dans le cadre de l’expérience de bureau Windows.</span><span class="sxs-lookup"><span data-stu-id="aa4de-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="aa4de-118">Pour plus d’informations sur la configuration audio requise, voir « exigences relatives au fichier audio » plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="aa4de-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="aa4de-119">Configuration requise pour les ports</span><span class="sxs-lookup"><span data-stu-id="aa4de-119">Port Requirements</span></span>

<span data-ttu-id="aa4de-120">L’application Response Group utilise les ports suivants :</span><span class="sxs-lookup"><span data-stu-id="aa4de-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="aa4de-121">**Port 5071**   utilisé pour les demandes d’écoute SIP</span><span class="sxs-lookup"><span data-stu-id="aa4de-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="aa4de-122">**Port 8404**   utilisé pour les communications entre les serveurs</span><span class="sxs-lookup"><span data-stu-id="aa4de-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa4de-123">Ce port est utilisé pour le service de mise en correspondance et est requis lors du déploiement de l’application Response Group dans un pool qui comporte plusieurs serveurs front-end.</span><span class="sxs-lookup"><span data-stu-id="aa4de-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="aa4de-124">Ces ports sont les paramètres par défaut que vous pouvez modifier à l’aide de l’applet de commande <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="aa4de-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="aa4de-125">Pour plus d’informations sur cette applet de connexion, consultez la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="aa4de-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="aa4de-126">Conditions requises pour les fichiers audio</span><span class="sxs-lookup"><span data-stu-id="aa4de-126">Audio File Requirements</span></span>

<span data-ttu-id="aa4de-127">L’application Response Group prend en charge le format de fichier Wave (. wav) et le format de fichier Windows Media audio (. WMA) pour les messages de groupe de réponse, la musique en attente ou les questions de réponse vocale interactive.</span><span class="sxs-lookup"><span data-stu-id="aa4de-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="aa4de-128">Le format de fichier audio Windows Media nécessite que le runtime du format Windows Media soit installé sur les serveurs frontaux exécutant Windows Server 2008 R2 et Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="aa4de-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="aa4de-129">Pour plus d’informations, reportez-vous à « Configuration logicielle requise » plus haut dans cette section.</span><span class="sxs-lookup"><span data-stu-id="aa4de-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="aa4de-130">Formats de fichiers Wave pris en charge</span><span class="sxs-lookup"><span data-stu-id="aa4de-130">Supported Wave File Formats</span></span>

<span data-ttu-id="aa4de-131">Tous les fichiers Wave doivent répondre aux conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="aa4de-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="aa4de-132">fichier 8 bits ou 16 bits ;</span><span class="sxs-lookup"><span data-stu-id="aa4de-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="aa4de-133">format LPCM (Linear Pulse Code Modulation), A-Law ou mu-Law ;</span><span class="sxs-lookup"><span data-stu-id="aa4de-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="aa4de-134">mono ou stéréo ;</span><span class="sxs-lookup"><span data-stu-id="aa4de-134">Mono or stereo</span></span>

  - <span data-ttu-id="aa4de-135">4 Mo ou moins.</span><span class="sxs-lookup"><span data-stu-id="aa4de-135">4MB or less</span></span>

<span data-ttu-id="aa4de-136">Pour des performances de fichiers Wave optimales, nous vous recommandons d’utiliser un fichier Wave correspondant au profil suivant : 16 kHz, Mono, 16 bits.</span><span class="sxs-lookup"><span data-stu-id="aa4de-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="aa4de-137">Formats de fichiers audio Windows Media pris en charge</span><span class="sxs-lookup"><span data-stu-id="aa4de-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="aa4de-138">Si vous utilisez un fichier audio Windows Media, prévoyez d’utiliser de faibles vitesses de transmission et vérifiez les performances de votre système quand il est surchargé.</span><span class="sxs-lookup"><span data-stu-id="aa4de-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="aa4de-139">Vous pouvez utiliser Microsoft Expression Encoder 4 pour convertir un fichier au format audio Windows Media.</span><span class="sxs-lookup"><span data-stu-id="aa4de-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="aa4de-140">Pour télécharger Expression Encoder 4 [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843), voir.</span><span class="sxs-lookup"><span data-stu-id="aa4de-140">To download Expression Encoder 4, see [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="aa4de-141">Conditions requises pour l’outil de configuration Response Group</span><span class="sxs-lookup"><span data-stu-id="aa4de-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="aa4de-142">L’outil de configuration de Response Group prend en charge les combinaisons de systèmes d’exploitation et de navigateurs Web décrits dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="aa4de-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa4de-p107">Les versions 32 bits ou 64 bits des systèmes d’exploitation sont prises en charge. Seules les versions 32 bits d’Internet Explorer sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="aa4de-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="aa4de-145">Systèmes d’exploitation et navigateurs web pris en charge</span><span class="sxs-lookup"><span data-stu-id="aa4de-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa4de-146">Système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="aa4de-146">Operating system</span></span></th>
<th><span data-ttu-id="aa4de-147">Navigateur web</span><span class="sxs-lookup"><span data-stu-id="aa4de-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa4de-148">Windows Vista avec Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="aa4de-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="aa4de-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="aa4de-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="aa4de-150">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa4de-151">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa4de-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="aa4de-152">Windows 7</span></span></p>
<p><span data-ttu-id="aa4de-153">Windows 7 avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="aa4de-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="aa4de-154">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa4de-155">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa4de-156">Windows Server 2008 avec Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="aa4de-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="aa4de-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="aa4de-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="aa4de-158">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa4de-159">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa4de-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="aa4de-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="aa4de-161">Windows Server 2008 R2 avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="aa4de-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="aa4de-162">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa4de-163">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="aa4de-164">Console des agents Response Group</span><span class="sxs-lookup"><span data-stu-id="aa4de-164">Response Group Agent Console</span></span>

<span data-ttu-id="aa4de-165">La console des agents prend en charge les combinaisons de systèmes d’exploitation et de navigateurs indiquées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="aa4de-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa4de-p108">Les versions 32 bits ou 64 bits des systèmes d’exploitation sont prises en charge. Seules les versions 32 bits d’Internet Explorer sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="aa4de-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="aa4de-168">Systèmes d’exploitation et navigateurs web pris en charge</span><span class="sxs-lookup"><span data-stu-id="aa4de-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa4de-169">Système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="aa4de-169">Operating system</span></span></th>
<th><span data-ttu-id="aa4de-170">Navigateur web</span><span class="sxs-lookup"><span data-stu-id="aa4de-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa4de-171">Windows Vista avec Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="aa4de-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="aa4de-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="aa4de-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="aa4de-173">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa4de-174">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa4de-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="aa4de-175">Windows 7</span></span></p>
<p><span data-ttu-id="aa4de-176">Windows 7 avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="aa4de-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="aa4de-177">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa4de-178">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="aa4de-179">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="aa4de-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="aa4de-180">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="aa4de-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa4de-181">Windows Server 2008 avec Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="aa4de-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="aa4de-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="aa4de-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="aa4de-183">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa4de-184">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa4de-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="aa4de-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="aa4de-186">Windows Server 2008 R2 avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="aa4de-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="aa4de-187">Internet Explorer 8 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa4de-188">Internet Explorer 9 (mode natif)</span><span class="sxs-lookup"><span data-stu-id="aa4de-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="aa4de-189">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="aa4de-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="aa4de-190">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="aa4de-190">Chrome 18.0</span></span></p></td>
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

