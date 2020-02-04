---
title: Configuration technique requise pour les conférences dans Lync Server 2013
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
ms.openlocfilehash: 3a275836b940cfe2c56b184d238bc12c432132e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="67b6c-102">Configuration technique requise pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67b6c-102">Technical requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67b6c-103">_**Dernière modification de la rubrique :** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="67b6c-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="67b6c-104">Pour Lync Server 2013, les conférences rendez-vous, les conférences rendez-vous, les conférences par messagerie instantanée et les fonctionnalités de conférences Web toujours exécutées sur des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="67b6c-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="67b6c-105">Cette section détaille les configurations matérielles et logicielles requises pour ces serveurs, ainsi que la colocalisation prise en charge.</span><span class="sxs-lookup"><span data-stu-id="67b6c-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="67b6c-106">La fonction de conférence rendez-vous est une fonctionnalité qui inclut de nombreux composants.</span><span class="sxs-lookup"><span data-stu-id="67b6c-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="67b6c-107">Certains composants sont spécifiques aux conférences rendez-vous, et certains sont des composants voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="67b6c-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="67b6c-108">Cette section décrit les exigences relatives aux composants spécifiques aux conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="67b6c-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="67b6c-109">Pour plus d’informations sur la configuration requise pour les passerelles de réseau téléphonique commuté (RTC) et de réseau téléphonique commuté (RTC), consultez la section [composant serveur de médiation dans Lync server 2013](lync-server-2013-mediation-server-component.md) et les [composants et topologies du serveur de médiation dans Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="67b6c-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="67b6c-110">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="67b6c-110">Hardware Requirements</span></span>

<span data-ttu-id="67b6c-111">Dans la mesure où les conférences Web et les conférences à l’aide de la fonctionnalité de conférence A/V sont colocalisées avec le serveur frontal, la configuration matérielle requise pour le serveur est la même que celle des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="67b6c-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="67b6c-112">Pour plus d’informations sur la configuration matérielle requise, voir [plates-formes matérielles pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="67b6c-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="67b6c-113">Les composants suivants requis pour les conférences rendez-vous présentent également les mêmes exigences matérielles que les serveurs frontaux :</span><span class="sxs-lookup"><span data-stu-id="67b6c-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="67b6c-114">service d’application</span><span class="sxs-lookup"><span data-stu-id="67b6c-114">Application service</span></span>

  - <span data-ttu-id="67b6c-115">application Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="67b6c-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="67b6c-116">application d’annonce de conférence</span><span class="sxs-lookup"><span data-stu-id="67b6c-116">Conferencing Announcement application</span></span>

<span data-ttu-id="67b6c-117">La configuration matérielle requise pour le serveur frontal est la même que celle de nombreux autres rôles de serveur dans Lync Server 2013, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="67b6c-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="67b6c-118">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="67b6c-118">Software Requirements</span></span>

<span data-ttu-id="67b6c-119">Dans la mesure où les conférences Web et les conférences A/V sont colocalisées avec le serveur frontal, la configuration logicielle requise pour le serveur est la même que celle des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="67b6c-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="67b6c-120">Pour plus d’informations sur la configuration logicielle requise, voir [prise en charge du système d’exploitation serveur et outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="67b6c-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="67b6c-121">Pour les conférences Web, Lync Server 2013 nécessite également Office Web Apps et Office Web Apps Server (auparavant appelé Companion Server) pour gérer les présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="67b6c-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="67b6c-122">Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="67b6c-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="67b6c-123">Pour les conférences rendez-vous, le service d’application, les applications de surveillance des conférences et les annonces de conférences présentent les mêmes exigences relatives au système d’exploitation que les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="67b6c-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="67b6c-124">Pour plus d’informations sur la configuration logicielle requise, voir [prise en charge du système d’exploitation serveur et outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="67b6c-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="67b6c-125">L’application assistance de conférence et d’annonce de conférences nécessite que le runtime du format Windows Media soit installé sur les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="67b6c-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="67b6c-126">Windows Media Format Runtime est requis pour lire des fichiers Windows Media audio (WMA) qui sont utilisés pour la musique en attente, des noms enregistrés et des invites.</span><span class="sxs-lookup"><span data-stu-id="67b6c-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="67b6c-127">À l’exception de Windows Server 2012 et de Windows Server 2012 R2, le runtime du format Windows Media Runtime est automatiquement installé dans le cadre de l’expérience de bureau Windows lorsque vous exécutez le programme d’installation, mais vous devrez peut-être redémarrer l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="67b6c-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="67b6c-128">Par conséquent, nous vous conseillons de procéder à l’installation dans le cadre de l’expérience de bureau Windows, qui inclut le runtime du format Windows Media, avant d’exécuter le programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="67b6c-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="67b6c-129">Windows Server 2012 et Windows Server 2012 R2 nécessitent Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="67b6c-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="67b6c-130">Exigences relatives aux ports pour les conférences rendez-vous</span><span class="sxs-lookup"><span data-stu-id="67b6c-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="67b6c-131">Le tableau suivant décrit les ports utilisés par les conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="67b6c-131">The following table describes the ports that are used by dial-in conferencing.</span></span> <span data-ttu-id="67b6c-132">Si vous utilisez un équilibreur de charge, assurez-vous que l’équilibrage de charge est configuré pour les ports utilisés par toutes les applications qui s’exécutent dans le pool.</span><span class="sxs-lookup"><span data-stu-id="67b6c-132">If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="67b6c-133">Ces ports sont les paramètres par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="67b6c-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="67b6c-134">Pour plus d’informations sur cette applet de connexion, consultez la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="67b6c-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67b6c-135">Toutes les instances de la même application dans un pool utilisent le même port d’écoute SIP.</span><span class="sxs-lookup"><span data-stu-id="67b6c-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="67b6c-136">Ports utilisés par les conférences rendez-vous</span><span class="sxs-lookup"><span data-stu-id="67b6c-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67b6c-137">Numéro de port</span><span class="sxs-lookup"><span data-stu-id="67b6c-137">Port number</span></span></th>
<th><span data-ttu-id="67b6c-138">Description</span><span class="sxs-lookup"><span data-stu-id="67b6c-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67b6c-139">5072</span><span class="sxs-lookup"><span data-stu-id="67b6c-139">5072</span></span></p></td>
<td><p><span data-ttu-id="67b6c-140">Utilisé par l’application de surveillance des conférences pour les demandes d’écoute SIP</span><span class="sxs-lookup"><span data-stu-id="67b6c-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67b6c-141">5073</span><span class="sxs-lookup"><span data-stu-id="67b6c-141">5073</span></span></p></td>
<td><p><span data-ttu-id="67b6c-142">Utilisé par l’application d’annonce de conférence pour les demandes d’écoute SIP</span><span class="sxs-lookup"><span data-stu-id="67b6c-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="67b6c-143">Clients pris en charge pour les conférences rendez-vous</span><span class="sxs-lookup"><span data-stu-id="67b6c-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="67b6c-144">Vous pouvez utiliser le client suivant pour planifier des conférences locales prenant en charge l’accès rendez-vous :</span><span class="sxs-lookup"><span data-stu-id="67b6c-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="67b6c-145">Complément réunion en ligne pour Lync 2013 (installé automatiquement lors de l’installation de Lync 2013 ou participant)</span><span class="sxs-lookup"><span data-stu-id="67b6c-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="67b6c-146">Configuration requise pour la page des paramètres de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="67b6c-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="67b6c-147">La page des paramètres de conférence rendez-vous prend en charge les combinaisons de systèmes d’exploitation et de navigateurs Web décrits dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="67b6c-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67b6c-148">les versions 32 bits et 64 bits des systèmes d’exploitation sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="67b6c-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="67b6c-149">Systèmes d’exploitation et navigateurs web pris en charge</span><span class="sxs-lookup"><span data-stu-id="67b6c-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67b6c-150">Système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="67b6c-150">Operating system</span></span></th>
<th><span data-ttu-id="67b6c-151">Navigateur web</span><span class="sxs-lookup"><span data-stu-id="67b6c-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67b6c-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="67b6c-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="67b6c-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="67b6c-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="67b6c-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="67b6c-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="67b6c-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="67b6c-155">Firefox</span></span></p></td>
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
<td><p><span data-ttu-id="67b6c-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="67b6c-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="67b6c-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="67b6c-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="67b6c-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="67b6c-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="67b6c-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="67b6c-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67b6c-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="67b6c-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="67b6c-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="67b6c-161">Firefox</span></span></p>
<p><span data-ttu-id="67b6c-162">Safari</span><span class="sxs-lookup"><span data-stu-id="67b6c-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="67b6c-163">Exigences relatives aux fichiers audio pour les conférences rendez-vous</span><span class="sxs-lookup"><span data-stu-id="67b6c-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="67b6c-164">Lync Server 2013 ne prend pas en charge la personnalisation des invites vocales et de la musique pour les conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="67b6c-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="67b6c-165">Toutefois, si vous avez un besoin professionnel qui nécessite que vous deviez modifier les fichiers audio par défaut, voir l’article 961177 de la base de connaissances Microsoft, [Comment personnaliser les invites vocales ou les fichiers audio pour les conférences rendez-vous dans Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span><span class="sxs-lookup"><span data-stu-id="67b6c-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="67b6c-166">Vous pouvez également utiliser l’utilitaire de gestion des [invites de voix personnalisées du surveillant des conférences Microsoft Lync Server](http://go.microsoft.com/fwlink/p/?linkid=396880) , qui permet aux administrateurs de remplacer les invites vocales par défaut utilisées lorsqu’un appelant de téléphone rejoint une réunion Lync à l’aide d’invites personnalisées afin de fournir une autre utilisation de la réunion.</span><span class="sxs-lookup"><span data-stu-id="67b6c-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](http://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="67b6c-167">Les invites vocales personnalisées peuvent être installées sur un serveur exécutant Lync Server 2010 ou Lync Server 2013, Enterprise ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="67b6c-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="67b6c-168">L’application du service de conférence et l’application d’annonce présentent les exigences suivantes concernant la musique en attente, le nom enregistré et les fichiers d’invite audio :</span><span class="sxs-lookup"><span data-stu-id="67b6c-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="67b6c-169">Format de fichier audio Windows Media (.wma)</span><span class="sxs-lookup"><span data-stu-id="67b6c-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="67b6c-170">Mono 16 bits</span><span class="sxs-lookup"><span data-stu-id="67b6c-170">16-bit mono</span></span>

  - <span data-ttu-id="67b6c-171">Vitesse de transmission constante (CBR) 2 passes 48 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="67b6c-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="67b6c-172">Niveau de voix à -24 Db</span><span class="sxs-lookup"><span data-stu-id="67b6c-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="67b6c-173">Exigences utilisateur pour la Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="67b6c-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="67b6c-174">Les utilisateurs de la conférence rendez-vous doivent avoir un numéro de téléphone ou de poste unique rattaché à leur compte.</span><span class="sxs-lookup"><span data-stu-id="67b6c-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="67b6c-175">Cette exigence n’empêche pas l’authentification dans le cadre de la conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="67b6c-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="67b6c-176">Utilisateurs d’entreprise (c’est-à-dire, les utilisateurs disposant d’informations d’identification de services de domaine Active Directory et de compte Lync au sein de votre organisation) entrent leur numéro de téléphone (ou leur extension) et un code confidentiel (PIN) pour se connecter aux conférences en tant que utilisateur authentifié.</span><span class="sxs-lookup"><span data-stu-id="67b6c-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

