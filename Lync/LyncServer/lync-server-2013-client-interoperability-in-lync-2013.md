---
title: 'Lync Server 2013 : interopérabilité des clients dans Lync 2013'
description: 'Lync Server 2013 : interopérabilité des clients dans Lync 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea6e90d9479f03dd6d946787e70a2b3cc078699
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549610"
---
# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="d4123-103">Interopérabilité des clients dans Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d4123-103">Client interoperability in Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4123-104">_**Dernière modification de la rubrique :** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="d4123-104">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="d4123-105">Cette rubrique décrit la capacité des clients Microsoft Lync Server 2013 à coexister et interagir avec les clients à partir de versions antérieures de Lync Server et Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="d4123-105">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="d4123-106">Compatibilité serveur-client</span><span class="sxs-lookup"><span data-stu-id="d4123-106">Server and Client Compatibility</span></span>

<span data-ttu-id="d4123-107">Le tableau suivant indique les combinaisons prises en charge des versions de client et de serveur.</span><span class="sxs-lookup"><span data-stu-id="d4123-107">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="d4123-108">Ce tableau indique également si la connexion est prise en charge lorsque le client tente de se connecter au serveur indiqué.</span><span class="sxs-lookup"><span data-stu-id="d4123-108">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="d4123-109">Lync Server 2013 prend en charge la version précédente du client.</span><span class="sxs-lookup"><span data-stu-id="d4123-109">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="d4123-110">Par ailleurs, à la différence des versions précédentes, Lync Server 2010 prend en charge les nouveaux clients Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d4123-110">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="d4123-111">Cela permet aux organisations qui effectuent une mise à niveau à partir de Lync Server 2010 de déployer de nouveaux clients indépendamment des mises à niveau Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4123-111">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4123-112">Client</span><span class="sxs-lookup"><span data-stu-id="d4123-112">Client</span></span></th>
<th><span data-ttu-id="d4123-113">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4123-113">Lync Server 2013</span></span></th>
<th><span data-ttu-id="d4123-114">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d4123-114">Lync Server 2010</span></span></th>
<th><span data-ttu-id="d4123-115">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d4123-115">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4123-116">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d4123-116">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="d4123-117">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-117">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-118">Supported5</span><span class="sxs-lookup"><span data-stu-id="d4123-118">Supported5</span></span></p></td>
<td><p><span data-ttu-id="d4123-119">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-119">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-120">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="d4123-120">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="d4123-121">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-122">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-122">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-123">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-123">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-124">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="d4123-124">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="d4123-125">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-125">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-126">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-126">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-127">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-127">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-128">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d4123-128">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d4123-129">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-130">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-130">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-131">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-131">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-132">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="d4123-132">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="d4123-133">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-134">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-134">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-135">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-135">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-136">conversation de groupe Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d4123-136">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="d4123-137">Supported1</span><span class="sxs-lookup"><span data-stu-id="d4123-137">Supported1</span></span></p></td>
<td><p><span data-ttu-id="d4123-138">Supported2</span><span class="sxs-lookup"><span data-stu-id="d4123-138">Supported2</span></span></p></td>
<td><p><span data-ttu-id="d4123-139">Non applicable</span><span class="sxs-lookup"><span data-stu-id="d4123-139">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-140">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="d4123-140">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="d4123-141">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-141">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-142">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-142">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-143">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-143">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-144">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="d4123-144">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="d4123-145">Non Supported3</span><span class="sxs-lookup"><span data-stu-id="d4123-145">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="d4123-146">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-146">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-147">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-147">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-148">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d4123-148">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="d4123-149">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="d4123-149">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="d4123-150">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-150">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-151">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-151">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-152">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="d4123-152">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="d4123-153">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-153">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-154">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-154">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-155">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-155">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-156">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="d4123-156">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="d4123-157">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-157">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-158">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-158">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-159">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-159">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-160">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="d4123-160">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="d4123-161">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-161">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-162">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-162">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-163">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-163">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-164">Application Lync du Windows Store</span><span class="sxs-lookup"><span data-stu-id="d4123-164">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="d4123-165">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-166">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-166">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-167">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-167">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d4123-168">1Pour plus d’informations, consultez la rubrique [migration from Lync server 2010, Group chat ou Office Communications Server 2007 R2 Group chat to Lync server 2013, persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="d4123-168">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="d4123-169">2In Microsoft Lync Server 2010, la fonctionnalité de conversation de groupe était disponible avec le serveur de conversation de groupe, une application tierce approuvée pour Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d4123-169">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="d4123-170">Les clients Lync 2013 ne sont pas compatibles avec Lync Server 2010, Group chat.</span><span class="sxs-lookup"><span data-stu-id="d4123-170">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="d4123-171">3Lync Web App 2013 offre désormais une expérience complète en matière de réunion, y compris l’audio et la vidéo de l’ordinateur, et est considérée comme le remplacement de Lync 2010 Attendee.</span><span class="sxs-lookup"><span data-stu-id="d4123-171">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="d4123-172">Lync 2010 Attendee se connectera à Lync Server 2013 uniquement lorsque vous utilisez un navigateur non pris en charge (Internet Explorer 6 ou Internet Explorer 7) et Windows XP.</span><span class="sxs-lookup"><span data-stu-id="d4123-172">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="d4123-173">les fonctionnalités de présence et de messagerie instantanée 4The dans Office Communicator 2007 R2 sont compatibles avec Lync Server 2013, mais pas les fonctionnalités de conférence.</span><span class="sxs-lookup"><span data-stu-id="d4123-173">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="d4123-174">Lors de la migration à partir d’Office Communications Server 2007 R2, Office Communicator 2007 R2 convient à l’interopérabilité de la présence et de la messagerie instantanée, mais les utilisateurs doivent utiliser Lync Web App 2013 pour rejoindre des réunions Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4123-174">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="d4123-175">5 pour des limitations, voir « prise en charge des fonctionnalités de conférence pour les clients Lync 2013 dans les réunions Lync Server 2010 » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="d4123-175">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="d4123-176">Interopérabilité entre les clients</span><span class="sxs-lookup"><span data-stu-id="d4123-176">Interoperability among Clients</span></span>

