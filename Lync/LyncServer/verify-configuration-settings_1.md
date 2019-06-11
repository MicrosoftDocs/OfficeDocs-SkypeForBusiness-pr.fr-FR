---
title: Vérifier les paramètres de configuration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a20b78ac9275657461beb74a7325c0c46e4e40fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="98844-102">Vérifier les paramètres de configuration</span><span class="sxs-lookup"><span data-stu-id="98844-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98844-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="98844-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="98844-104">Après avoir fusionné la topologie et exécuté l’applet de contrôle **Import-CsLegacyConfiguration** , assurez-vous que les stratégies et paramètres de votre serveur Office Communications Server 2007 R2 ont été importés dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98844-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="98844-105">Le tableau suivant répertorie les stratégies et les paramètres que vous devez vérifier.</span><span class="sxs-lookup"><span data-stu-id="98844-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="98844-106">Stratégies et paramètres à vérifier après la migration</span><span class="sxs-lookup"><span data-stu-id="98844-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98844-107">Si vous utilisez cette charge de travail:</span><span class="sxs-lookup"><span data-stu-id="98844-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="98844-108">Vérifiez les stratégies et les paramètres suivants:</span><span class="sxs-lookup"><span data-stu-id="98844-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98844-109">Messagerie instantanée et conférences</span><span class="sxs-lookup"><span data-stu-id="98844-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="98844-110">Politique de présence</span><span class="sxs-lookup"><span data-stu-id="98844-110">Presence policy</span></span></p>
<p><span data-ttu-id="98844-111">Stratégie de conférence</span><span class="sxs-lookup"><span data-stu-id="98844-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98844-112">Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="98844-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="98844-113">Numéros d’accès rendez-vous</span><span class="sxs-lookup"><span data-stu-id="98844-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="98844-114">Plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="98844-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98844-115">Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="98844-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="98844-116">Stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="98844-116">Voice policy</span></span></p>
<p><span data-ttu-id="98844-117">Itinéraires des communications vocales</span><span class="sxs-lookup"><span data-stu-id="98844-117">Voice routes</span></span></p>
<p><span data-ttu-id="98844-118">Plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="98844-118">Dial plans</span></span></p>
<p><span data-ttu-id="98844-119">Paramètres d’utilisation RTC</span><span class="sxs-lookup"><span data-stu-id="98844-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98844-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="98844-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="98844-121">URL simples </span><span class="sxs-lookup"><span data-stu-id="98844-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98844-122">Utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="98844-122">External users</span></span></p></td>
<td><p><span data-ttu-id="98844-123">Stratégies d’accès externe</span><span class="sxs-lookup"><span data-stu-id="98844-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98844-124">Archivage</span><span class="sxs-lookup"><span data-stu-id="98844-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="98844-125">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="98844-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="98844-126">Pour vérifier les stratégies et les paramètres</span><span class="sxs-lookup"><span data-stu-id="98844-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="98844-127">Dans votre environnement Office Communications Server 2007 R2, notez les noms des plans de numérotation (auparavant appelés profils d’emplacement), les numéros d’accès entrants (numéros de téléphone d’accès au service de conférence), les itinéraires vocaux et les stratégies répertoriées dans le tableau précédent, en plus des URL utilisées pour Communicator Web Access.</span><span class="sxs-lookup"><span data-stu-id="98844-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="98844-128">Sur le serveur frontal Lync Server 2013, ouvrez le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98844-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="98844-129">Pour vérifier les stratégies de conférence importées, dans le volet gauche, cliquez sur **Conférence**, cliquez sur **stratégie de conférence**, puis vérifiez que toutes les stratégies de conférence dans votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="98844-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98844-130">La stratégie de <STRONG>réunion</STRONG> à partir de versions précédentes d’Office Communications Server est désormais désignée sous le nom de stratégie de conférence dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98844-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="98844-131">Par ailleurs, le paramètre <STRONG>particpants anonyme</STRONG> à partir des versions précédentes d’Office Communications Server est désormais un paramètre dans la stratégie de conférence 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98844-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98844-132">Dans Office Communications Server 2007 R2, si la stratégie de conférence n’est pas définie pour une <STRONG>utilisation par utilisateur</STRONG>, seuls les paramètres de stratégie globale sont importés.</span><span class="sxs-lookup"><span data-stu-id="98844-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="98844-133">Aucune autre stratégie de conférence n’est importée dans cette situation.</span><span class="sxs-lookup"><span data-stu-id="98844-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98844-134">Si les <STRONG>participants anonymes</STRONG> sont définis pour <STRONG>appliquer par utilisateur</STRONG> dans votre stratégie de conférence Office Communications Server 2007 R2, deux stratégies de conférence sont créées lors de la migration: une avec <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> défini sur <STRONG>Vrai</STRONG> et un avec <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> défini sur <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="98844-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="98844-135">Pour vérifier la présence de plans de numérotation, cliquez sur **routage des communications vocales**, sur **plan**de numérotation, puis vérifiez que tous les plans de numérotation dans votre environnement Office Communicator 2007 R2 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="98844-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98844-136">Dans Lync Server 2013, les <STRONG>profils d’emplacement</STRONG> sont désormais désignés sous le nom de plan de <STRONG>numérotation</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="98844-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="98844-137">Pour vérifier les stratégies vocales importées, cliquez sur **routage des communications**vocales, cliquez sur **politique vocale**, puis vérifiez que toutes les stratégies vocales dans votre environnement Office Communicator 2007 R2 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="98844-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98844-138">Si la stratégie vocale n’est pas configurée pour être <STRONG>utilisée par utilisateur</STRONG> dans votre environnement Office Communications Server 2007 R2, seuls les paramètres de stratégie globale sont importés.</span><span class="sxs-lookup"><span data-stu-id="98844-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="98844-139">Aucune autre politique vocale n’est importée dans cette situation.</span><span class="sxs-lookup"><span data-stu-id="98844-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="98844-140">Pour vérifier les itinéraires vocaux importés, cliquez sur \*\*\*\* **routage des communications**vocales, sur routage, puis vérifiez que tous les itinéraires vocaux dans votre environnement Office Communicator 2007 R2 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="98844-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="98844-141">Pour vérifier les paramètres d’utilisation RTC importés, cliquez sur **routage des communications vocales**, sur **utilisation PSTN**, puis vérifiez que les paramètres d’utilisation RTC de votre environnement Office Communicator 2007 R2 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="98844-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="98844-142">Pour vérifier les stratégies d’accès externe importées, cliquez sur **Fédération et accès externe**, cliquez sur **stratégie d’accès externe**, puis vérifiez que toutes les stratégies d’accès externe dans votre environnement Office Communicator 2007 R2 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="98844-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="98844-143">Pour vérifier les stratégies d’archivage, cliquez sur **surveillance et archivage**, sur **stratégie**d’archivage, puis vérifiez que toutes les stratégies d’archivage de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="98844-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="98844-144">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="98844-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="98844-145">Pour vérifier les stratégies de présence, à partir de la ligne de commande, tapez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="98844-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="98844-146">En examinant le nom dans le \*\*\*\* paramètre Identity, vérifiez que toutes les stratégies de présence de votre environnement Office Communications Server 2007 R2 ont été importées.</span><span class="sxs-lookup"><span data-stu-id="98844-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="98844-147">Pour vérifier les stratégies et les paramètres à l’aide d’applets de contrôle</span><span class="sxs-lookup"><span data-stu-id="98844-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="98844-148">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="98844-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="98844-149">Dans le tableau ci-dessous, exécutez les applets de commande pour vérifier les stratégies et les paramètres.</span><span class="sxs-lookup"><span data-stu-id="98844-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="98844-150">La syntaxe de ces applets de commande est semblable à l’exemple suivant:</span><span class="sxs-lookup"><span data-stu-id="98844-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="98844-151">Pour plus d’informations sur ces cmdlets, exécutez:</span><span class="sxs-lookup"><span data-stu-id="98844-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98844-152">Pour cette stratégie ou ce paramètre:</span><span class="sxs-lookup"><span data-stu-id="98844-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="98844-153">Utilisez cette applet de cmdlet:</span><span class="sxs-lookup"><span data-stu-id="98844-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98844-154">Politique de présence</span><span class="sxs-lookup"><span data-stu-id="98844-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="98844-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="98844-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98844-156">Stratégie de conférence</span><span class="sxs-lookup"><span data-stu-id="98844-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="98844-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="98844-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98844-158">Numéros d’accès rendez-vous</span><span class="sxs-lookup"><span data-stu-id="98844-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="98844-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span><span class="sxs-lookup"><span data-stu-id="98844-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98844-160">Plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="98844-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="98844-161"><strong>Get-CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="98844-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98844-162">Stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="98844-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="98844-163"><strong>Get-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="98844-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98844-164">Itinéraires des communications vocales</span><span class="sxs-lookup"><span data-stu-id="98844-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="98844-165"><strong>Get-CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="98844-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98844-166">Utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="98844-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="98844-167"><strong>Get-CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="98844-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98844-168">URL</span><span class="sxs-lookup"><span data-stu-id="98844-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="98844-169"><strong>Get-CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="98844-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98844-170">Stratégies d’accès externe</span><span class="sxs-lookup"><span data-stu-id="98844-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="98844-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="98844-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98844-172">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="98844-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="98844-173"><strong>Get-CsArchivingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="98844-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

