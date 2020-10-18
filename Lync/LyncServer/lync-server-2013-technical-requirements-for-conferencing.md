---
title: Configuration technique requise pour Lync Server 2013 pour les conférences
description: Configuration technique requise pour Lync Server 2013 pour les conférences.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3b787d84288d789cd0d824081439004f19327e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577120"
---
# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="95a20-103">Configuration technique requise pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95a20-103">Technical requirements for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95a20-104">_**Dernière modification de la rubrique :** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="95a20-104">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="95a20-105">Pour Lync Server 2013, les fonctionnalités de conférence rendez-vous, de conférence A/V, de conférence par messagerie instantanée et de conférence Web s’exécutent toujours sur des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="95a20-105">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="95a20-106">Cette section présente la configuration matérielle et logicielle requise pour ces serveurs ainsi que les types de colocalisation pris en charge.</span><span class="sxs-lookup"><span data-stu-id="95a20-106">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="95a20-107">La conférence rendez-vous est une fonctionnalité qui intègre divers composants.</span><span class="sxs-lookup"><span data-stu-id="95a20-107">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="95a20-108">Certains des composants sont spécifiques à la Conférence rendez-vous et d’autres sont des composants voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="95a20-108">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="95a20-109">Cette section décrit la configuration requise pour les composants spécifiques à la conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="95a20-109">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="95a20-110">Pour plus d’informations sur la configuration requise pour le serveur de médiation et la passerelle RTC (réseau téléphonique commuté), voir [composant serveur de médiation dans Lync server 2013](lync-server-2013-mediation-server-component.md) et [composants et topologies pour le serveur de médiation dans Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="95a20-110">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="95a20-111">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="95a20-111">Hardware Requirements</span></span>

