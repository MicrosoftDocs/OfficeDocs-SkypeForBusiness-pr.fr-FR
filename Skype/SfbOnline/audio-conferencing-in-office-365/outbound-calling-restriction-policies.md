---
title: Stratégies de restriction des appels sortants pour l’audioconférence et les appels PSTN des utilisateurs
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler le type de conférence audio et d'appels RTC d’utilisateur final pouvant être effectuées par les utilisateurs.
ms.openlocfilehash: e4589a2785d5debf4de6d6a146ede76b020cd2d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299152"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="326e3-103">Stratégies de restriction des appels sortants pour l’audioconférence et les appels PSTN des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="326e3-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="326e3-104">En tant qu'administrateur, vous pouvez utiliser les contrôles d'appels sortants pour restreindre le type de conférence audio et d'appels RTC d'utilisateur final pouvant être effectués par les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="326e3-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="326e3-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span><span class="sxs-lookup"><span data-stu-id="326e3-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="326e3-107">Télécommande</span><span class="sxs-lookup"><span data-stu-id="326e3-107">Control</span></span>|<span data-ttu-id="326e3-108">Description</span><span class="sxs-lookup"><span data-stu-id="326e3-108">Description</span></span>|<span data-ttu-id="326e3-109">Options de contrôle</span><span class="sxs-lookup"><span data-stu-id="326e3-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="326e3-110">Appels RTC de conférence audio</span><span class="sxs-lookup"><span data-stu-id="326e3-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="326e3-111">Limite le type de sortie</span><span class="sxs-lookup"><span data-stu-id="326e3-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="326e3-112">les appels autorisés de l'intérieur</span><span class="sxs-lookup"><span data-stu-id="326e3-112">calls that are allowed from within</span></span> </br><span data-ttu-id="326e3-113">réunions organisées par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="326e3-113">meetings organized by a user.</span></span>|<span data-ttu-id="326e3-114">International et national (par défaut)</span><span class="sxs-lookup"><span data-stu-id="326e3-114">International and Domestic (default)</span></span></br><span data-ttu-id="326e3-115">Nationaux</span><span class="sxs-lookup"><span data-stu-id="326e3-115">Domestic</span></span></br><span data-ttu-id="326e3-116">Aucun</span><span class="sxs-lookup"><span data-stu-id="326e3-116">None</span></span>|
|<span data-ttu-id="326e3-117">Appels RTC utilisateur final</span><span class="sxs-lookup"><span data-stu-id="326e3-117">End user PSTN calls</span></span>|<span data-ttu-id="326e3-118">Limite le type d'appels</span><span class="sxs-lookup"><span data-stu-id="326e3-118">Restricts the type of calls</span></span> </br><span data-ttu-id="326e3-119">qui peuvent être effectués par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="326e3-119">that can be made by a user.</span></span>|<span data-ttu-id="326e3-120">International et national (par défaut)</span><span class="sxs-lookup"><span data-stu-id="326e3-120">International and Domestic (default)</span></span></br><span data-ttu-id="326e3-121">Nationaux</span><span class="sxs-lookup"><span data-stu-id="326e3-121">Domestic</span></span></br><span data-ttu-id="326e3-122">Aucun</span><span class="sxs-lookup"><span data-stu-id="326e3-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="326e3-123">Un appel est considéré comme domestique si le numéro composé est dans le même pays que celui où Office 365 a été configuré pour l’organisateur de la réunion (dans le cas d’une audioconférence) ou l’utilisateur final (dans le cas d’appels RTC de l’utilisateur final).</span><span class="sxs-lookup"><span data-stu-id="326e3-123">A call is considered domestic if the number dialed is in the same country where Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="326e3-124">Restreindre les appels sortants de conférence audio</span><span class="sxs-lookup"><span data-stu-id="326e3-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="326e3-125">![teams-logo-30x30. png](../images/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="326e3-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="326e3-126">Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="326e3-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="326e3-127">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="326e3-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="326e3-128">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="326e3-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="326e3-129">Sous **Autorisation d’appel sortant de réunions**, sélectionnez l’option de restriction d’appel sortant souhaitée.</span><span class="sxs-lookup"><span data-stu-id="326e3-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="326e3-130">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="326e3-130">Click **Save**.</span></span> 

<span data-ttu-id="326e3-131">![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **à l’aide du centre d’administration Skype entreprise**</span><span class="sxs-lookup"><span data-stu-id="326e3-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="326e3-132">Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation de gauche, sélectionnez**utilisateurs**de l' **audioconférence** > , puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="326e3-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="326e3-133">Dans le volet Action, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="326e3-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="326e3-134">Sous **Restrictions de numérotation des réunions de cet utilisateur**, sélectionnez l’option de restriction d’appel sortant souhaitée.</span><span class="sxs-lookup"><span data-stu-id="326e3-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Les restrictions aux options de numérotation](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="326e3-136">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="326e3-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="326e3-137">**Utiliser PowerShell**</span><span class="sxs-lookup"><span data-stu-id="326e3-137">**Using PowerShell**</span></span>

<span data-ttu-id="326e3-p102">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span><span class="sxs-lookup"><span data-stu-id="326e3-p102">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="326e3-p103">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span><span class="sxs-lookup"><span data-stu-id="326e3-p103">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="326e3-142">Le tableau suivant fournit une vue d’ensemble de chaque stratégie.</span><span class="sxs-lookup"><span data-stu-id="326e3-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="326e3-143">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="326e3-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="326e3-144">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur peut également passer des appels vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="326e3-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="326e3-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="326e3-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="326e3-146">L'utilisateur de la conférence peut uniquement composer des numéros nationaux et cet utilisateur peut passer des appels vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="326e3-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="326e3-147">Identité = 'tag : DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="326e3-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="326e3-148">L'utilisateur de la conférence ne peut effectuer aucun appel sortant. Cet utilisateur peut effectuer des appels sortants vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="326e3-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="326e3-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="326e3-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="326e3-150">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux, et cet utilisateur ne peut passer que des appels sortants vers un numéro RTC national.</span><span class="sxs-lookup"><span data-stu-id="326e3-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="326e3-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="326e3-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="326e3-152">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur ne peut pas effectuer d'appels sortants vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="326e3-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="326e3-153">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="326e3-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="326e3-154">L'utilisateur de la conférence ne peut appeler que des numéros nationaux, et cet utilisateur ne peut émettre que des appels vers des numéros RTC nationaux.</span><span class="sxs-lookup"><span data-stu-id="326e3-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="326e3-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="326e3-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="326e3-156">L'utilisateur de la conférence peut uniquement composer des numéros nationaux, et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="326e3-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="326e3-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="326e3-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="326e3-158">L'utilisateur de la conférence ne peut effectuer aucun appel sortant et cet utilisateur peut uniquement effectuer des appels sortants vers des numéros RTC nationaux.</span><span class="sxs-lookup"><span data-stu-id="326e3-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="326e3-159">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="326e3-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="326e3-160">L'utilisateur de la conférence ne peut effectuer aucun appel sortant et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="326e3-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
