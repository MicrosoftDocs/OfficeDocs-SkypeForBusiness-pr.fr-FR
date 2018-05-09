---
title: Stratégies de restriction appel sortant pour les appels PSTN utilisateur et de conférence Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler le type d’appels audio d’utilisateur final et de conférence PSTN qui peuvent être effectuées par les utilisateurs.
ms.openlocfilehash: 2929198a8bfff866f0d9f6d375593cd429885b2e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="0fcdb-103">Stratégies de restriction appel sortant pour les appels PSTN utilisateur et de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="0fcdb-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="0fcdb-104">En tant qu’administrateur, vous pouvez utiliser des contrôles d’appel sortant pour restreindre le type d’appels audio d’utilisateur final et de conférence PSTN qui peuvent être effectuées par les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="0fcdb-105">Contrôles d’appel sortant peuvent être appliquées par utilisateur et fournissent deux contrôles suivants pour limiter l’accès indépendamment chaque type d’appels sortants.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="0fcdb-106">Par défaut, les deux contrôles sont configurés pour autoriser les appels sortants et internationales.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="0fcdb-107">Contrôle</span><span class="sxs-lookup"><span data-stu-id="0fcdb-107">Control</span></span>|<span data-ttu-id="0fcdb-108">Description</span><span class="sxs-lookup"><span data-stu-id="0fcdb-108">Description</span></span>|<span data-ttu-id="0fcdb-109">Options de contrôle</span><span class="sxs-lookup"><span data-stu-id="0fcdb-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0fcdb-110">Appels audio de conférence PSTN</span><span class="sxs-lookup"><span data-stu-id="0fcdb-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="0fcdb-111">Limite le type de sortie</span><span class="sxs-lookup"><span data-stu-id="0fcdb-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="0fcdb-112">appels qui sont autorisés à partir</span><span class="sxs-lookup"><span data-stu-id="0fcdb-112">calls that are allowed from within</span></span> </br><span data-ttu-id="0fcdb-113">réunions organisées par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-113">meetings organized by a user.</span></span>|<span data-ttu-id="0fcdb-114">International et national (par défaut)</span><span class="sxs-lookup"><span data-stu-id="0fcdb-114">International and Domestic (default)</span></span></br><span data-ttu-id="0fcdb-115">Nationaux</span><span class="sxs-lookup"><span data-stu-id="0fcdb-115">Domestic</span></span></br><span data-ttu-id="0fcdb-116">Aucun</span><span class="sxs-lookup"><span data-stu-id="0fcdb-116">None</span></span>|
|<span data-ttu-id="0fcdb-117">Appels PSTN utilisateur final</span><span class="sxs-lookup"><span data-stu-id="0fcdb-117">End user PSTN calls</span></span>|<span data-ttu-id="0fcdb-118">Restreint les types d’appels</span><span class="sxs-lookup"><span data-stu-id="0fcdb-118">Restricts the type of calls</span></span> </br><span data-ttu-id="0fcdb-119">qui peut être effectué par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-119">that can be made by a user.</span></span>|<span data-ttu-id="0fcdb-120">International et national (par défaut)</span><span class="sxs-lookup"><span data-stu-id="0fcdb-120">International and Domestic (default)</span></span></br><span data-ttu-id="0fcdb-121">Nationaux</span><span class="sxs-lookup"><span data-stu-id="0fcdb-121">Domestic</span></span></br><span data-ttu-id="0fcdb-122">Aucun</span><span class="sxs-lookup"><span data-stu-id="0fcdb-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="0fcdb-123">Un appel est déterminé à l’intérieur si le numéro de téléphone appelé se trouve dans le même pays que celui qui a été défini dans Office 365 pour l’organisateur de la réunion (dans le cas des services d’audioconférence) ou de l’utilisateur final (dans le cas d’utilisateurs finaux des appels PSTN).</span><span class="sxs-lookup"><span data-stu-id="0fcdb-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 


## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="0fcdb-124">Restreindre les appels sortants de services d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="0fcdb-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="0fcdb-125">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="0fcdb-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="0fcdb-126">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="0fcdb-127">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="0fcdb-128">Cliquez sur le menu en regard de **Ponts de conférence**, puis cliquez sur **Modifier** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-128">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="0fcdb-129">Dans le volet de **fournisseur de pont de conférence** , sous **Restrictions de numérotation issus de réunions de cet utilisateur**, sélectionnez l’option de restriction d’appel sortant.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-129">In the **Conference bridge provider** pane, under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="0fcdb-130">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-130">Click **Apply**.</span></span> 

<span data-ttu-id="0fcdb-131">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="0fcdb-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="0fcdb-132">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **les utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="0fcdb-133">Dans le volet Action, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="0fcdb-134">Sous **Restrictions de numérotation issus de réunions de cet utilisateur**, sélectionnez l’option de restriction d’appel sortant.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Les Restrictions sur les options de numérotation-outs](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="0fcdb-136">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="0fcdb-137">**À l’aide de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0fcdb-137">**Using PowerShell**</span></span>

<span data-ttu-id="0fcdb-138">Restrictions des appels sortants sont contrôlées par une seule stratégie appelée OnlineDialOutPolicy qui possède un attribut de restriction pour chacun.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="0fcdb-139">La stratégie ne peuvent pas être personnalisée, au lieu de cela, il existe des instances de stratégie prédéfinies pour chaque combinaison des paramètres.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="0fcdb-140">Vous pouvez utiliser l’applet de commande Get-CSOnlineDialOutPolicy pour afficher les stratégies d’appel sortants et les attribuer aux utilisateurs à l’aide de l’applet de commande Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="0fcdb-141">(Notez que l’applet de commande Grant ne contient pas le mot « Online » comme l’applet de commande Get).</span><span class="sxs-lookup"><span data-stu-id="0fcdb-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="0fcdb-142">Le tableau suivant fournit une vue d’ensemble de chaque stratégie.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0fcdb-143">Identité = 'tag : DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0fcdb-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="0fcdb-144">Utilisateur à la conférence peut appeler des numéros et internationales, et cet utilisateur peut aussi passer des appels sortants vers des numéros et internationales.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="0fcdb-145">Identité = 'tag : DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0fcdb-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="0fcdb-146">Utilisateur de la conférence peut appeler uniquement des numéros nationaux et cet utilisateur peut effectuer des appels sortants vers des numéros et internationales.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="0fcdb-147">Identité = 'tag : DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0fcdb-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="0fcdb-148">Utilisateur à la conférence ne peut pas réaliser toute numérotation. Cet utilisateur peut effectuer des appels sortants vers des numéros et internationales.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="0fcdb-149">Identité = 'tag : DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0fcdb-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="0fcdb-150">Utilisateur à la conférence peut appeler des numéros et internationales et cet utilisateur peut uniquement établir des appels sortants vers un numéro RTC nationale.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="0fcdb-151">Identité = 'tag : DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0fcdb-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="0fcdb-152">Utilisateur à la conférence peut appeler des numéros et internationales et cet utilisateur ne peut pas émettre des appels sortants vers un numéro RTC en plus des numéros d’urgence.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="0fcdb-153">Identité = 'tag : DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0fcdb-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="0fcdb-154">Utilisateur de la conférence peut appeler uniquement des numéros nationaux et cet utilisateur peut uniquement établir des appels sortants vers les numéros RTPC nationales.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="0fcdb-155">Identité = 'tag : DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0fcdb-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="0fcdb-156">Utilisateur de la conférence peut appeler uniquement des numéros nationaux et cet utilisateur ne peut pas émettre des appels sortants vers un numéro RTC en plus des numéros d’urgence.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="0fcdb-157">Identité = 'tag : DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0fcdb-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="0fcdb-158">Utilisateur à la conférence ne peut pas émettre des appels sortants, et cet utilisateur peut uniquement établir des appels sortants vers les numéros RTPC nationales.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="0fcdb-159">Identité = 'tag : DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0fcdb-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="0fcdb-160">Utilisateur à la conférence ne peut pas émettre des appels sortants, et cet utilisateur ne peut pas émettre des appels sortants vers un numéro RTC en plus des numéros d’urgence.</span><span class="sxs-lookup"><span data-stu-id="0fcdb-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
