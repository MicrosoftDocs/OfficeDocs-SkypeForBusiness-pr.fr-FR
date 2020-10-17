---
title: 'Lync Server 2013 : configuration de voix entreprise'
description: 'Lync Server 2013 : configuration de voix entreprise.'
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
ms.openlocfilehash: 49a231b92bf7b04aa3466927a79258f0cbad4e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548430"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="00531-103">Configuration de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00531-103">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00531-104">_**Dernière modification de la rubrique :** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="00531-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="00531-105">Pour déployer voix entreprise, vous devez configurer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="00531-105">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="00531-106">Créer une jonction</span><span class="sxs-lookup"><span data-stu-id="00531-106">Create a Trunk</span></span>

  - <span data-ttu-id="00531-107">Définir une stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="00531-107">Define a Voice Policy</span></span>

  - <span data-ttu-id="00531-108">Définition d’un itinéraire des communications vocales</span><span class="sxs-lookup"><span data-stu-id="00531-108">Define a Voice Route</span></span>

  - <span data-ttu-id="00531-109">Activer les utilisateurs pour voix entreprise</span><span class="sxs-lookup"><span data-stu-id="00531-109">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="00531-110">Créer une jonction</span><span class="sxs-lookup"><span data-stu-id="00531-110">Create a Trunk</span></span>

