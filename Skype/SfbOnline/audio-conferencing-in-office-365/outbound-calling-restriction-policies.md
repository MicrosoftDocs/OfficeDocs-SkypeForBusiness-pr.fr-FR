---
title: Stratégies de restriction des appels sortants pour l’audioconférence et les appels RTC des utilisateurs
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler le type de conférence audio et d'appels RTC d’utilisateur final pouvant être effectuées par les utilisateurs.
ms.openlocfilehash: fd1a3b770debfcc6aa048d150b6536c94db4f9ce
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856880"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="915a7-103">Stratégies de restriction des appels sortants pour l’audioconférence et les appels RTC des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="915a7-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="915a7-104">En tant qu'administrateur, vous pouvez utiliser les contrôles d'appels sortants pour restreindre le type de conférence audio et d'appels RTC d'utilisateur final pouvant être effectués par les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="915a7-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="915a7-105">Les contrôles d’appel sortant peuvent être appliqués par utilisateur et fournissent les deux contrôles suivants pour limiter indépendamment chaque type d’appels sortants.</span><span class="sxs-lookup"><span data-stu-id="915a7-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="915a7-106">Par défaut, les deux contrôles sont définis pour autoriser les appels sortants internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="915a7-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="915a7-107">Contrôle</span><span class="sxs-lookup"><span data-stu-id="915a7-107">CONTROL</span></span>|<span data-ttu-id="915a7-108">Description</span><span class="sxs-lookup"><span data-stu-id="915a7-108">Description</span></span>|<span data-ttu-id="915a7-109">Options de contrôle</span><span class="sxs-lookup"><span data-stu-id="915a7-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="915a7-110">Appels RTC de conférence audio</span><span class="sxs-lookup"><span data-stu-id="915a7-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="915a7-111">Limite le type de sortie</span><span class="sxs-lookup"><span data-stu-id="915a7-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="915a7-112">les appels autorisés de l'intérieur</span><span class="sxs-lookup"><span data-stu-id="915a7-112">calls that are allowed from within</span></span> </br><span data-ttu-id="915a7-113">réunions organisées par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="915a7-113">meetings organized by a user.</span></span>|<span data-ttu-id="915a7-114">International et national (par défaut)</span><span class="sxs-lookup"><span data-stu-id="915a7-114">International and Domestic (default)</span></span></br><span data-ttu-id="915a7-115">National</span><span class="sxs-lookup"><span data-stu-id="915a7-115">Domestic</span></span></br><span data-ttu-id="915a7-116">Aucun</span><span class="sxs-lookup"><span data-stu-id="915a7-116">None</span></span>|
|<span data-ttu-id="915a7-117">Appels RTC utilisateur final</span><span class="sxs-lookup"><span data-stu-id="915a7-117">End user PSTN calls</span></span>|<span data-ttu-id="915a7-118">Limite le type d'appels</span><span class="sxs-lookup"><span data-stu-id="915a7-118">Restricts the type of calls</span></span> </br><span data-ttu-id="915a7-119">qui peuvent être effectués par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="915a7-119">that can be made by a user.</span></span>|<span data-ttu-id="915a7-120">International et national (par défaut)</span><span class="sxs-lookup"><span data-stu-id="915a7-120">International and Domestic (default)</span></span></br><span data-ttu-id="915a7-121">National</span><span class="sxs-lookup"><span data-stu-id="915a7-121">Domestic</span></span></br><span data-ttu-id="915a7-122">Aucun</span><span class="sxs-lookup"><span data-stu-id="915a7-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="915a7-123">Un appel est déterminé comme étant national si le numéro de téléphone appelé se trouve dans le même pays que celui qui a été défini dans Office 365 pour l’organisateur de la réunion (dans le cas d'une audioconférence) ou de l’utilisateur final (dans le cas d'appels RTC d'utilisateur final).</span><span class="sxs-lookup"><span data-stu-id="915a7-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="915a7-124">Restreindre les appels sortants de conférence audio</span><span class="sxs-lookup"><span data-stu-id="915a7-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="915a7-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="915a7-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="915a7-126">Dans la navigation de gauche, cliquez sur **Utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="915a7-126">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="915a7-127">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="915a7-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="915a7-128">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="915a7-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="915a7-129">Sous **Autorisation d’appel sortant de réunions**, sélectionnez l’option de restriction d’appel sortant souhaitée.</span><span class="sxs-lookup"><span data-stu-id="915a7-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="915a7-130">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="915a7-130">Click **Save**.</span></span> 

