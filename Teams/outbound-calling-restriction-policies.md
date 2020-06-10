---
title: Restrictions des appels sortants-audioconférence & appels RTC
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Les administrateurs peuvent contrôler le type de conférence audio et d'appels RTC d’utilisateur final pouvant être effectuées par les utilisateurs.
ms.openlocfilehash: ca4b7920ccad27a9434cbd1e5f76d7d10c4f4612
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665906"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="e87ee-103">Stratégies de restriction des appels sortants pour l’audioconférence et les appels PSTN des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e87ee-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="e87ee-104">En tant qu'administrateur, vous pouvez utiliser les contrôles d'appels sortants pour restreindre le type de conférence audio et d'appels RTC d'utilisateur final pouvant être effectués par les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e87ee-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="e87ee-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span><span class="sxs-lookup"><span data-stu-id="e87ee-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="e87ee-107">Télécommande</span><span class="sxs-lookup"><span data-stu-id="e87ee-107">Control</span></span>|<span data-ttu-id="e87ee-108">Description</span><span class="sxs-lookup"><span data-stu-id="e87ee-108">Description</span></span>|<span data-ttu-id="e87ee-109">Options de contrôle</span><span class="sxs-lookup"><span data-stu-id="e87ee-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e87ee-110">Appels RTC de conférence audio</span><span class="sxs-lookup"><span data-stu-id="e87ee-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="e87ee-111">Limite le type de sortie</span><span class="sxs-lookup"><span data-stu-id="e87ee-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="e87ee-112">les appels autorisés de l'intérieur</span><span class="sxs-lookup"><span data-stu-id="e87ee-112">calls that are allowed from within</span></span> </br><span data-ttu-id="e87ee-113">réunions organisées par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e87ee-113">meetings organized by a user.</span></span>|<span data-ttu-id="e87ee-114">Toute destination (par défaut)</span><span class="sxs-lookup"><span data-stu-id="e87ee-114">Any destination (default)</span></span></br><span data-ttu-id="e87ee-115">Dans le même pays ou la même région que le organizor</span><span class="sxs-lookup"><span data-stu-id="e87ee-115">In the same country or region as the organizor</span></span> </br> </br><span data-ttu-id="e87ee-116">Zonage uniquement dans les pays ou régions</span><span class="sxs-lookup"><span data-stu-id="e87ee-116">Zone A countries or regions only</span></span> </br><span data-ttu-id="e87ee-117">Ne pas autoriser</span><span class="sxs-lookup"><span data-stu-id="e87ee-117">Don't allow</span></span>|
|<span data-ttu-id="e87ee-118">Appels RTC utilisateur final</span><span class="sxs-lookup"><span data-stu-id="e87ee-118">End user PSTN calls</span></span>|<span data-ttu-id="e87ee-119">Limite le type d'appels</span><span class="sxs-lookup"><span data-stu-id="e87ee-119">Restricts the type of calls</span></span> </br><span data-ttu-id="e87ee-120">qui peuvent être effectués par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e87ee-120">that can be made by a user.</span></span>|<span data-ttu-id="e87ee-121">International et national (par défaut)</span><span class="sxs-lookup"><span data-stu-id="e87ee-121">International and Domestic (default)</span></span></br><span data-ttu-id="e87ee-122">Nationaux</span><span class="sxs-lookup"><span data-stu-id="e87ee-122">Domestic</span></span></br><span data-ttu-id="e87ee-123">Aucun</span><span class="sxs-lookup"><span data-stu-id="e87ee-123">None</span></span>|

