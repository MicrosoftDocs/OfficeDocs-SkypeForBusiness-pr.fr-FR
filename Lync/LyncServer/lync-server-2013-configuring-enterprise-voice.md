---
title: 'Lync Server 2013 : configuration de voix entreprise'
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
ms.openlocfilehash: ca998a723e4ef84fc1c203d6eddc5f9016f28739
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532551"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="3db32-102">Configuration de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3db32-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3db32-103">_**Dernière modification de la rubrique :** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="3db32-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="3db32-104">Pour déployer voix entreprise, vous devez configurer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="3db32-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="3db32-105">Créer une jonction</span><span class="sxs-lookup"><span data-stu-id="3db32-105">Create a Trunk</span></span>

  - <span data-ttu-id="3db32-106">Définir une stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="3db32-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="3db32-107">Définition d’un itinéraire des communications vocales</span><span class="sxs-lookup"><span data-stu-id="3db32-107">Define a Voice Route</span></span>

  - <span data-ttu-id="3db32-108">Activer les utilisateurs pour voix entreprise</span><span class="sxs-lookup"><span data-stu-id="3db32-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="3db32-109">Créer une jonction</span><span class="sxs-lookup"><span data-stu-id="3db32-109">Create a Trunk</span></span>

<span data-ttu-id="3db32-110">Vous devez définir des jonctions dans votre déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="3db32-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="3db32-111">Pour le routage des Location-Based, vous devez créer une configuration de jonction par jonction.</span><span class="sxs-lookup"><span data-stu-id="3db32-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="3db32-112">À l’aide du générateur de topologie Lync Server, définissez vos jonctions et utilisez la commande Lync Server Windows PowerShell, New-applet cstrunkconfiguration ou le panneau de configuration Lync Server pour définir les configurations de jonction correspondantes.</span><span class="sxs-lookup"><span data-stu-id="3db32-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="3db32-113">Pour plus d’informations sur l’activation du routage des Location-Based sur les configurations de jonctions, consultez la section relative à l’activation du routage des Location-Based sur les jonctions dans la rubrique, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="3db32-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="3db32-114">Pour cet exemple, le tableau suivant illustre les jonctions utilisées dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="3db32-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="3db32-115">Pour plus d’informations, reportez-vous à la rubrique [define Additional jonctions in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="3db32-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="3db32-116">Nom de la jonction</span><span class="sxs-lookup"><span data-stu-id="3db32-116">Trunk name</span></span></th>
<th><span data-ttu-id="3db32-117">Type du système</span><span class="sxs-lookup"><span data-stu-id="3db32-117">System type</span></span></th>
<th><span data-ttu-id="3db32-118">Nom</span><span class="sxs-lookup"><span data-stu-id="3db32-118">Name</span></span></th>
<th><span data-ttu-id="3db32-119">Emplacement</span><span class="sxs-lookup"><span data-stu-id="3db32-119">Location</span></span></th>
<th><span data-ttu-id="3db32-120">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="3db32-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3db32-121">Jonction 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="3db32-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="3db32-122">Passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="3db32-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="3db32-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="3db32-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="3db32-124">Delhi</span><span class="sxs-lookup"><span data-stu-id="3db32-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="3db32-125">MS1</span><span class="sxs-lookup"><span data-stu-id="3db32-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3db32-126">Jonction 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="3db32-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="3db32-127">Passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="3db32-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="3db32-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="3db32-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="3db32-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3db32-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="3db32-130">MS1</span><span class="sxs-lookup"><span data-stu-id="3db32-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3db32-131">Jonction 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="3db32-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="3db32-132">PBX</span><span class="sxs-lookup"><span data-stu-id="3db32-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="3db32-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="3db32-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="3db32-134">Delhi</span><span class="sxs-lookup"><span data-stu-id="3db32-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="3db32-135">MS1</span><span class="sxs-lookup"><span data-stu-id="3db32-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3db32-136">Jonction 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="3db32-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="3db32-137">PBX</span><span class="sxs-lookup"><span data-stu-id="3db32-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="3db32-138">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="3db32-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="3db32-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3db32-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="3db32-140">MS1</span><span class="sxs-lookup"><span data-stu-id="3db32-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="3db32-141">Définit les stratégies de voix</span><span class="sxs-lookup"><span data-stu-id="3db32-141">Defines Voice Policies</span></span>