<span data-ttu-id="915a7-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilisation du centre d'administration de Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="915a7-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1.  <span data-ttu-id="915a7-132">Dans **centre d’administration Skype Entreprise**, dans la navigation de gauche, accédez à la **Conférence Audio** > **Utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="915a7-132">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Dial-in users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="915a7-133">Dans le volet Action, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="915a7-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="915a7-134">Sous **Restrictions de numérotation des réunions de cet utilisateur**, sélectionnez l’option de restriction d’appel sortant souhaitée.</span><span class="sxs-lookup"><span data-stu-id="915a7-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Les restrictions aux options de numérotation](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="915a7-136">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="915a7-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="915a7-137">**À l’aide de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="915a7-137">\*\*\*\* Using Windows PowerShell</span></span>

<span data-ttu-id="915a7-138">Les restrictions des appels sortants sont contrôlées par une stratégie unique appelée OnlineDialOutPolicy qui possède un attribut de restriction pour chacun.</span><span class="sxs-lookup"><span data-stu-id="915a7-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="915a7-139">La stratégie ne peut pas être personnalisée, mais il existe des instances de stratégie prédéfinies pour chaque combinaison de paramètres.</span><span class="sxs-lookup"><span data-stu-id="915a7-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="915a7-140">Vous pouvez utiliser la cmdlet Get-CSOnlineDialOutPolicy pour afficher les stratégies d'appels sortants et les affecter aux utilisateurs à l'aide de la cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="915a7-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="915a7-141">(Notez que l’applet de commande Grant ne contient pas le mot "Connecté" comme l’applet de commande Get.)</span><span class="sxs-lookup"><span data-stu-id="915a7-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="915a7-142">Le tableau suivant fournit une vue d’ensemble de chaque stratégie.</span><span class="sxs-lookup"><span data-stu-id="915a7-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="915a7-143">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="915a7-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="915a7-144">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur peut également passer des appels vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="915a7-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="915a7-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="915a7-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="915a7-146">L'utilisateur de la conférence peut uniquement composer des numéros nationaux et cet utilisateur peut passer des appels vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="915a7-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="915a7-147">Identité = 'tag : DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="915a7-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="915a7-148">L'utilisateur de la conférence ne peut effectuer aucun appel sortant. Cet utilisateur peut effectuer des appels sortants vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="915a7-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="915a7-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="915a7-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="915a7-150">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux, et cet utilisateur ne peut passer que des appels sortants vers un numéro RTC national.</span><span class="sxs-lookup"><span data-stu-id="915a7-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="915a7-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="915a7-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="915a7-152">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur ne peut pas effectuer d'appels sortants vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="915a7-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="915a7-153">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="915a7-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="915a7-154">L'utilisateur de la conférence ne peut appeler que des numéros nationaux, et cet utilisateur ne peut émettre que des appels vers des numéros RTC nationaux.</span><span class="sxs-lookup"><span data-stu-id="915a7-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="915a7-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="915a7-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="915a7-156">L'utilisateur de la conférence peut uniquement composer des numéros nationaux, et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="915a7-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="915a7-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="915a7-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="915a7-158">L'utilisateur de la conférence ne peut effectuer aucun appel sortant et cet utilisateur peut uniquement effectuer des appels sortants vers des numéros RTC nationaux.</span><span class="sxs-lookup"><span data-stu-id="915a7-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="915a7-159">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="915a7-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="915a7-160">L'utilisateur de la conférence ne peut effectuer aucun appel sortant et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="915a7-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
