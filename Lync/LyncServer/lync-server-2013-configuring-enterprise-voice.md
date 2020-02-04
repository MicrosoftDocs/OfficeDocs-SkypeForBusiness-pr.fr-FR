---
title: 'Lync Server 2013 : configuration d’Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d6bf9f79725f1f4812ac1e1c1c3c0e3217b939b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="84b51-102">Configuration d’Enterprise Voice dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b51-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84b51-103">_**Dernière modification de la rubrique :** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="84b51-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="84b51-104">Pour déployer Enterprise Voice, vous devez configurer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="84b51-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="84b51-105">Créer un Trunk</span><span class="sxs-lookup"><span data-stu-id="84b51-105">Create a Trunk</span></span>

  - <span data-ttu-id="84b51-106">Définir une politique vocale</span><span class="sxs-lookup"><span data-stu-id="84b51-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="84b51-107">Définir une gamme vocale</span><span class="sxs-lookup"><span data-stu-id="84b51-107">Define a Voice Route</span></span>

  - <span data-ttu-id="84b51-108">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="84b51-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="84b51-109">Créer un Trunk</span><span class="sxs-lookup"><span data-stu-id="84b51-109">Create a Trunk</span></span>

<span data-ttu-id="84b51-110">Vous devez définir des Trunks dans votre déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="84b51-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="84b51-111">Pour le routage basé sur l’emplacement, vous devez créer une configuration de Trunk par Trunk.</span><span class="sxs-lookup"><span data-stu-id="84b51-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="84b51-112">Utilisez le générateur de topologie de serveur Lync pour définir vos Trunks, puis utilisez la commande Windows PowerShell de Lync Server, le nouveau-CsTrunkConfiguration ou le panneau de configuration de Lync Server pour définir les configurations de Trunk correspondantes.</span><span class="sxs-lookup"><span data-stu-id="84b51-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="84b51-113">Pour plus d’informations sur l’activation du routage par emplacement sur des configurations de Trunk, reportez-vous à la section permettre le routage par emplacement vers des lignes de routage dans [Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="84b51-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="84b51-114">Pour cet exemple, le tableau ci-dessous illustre les Trunks utilisés dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="84b51-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="84b51-115">Pour plus d’informations, reportez-vous à la section [définir des lignes supplémentaires dans le générateur de topologie de Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="84b51-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="84b51-116">Nom du Trunk</span><span class="sxs-lookup"><span data-stu-id="84b51-116">Trunk name</span></span></th>
<th><span data-ttu-id="84b51-117">Type de système</span><span class="sxs-lookup"><span data-stu-id="84b51-117">System type</span></span></th>
<th><span data-ttu-id="84b51-118">Nom</span><span class="sxs-lookup"><span data-stu-id="84b51-118">Name</span></span></th>
<th><span data-ttu-id="84b51-119">Lieu</span><span class="sxs-lookup"><span data-stu-id="84b51-119">Location</span></span></th>
<th><span data-ttu-id="84b51-120">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="84b51-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84b51-121">Trunk 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="84b51-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="84b51-122">Passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="84b51-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="84b51-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="84b51-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="84b51-124">Delhi</span><span class="sxs-lookup"><span data-stu-id="84b51-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="84b51-125">MS1</span><span class="sxs-lookup"><span data-stu-id="84b51-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84b51-126">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="84b51-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="84b51-127">Passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="84b51-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="84b51-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="84b51-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="84b51-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b51-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="84b51-130">MS1</span><span class="sxs-lookup"><span data-stu-id="84b51-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84b51-131">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="84b51-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="84b51-132">Private</span><span class="sxs-lookup"><span data-stu-id="84b51-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="84b51-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="84b51-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="84b51-134">Delhi</span><span class="sxs-lookup"><span data-stu-id="84b51-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="84b51-135">MS1</span><span class="sxs-lookup"><span data-stu-id="84b51-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84b51-136">Trunk 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="84b51-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="84b51-137">Private</span><span class="sxs-lookup"><span data-stu-id="84b51-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="84b51-138">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="84b51-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="84b51-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b51-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="84b51-140">MS1</span><span class="sxs-lookup"><span data-stu-id="84b51-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="84b51-141">Définit les stratégies vocales</span><span class="sxs-lookup"><span data-stu-id="84b51-141">Defines Voice Policies</span></span>