<span data-ttu-id="d4123-177">Avec la version Lync Server 2013, différentes versions de client peuvent interagir de façon transparente dans les scénarios d’égal à égal et de conférence.</span><span class="sxs-lookup"><span data-stu-id="d4123-177">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="d4123-178">Cette section décrit la disponibilité des fonctionnalités lorsque les utilisateurs interagissent avec d’autres utilisateurs exécutant des versions différentes de client et de serveur.</span><span class="sxs-lookup"><span data-stu-id="d4123-178">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="d4123-179">Prise en charge de la fonctionnalité d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="d4123-179">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="d4123-p106">Les fonctionnalités d’égal-à-égal sont prises en charge pour les utilisateurs qui sont hébergés sur différentes versions du serveur et qui utilisent différentes versions du client. L’expérience de l’utilisateur final et les fonctionnalités disponibles reflètent les capacités du client de l’utilisateur et de la version du serveur auquel l’utilisateur est connecté. En d’autres termes :</span><span class="sxs-lookup"><span data-stu-id="d4123-p106">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions. The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to. In other words:</span></span>

  - <span data-ttu-id="d4123-183">Si un utilisateur est connecté à Lync Server 2013 avec un ancien client, l’expérience de l’utilisateur sera la même que pour.</span><span class="sxs-lookup"><span data-stu-id="d4123-183">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="d4123-184">Aucune des nouvelles fonctionnalités introduites dans Lync Server 2013 ne sera disponible tant que le client de l’utilisateur n’aura pas été mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="d4123-184">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="d4123-185">Les exemples incluent la Galerie vidéo, la vidéo HD, le partage PowerPoint mis à jour et l’option de désactivation de l’audio et de la vidéo de tous les participants lors de l’entrée de la réunion.</span><span class="sxs-lookup"><span data-stu-id="d4123-185">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="d4123-186">Les nouvelles fonctionnalités sont présentées dans la [nouvelle fonctionnalité de conférence de Lync server 2013](lync-server-2013-new-conferencing-features.md) et les nouveautés [pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="d4123-186">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="d4123-187">Si un utilisateur est connecté à Lync Server 2010 avec un client Lync 2013, toutes les nouvelles fonctionnalités non prises en charge par Lync Server 2010 seront indisponibles jusqu’à ce que l’utilisateur soit déplacé vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4123-187">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="d4123-188">Le tableau suivant compare la disponibilité des fonctionnalités dans les sessions P2P où le client est connecté à Lync Server 2013 ou Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d4123-188">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4123-189">Lync Web App et Lync 2010 Attendee sont des clients de réunion uniquement et ne sont pas inclus dans ce tableau.</span><span class="sxs-lookup"><span data-stu-id="d4123-189">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4123-190">Client</span><span class="sxs-lookup"><span data-stu-id="d4123-190">Client</span></span></th>
<th><span data-ttu-id="d4123-191">Messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="d4123-191">Instant Messaging</span></span></th>
<th><span data-ttu-id="d4123-192">Présence</span><span class="sxs-lookup"><span data-stu-id="d4123-192">Presence</span></span></th>
<th><span data-ttu-id="d4123-193">Voix</span><span class="sxs-lookup"><span data-stu-id="d4123-193">Voice</span></span></th>
<th><span data-ttu-id="d4123-194">Vidéo</span><span class="sxs-lookup"><span data-stu-id="d4123-194">Video</span></span></th>
<th><span data-ttu-id="d4123-195">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="d4123-195">Application Sharing</span></span></th>
<th><span data-ttu-id="d4123-196">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="d4123-196">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4123-197">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d4123-197">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="d4123-198">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-199">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-200">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-201">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-202">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-203">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-203">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-204">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="d4123-204">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="d4123-205">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-206">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-207">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-208">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-209">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-210">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-210">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-211">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d4123-211">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d4123-212">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-213">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-214">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-215">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-216">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-217">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-217">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-218">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="d4123-218">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="d4123-219">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-220">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-221">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-221">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-222">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="d4123-222">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="d4123-223">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-224">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-224">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-225">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="d4123-225">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="d4123-226">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-227">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-228">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-228">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-229">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d4123-229">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="d4123-230">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-231">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-232">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-233">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-234">Yes1</span><span class="sxs-lookup"><span data-stu-id="d4123-234">Yes1</span></span></p></td>
<td><p><span data-ttu-id="d4123-235">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-235">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-236">Messagerie instantanée publique (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="d4123-236">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="d4123-237">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-237">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-238">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-238">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-239">Messagerie instantanée publique (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="d4123-239">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="d4123-240">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-241">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-242">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-243">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-243">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="d4123-244">À partir du 2012 1er septembre, la licence d’abonnement aux utilisateurs de la connectivité PIC de Microsoft Lync public (PIC) n’est plus disponible pour l’achat de contrats de nouvelle ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="d4123-244">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="d4123-245">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="d4123-245">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d4123-246">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="d4123-246">Messenger until the service shutdown date.</span></span> <span data-ttu-id="d4123-247">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="d4123-247">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="d4123-248">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="d4123-248">has been announced.</span></span> <span data-ttu-id="d4123-249">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>..</span><span class="sxs-lookup"><span data-stu-id="d4123-249">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="d4123-250">La fonction USL PIC est une licence d’abonnement mensuel, mensuelle, nécessaire pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="d4123-250">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="d4123-251">Messenger.</span><span class="sxs-lookup"><span data-stu-id="d4123-251">Messenger.</span></span> <span data-ttu-id="d4123-252">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent qui n’est pas renouvelé.</span><span class="sxs-lookup"><span data-stu-id="d4123-252">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="d4123-253">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="d4123-253">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d4123-254">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="d4123-254">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="d4123-255">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes via la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="d4123-255">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="d4123-256">1 dans Office Communicator 2007 R2, seul le partage de bureau (et non le partage de programmes) est disponible.</span><span class="sxs-lookup"><span data-stu-id="d4123-256">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4123-257">Le partage de bureau entre Office Communicator 2007 R2 et Skype entreprise 2015 ne peut pas être initié à partir du client plus récent lorsque l’interface utilisateur du client Skype entreprise 2015 est appliquée.</span><span class="sxs-lookup"><span data-stu-id="d4123-257">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="d4123-258">Prise en charge des fonctionnalités de conférence pour les clients Lync 2013 dans les réunions Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d4123-258">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="d4123-259">Lorsque les utilisateurs rejoignent des réunions Lync Server 2010 avec un client Lync 2013, ils ont accès aux fonctionnalités clientes de Lync 2013 avec les exceptions suivantes :</span><span class="sxs-lookup"><span data-stu-id="d4123-259">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="d4123-260">Dans les options de gestion des **participants** , qui sont accessibles en pointant sur l’icône contacts dans la fenêtre de la réunion, l’option **aucun message instantané** ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="d4123-260">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="d4123-261">La vue de la galerie ne fonctionne pas dans les vidéoconférences.</span><span class="sxs-lookup"><span data-stu-id="d4123-261">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="d4123-262">L’utilisateur voit uniquement le haut-parleur actif au lieu de tous les haut-parleurs.</span><span class="sxs-lookup"><span data-stu-id="d4123-262">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="d4123-263">Dans la liste des options de **sélection de disposition** , le **mode Galerie** n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d4123-263">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="d4123-264">La liste des participants s’affiche par défaut dans les vidéoconférences.</span><span class="sxs-lookup"><span data-stu-id="d4123-264">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="d4123-265">Lorsque vous cliquez avec le bouton droit de la souris sur un utilisateur dans la liste des participants, les options **verrouiller les vidéos en vedette** de la vidéo et **accrocher aux participants de la Galerie** ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="d4123-265">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="d4123-266">Prise en charge des fonctionnalités de conférence dans les réunions Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4123-266">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="d4123-267">Lync Server 2013 fournit de nouvelles fonctionnalités de conférence qui deviennent accessibles aux utilisateurs une fois que leurs comptes sont déplacés vers Lync Server 2013 et qu’ils se connectent avec le client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d4123-267">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="d4123-268">Les exemples incluent la Galerie vidéo, la vidéo HD, le partage PowerPoint et l’option de mise en sourdine de tous les participants audio et vidéo lors de l’entrée de la réunion.</span><span class="sxs-lookup"><span data-stu-id="d4123-268">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="d4123-269">Les nouvelles fonctionnalités sont présentées dans la [nouvelle fonctionnalité de conférence de Lync server 2013](lync-server-2013-new-conferencing-features.md) et les nouveautés [pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="d4123-269">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="d4123-270">Dans les réunions Lync Server 2013, certaines fonctionnalités de conférence sont prises en charge pour les utilisateurs qui sont hébergés sur des versions différentes du serveur et qui utilisent des clients et des versions de client différents.</span><span class="sxs-lookup"><span data-stu-id="d4123-270">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="d4123-271">Lorsque les clients rejoignent une réunion Lync Server 2013, les utilisateurs ont accès aux fonctionnalités et aux fonctionnalités présentées dans ce tableau.</span><span class="sxs-lookup"><span data-stu-id="d4123-271">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4123-272">Client</span><span class="sxs-lookup"><span data-stu-id="d4123-272">Client</span></span></th>
<th><span data-ttu-id="d4123-273">Messagerie instantanée d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="d4123-273">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="d4123-274">Voix</span><span class="sxs-lookup"><span data-stu-id="d4123-274">Voice</span></span></th>
<th><span data-ttu-id="d4123-275">Vidéo</span><span class="sxs-lookup"><span data-stu-id="d4123-275">Video</span></span></th>
<th><span data-ttu-id="d4123-276">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="d4123-276">Application Sharing</span></span></th>
<th><span data-ttu-id="d4123-277">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d4123-277">PowerPoint</span></span></th>
<th><span data-ttu-id="d4123-278">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="d4123-278">File Transfer</span></span></th>
<th><span data-ttu-id="d4123-279">Tableau blanc collaboratif</span><span class="sxs-lookup"><span data-stu-id="d4123-279">Whiteboard</span></span></th>
<th><span data-ttu-id="d4123-280">Interrogation</span><span class="sxs-lookup"><span data-stu-id="d4123-280">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4123-281">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d4123-281">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="d4123-282">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-283">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-284">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-285">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-286">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-287">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-288">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-288">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-289">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-289">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-290">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="d4123-290">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="d4123-291">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-292">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-293">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-294">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-295">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-296">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-297">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-297">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-298">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-298">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-299">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="d4123-299">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="d4123-300">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-301">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-302">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-303">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-304">Oui2</span><span class="sxs-lookup"><span data-stu-id="d4123-304">Yes2</span></span></p></td>
<td><p><span data-ttu-id="d4123-305">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-306">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-306">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-307">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-307">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-308">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d4123-308">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d4123-309">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-310">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-311">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-312">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-313">Yes3</span><span class="sxs-lookup"><span data-stu-id="d4123-313">Yes3</span></span></p></td>
<td><p><span data-ttu-id="d4123-314">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-315">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-315">Yes</span></span></p></td>
<td><p><span data-ttu-id="d4123-316">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-316">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-317">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="d4123-317">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="d4123-318">Oui</span><span class="sxs-lookup"><span data-stu-id="d4123-318">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d4123-319">1 dans Office Communicator 2007 R2, seul le partage de bureau (et non le partage de programmes) est disponible.</span><span class="sxs-lookup"><span data-stu-id="d4123-319">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="d4123-320">2 Lync Server 2013 utilise un mécanisme mis à jour pour télécharger des fichiers PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d4123-320">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="d4123-321">Les utilisateurs de Lync Web App qui rejoignent une réunion initialement planifiée sur Lync Server 2010 peuvent afficher et naviguer dans les présentations PowerPoint, mais ne peuvent pas télécharger de fichiers PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d4123-321">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="d4123-322">3 Si la réunion a été planifiée sur Lync Server 2013 et que les diapositives PowerPoint ont été téléchargées par un client Lync 2013, les utilisateurs de Lync 2010 disposent d’un accès en lecture seule aux diapositives.</span><span class="sxs-lookup"><span data-stu-id="d4123-322">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="d4123-323">À l’inverse, si les diapositives PowerPoint ont été téléchargées par un utilisateur de Lync 2010, les utilisateurs de Lync Server 2013 peuvent afficher et diapositives et, si Office Web Apps Server est configuré, accéder à de nouvelles fonctionnalités telles que l’affichage de plus haute résolution, les animations, les transitions de diapositives et la vidéo incorporée.</span><span class="sxs-lookup"><span data-stu-id="d4123-323">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="d4123-324">Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="d4123-324">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="d4123-325">les fonctionnalités de présence et de messagerie instantanée 4The dans Office Communicator 2007 R2 sont compatibles avec Lync Server 2013, mais pas les fonctionnalités de conférence.</span><span class="sxs-lookup"><span data-stu-id="d4123-325">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="d4123-326">Lors de la migration à partir d’Office Communications Server 2007 R2, Office Communicator 2007 R2 convient à l’interopérabilité de la présence et de la messagerie instantanée, mais les utilisateurs doivent utiliser Lync Web App 2013 pour rejoindre des réunions Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4123-326">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="d4123-327">Prise en charge des compléments de planification</span><span class="sxs-lookup"><span data-stu-id="d4123-327">Scheduling Add-in Support</span></span>

<span data-ttu-id="d4123-328">La prise en charge par le serveur des différents compléments de planification reflète la compatibilité de la version du serveur et du client.</span><span class="sxs-lookup"><span data-stu-id="d4123-328">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="d4123-329">En règle générale, les compléments de planification suivants sont pris en charge sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4123-329">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="d4123-330">Toutefois, les versions précédentes des compléments ne fournissent pas de nouvelles fonctionnalités de complément Lync 2013, telles que l’option de désactivation de l’audio et de la vidéo de tous les participants lors de l’entrée de la réunion.</span><span class="sxs-lookup"><span data-stu-id="d4123-330">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="d4123-331">**Complément de réunion en ligne pour Lync 2013**     Fournit les mêmes fonctionnalités que le complément de réunion en ligne pour Lync 2010, avec l’ajout de contrôles muet des participants, qui permettent aux organisateurs de la réunion de planifier des conférences avec audio et vidéo en sourdine par défaut.</span><span class="sxs-lookup"><span data-stu-id="d4123-331">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="d4123-332">Les administrateurs peuvent également personnaliser les invitations aux réunions de l’organisation en ajoutant un logo personnalisé, une URL de support, une URL de clause d’exclusion de responsabilité ou un texte de pied de page personnalisé.</span><span class="sxs-lookup"><span data-stu-id="d4123-332">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="d4123-333">**Complément de réunion en ligne pour Lync 2010**     Fournit la planification des réunions Lync et supprime la possibilité de planifier des conférences Office Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="d4123-333">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="d4123-334">Complément Office Communicator **2007 R2 Conferencing**     Fournit la planification des conférences Office Live Meeting et des conférences Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d4123-334">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="d4123-335">Les conférences Live Meeting ne peuvent pas être planifiées sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4123-335">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4123-336">Client de planification</span><span class="sxs-lookup"><span data-stu-id="d4123-336">Scheduling Client</span></span></th>
<th><span data-ttu-id="d4123-337">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4123-337">Lync Server 2013</span></span></th>
<th><span data-ttu-id="d4123-338">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d4123-338">Lync Server 2010</span></span></th>
<th><span data-ttu-id="d4123-339">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d4123-339">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4123-340">Complément de réunion en ligne pour Lync 2013 (peut être utilisé avec Office 2013, Outlook 2010 et Outlook 2007)</span><span class="sxs-lookup"><span data-stu-id="d4123-340">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="d4123-341">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-341">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-342">Pris en charge (nouvelles fonctionnalités de complément non disponible)</span><span class="sxs-lookup"><span data-stu-id="d4123-342">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="d4123-343">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-343">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-344">Planificateur Web Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d4123-344">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="d4123-345">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-345">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-346">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-346">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-347">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-347">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4123-348">complément de réunion en ligne pour Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d4123-348">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d4123-349">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-350">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-350">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-351">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-351">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4123-352">Complément de conférence pour Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d4123-352">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="d4123-353">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-353">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-354">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-354">Supported</span></span></p></td>
<td><p><span data-ttu-id="d4123-355">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="d4123-355">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="d4123-356">Prise en charge de la participation aux réunions</span><span class="sxs-lookup"><span data-stu-id="d4123-356">Support for Joining Meetings</span></span>

<span data-ttu-id="d4123-357">Tous les clients pris en charge par Lync Server 2013 sont autorisés à rejoindre des réunions Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d4123-357">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="d4123-358">Dans la mesure où Lync Web App est un composant Web du serveur, dans les cas où Lync Web App est utilisé pour rejoindre une réunion Lync Server 2013, la version plus récente de Lync Web App est toujours utilisée.</span><span class="sxs-lookup"><span data-stu-id="d4123-358">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="d4123-359">Les clients Lync 2013 peuvent rejoindre des réunions hébergées sur Lync 2010 et Office Communications Server 2007 R2 avec des fonctionnalités réduites.</span><span class="sxs-lookup"><span data-stu-id="d4123-359">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="d4123-360">Les fonctionnalités de réunion sont limitées par la version du serveur sur lequel la réunion est hébergée.</span><span class="sxs-lookup"><span data-stu-id="d4123-360">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4123-361">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d4123-361">See Also</span></span>


[<span data-ttu-id="d4123-362">Configuration requise pour les applications Lync Windows Store pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4123-362">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="d4123-363">Nouvelles fonctionnalités de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4123-363">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="d4123-364">Nouveautés pour les clients dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4123-364">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