<span data-ttu-id="e87ee-124">Pour connaître les pays/régions qui sont considérés comme la zone A, consultez [la rubrique zone a pays/régions](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="e87ee-124">To find out which countries/regions are considered Zone A, see [Zone A countries/regions](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).</span></span>

   > [!NOTE]
   > <span data-ttu-id="e87ee-125">Un appel est considéré comme domestique si le numéro composé est dans le même pays que Microsoft 365 ou Office 365 a été configuré pour l’organisateur de la réunion (dans le cas d’une audioconférence) ou par l’utilisateur final (dans le cas d’appels RTC de l’utilisateur final).</span><span class="sxs-lookup"><span data-stu-id="e87ee-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="e87ee-126">Restreindre les appels sortants de conférence audio</span><span class="sxs-lookup"><span data-stu-id="e87ee-126">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="e87ee-127">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="e87ee-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="e87ee-128">Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="e87ee-128">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="e87ee-129">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e87ee-129">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="e87ee-130">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e87ee-130">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="e87ee-131">Sous **Autorisation d’appel sortant de réunions**, sélectionnez l’option de restriction d’appel sortant souhaitée.</span><span class="sxs-lookup"><span data-stu-id="e87ee-131">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="e87ee-132">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e87ee-132">Click **Save**.</span></span> 

<span data-ttu-id="e87ee-133">![Icône affichant le logo Skype Entreprise](media/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="e87ee-133">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.    <span data-ttu-id="e87ee-134">Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation de gauche, sélectionnez utilisateurs de l' **audioconférence**  >  **Users**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="e87ee-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.    <span data-ttu-id="e87ee-135">Dans le volet Action, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e87ee-135">In the Action pane, click **Edit**.</span></span>

3.    <span data-ttu-id="e87ee-136">Sous **Restrictions de numérotation des réunions de cet utilisateur**, sélectionnez l’option de restriction d’appel sortant souhaitée.</span><span class="sxs-lookup"><span data-stu-id="e87ee-136">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Les restrictions aux options de numérotation](media/restrictions-to-dial-outs.png)

5. <span data-ttu-id="e87ee-138">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e87ee-138">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="e87ee-139">**Utiliser PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e87ee-139">**Using PowerShell**</span></span>

<span data-ttu-id="e87ee-140">Les restrictions des appels sortants sont contrôlées par une stratégie unique appelée OnlineDialOutPolicy qui possède un attribut de restriction pour chacun.</span><span class="sxs-lookup"><span data-stu-id="e87ee-140">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="e87ee-141">La stratégie ne peut pas être personnalisée, mais il existe des instances de stratégie prédéfinies pour chaque combinaison de paramètres.</span><span class="sxs-lookup"><span data-stu-id="e87ee-141">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="e87ee-142">Vous pouvez utiliser la cmdlet Get-CSOnlineDialOutPolicy pour afficher les stratégies d'appels sortants et les affecter aux utilisateurs à l'aide de la cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="e87ee-142">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="e87ee-143">(Veuillez noter que la cmdlet Grant ne contient pas le mot « Online » en tant que cmdlet Get.)</span><span class="sxs-lookup"><span data-stu-id="e87ee-143">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="e87ee-144">Le tableau suivant fournit une vue d’ensemble de chaque stratégie.</span><span class="sxs-lookup"><span data-stu-id="e87ee-144">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e87ee-145">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="e87ee-145">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="e87ee-146">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur peut également passer des appels vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="e87ee-146">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="e87ee-147">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="e87ee-147">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="e87ee-148">L'utilisateur de la conférence peut uniquement composer des numéros nationaux et cet utilisateur peut passer des appels vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="e87ee-148">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e87ee-149">Identité = 'tag : DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="e87ee-149">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="e87ee-150">L'utilisateur de la conférence ne peut effectuer aucun appel sortant. Cet utilisateur peut effectuer des appels sortants vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="e87ee-150">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e87ee-151">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="e87ee-151">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="e87ee-152">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux, et cet utilisateur ne peut passer que des appels sortants vers un numéro RTC national.</span><span class="sxs-lookup"><span data-stu-id="e87ee-152">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="e87ee-153">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="e87ee-153">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="e87ee-154">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur ne peut pas effectuer d'appels sortants vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="e87ee-154">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e87ee-155">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="e87ee-155">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="e87ee-156">L'utilisateur de la conférence ne peut appeler que des numéros nationaux, et cet utilisateur ne peut émettre que des appels vers des numéros RTC nationaux.</span><span class="sxs-lookup"><span data-stu-id="e87ee-156">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="e87ee-157">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="e87ee-157">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="e87ee-158">L'utilisateur de la conférence peut uniquement composer des numéros nationaux, et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="e87ee-158">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e87ee-159">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="e87ee-159">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="e87ee-160">L'utilisateur de la conférence ne peut effectuer aucun appel sortant et cet utilisateur peut uniquement effectuer des appels sortants vers des numéros RTC nationaux.</span><span class="sxs-lookup"><span data-stu-id="e87ee-160">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="e87ee-161">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="e87ee-161">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="e87ee-162">L'utilisateur de la conférence ne peut effectuer aucun appel sortant et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="e87ee-162">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e87ee-163">Identity = 'tag : DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="e87ee-163">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="e87ee-164">Dans la Conférence, l’utilisateur peut uniquement appeler les pays et régions d’un pays ou d’une région, et cet utilisateur peut passer des appels sortants vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="e87ee-164">User in the conference can only dial out to Zone A countries and regions, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e87ee-165">Identity = 'tag : DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="e87ee-165">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="e87ee-166">Dans la Conférence, l’utilisateur peut uniquement appeler des pays et des régions, et cet utilisateur ne peut émettre des appels sortants que vers son numéro RTC local.</span><span class="sxs-lookup"><span data-stu-id="e87ee-166">User in the conference can only dial out to Zone A countries and regions, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="e87ee-167">Identity = 'tag : DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="e87ee-167">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="e87ee-168">Dans la Conférence, l’utilisateur peut uniquement appeler des pays et des régions, et cet utilisateur ne peut pas passer d’appels sortants au numéro RTC en plus des numéros d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e87ee-168">User in the conference can only dial out to Zone A countries and regions, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