<span data-ttu-id="84b51-142">Vous devez définir des politiques vocales pour le déploiement de votre voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="84b51-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="84b51-143">Définissez une stratégie vocale pour appliquer des restrictions de routage basées sur les emplacements à un sous-ensemble d’utilisateurs, si seul un sous-ensemble de ces derniers est requis pour utiliser le routage basé sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="84b51-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="84b51-144">Pour cet exemple, le tableau ci-dessous illustre les stratégies vocales utilisées dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="84b51-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="84b51-145">Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="84b51-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="84b51-146">Pour plus d’informations, reportez-vous [à configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités et privilèges d’utilisation dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="84b51-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="84b51-147">Politique vocale 1</span><span class="sxs-lookup"><span data-stu-id="84b51-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="84b51-148">Politique vocale 2</span><span class="sxs-lookup"><span data-stu-id="84b51-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84b51-149">ID de la stratégie vocale</span><span class="sxs-lookup"><span data-stu-id="84b51-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="84b51-150">Politique vocale de Delhi</span><span class="sxs-lookup"><span data-stu-id="84b51-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="84b51-151">Politique vocale Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b51-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84b51-152">Usages RTC</span><span class="sxs-lookup"><span data-stu-id="84b51-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="84b51-153">Utilisation de Delhi, utilisation de PBX del, utilisation du PBX HYD</span><span class="sxs-lookup"><span data-stu-id="84b51-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="84b51-154">Utilisation de Hyderabad, utilisation de PBX HYD, utilisation de PBX del</span><span class="sxs-lookup"><span data-stu-id="84b51-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84b51-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="84b51-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="84b51-156">False</span><span class="sxs-lookup"><span data-stu-id="84b51-156">False</span></span></p></td>
<td><p><span data-ttu-id="84b51-157">False</span><span class="sxs-lookup"><span data-stu-id="84b51-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="84b51-158">Définir des itinéraires vocaux</span><span class="sxs-lookup"><span data-stu-id="84b51-158">Define Voice Routes</span></span>

<span data-ttu-id="84b51-159">Vous devez définir des itinéraires vocaux pour votre déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="84b51-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="84b51-160">Pour cet exemple, le tableau ci-dessous illustre les itinéraires vocaux utilisés dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="84b51-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="84b51-161">Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="84b51-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="84b51-162">Pour plus d’informations, reportez-vous à la rubrique [Configuration des itinéraires vocaux pour les appels sortants dans Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="84b51-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th></th>
<th><span data-ttu-id="84b51-163">Route vocale 1</span><span class="sxs-lookup"><span data-stu-id="84b51-163">Voice route 1</span></span></th>
<th><span data-ttu-id="84b51-164">Route vocale 2</span><span class="sxs-lookup"><span data-stu-id="84b51-164">Voice route 2</span></span></th>
<th><span data-ttu-id="84b51-165">Route vocale 3</span><span class="sxs-lookup"><span data-stu-id="84b51-165">Voice route 3</span></span></th>
<th><span data-ttu-id="84b51-166">Route vocale 4</span><span class="sxs-lookup"><span data-stu-id="84b51-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84b51-167">Nom</span><span class="sxs-lookup"><span data-stu-id="84b51-167">Name</span></span></p></td>
<td><p><span data-ttu-id="84b51-168">Delhi route</span><span class="sxs-lookup"><span data-stu-id="84b51-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="84b51-169">Route Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b51-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="84b51-170">Route PBX del</span><span class="sxs-lookup"><span data-stu-id="84b51-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="84b51-171">Route HYD PBX</span><span class="sxs-lookup"><span data-stu-id="84b51-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84b51-172">Usages RTC</span><span class="sxs-lookup"><span data-stu-id="84b51-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="84b51-173">L’utilisation de Delhi</span><span class="sxs-lookup"><span data-stu-id="84b51-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="84b51-174">Utilisation de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b51-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="84b51-175">Utilisation de PBX del</span><span class="sxs-lookup"><span data-stu-id="84b51-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="84b51-176">Utilisation de HYD PBX</span><span class="sxs-lookup"><span data-stu-id="84b51-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84b51-177">Jonction</span><span class="sxs-lookup"><span data-stu-id="84b51-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="84b51-178">Trunk 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="84b51-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="84b51-179">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="84b51-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="84b51-180">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="84b51-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="84b51-181">Trunk 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="84b51-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="84b51-182">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="84b51-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="84b51-183">Activez les utilisateurs pour voix entreprise et attribuez-leur une stratégie vocale déjà définie.</span><span class="sxs-lookup"><span data-stu-id="84b51-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="84b51-184">Pour cet exemple, le tableau ci-dessous illustre l’affectation utilisée dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="84b51-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="84b51-185">Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="84b51-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="84b51-186">Pour plus d’informations, reportez-vous à [activer l’application voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="84b51-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="84b51-187">Utilisateurs situés à Delhi</span><span class="sxs-lookup"><span data-stu-id="84b51-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="84b51-188">Utilisateurs situés dans Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b51-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84b51-189">Politique vocale associée</span><span class="sxs-lookup"><span data-stu-id="84b51-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="84b51-190">Politique vocale de Delhi</span><span class="sxs-lookup"><span data-stu-id="84b51-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="84b51-191">Politique vocale Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b51-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84b51-192">Exemples d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="84b51-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="84b51-193">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="84b51-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="84b51-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="84b51-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84b51-195">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84b51-195">See Also</span></span>


[<span data-ttu-id="84b51-196">Configuration du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b51-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

