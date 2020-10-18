---
title: 'Lync Server 2013 : table d’enregistrement'
description: 'Lync Server 2013 : table d’inscription.'
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
ms.openlocfilehash: 806e1a4e944c9bc04ebdd167c41c80a57fde3f29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578523"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="f70dc-103">Table Registration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f70dc-103">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f70dc-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f70dc-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f70dc-105">Chaque enregistrement représente un événement relatif à l’inscription d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f70dc-105">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f70dc-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="f70dc-106">Column</span></span></th>
<th><span data-ttu-id="f70dc-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="f70dc-107">Data Type</span></span></th>
<th><span data-ttu-id="f70dc-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="f70dc-108">Key/Index</span></span></th>
<th><span data-ttu-id="f70dc-109">Détails</span><span class="sxs-lookup"><span data-stu-id="f70dc-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f70dc-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f70dc-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f70dc-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="f70dc-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f70dc-113">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="f70dc-113">Time of session request.</span></span> <span data-ttu-id="f70dc-114">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="f70dc-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f70dc-115">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f70dc-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70dc-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-117">int</span><span class="sxs-lookup"><span data-stu-id="f70dc-117">int</span></span></p></td>
<td><p><span data-ttu-id="f70dc-118">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="f70dc-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f70dc-119">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="f70dc-119">ID number to identify the session.</span></span> <span data-ttu-id="f70dc-120">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="f70dc-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f70dc-121">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f70dc-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f70dc-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-123">int</span><span class="sxs-lookup"><span data-stu-id="f70dc-123">int</span></span></p></td>
<td><p><span data-ttu-id="f70dc-124">Etranger</span><span class="sxs-lookup"><span data-stu-id="f70dc-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f70dc-125">ID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f70dc-125">The user ID.</span></span> <span data-ttu-id="f70dc-126">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f70dc-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70dc-127"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-127"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-128">unique</span><span class="sxs-lookup"><span data-stu-id="f70dc-128">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f70dc-p104">GUID pour identifier un système d’extrémité d’inscription. Généralement, l’événement d’inscription d’un même ordinateur et d’un même utilisateur aura le même ID de système d’extrémité. Des ordinateurs différents ont un ID de système d’extrémité différent.</span><span class="sxs-lookup"><span data-stu-id="f70dc-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f70dc-132"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-132"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-133">Unique</span><span class="sxs-lookup"><span data-stu-id="f70dc-133">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f70dc-134">ID utilisé pour différencier des inscriptions qui impliquent le même utilisateur et le même point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="f70dc-134">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="f70dc-135">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f70dc-135">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70dc-136"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-136"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-137">int</span><span class="sxs-lookup"><span data-stu-id="f70dc-137">int</span></span></p></td>
<td><p><span data-ttu-id="f70dc-138">Etranger</span><span class="sxs-lookup"><span data-stu-id="f70dc-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f70dc-139">Version du client de l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="f70dc-139">Client version of current user.</span></span> <span data-ttu-id="f70dc-140">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f70dc-140">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f70dc-141"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-141"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-142">int</span><span class="sxs-lookup"><span data-stu-id="f70dc-142">int</span></span></p></td>
<td><p><span data-ttu-id="f70dc-143">Etranger</span><span class="sxs-lookup"><span data-stu-id="f70dc-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f70dc-144">ID du serveur d’inscriptions utilisé pour l’inscription.</span><span class="sxs-lookup"><span data-stu-id="f70dc-144">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="f70dc-145">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f70dc-145">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70dc-146"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-146"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-147">int</span><span class="sxs-lookup"><span data-stu-id="f70dc-147">int</span></span></p></td>
<td><p><span data-ttu-id="f70dc-148">Etranger</span><span class="sxs-lookup"><span data-stu-id="f70dc-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f70dc-149">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="f70dc-149">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="f70dc-150">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f70dc-150">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f70dc-151"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-151"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-152">int</span><span class="sxs-lookup"><span data-stu-id="f70dc-152">int</span></span></p></td>
<td><p><span data-ttu-id="f70dc-153">Etranger</span><span class="sxs-lookup"><span data-stu-id="f70dc-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f70dc-154">Serveur Edge sur lequel l’inscription a lieu.</span><span class="sxs-lookup"><span data-stu-id="f70dc-154">Edge Server the registration is going through.</span></span> <span data-ttu-id="f70dc-155">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">table table edgeservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f70dc-155">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70dc-156"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-156"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-157">Légèrement</span><span class="sxs-lookup"><span data-stu-id="f70dc-157">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f70dc-158">Si l’utilisateur est connecté en interne ou non.</span><span class="sxs-lookup"><span data-stu-id="f70dc-158">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f70dc-159"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-159"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-160">légèrement</span><span class="sxs-lookup"><span data-stu-id="f70dc-160">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f70dc-161">Si UserService est disponible ou non.</span><span class="sxs-lookup"><span data-stu-id="f70dc-161">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70dc-162"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-162"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-163">légèrement</span><span class="sxs-lookup"><span data-stu-id="f70dc-163">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f70dc-164">Si l’inscription est effectuée sur le serveur d’inscriptions principal ou non.</span><span class="sxs-lookup"><span data-stu-id="f70dc-164">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f70dc-165"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-165"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-166">légèrement</span><span class="sxs-lookup"><span data-stu-id="f70dc-166">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f70dc-167">Indique si l’utilisateur est inscrit ou non avec un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="f70dc-167">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="f70dc-168">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f70dc-168">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70dc-169"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-169"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-170">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f70dc-170">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f70dc-171">Heure d’inscription.</span><span class="sxs-lookup"><span data-stu-id="f70dc-171">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f70dc-172"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-172"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-173">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f70dc-173">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f70dc-174">Heure de désinscription.</span><span class="sxs-lookup"><span data-stu-id="f70dc-174">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70dc-175"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-175"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-176">int</span><span class="sxs-lookup"><span data-stu-id="f70dc-176">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f70dc-177">Code de réponse de la demande d’inscription.</span><span class="sxs-lookup"><span data-stu-id="f70dc-177">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f70dc-178"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-178"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-179">int</span><span class="sxs-lookup"><span data-stu-id="f70dc-179">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f70dc-p109">ID de diagnostic de la demande d’inscription. Indique les informations du type de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="f70dc-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70dc-182"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-182"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-183">int</span><span class="sxs-lookup"><span data-stu-id="f70dc-183">int</span></span></p></td>
<td><p><span data-ttu-id="f70dc-184">Etranger</span><span class="sxs-lookup"><span data-stu-id="f70dc-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f70dc-185">L’appareil à partir duquel est émise la demande d’inscription.</span><span class="sxs-lookup"><span data-stu-id="f70dc-185">The device that the register request is coming from.</span></span> <span data-ttu-id="f70dc-186">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-devices-table.md">tableau périphériques dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f70dc-186">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f70dc-187"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-187"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-188">entier très petit</span><span class="sxs-lookup"><span data-stu-id="f70dc-188">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f70dc-189">Etranger</span><span class="sxs-lookup"><span data-stu-id="f70dc-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f70dc-190">La raison de l’annulation de l’inscription, par exemple « initié par l’utilisateur », « expiration de l’inscription », « échec du client », et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="f70dc-190">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="f70dc-191">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-deregistertype-table.md">table DeRegisterType dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f70dc-191">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70dc-192"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="f70dc-192"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="f70dc-193">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f70dc-193">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f70dc-194">Adresse IP du point de terminaison avec laquelle l’utilisateur s’est inscrit.</span><span class="sxs-lookup"><span data-stu-id="f70dc-194">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="f70dc-195">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="f70dc-195">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="f70dc-196">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f70dc-196">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

