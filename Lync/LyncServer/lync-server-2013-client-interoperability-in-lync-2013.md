---
title: 'Lync Server 2013 : Interopérabilité des clients dans Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8ccc6239ffa0216e36839a7e58b510d8c8c3240
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="3152a-102">Interopérabilité des clients dans Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3152a-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3152a-103">_**Dernière modification de la rubrique:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="3152a-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="3152a-104">Cette rubrique explique la possibilité pour les clients Microsoft Lync Server 2013 de cohabiter et d’interagir avec les clients provenant de versions antérieures de Lync Server et d’Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="3152a-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="3152a-105">Compatibilité entre le serveur et le client</span><span class="sxs-lookup"><span data-stu-id="3152a-105">Server and Client Compatibility</span></span>

<span data-ttu-id="3152a-106">Le tableau ci-dessous indique les combinaisons prises en charge par les versions de client et serveur.</span><span class="sxs-lookup"><span data-stu-id="3152a-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="3152a-107">Ce tableau indique si la connexion est prise en charge lorsque le client tente de se connecter au serveur indiqué.</span><span class="sxs-lookup"><span data-stu-id="3152a-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="3152a-108">Lync Server 2013 prend en charge la version précédente du client.</span><span class="sxs-lookup"><span data-stu-id="3152a-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="3152a-109">Par ailleurs, contrairement aux versions précédentes, Lync Server 2010 prend en charge les nouveaux clients Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3152a-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="3152a-110">Cela permet aux organisations qui effectuent la mise à niveau de Lync Server 2010 de déployer de nouveaux clients indépendamment des mises à niveau de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3152a-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3152a-111">Client</span><span class="sxs-lookup"><span data-stu-id="3152a-111">Client</span></span></th>
<th><span data-ttu-id="3152a-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3152a-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="3152a-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3152a-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="3152a-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3152a-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3152a-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3152a-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="3152a-116">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="3152a-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="3152a-118">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-119">Lync 2013 de base</span><span class="sxs-lookup"><span data-stu-id="3152a-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="3152a-120">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="3152a-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-121">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-122">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="3152a-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="3152a-124">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-125">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-126">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3152a-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="3152a-128">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="3152a-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-129">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-130">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-131">Lync 2010 attendant</span><span class="sxs-lookup"><span data-stu-id="3152a-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="3152a-132">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="3152a-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-133">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-134">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-135">Conversation de groupe Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3152a-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="3152a-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="3152a-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="3152a-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="3152a-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="3152a-138">Non applicable</span><span class="sxs-lookup"><span data-stu-id="3152a-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="3152a-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="3152a-140">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-141">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-142">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-143">Lync 2010 participant</span><span class="sxs-lookup"><span data-stu-id="3152a-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="3152a-144">Non Supported3</span><span class="sxs-lookup"><span data-stu-id="3152a-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="3152a-145">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-146">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3152a-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="3152a-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="3152a-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="3152a-149">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="3152a-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-150">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-151">Microsoft Office Communications Server 2007 R2 attendant</span><span class="sxs-lookup"><span data-stu-id="3152a-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="3152a-152">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-153">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="3152a-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-154">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="3152a-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="3152a-156">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-157">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="3152a-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-158">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="3152a-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="3152a-160">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-161">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="3152a-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-162">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-163">application Lync du Windows Store</span><span class="sxs-lookup"><span data-stu-id="3152a-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="3152a-164">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="3152a-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-165">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-166">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3152a-167">1Pour plus d’informations, reportez-vous à la section [migration de Lync server 2010, discussion de groupe ou Office Communications Server 2007 R2 en conversation de groupe vers Lync server 2013, serveur de conversation persistant](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="3152a-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="3152a-168">2In Microsoft Lync Server 2010, les fonctionnalités de discussion de groupe étaient disponibles avec le serveur de discussion de groupe, une application de confiance tierce pour Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3152a-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="3152a-169">Les clients 2013 Lync ne sont pas compatibles avec Lync Server 2010 et la discussion de groupe.</span><span class="sxs-lookup"><span data-stu-id="3152a-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="3152a-170">3Lync Web App 2013 offre désormais une prise en compte complète de la réunion, y compris le son et la vidéo de l’ordinateur, et est considérée comme un élément de remplacement de Lync 2010 Attendee.</span><span class="sxs-lookup"><span data-stu-id="3152a-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="3152a-171">Lync 2010 Attendee se connecte à Lync Server 2013 uniquement si vous utilisez un navigateur non pris en charge (Internet Explorer 6 ou Internet Explorer 7) et Windows XP.</span><span class="sxs-lookup"><span data-stu-id="3152a-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="3152a-172">4Synthèse les fonctionnalités de présence et de messagerie instantanée d’Office Communicator 2007 R2 sont compatibles avec Lync Server 2013, mais pas les fonctionnalités de conférence.</span><span class="sxs-lookup"><span data-stu-id="3152a-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="3152a-173">Lors de la migration à partir d’Office Communications Server 2007 R2, Office Communicator 2007 R2 est approprié pour l’interopérabilité de la présence et de la messagerie instantanée, mais les utilisateurs doivent utiliser Lync Web App 2013 pour participer aux réunions Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3152a-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="3152a-174">5 pour plus d’limitations, voir la section «assistance technique pour les clients Lync 2013 dans les réunions Lync Server 2010» plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="3152a-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="3152a-175">Interopérabilité entre les clients</span><span class="sxs-lookup"><span data-stu-id="3152a-175">Interoperability among Clients</span></span>

<span data-ttu-id="3152a-176">Avec la version 2013 du serveur Lync, les différentes versions du client peuvent interagir en toute transparence dans les scénarios d’égal à égal et de conférence.</span><span class="sxs-lookup"><span data-stu-id="3152a-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="3152a-177">Cette section traite de la disponibilité des fonctionnalités lorsque les utilisateurs interagissent avec d’autres utilisateurs qui utilisent des versions différentes de clients et de serveurs.</span><span class="sxs-lookup"><span data-stu-id="3152a-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="3152a-178">Prise en charge des fonctionnalités d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="3152a-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="3152a-179">Les fonctionnalités d’égal à égal sont prises en charge pour les utilisateurs hébergés sur des versions différentes du serveur et utilisant des versions de clients différentes.</span><span class="sxs-lookup"><span data-stu-id="3152a-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="3152a-180">L’utilisation des fonctionnalités finales et des fonctionnalités disponibles est cohérente avec les fonctionnalités du client de l’utilisateur et celle du serveur auquel il est connecté.</span><span class="sxs-lookup"><span data-stu-id="3152a-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="3152a-181">En d’autres termes :</span><span class="sxs-lookup"><span data-stu-id="3152a-181">In other words:</span></span>

  - <span data-ttu-id="3152a-182">Si un utilisateur est connecté à Lync Server 2013 avec un client plus ancien, il aura la même connaissance qu’il est utilisé.</span><span class="sxs-lookup"><span data-stu-id="3152a-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="3152a-183">Aucune des nouvelles fonctionnalités introduites dans Lync Server 2013 ne sera disponible tant que le client de l’utilisateur n’a pas été mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="3152a-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="3152a-184">Il s’agit notamment de l’affichage Galerie de vidéos, de la vidéo HD, de la mise à jour du partage PowerPoint et de l’option désactiver l’audio et la vidéo des participants lors de la réunion.</span><span class="sxs-lookup"><span data-stu-id="3152a-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="3152a-185">Les nouvelles fonctionnalités sont présentées dans les [nouvelles fonctionnalités de conférence de Lync server 2013](lync-server-2013-new-conferencing-features.md) et [les nouveautés pour les clients de Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="3152a-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="3152a-186">Si un utilisateur est connecté à Lync Server 2010 avec un client 2013 Lync, toutes les nouvelles fonctionnalités non prises en charge par Lync Server 2010 ne seront pas disponibles tant que l’utilisateur n’aura pas été déplacé vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3152a-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="3152a-187">Le tableau suivant compare la disponibilité des fonctionnalités dans les sessions d’égal à égal où le client est connecté à Lync Server 2013 ou Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3152a-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3152a-188">Lync Web App et Lync 2010 ne sont pas des clients de réunion et ne sont pas inclus dans ce tableau.</span><span class="sxs-lookup"><span data-stu-id="3152a-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="3152a-189">Client</span><span class="sxs-lookup"><span data-stu-id="3152a-189">Client</span></span></th>
<th><span data-ttu-id="3152a-190">Messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="3152a-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="3152a-191">Présence</span><span class="sxs-lookup"><span data-stu-id="3152a-191">Presence</span></span></th>
<th><span data-ttu-id="3152a-192">Audio</span><span class="sxs-lookup"><span data-stu-id="3152a-192">Voice</span></span></th>
<th><span data-ttu-id="3152a-193">Vidéo</span><span class="sxs-lookup"><span data-stu-id="3152a-193">Video</span></span></th>
<th><span data-ttu-id="3152a-194">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="3152a-194">Application Sharing</span></span></th>
<th><span data-ttu-id="3152a-195">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="3152a-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3152a-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3152a-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="3152a-197">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-198">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-199">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-200">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-201">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-202">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-203">Lync 2013 de base</span><span class="sxs-lookup"><span data-stu-id="3152a-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="3152a-204">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-205">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-206">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-207">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-208">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-209">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3152a-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="3152a-211">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-212">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-213">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-214">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-215">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-216">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-217">Lync 2010 attendant</span><span class="sxs-lookup"><span data-stu-id="3152a-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="3152a-218">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-219">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-220">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-221">Lync 2010 mobile</span><span class="sxs-lookup"><span data-stu-id="3152a-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="3152a-222">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-223">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="3152a-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="3152a-225">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-226">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-227">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3152a-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="3152a-229">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-230">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-231">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-232">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-233">Oui1</span><span class="sxs-lookup"><span data-stu-id="3152a-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="3152a-234">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-235">Messagerie instantanée publique (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="3152a-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="3152a-236">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-237">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-238">Messagerie instantanée publique (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="3152a-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="3152a-239">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-240">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-241">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-242">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="3152a-243">À compter du 1er septembre 2012, la licence de l’abonnement à l’utilisateur de la connectivité PIC (Public IM Connectivity) de Microsoft Lync n’est plus disponible pour l’achat de contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="3152a-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="3152a-244">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo!</span><span class="sxs-lookup"><span data-stu-id="3152a-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="3152a-245">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="3152a-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="3152a-246">Date de fin de vie du 2014 juin pour AOL et Yahoo!</span><span class="sxs-lookup"><span data-stu-id="3152a-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="3152a-247">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="3152a-247">has been announced.</span></span> <span data-ttu-id="3152a-248">Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3152a-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="3152a-249">La fonction USL (PIC) est une licence d’abonnement par utilisateur et par mois requise pour la Fédération de Lync Server ou d’Office Communications Server avec Yahoo!</span><span class="sxs-lookup"><span data-stu-id="3152a-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="3152a-250">Messenger.</span><span class="sxs-lookup"><span data-stu-id="3152a-250">Messenger.</span></span> <span data-ttu-id="3152a-251">La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, qui n’est pas renouvelé.</span><span class="sxs-lookup"><span data-stu-id="3152a-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="3152a-252">Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="3152a-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="3152a-253">La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync.</span><span class="sxs-lookup"><span data-stu-id="3152a-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="3152a-254">Skype Federation sera ajouté à cette liste, ce qui permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes par messagerie instantanée et vocale.</span><span class="sxs-lookup"><span data-stu-id="3152a-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="3152a-255">1 dans Office Communicator 2007 R2, seul le partage de bureau (et non le partage de programme) est disponible.</span><span class="sxs-lookup"><span data-stu-id="3152a-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3152a-256">Le partage de bureau entre Office Communicator 2007 R2 et Skype entreprise 2015 ne peut pas être démarré à partir du client plus récent lorsque l’interface utilisateur du client Skype entreprise 2015 est appliquée.</span><span class="sxs-lookup"><span data-stu-id="3152a-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="3152a-257">Prise en charge des fonctionnalités de conférence pour les clients Lync 2013 dans les réunions Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3152a-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="3152a-258">Lorsque des utilisateurs rejoignent des réunions Lync Server 2010 avec un client Lync 2013, ils ont accès aux fonctionnalités du client Lync 2013 avec les exceptions suivantes:</span><span class="sxs-lookup"><span data-stu-id="3152a-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="3152a-259">Dans les options de gestion des **participants** accessibles en pointant sur l’icône personnes dans la fenêtre de la réunion, l’option **aucun message instantané** ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="3152a-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="3152a-260">Le mode Galerie ne fonctionne pas dans les conférences vidéo.</span><span class="sxs-lookup"><span data-stu-id="3152a-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="3152a-261">L’utilisateur ne voit que le haut-parleur actif au lieu de ses haut-parleurs.</span><span class="sxs-lookup"><span data-stu-id="3152a-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="3152a-262">Dans la liste des options **choisir une disposition, la** **vue Galerie** n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="3152a-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="3152a-263">La liste des participants s’affiche par défaut dans les conférences vidéo.</span><span class="sxs-lookup"><span data-stu-id="3152a-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="3152a-264">Lorsque vous cliquez avec le bouton droit sur un utilisateur dans la liste des participants, les options **verrouiller les actualités vidéo** et **épingler aux participants à la Galerie** ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="3152a-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="3152a-265">Prise en charge des fonctionnalités de conférence dans les réunions Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3152a-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="3152a-266">Lync Server 2013 fournit de nouvelles fonctionnalités de conférence qui deviennent accessibles aux utilisateurs une fois leur compte déplacé vers Lync Server 2013 et se connectant avec le client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3152a-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="3152a-267">Il s’agit notamment de l’affichage Galerie de vidéos, de la vidéo HD, du partage PowerPoint et de l’option désactiver l’audio et la vidéo des participants à la réunion.</span><span class="sxs-lookup"><span data-stu-id="3152a-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="3152a-268">Les nouvelles fonctionnalités sont présentées dans les [nouvelles fonctionnalités de conférence de Lync server 2013](lync-server-2013-new-conferencing-features.md) et [les nouveautés pour les clients de Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="3152a-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="3152a-269">Dans les réunions Lync Server 2013, certaines fonctions de conférence sont prises en charge pour les utilisateurs qui sont hébergés sur des versions différentes du serveur et qui utilisent des clients et des versions de clients différents.</span><span class="sxs-lookup"><span data-stu-id="3152a-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="3152a-270">Lorsque des clients rejoignent une réunion Lync Server 2013, les utilisateurs ont accès aux fonctionnalités et fonctionnalités présentées dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="3152a-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="3152a-271">Client</span><span class="sxs-lookup"><span data-stu-id="3152a-271">Client</span></span></th>
<th><span data-ttu-id="3152a-272">Messagerie instantanée d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="3152a-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="3152a-273">Audio</span><span class="sxs-lookup"><span data-stu-id="3152a-273">Voice</span></span></th>
<th><span data-ttu-id="3152a-274">Vidéo</span><span class="sxs-lookup"><span data-stu-id="3152a-274">Video</span></span></th>
<th><span data-ttu-id="3152a-275">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="3152a-275">Application Sharing</span></span></th>
<th><span data-ttu-id="3152a-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="3152a-276">PowerPoint</span></span></th>
<th><span data-ttu-id="3152a-277">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="3152a-277">File Transfer</span></span></th>
<th><span data-ttu-id="3152a-278">Tableau blanc</span><span class="sxs-lookup"><span data-stu-id="3152a-278">Whiteboard</span></span></th>
<th><span data-ttu-id="3152a-279">Interrogation</span><span class="sxs-lookup"><span data-stu-id="3152a-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3152a-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3152a-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="3152a-281">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-282">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-283">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-284">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-285">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-286">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-287">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-288">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-289">Lync 2013 de base</span><span class="sxs-lookup"><span data-stu-id="3152a-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="3152a-290">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-291">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-292">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-293">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-294">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-295">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-296">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-297">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="3152a-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="3152a-299">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-300">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-301">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-302">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-303">Oui2</span><span class="sxs-lookup"><span data-stu-id="3152a-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="3152a-304">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-305">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-306">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3152a-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="3152a-308">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-309">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-310">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-311">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-312">Oui3</span><span class="sxs-lookup"><span data-stu-id="3152a-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="3152a-313">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-314">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="3152a-315">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="3152a-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="3152a-317">Oui</span><span class="sxs-lookup"><span data-stu-id="3152a-317">Yes</span></span></p></td>
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


<span data-ttu-id="3152a-318">1 dans Office Communicator 2007 R2, seul le partage de bureau (et non le partage de programme) est disponible.</span><span class="sxs-lookup"><span data-stu-id="3152a-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="3152a-319">2 Lync Server 2013 utilise un mécanisme de mise à jour pour télécharger des fichiers PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="3152a-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="3152a-320">Les utilisateurs Lync Web App qui rejoignent une réunion planifiée à l’origine sur Lync Server 2010 peuvent afficher et parcourir les présentations PowerPoint, mais ne peuvent pas télécharger de fichiers PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="3152a-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="3152a-321">3 Si la réunion a été planifiée sur Lync Server 2013 et les diapositives PowerPoint téléchargées par un client 2013 Lync, les utilisateurs de Lync 2010 disposent d’un accès en affichage seul aux diapositives.</span><span class="sxs-lookup"><span data-stu-id="3152a-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="3152a-322">À l’inverse, si les diapositives PowerPoint ont été téléchargées par un utilisateur de Lync 2010, les utilisateurs de Lync Server 2013 pourront afficher et des diapositives et, si Office Web Apps Server est configuré, accéder aux nouvelles fonctionnalités telles que l’affichage d’une résolution supérieure, des animations, des transitions entre les diapositives et vidéo incorporée.</span><span class="sxs-lookup"><span data-stu-id="3152a-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="3152a-323">Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="3152a-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="3152a-324">4Synthèse les fonctionnalités de présence et de messagerie instantanée d’Office Communicator 2007 R2 sont compatibles avec Lync Server 2013, mais pas les fonctionnalités de conférence.</span><span class="sxs-lookup"><span data-stu-id="3152a-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="3152a-325">Lors de la migration à partir d’Office Communications Server 2007 R2, Office Communicator 2007 R2 est approprié pour l’interopérabilité de la présence et de la messagerie instantanée, mais les utilisateurs doivent utiliser Lync Web App 2013 pour participer aux réunions Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3152a-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="3152a-326">Planification de la prise en charge des compléments</span><span class="sxs-lookup"><span data-stu-id="3152a-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="3152a-327">La prise en charge du serveur pour les divers compléments de planification est cohérente avec la compatibilité entre les versions serveur et client.</span><span class="sxs-lookup"><span data-stu-id="3152a-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="3152a-328">En général, les compléments de planification suivants sont pris en charge sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3152a-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="3152a-329">Toutefois, les versions précédentes des compléments ne fournissent pas de nouvelles fonctionnalités de complément Lync 2013, comme l’option permettant de désactiver l’audio et la vidéo de tous les participants lors de la réunion.</span><span class="sxs-lookup"><span data-stu-id="3152a-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="3152a-330">**Le complément réunion en ligne pour Lync 2013**   fournit les mêmes fonctionnalités que le complément réunion en ligne pour Lync 2010, ainsi que l’ajout de contrôles de désactivation des participants, qui permettent aux organisateurs de la réunion de programmer des conférences qui ont désactivé le son et la vidéo des participants. définie.</span><span class="sxs-lookup"><span data-stu-id="3152a-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="3152a-331">Les administrateurs peuvent également personnaliser les invitations aux réunions de l’organisation en ajoutant un logo personnalisé, une URL d’assistance, une URL d’exclusion de responsabilité ou un texte de pied de page personnalisé.</span><span class="sxs-lookup"><span data-stu-id="3152a-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="3152a-332">**Le complément réunion en ligne pour Lync 2010**   fournit une planification pour les réunions Lync et supprime la possibilité de planifier des conférences Office Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="3152a-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="3152a-333">**Le complément de**   conférence Office Communicator 2007 R2 fournit une planification pour les conférences Office Live Meeting et les conférences Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3152a-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="3152a-334">Les conférences Live Meeting ne peuvent pas être planifiées sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3152a-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="3152a-335">Client de planification</span><span class="sxs-lookup"><span data-stu-id="3152a-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="3152a-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3152a-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="3152a-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3152a-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="3152a-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3152a-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3152a-339">Complément réunion en ligne pour Lync 2013 (peut être utilisé avec Office 2013, Outlook 2010 et Outlook 2007)</span><span class="sxs-lookup"><span data-stu-id="3152a-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="3152a-340">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-341">Pris en charge (les nouvelles fonctionnalités des compléments ne sont pas disponibles)</span><span class="sxs-lookup"><span data-stu-id="3152a-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="3152a-342">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-343">Lync 2013 Web Scheduler</span><span class="sxs-lookup"><span data-stu-id="3152a-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="3152a-344">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-345">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-346">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3152a-347">Complément réunion en ligne pour Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3152a-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="3152a-348">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="3152a-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-349">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-350">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3152a-351">Complément de conférence Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3152a-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="3152a-352">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-353">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="3152a-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="3152a-354">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="3152a-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="3152a-355">Prise en charge de la participation aux réunions</span><span class="sxs-lookup"><span data-stu-id="3152a-355">Support for Joining Meetings</span></span>

<span data-ttu-id="3152a-356">Tous les clients pris en charge par Lync Server 2013 sont autorisés à participer à des réunions Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3152a-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="3152a-357">Comme Lync Web App est un composant Web du serveur, dans les cas où Lync Web App est utilisé pour participer à une réunion Lync Server 2013, la version la plus récente de Lync Web App est toujours utilisée.</span><span class="sxs-lookup"><span data-stu-id="3152a-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="3152a-358">Les clients 2013 Lync peuvent rejoindre des réunions hébergées sur Lync 2010 et Office Communications Server 2007 R2 avec des fonctionnalités mises à l’échelle.</span><span class="sxs-lookup"><span data-stu-id="3152a-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="3152a-359">Les fonctionnalités en réunion sont limitées par la version du serveur sur lequel la réunion est hébergée.</span><span class="sxs-lookup"><span data-stu-id="3152a-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3152a-360">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3152a-360">See Also</span></span>


[<span data-ttu-id="3152a-361">Configuration requise pour l’application Lync du Windows Store pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3152a-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="3152a-362">Nouvelles fonctionnalités de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3152a-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="3152a-363">Nouveautés pour les clients dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3152a-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