<span data-ttu-id="3db32-142">Vous devez définir des stratégies de voix pour votre déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="3db32-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="3db32-143">Définir une stratégie de voix pour appliquer des restrictions de routage Location-Based à un sous-ensemble d’utilisateurs si seul un sous-ensemble de ces derniers est requis pour utiliser le routage de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="3db32-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="3db32-144">Pour cet exemple, le tableau suivant illustre les stratégies de voix utilisées dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="3db32-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="3db32-145">Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="3db32-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="3db32-146">Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités d’appel et les privilèges dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="3db32-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="3db32-147">Stratégie de voix 1</span><span class="sxs-lookup"><span data-stu-id="3db32-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="3db32-148">Stratégie de voix 2</span><span class="sxs-lookup"><span data-stu-id="3db32-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3db32-149">ID de stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="3db32-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="3db32-150">Stratégie de voix de Delhi</span><span class="sxs-lookup"><span data-stu-id="3db32-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="3db32-151">Stratégie de voix Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3db32-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3db32-152">Utilisations RTC</span><span class="sxs-lookup"><span data-stu-id="3db32-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="3db32-153">Utilisation de Delhi, utilisation de PBX del, utilisation de PBX HYD</span><span class="sxs-lookup"><span data-stu-id="3db32-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="3db32-154">Utilisation de Hyderabad, utilisation de la HYD PBX, utilisation de PBX del</span><span class="sxs-lookup"><span data-stu-id="3db32-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3db32-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="3db32-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="3db32-156">False</span><span class="sxs-lookup"><span data-stu-id="3db32-156">False</span></span></p></td>
<td><p><span data-ttu-id="3db32-157">False</span><span class="sxs-lookup"><span data-stu-id="3db32-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="3db32-158">Définir les itinéraires des communications vocales</span><span class="sxs-lookup"><span data-stu-id="3db32-158">Define Voice Routes</span></span>

<span data-ttu-id="3db32-159">Vous devez définir des itinéraires de communications vocales pour votre déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="3db32-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="3db32-160">Pour cet exemple, le tableau suivant illustre les itinéraires des communications vocales utilisés dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="3db32-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="3db32-161">Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="3db32-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="3db32-162">Pour plus d’informations, reportez-vous à la rubrique [Configuration des itinéraires des communications vocales pour les appels sortants dans Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="3db32-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="3db32-163">Itinéraire des communications vocales 1</span><span class="sxs-lookup"><span data-stu-id="3db32-163">Voice route 1</span></span></th>
<th><span data-ttu-id="3db32-164">Itinéraire des communications vocales 2</span><span class="sxs-lookup"><span data-stu-id="3db32-164">Voice route 2</span></span></th>
<th><span data-ttu-id="3db32-165">Itinéraire des communications vocales 3</span><span class="sxs-lookup"><span data-stu-id="3db32-165">Voice route 3</span></span></th>
<th><span data-ttu-id="3db32-166">Itinéraire des communications vocales 4</span><span class="sxs-lookup"><span data-stu-id="3db32-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3db32-167">Nom</span><span class="sxs-lookup"><span data-stu-id="3db32-167">Name</span></span></p></td>
<td><p><span data-ttu-id="3db32-168">Itinéraire de l’Delhi</span><span class="sxs-lookup"><span data-stu-id="3db32-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="3db32-169">Itinéraire Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3db32-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="3db32-170">Itinéraire de la del PBX</span><span class="sxs-lookup"><span data-stu-id="3db32-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="3db32-171">Itinéraire HYD PBX</span><span class="sxs-lookup"><span data-stu-id="3db32-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3db32-172">Utilisations RTC</span><span class="sxs-lookup"><span data-stu-id="3db32-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="3db32-173">Utilisation de Delhi</span><span class="sxs-lookup"><span data-stu-id="3db32-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="3db32-174">Utilisation de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3db32-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="3db32-175">Utilisation de PBX del</span><span class="sxs-lookup"><span data-stu-id="3db32-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="3db32-176">Utilisation de la HYD PBX</span><span class="sxs-lookup"><span data-stu-id="3db32-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3db32-177">Urbain</span><span class="sxs-lookup"><span data-stu-id="3db32-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="3db32-178">Jonction 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="3db32-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="3db32-179">Jonction 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="3db32-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="3db32-180">Jonction 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="3db32-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="3db32-181">Jonction 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="3db32-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="3db32-182">Activer les utilisateurs pour voix entreprise</span><span class="sxs-lookup"><span data-stu-id="3db32-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="3db32-183">Activez les utilisateurs pour voix entreprise et affectez-leur une stratégie de voix que vous avez définie précédemment.</span><span class="sxs-lookup"><span data-stu-id="3db32-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="3db32-184">Pour cet exemple, le tableau suivant illustre l’affectation utilisée dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="3db32-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="3db32-185">Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="3db32-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="3db32-186">Pour plus d’informations, consultez la rubrique [activation des utilisateurs pour voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="3db32-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="3db32-187">Utilisateurs situés à l’adresse de Delhi</span><span class="sxs-lookup"><span data-stu-id="3db32-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="3db32-188">Utilisateurs situés dans Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3db32-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3db32-189">Stratégie de voix associée</span><span class="sxs-lookup"><span data-stu-id="3db32-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="3db32-190">Stratégie de voix de Delhi</span><span class="sxs-lookup"><span data-stu-id="3db32-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="3db32-191">Stratégie de voix Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3db32-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3db32-192">Exemples d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="3db32-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="3db32-193">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="3db32-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="3db32-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="3db32-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3db32-195">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3db32-195">See Also</span></span>


[<span data-ttu-id="3db32-196">Configuration du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3db32-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