<span data-ttu-id="00531-111">Vous devez définir des jonctions dans votre déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="00531-111">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="00531-112">Pour le routage des Location-Based, vous devez créer une configuration de jonction par jonction.</span><span class="sxs-lookup"><span data-stu-id="00531-112">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="00531-113">À l’aide du générateur de topologie Lync Server, définissez vos jonctions et utilisez la commande Lync Server Windows PowerShell, New-applet cstrunkconfiguration ou le panneau de configuration Lync Server pour définir les configurations de jonction correspondantes.</span><span class="sxs-lookup"><span data-stu-id="00531-113">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="00531-114">Pour plus d’informations sur l’activation du routage des Location-Based sur les configurations de jonctions, consultez la section relative à l’activation du routage des Location-Based sur les jonctions dans la rubrique, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="00531-114">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="00531-115">Pour cet exemple, le tableau suivant illustre les jonctions utilisées dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="00531-115">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="00531-116">Pour plus d’informations, reportez-vous à la rubrique [define Additional jonctions in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="00531-116">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="00531-117">Nom de la jonction</span><span class="sxs-lookup"><span data-stu-id="00531-117">Trunk name</span></span></th>
<th><span data-ttu-id="00531-118">Type du système</span><span class="sxs-lookup"><span data-stu-id="00531-118">System type</span></span></th>
<th><span data-ttu-id="00531-119">Nom</span><span class="sxs-lookup"><span data-stu-id="00531-119">Name</span></span></th>
<th><span data-ttu-id="00531-120">Emplacement</span><span class="sxs-lookup"><span data-stu-id="00531-120">Location</span></span></th>
<th><span data-ttu-id="00531-121">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="00531-121">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00531-122">Jonction 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="00531-122">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="00531-123">Passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="00531-123">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="00531-124">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="00531-124">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="00531-125">Delhi</span><span class="sxs-lookup"><span data-stu-id="00531-125">Delhi</span></span></p></td>
<td><p><span data-ttu-id="00531-126">MS1</span><span class="sxs-lookup"><span data-stu-id="00531-126">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00531-127">Jonction 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="00531-127">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="00531-128">Passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="00531-128">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="00531-129">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="00531-129">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="00531-130">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="00531-130">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="00531-131">MS1</span><span class="sxs-lookup"><span data-stu-id="00531-131">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00531-132">Jonction 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="00531-132">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="00531-133">PBX</span><span class="sxs-lookup"><span data-stu-id="00531-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="00531-134">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="00531-134">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="00531-135">Delhi</span><span class="sxs-lookup"><span data-stu-id="00531-135">Delhi</span></span></p></td>
<td><p><span data-ttu-id="00531-136">MS1</span><span class="sxs-lookup"><span data-stu-id="00531-136">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00531-137">Jonction 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="00531-137">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="00531-138">PBX</span><span class="sxs-lookup"><span data-stu-id="00531-138">PBX</span></span></p></td>
<td><p><span data-ttu-id="00531-139">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="00531-139">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="00531-140">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="00531-140">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="00531-141">MS1</span><span class="sxs-lookup"><span data-stu-id="00531-141">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="00531-142">Définit les stratégies de voix</span><span class="sxs-lookup"><span data-stu-id="00531-142">Defines Voice Policies</span></span>

<span data-ttu-id="00531-143">Vous devez définir des stratégies de voix pour votre déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="00531-143">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="00531-144">Définir une stratégie de voix pour appliquer des restrictions de routage Location-Based à un sous-ensemble d’utilisateurs si seul un sous-ensemble de ces derniers est requis pour utiliser le routage de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="00531-144">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="00531-145">Pour cet exemple, le tableau suivant illustre les stratégies de voix utilisées dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="00531-145">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="00531-146">Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="00531-146">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="00531-147">Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités d’appel et les privilèges dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="00531-147">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="00531-148">Stratégie de voix 1</span><span class="sxs-lookup"><span data-stu-id="00531-148">Voice policy 1</span></span></th>
<th><span data-ttu-id="00531-149">Stratégie de voix 2</span><span class="sxs-lookup"><span data-stu-id="00531-149">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00531-150">ID de stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="00531-150">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="00531-151">Stratégie de voix de Delhi</span><span class="sxs-lookup"><span data-stu-id="00531-151">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="00531-152">Stratégie de voix Hyderabad</span><span class="sxs-lookup"><span data-stu-id="00531-152">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00531-153">Utilisations RTC</span><span class="sxs-lookup"><span data-stu-id="00531-153">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="00531-154">Utilisation de Delhi, utilisation de PBX del, utilisation de PBX HYD</span><span class="sxs-lookup"><span data-stu-id="00531-154">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="00531-155">Utilisation de Hyderabad, utilisation de la HYD PBX, utilisation de PBX del</span><span class="sxs-lookup"><span data-stu-id="00531-155">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00531-156">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="00531-156">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="00531-157">False</span><span class="sxs-lookup"><span data-stu-id="00531-157">False</span></span></p></td>
<td><p><span data-ttu-id="00531-158">False</span><span class="sxs-lookup"><span data-stu-id="00531-158">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="00531-159">Définir les itinéraires des communications vocales</span><span class="sxs-lookup"><span data-stu-id="00531-159">Define Voice Routes</span></span>

<span data-ttu-id="00531-160">Vous devez définir des itinéraires de communications vocales pour votre déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="00531-160">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="00531-161">Pour cet exemple, le tableau suivant illustre les itinéraires des communications vocales utilisés dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="00531-161">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="00531-162">Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="00531-162">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="00531-163">Pour plus d’informations, reportez-vous à la rubrique [Configuration des itinéraires des communications vocales pour les appels sortants dans Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="00531-163">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="00531-164">Itinéraire des communications vocales 1</span><span class="sxs-lookup"><span data-stu-id="00531-164">Voice route 1</span></span></th>
<th><span data-ttu-id="00531-165">Itinéraire des communications vocales 2</span><span class="sxs-lookup"><span data-stu-id="00531-165">Voice route 2</span></span></th>
<th><span data-ttu-id="00531-166">Itinéraire des communications vocales 3</span><span class="sxs-lookup"><span data-stu-id="00531-166">Voice route 3</span></span></th>
<th><span data-ttu-id="00531-167">Itinéraire des communications vocales 4</span><span class="sxs-lookup"><span data-stu-id="00531-167">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00531-168">Nom</span><span class="sxs-lookup"><span data-stu-id="00531-168">Name</span></span></p></td>
<td><p><span data-ttu-id="00531-169">Itinéraire de l’Delhi</span><span class="sxs-lookup"><span data-stu-id="00531-169">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="00531-170">Itinéraire Hyderabad</span><span class="sxs-lookup"><span data-stu-id="00531-170">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="00531-171">Itinéraire de la del PBX</span><span class="sxs-lookup"><span data-stu-id="00531-171">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="00531-172">Itinéraire HYD PBX</span><span class="sxs-lookup"><span data-stu-id="00531-172">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00531-173">Utilisations RTC</span><span class="sxs-lookup"><span data-stu-id="00531-173">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="00531-174">Utilisation de Delhi</span><span class="sxs-lookup"><span data-stu-id="00531-174">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="00531-175">Utilisation de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="00531-175">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="00531-176">Utilisation de PBX del</span><span class="sxs-lookup"><span data-stu-id="00531-176">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="00531-177">Utilisation de la HYD PBX</span><span class="sxs-lookup"><span data-stu-id="00531-177">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00531-178">Urbain</span><span class="sxs-lookup"><span data-stu-id="00531-178">Trunk</span></span></p></td>
<td><p><span data-ttu-id="00531-179">Jonction 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="00531-179">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="00531-180">Jonction 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="00531-180">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="00531-181">Jonction 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="00531-181">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="00531-182">Jonction 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="00531-182">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="00531-183">Activer les utilisateurs pour voix entreprise</span><span class="sxs-lookup"><span data-stu-id="00531-183">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="00531-184">Activez les utilisateurs pour voix entreprise et affectez-leur une stratégie de voix que vous avez définie précédemment.</span><span class="sxs-lookup"><span data-stu-id="00531-184">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="00531-185">Pour cet exemple, le tableau suivant illustre l’affectation utilisée dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="00531-185">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="00531-186">Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="00531-186">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="00531-187">Pour plus d’informations, consultez la rubrique [activation des utilisateurs pour voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="00531-187">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="00531-188">Utilisateurs situés à l’adresse de Delhi</span><span class="sxs-lookup"><span data-stu-id="00531-188">Users located in Delhi</span></span></th>
<th><span data-ttu-id="00531-189">Utilisateurs situés dans Hyderabad</span><span class="sxs-lookup"><span data-stu-id="00531-189">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00531-190">Stratégie de voix associée</span><span class="sxs-lookup"><span data-stu-id="00531-190">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="00531-191">Stratégie de voix de Delhi</span><span class="sxs-lookup"><span data-stu-id="00531-191">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="00531-192">Stratégie de voix Hyderabad</span><span class="sxs-lookup"><span data-stu-id="00531-192">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00531-193">Exemples d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="00531-193">Sample users</span></span></p></td>
<td><p><span data-ttu-id="00531-194">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="00531-194">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="00531-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="00531-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="00531-196">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00531-196">See Also</span></span>


[<span data-ttu-id="00531-197">Configuration du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00531-197">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

