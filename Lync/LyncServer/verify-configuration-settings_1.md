---
title: Vérifier les paramètres de configuration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1ad498f25656e01507e55c41d98ff4bb9143b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508411"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="ac87b-102">Vérifier les paramètres de configuration</span><span class="sxs-lookup"><span data-stu-id="ac87b-102">Verify configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac87b-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ac87b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ac87b-104">Après avoir fusionné la topologie et exécuté l’applet de commande **Import-applet cslegacyconfiguration** , vérifiez que vos stratégies et paramètres Office Communications Server 2007 R2 ont été importés dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac87b-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="ac87b-105">Le tableau suivant répertorie les stratégies et les paramètres que vous devez vérifier.</span><span class="sxs-lookup"><span data-stu-id="ac87b-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="ac87b-106">Stratégies et paramètres à vérifier après la migration</span><span class="sxs-lookup"><span data-stu-id="ac87b-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac87b-107">Si vous avez utilisé cette charge de travail :</span><span class="sxs-lookup"><span data-stu-id="ac87b-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="ac87b-108">Vérifiez ces stratégies et paramètres :</span><span class="sxs-lookup"><span data-stu-id="ac87b-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac87b-109">Messagerie instantanée et conférence</span><span class="sxs-lookup"><span data-stu-id="ac87b-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="ac87b-110">Stratégie de présence</span><span class="sxs-lookup"><span data-stu-id="ac87b-110">Presence policy</span></span></p>
<p><span data-ttu-id="ac87b-111">Stratégie de conférence</span><span class="sxs-lookup"><span data-stu-id="ac87b-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac87b-112">Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="ac87b-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="ac87b-113">Numéros d’accès entrant</span><span class="sxs-lookup"><span data-stu-id="ac87b-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="ac87b-114">Plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="ac87b-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac87b-115">Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="ac87b-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="ac87b-116">Stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="ac87b-116">Voice policy</span></span></p>
<p><span data-ttu-id="ac87b-117">Itinéraires des communications vocales</span><span class="sxs-lookup"><span data-stu-id="ac87b-117">Voice routes</span></span></p>
<p><span data-ttu-id="ac87b-118">Plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="ac87b-118">Dial plans</span></span></p>
<p><span data-ttu-id="ac87b-119">Paramètres d’utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="ac87b-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac87b-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="ac87b-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="ac87b-121">URL simples</span><span class="sxs-lookup"><span data-stu-id="ac87b-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac87b-122">Utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="ac87b-122">External users</span></span></p></td>
<td><p><span data-ttu-id="ac87b-123">Stratégies d’accès externe</span><span class="sxs-lookup"><span data-stu-id="ac87b-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac87b-124">Archivage</span><span class="sxs-lookup"><span data-stu-id="ac87b-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="ac87b-125">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="ac87b-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="ac87b-126">Pour vérifier les stratégies et les paramètres</span><span class="sxs-lookup"><span data-stu-id="ac87b-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="ac87b-127">Dans votre environnement Office Communications Server 2007 R2, notez les noms des plans de numérotation (anciennement appelés profils d’emplacement), les numéros d’accès entrant (numéros de téléphone et régions), les itinéraires de communications vocales et les stratégies répertoriées dans le tableau précédent, ainsi que les URL utilisées pour Office Communicator Web Access.</span><span class="sxs-lookup"><span data-stu-id="ac87b-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="ac87b-128">Sur le serveur frontal Lync Server 2013, ouvrez le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ac87b-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="ac87b-129">Pour vérifier les stratégies de conférence importées, dans le volet de gauche, cliquez sur **Conférence**, sur **stratégie de conférence**, puis vérifiez que toutes les stratégies de conférence de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ac87b-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac87b-130">La stratégie de <STRONG>réunion</STRONG> des versions précédentes d’Office Communications Server est désormais appelée stratégie de conférence dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac87b-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="ac87b-131">De plus, le paramètre <STRONG>particpants anonyme</STRONG> des versions précédentes d’Office Communications Server est désormais un paramètre de la stratégie de conférence Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac87b-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac87b-132">Dans Office Communications Server 2007 R2, si la stratégie de conférence n’est pas définie sur <STRONG>utiliser par utilisateur</STRONG>, seuls les paramètres de stratégie globale sont importés.</span><span class="sxs-lookup"><span data-stu-id="ac87b-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="ac87b-133">Aucune autre stratégie de conférence n’est importée dans cette situation.</span><span class="sxs-lookup"><span data-stu-id="ac87b-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac87b-134">Si les <STRONG>participants anonymes</STRONG> sont définis sur <STRONG>Enforce per User</STRONG> dans votre stratégie de conférence Office Communications Server 2007 R2, deux stratégies de conférence sont créées lors de la migration : une avec <STRONG>allowanonymousparticipantsinmeetings ayant</STRONG> définie sur <STRONG>true</STRONG> et une avec <STRONG>allowanonymousparticipantsinmeetings ayant</STRONG> défini sur <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ac87b-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="ac87b-135">Pour vérifier les plans de numérotation importés, cliquez sur **Routage des communications vocales**, sur **Plan de numérotation**, puis contrôlez la présence de tous les plans de numérotation de votre environnement Office Communicator 2007 R2 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ac87b-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac87b-136">Dans Lync Server 2013, les <STRONG>profils d’emplacement</STRONG> sont désormais appelés <STRONG>plans de numérotation</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ac87b-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="ac87b-137">Pour vérifier les stratégies de voix importées, cliquez sur **Routage des communications vocales**, sur **Stratégie de voix**, puis contrôlez la présence de toutes les stratégies de voix de votre environnement Office Communicator 2007 R2 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ac87b-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac87b-138">Si la stratégie de voix n’est pas définie sur <STRONG>utiliser par utilisateur</STRONG> dans votre environnement Office Communications Server 2007 R2, seuls les paramètres de stratégie globale sont importés.</span><span class="sxs-lookup"><span data-stu-id="ac87b-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="ac87b-139">Aucune autre stratégie de voix n’est importée dans ce cas.</span><span class="sxs-lookup"><span data-stu-id="ac87b-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="ac87b-140">Pour vérifier les itinéraires des communications vocales importés, cliquez sur **Routage des communications vocales**, sur **Itinéraire**, puis contrôlez la présence de tous les itinéraires des communications vocales de votre environnement Office Communicator 2007 R2 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ac87b-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="ac87b-141">Pour vérifier les paramètres d’utilisation PSTN importés, cliquez sur **Routage des communications vocales**, sur **Utilisation PSTN**, puis contrôlez la présence de tous les paramètres d’utilisation PSTN de votre environnement Office Communicator 2007 R2 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ac87b-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="ac87b-142">Pour vérifier les stratégies d’accès externe importées, cliquez sur **Fédération et accès externe**, sur **Stratégie d’accès externe**, puis contrôlez la présence de toutes les stratégies d’accès externe de votre environnement Office Communicator 2007 R2 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ac87b-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="ac87b-143">Pour vérifier les stratégies d’archivage, cliquez sur **surveillance et archivage**, cliquez sur **stratégie d’archivage**, puis vérifiez que toutes les stratégies d’archivage de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ac87b-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="ac87b-144">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ac87b-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="ac87b-145">Pour vérifier les stratégies de présence, sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ac87b-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="ac87b-146">En regardant le nom dans le paramètre **Identity** , vérifiez que toutes les stratégies de présence de votre environnement Office Communications Server 2007 R2 ont été importées.</span><span class="sxs-lookup"><span data-stu-id="ac87b-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="ac87b-147">Pour vérifier les stratégies et les paramètres à l’aide des applets de commande</span><span class="sxs-lookup"><span data-stu-id="ac87b-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="ac87b-148">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ac87b-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="ac87b-149">Exécutez les applets de commande dans le tableau suivant pour vérifier les stratégies et les paramètres.</span><span class="sxs-lookup"><span data-stu-id="ac87b-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="ac87b-150">La syntaxe de ces applets de commande ressemble à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="ac87b-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="ac87b-151">Pour plus d’informations sur ces applets de commande, exécutez :</span><span class="sxs-lookup"><span data-stu-id="ac87b-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac87b-152">Pour cette stratégie ou ce paramètre :</span><span class="sxs-lookup"><span data-stu-id="ac87b-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="ac87b-153">Utilisez cette applet de commande :</span><span class="sxs-lookup"><span data-stu-id="ac87b-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac87b-154">Stratégie de présence</span><span class="sxs-lookup"><span data-stu-id="ac87b-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="ac87b-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="ac87b-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac87b-156">Stratégie de conférence</span><span class="sxs-lookup"><span data-stu-id="ac87b-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="ac87b-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="ac87b-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac87b-158">Numéros d’accès entrant</span><span class="sxs-lookup"><span data-stu-id="ac87b-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="ac87b-159"><strong>Get-applet csdialinconferencingaccessnumber</strong></span><span class="sxs-lookup"><span data-stu-id="ac87b-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac87b-160">Plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="ac87b-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="ac87b-161"><strong>Get-CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="ac87b-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac87b-162">Stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="ac87b-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="ac87b-163"><strong>Get-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="ac87b-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac87b-164">Itinéraires des communications vocales</span><span class="sxs-lookup"><span data-stu-id="ac87b-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="ac87b-165"><strong>Get-CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="ac87b-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac87b-166">Utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="ac87b-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="ac87b-167"><strong>Get-CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="ac87b-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac87b-168">URL</span><span class="sxs-lookup"><span data-stu-id="ac87b-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="ac87b-169"><strong>Get-CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="ac87b-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac87b-170">Stratégies d’accès externe</span><span class="sxs-lookup"><span data-stu-id="ac87b-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="ac87b-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="ac87b-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac87b-172">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="ac87b-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="ac87b-173"><strong>Get-applet csarchivingpolicy</strong></span><span class="sxs-lookup"><span data-stu-id="ac87b-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