<span data-ttu-id="95a20-112">Étant donné que les conférences Web et les conférences A/V sont colocalisées avec le serveur frontal, la configuration matérielle requise du serveur est la même que pour les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="95a20-112">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="95a20-113">Pour plus d’informations sur la configuration matérielle requise, voir [Server Hardware Platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="95a20-113">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="95a20-114">Les composants suivants requis pour la Conférence rendez-vous ont également la configuration matérielle requise pour les serveurs frontaux :</span><span class="sxs-lookup"><span data-stu-id="95a20-114">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="95a20-115">service d’application</span><span class="sxs-lookup"><span data-stu-id="95a20-115">Application service</span></span>

  - <span data-ttu-id="95a20-116">application Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="95a20-116">Conferencing Attendant application</span></span>

  - <span data-ttu-id="95a20-117">application d’annonce de conférence</span><span class="sxs-lookup"><span data-stu-id="95a20-117">Conferencing Announcement application</span></span>

<span data-ttu-id="95a20-118">La configuration matérielle requise pour le serveur frontal est la même que pour de nombreux autres rôles serveur dans Lync Server 2013 sont décrits dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="95a20-118">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="95a20-119">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="95a20-119">Software Requirements</span></span>

<span data-ttu-id="95a20-120">Étant donné que les conférences Web et les conférences A/V sont colocalisées avec le serveur frontal, la configuration logicielle requise du serveur est la même que pour les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="95a20-120">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="95a20-121">Pour plus d’informations sur la configuration logicielle requise, voir [serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="95a20-121">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="95a20-122">Pour la conférence Web, Lync Server 2013 nécessite également Office Web Apps et Office Web Apps Server (anciennement appelé serveur WAC) pour gérer les présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="95a20-122">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="95a20-123">Pour plus d’informations, reportez-vous à la rubrique Configuration de l' [intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="95a20-123">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="95a20-124">Pour les applications de conférence rendez-vous, d’applications, de surveillance de conférence et d’annonce de conférence, la configuration requise du système d’exploitation est la même que pour les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="95a20-124">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="95a20-125">Pour plus d’informations sur la configuration logicielle requise, voir [serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="95a20-125">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="95a20-126">Application de surveillance de conférence et application d’annonce de conférence nécessitent que le module d’exécution du format Windows Media soit installé sur les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="95a20-126">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="95a20-127">Ce module est nécessaire pour lire les fichiers audio Windows Media (WMA) d’attente musicale, les noms enregistrés et les invites.</span><span class="sxs-lookup"><span data-stu-id="95a20-127">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="95a20-128">À l’exception de Windows Server 2012 et Windows Server 2012 R2, le runtime de format Windows Media est installé automatiquement dans le cadre de l’expérience de bureau Windows lorsque vous exécutez le programme d’installation, mais vous devrez peut-être redémarrer l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="95a20-128">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="95a20-129">Par conséquent, avant d’exécuter le programme d’installation, nous vous recommandons d’installer le module d’exécution du format Windows Media en même temps que l’expérience Bureau Windows, à laquelle il est intégré.</span><span class="sxs-lookup"><span data-stu-id="95a20-129">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="95a20-130">Windows Server 2012 et Windows Server 2012 R2 nécessitent Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="95a20-130">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="95a20-131">Configuration requise pour les ports dans le cadre de la conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="95a20-131">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="95a20-p107">Le tableau suivant décrit les ports utilisés par la fonctionnalité de conférence rendez-vous. Si vous utilisez un dispositif d’équilibrage de charge, vérifiez qu’il est configuré pour les ports utilisés par les applications appelées à s’exécuter dans le pool.</span><span class="sxs-lookup"><span data-stu-id="95a20-p107">The following table describes the ports that are used by dial-in conferencing. If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="95a20-134">Ces ports sont des paramètres par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="95a20-134">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="95a20-135">Pour plus d’informations sur cette applet de commande, voir la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="95a20-135">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="95a20-136">Toutes les instances d’une même application présentes dans un pool utilisent le même port d’écoute SIP.</span><span class="sxs-lookup"><span data-stu-id="95a20-136">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="95a20-137">Ports utilisés par la fonctionnalité de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="95a20-137">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95a20-138">Numéro du port</span><span class="sxs-lookup"><span data-stu-id="95a20-138">Port number</span></span></th>
<th><span data-ttu-id="95a20-139">Description</span><span class="sxs-lookup"><span data-stu-id="95a20-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95a20-140">5072</span><span class="sxs-lookup"><span data-stu-id="95a20-140">5072</span></span></p></td>
<td><p><span data-ttu-id="95a20-141">Utilisé par l’application de surveillance de conférence pour les demandes d’écoute SIP</span><span class="sxs-lookup"><span data-stu-id="95a20-141">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a20-142">5073</span><span class="sxs-lookup"><span data-stu-id="95a20-142">5073</span></span></p></td>
<td><p><span data-ttu-id="95a20-143">Utilisé par l’application d’annonce de conférence pour les demandes d’écoute SIP</span><span class="sxs-lookup"><span data-stu-id="95a20-143">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="95a20-144">Clients pris en charge pour la conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="95a20-144">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="95a20-145">Vous pouvez utiliser le client suivant pour planifier des conférences locales prenant en charge un accès entrant :</span><span class="sxs-lookup"><span data-stu-id="95a20-145">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="95a20-146">Complément de réunion en ligne pour Lync 2013 (installé automatiquement lors de l’installation de Lync 2013 ou Attendee)</span><span class="sxs-lookup"><span data-stu-id="95a20-146">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="95a20-147">Configuration requise pour la page des paramètres de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="95a20-147">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="95a20-148">La page Paramètres de conférence rendez-vous prend en charge les combinaisons de systèmes d’exploitation et de navigateurs Web décrites dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="95a20-148">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="95a20-149">Les versions 32 bits et 64 bits des systèmes d’exploitation sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="95a20-149">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="95a20-150">Systèmes d’exploitation et navigateurs web pris en charge</span><span class="sxs-lookup"><span data-stu-id="95a20-150">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95a20-151">Système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="95a20-151">Operating system</span></span></th>
<th><span data-ttu-id="95a20-152">Navigateur Web</span><span class="sxs-lookup"><span data-stu-id="95a20-152">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95a20-153">Windows 7</span><span class="sxs-lookup"><span data-stu-id="95a20-153">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="95a20-154">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="95a20-154">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="95a20-155">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="95a20-155">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="95a20-156">Firefox</span><span class="sxs-lookup"><span data-stu-id="95a20-156">Firefox</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a20-157">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="95a20-157">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="95a20-158">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="95a20-158">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="95a20-159">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="95a20-159">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="95a20-160">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="95a20-160">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a20-161">Mac OS</span><span class="sxs-lookup"><span data-stu-id="95a20-161">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="95a20-162">Firefox</span><span class="sxs-lookup"><span data-stu-id="95a20-162">Firefox</span></span></p>
<p><span data-ttu-id="95a20-163">Safari</span><span class="sxs-lookup"><span data-stu-id="95a20-163">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="95a20-164">Exigences concernant les fichiers audio pour la conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="95a20-164">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="95a20-165">Lync Server 2013 ne prend pas en charge la personnalisation des invites vocales et de la musique pour les conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="95a20-165">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="95a20-166">Toutefois, si vous avez un besoin important de votre entreprise qui nécessite de modifier les fichiers audio par défaut, consultez l’article 961177 de la base de connaissances Microsoft, [Comment personnaliser les invites vocales ou les fichiers musicaux pour les conférences audio de rendez-vous dans Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span><span class="sxs-lookup"><span data-stu-id="95a20-166">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="95a20-167">Vous pouvez également utiliser l’utilitaire de gestion des [invites vocales personnalisées du service de conférence Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkid=396880) , qui permet aux administrateurs de remplacer les invites vocales par défaut utilisées lorsqu’un appelant téléphonique rejoint une réunion Lync avec des invites personnalisées pour fournir une autre expérience d’entrée de réunion.</span><span class="sxs-lookup"><span data-stu-id="95a20-167">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](https://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="95a20-168">Les invites vocales personnalisées peuvent être installées sur un serveur qui exécute Lync Server 2010 ou Lync Server 2013, Enterprise ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="95a20-168">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="95a20-169">Application de surveillance de conférence et application d’annonce de conférence ont les exigences suivantes en matière d’attente musicale, de nom enregistré et de fichiers d’invite audio :</span><span class="sxs-lookup"><span data-stu-id="95a20-169">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="95a20-170">Format de fichier audio Windows Media (.wma)</span><span class="sxs-lookup"><span data-stu-id="95a20-170">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="95a20-171">Mono 16 bits</span><span class="sxs-lookup"><span data-stu-id="95a20-171">16-bit mono</span></span>

  - <span data-ttu-id="95a20-172">CBR (vitesse de transmission constante) 2 passes 48 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="95a20-172">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="95a20-173">Niveau de voix à -24 Db</span><span class="sxs-lookup"><span data-stu-id="95a20-173">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="95a20-174">Exigences imposées aux utilisateurs de la conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="95a20-174">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="95a20-175">Les utilisateurs de la conférence rendez-vous doivent avoir un numéro de téléphone ou de poste unique rattaché à leur compte.</span><span class="sxs-lookup"><span data-stu-id="95a20-175">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="95a20-176">Cette exigence n’empêche pas l’authentification dans le cadre de la conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="95a20-176">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="95a20-177">Les utilisateurs d’entreprise (c’est-à-dire, les utilisateurs disposant d’informations d’identification des services de domaine Active Directory et les comptes Lync Server au sein de votre organisation) entrent leur numéro de téléphone (ou poste) et un code confidentiel (PIN) pour se connecter aux conférences en tant qu’utilisateur authentifié.</span><span class="sxs-lookup"><span data-stu-id="95a20-177">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

