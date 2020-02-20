---
title: 'Lync Server 2013 : table d’enregistrement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d56f08db69fab4dfbf8da0c09d5d693bccf76bf2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="850a8-102">Table Registration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="850a8-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="850a8-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="850a8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="850a8-104">Chaque enregistrement représente un événement relatif à l’inscription d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="850a8-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="850a8-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="850a8-105">Column</span></span></th>
<th><span data-ttu-id="850a8-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="850a8-106">Data Type</span></span></th>
<th><span data-ttu-id="850a8-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="850a8-107">Key/Index</span></span></th>
<th><span data-ttu-id="850a8-108">Détails</span><span class="sxs-lookup"><span data-stu-id="850a8-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="850a8-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="850a8-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="850a8-111">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="850a8-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="850a8-112">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="850a8-112">Time of session request.</span></span> <span data-ttu-id="850a8-113">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="850a8-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="850a8-114">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="850a8-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="850a8-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-116">int</span><span class="sxs-lookup"><span data-stu-id="850a8-116">int</span></span></p></td>
<td><p><span data-ttu-id="850a8-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="850a8-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="850a8-118">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="850a8-118">ID number to identify the session.</span></span> <span data-ttu-id="850a8-119">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="850a8-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="850a8-120">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="850a8-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="850a8-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-122">int</span><span class="sxs-lookup"><span data-stu-id="850a8-122">int</span></span></p></td>
<td><p><span data-ttu-id="850a8-123">Etranger</span><span class="sxs-lookup"><span data-stu-id="850a8-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="850a8-124">ID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="850a8-124">The user ID.</span></span> <span data-ttu-id="850a8-125">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="850a8-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="850a8-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-127">unique</span><span class="sxs-lookup"><span data-stu-id="850a8-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="850a8-p104">GUID pour identifier un système d’extrémité d’inscription. Généralement, l’événement d’inscription d’un même ordinateur et d’un même utilisateur aura le même ID de système d’extrémité. Des ordinateurs différents ont un ID de système d’extrémité différent.</span><span class="sxs-lookup"><span data-stu-id="850a8-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="850a8-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-132">Unique</span><span class="sxs-lookup"><span data-stu-id="850a8-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="850a8-133">ID utilisé pour différencier des inscriptions qui impliquent le même utilisateur et le même point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="850a8-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="850a8-134">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="850a8-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="850a8-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-136">int</span><span class="sxs-lookup"><span data-stu-id="850a8-136">int</span></span></p></td>
<td><p><span data-ttu-id="850a8-137">Etranger</span><span class="sxs-lookup"><span data-stu-id="850a8-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="850a8-138">Version du client de l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="850a8-138">Client version of current user.</span></span> <span data-ttu-id="850a8-139">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="850a8-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="850a8-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-141">int</span><span class="sxs-lookup"><span data-stu-id="850a8-141">int</span></span></p></td>
<td><p><span data-ttu-id="850a8-142">Etranger</span><span class="sxs-lookup"><span data-stu-id="850a8-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="850a8-143">ID du serveur d’inscriptions utilisé pour l’inscription.</span><span class="sxs-lookup"><span data-stu-id="850a8-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="850a8-144">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="850a8-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="850a8-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-146">int</span><span class="sxs-lookup"><span data-stu-id="850a8-146">int</span></span></p></td>
<td><p><span data-ttu-id="850a8-147">Etranger</span><span class="sxs-lookup"><span data-stu-id="850a8-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="850a8-148">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="850a8-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="850a8-149">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="850a8-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="850a8-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-151">int</span><span class="sxs-lookup"><span data-stu-id="850a8-151">int</span></span></p></td>
<td><p><span data-ttu-id="850a8-152">Etranger</span><span class="sxs-lookup"><span data-stu-id="850a8-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="850a8-153">Serveur Edge sur lequel l’inscription a lieu.</span><span class="sxs-lookup"><span data-stu-id="850a8-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="850a8-154">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">table table edgeservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="850a8-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="850a8-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-156">Légèrement</span><span class="sxs-lookup"><span data-stu-id="850a8-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="850a8-157">Si l’utilisateur est connecté en interne ou non.</span><span class="sxs-lookup"><span data-stu-id="850a8-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="850a8-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-159">légèrement</span><span class="sxs-lookup"><span data-stu-id="850a8-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="850a8-160">Si UserService est disponible ou non.</span><span class="sxs-lookup"><span data-stu-id="850a8-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="850a8-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-162">légèrement</span><span class="sxs-lookup"><span data-stu-id="850a8-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="850a8-163">Si l’inscription est effectuée sur le serveur d’inscriptions principal ou non.</span><span class="sxs-lookup"><span data-stu-id="850a8-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="850a8-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-165">légèrement</span><span class="sxs-lookup"><span data-stu-id="850a8-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="850a8-166">Indique si l’utilisateur est inscrit ou non avec un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="850a8-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="850a8-167">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="850a8-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="850a8-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-169">DateHeure</span><span class="sxs-lookup"><span data-stu-id="850a8-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="850a8-170">Heure d’inscription.</span><span class="sxs-lookup"><span data-stu-id="850a8-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="850a8-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-172">DateHeure</span><span class="sxs-lookup"><span data-stu-id="850a8-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="850a8-173">Heure de désinscription.</span><span class="sxs-lookup"><span data-stu-id="850a8-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="850a8-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-175">int</span><span class="sxs-lookup"><span data-stu-id="850a8-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="850a8-176">Code de réponse de la demande d’inscription.</span><span class="sxs-lookup"><span data-stu-id="850a8-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="850a8-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-178">int</span><span class="sxs-lookup"><span data-stu-id="850a8-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="850a8-p109">ID de diagnostic de la demande d’inscription. Indique les informations du type de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="850a8-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="850a8-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-182">int</span><span class="sxs-lookup"><span data-stu-id="850a8-182">int</span></span></p></td>
<td><p><span data-ttu-id="850a8-183">Etranger</span><span class="sxs-lookup"><span data-stu-id="850a8-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="850a8-184">L’appareil à partir duquel est émise la demande d’inscription.</span><span class="sxs-lookup"><span data-stu-id="850a8-184">The device that the register request is coming from.</span></span> <span data-ttu-id="850a8-185">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-devices-table.md">tableau périphériques dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="850a8-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="850a8-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-187">entier très petit</span><span class="sxs-lookup"><span data-stu-id="850a8-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="850a8-188">Etranger</span><span class="sxs-lookup"><span data-stu-id="850a8-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="850a8-189">La raison de l’annulation de l’inscription, par exemple « initié par l’utilisateur », « expiration de l’inscription », « échec du client », et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="850a8-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="850a8-190">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-deregistertype-table.md">table DeRegisterType dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="850a8-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="850a8-191"><strong>IP</strong></span><span class="sxs-lookup"><span data-stu-id="850a8-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="850a8-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="850a8-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="850a8-193">Adresse IP du point de terminaison avec laquelle l’utilisateur s’est inscrit.</span><span class="sxs-lookup"><span data-stu-id="850a8-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="850a8-194">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="850a8-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="850a8-195">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="850a8-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

