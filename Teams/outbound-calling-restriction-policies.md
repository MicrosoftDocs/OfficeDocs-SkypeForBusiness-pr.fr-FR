---
title: Restrictions relatives aux appels sortants - Audioconférence et & appels PSTN
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
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908653"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="c981f-103">Stratégies de restriction des appels sortants pour l’audioconférence et les appels PSTN des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c981f-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="c981f-104">En tant qu'administrateur, vous pouvez utiliser les contrôles d'appels sortants pour restreindre le type de conférence audio et d'appels RTC d'utilisateur final pouvant être effectués par les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c981f-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="c981f-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span><span class="sxs-lookup"><span data-stu-id="c981f-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="c981f-107">Contrôle</span><span class="sxs-lookup"><span data-stu-id="c981f-107">Control</span></span>|<span data-ttu-id="c981f-108">Description</span><span class="sxs-lookup"><span data-stu-id="c981f-108">Description</span></span>|<span data-ttu-id="c981f-109">Options de contrôle</span><span class="sxs-lookup"><span data-stu-id="c981f-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c981f-110">Appels RTC de conférence audio</span><span class="sxs-lookup"><span data-stu-id="c981f-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="c981f-111">Limite le type de sortie</span><span class="sxs-lookup"><span data-stu-id="c981f-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="c981f-112">les appels autorisés de l'intérieur</span><span class="sxs-lookup"><span data-stu-id="c981f-112">calls that are allowed from within</span></span> </br><span data-ttu-id="c981f-113">réunions organisées par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c981f-113">meetings organized by a user.</span></span>|<span data-ttu-id="c981f-114">N’importe quelle destination (par défaut)</span><span class="sxs-lookup"><span data-stu-id="c981f-114">Any destination (default)</span></span></br><span data-ttu-id="c981f-115">Dans le même pays ou la même région que l’organisateur</span><span class="sxs-lookup"><span data-stu-id="c981f-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="c981f-116">[Zone A pays ou régions](audio-conferencing-zones.md) uniquement</span><span class="sxs-lookup"><span data-stu-id="c981f-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="c981f-117">Ne pas autoriser</span><span class="sxs-lookup"><span data-stu-id="c981f-117">Don't allow</span></span>|
|<span data-ttu-id="c981f-118">Appels RTC utilisateur final</span><span class="sxs-lookup"><span data-stu-id="c981f-118">End user PSTN calls</span></span>|<span data-ttu-id="c981f-119">Limite le type d'appels</span><span class="sxs-lookup"><span data-stu-id="c981f-119">Restricts the type of calls</span></span> </br><span data-ttu-id="c981f-120">qui peuvent être effectués par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c981f-120">that can be made by a user.</span></span>|<span data-ttu-id="c981f-121">International et national (par défaut)</span><span class="sxs-lookup"><span data-stu-id="c981f-121">International and Domestic (default)</span></span></br><span data-ttu-id="c981f-122">Nationaux</span><span class="sxs-lookup"><span data-stu-id="c981f-122">Domestic</span></span></br><span data-ttu-id="c981f-123">Aucun</span><span class="sxs-lookup"><span data-stu-id="c981f-123">None</span></span>|

<span data-ttu-id="c981f-124">Pour savoir quels pays et quelles régions sont considérés comme zone A, consultez les zones pays et [région pour audioconférence.](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="c981f-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="c981f-125">Un appel est considéré comme national si le numéro composé se trouve dans le même pays que celui où Microsoft 365 ou Office 365 a été créé pour l’organisateur de la réunion (en cas d’audioconférence) ou l’utilisateur final (en cas d’appels PSTN de l’utilisateur final).</span><span class="sxs-lookup"><span data-stu-id="c981f-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="c981f-126">Restreindre les appels sortants de conférence audio</span><span class="sxs-lookup"><span data-stu-id="c981f-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="c981f-127">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="c981f-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c981f-128">Dans le navigateur de gauche, **cliquez** sur Utilisateurs, puis sur le nom d’affichage de l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="c981f-128">In the left navigation, click **Users**, and then click the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="c981f-129">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="c981f-129">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="c981f-130">Sous **Appel sortant de réunions,** sélectionnez l’option de restriction d’appel sortant de votre choix.</span><span class="sxs-lookup"><span data-stu-id="c981f-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="c981f-131">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c981f-131">Click **Save**.</span></span> 

<span data-ttu-id="c981f-132">![Icône affichant le logo Skype Entreprise](media/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="c981f-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="c981f-133">Dans le **Centre d’administration Skype** Entreprise, dans le panneau de navigation de gauche, sélectionnez Utilisateurs de l’audioconférence, puis sélectionnez l’utilisateur dans la liste des   >  utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="c981f-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c981f-134">Dans le volet Action, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="c981f-134">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="c981f-135">Sous **Restrictions de numérotation des réunions de cet utilisateur**, sélectionnez l’option de restriction d’appel sortant souhaitée.</span><span class="sxs-lookup"><span data-stu-id="c981f-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![Les restrictions aux options de numérotation](media/restrictions-to-dial-outs.png)
      

4. <span data-ttu-id="c981f-137">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c981f-137">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="c981f-138">**Utiliser PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c981f-138">**Using PowerShell**</span></span>

<span data-ttu-id="c981f-139">Les restrictions des appels sortants sont contrôlées par une stratégie unique appelée OnlineDialOutPolicy qui possède un attribut de restriction pour chacun.</span><span class="sxs-lookup"><span data-stu-id="c981f-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="c981f-140">La stratégie ne peut pas être personnalisée, mais il existe des instances de stratégie prédéfinies pour chaque combinaison de paramètres.</span><span class="sxs-lookup"><span data-stu-id="c981f-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="c981f-141">Vous pouvez utiliser la cmdlet Get-CSOnlineDialOutPolicy pour afficher les stratégies d'appels sortants et les affecter aux utilisateurs à l'aide de la cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="c981f-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="c981f-142">(Notez que la cmdlet Grant ne contient pas le mot « En ligne » comme le fait la cmdlet Get.)</span><span class="sxs-lookup"><span data-stu-id="c981f-142">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="c981f-143">Le tableau suivant fournit une vue d’ensemble de chaque stratégie.</span><span class="sxs-lookup"><span data-stu-id="c981f-143">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c981f-144">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="c981f-144">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="c981f-145">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur peut également passer des appels vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="c981f-145">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="c981f-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="c981f-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="c981f-147">L'utilisateur de la conférence peut uniquement composer des numéros nationaux et cet utilisateur peut passer des appels vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="c981f-147">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="c981f-148">Identité = 'tag : DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="c981f-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="c981f-149">L'utilisateur de la conférence ne peut effectuer aucun appel sortant. Cet utilisateur peut effectuer des appels sortants vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="c981f-149">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="c981f-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="c981f-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="c981f-151">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux, et cet utilisateur ne peut passer que des appels sortants vers un numéro RTC national.</span><span class="sxs-lookup"><span data-stu-id="c981f-151">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="c981f-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="c981f-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="c981f-153">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur ne peut pas effectuer d'appels sortants vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="c981f-153">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="c981f-154">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="c981f-154">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="c981f-155">L'utilisateur de la conférence ne peut appeler que des numéros nationaux, et cet utilisateur ne peut émettre que des appels vers des numéros RTC nationaux.</span><span class="sxs-lookup"><span data-stu-id="c981f-155">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="c981f-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="c981f-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="c981f-157">L'utilisateur de la conférence peut uniquement composer des numéros nationaux, et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="c981f-157">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="c981f-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="c981f-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="c981f-159">L'utilisateur de la conférence ne peut effectuer aucun appel sortant et cet utilisateur peut uniquement effectuer des appels sortants vers des numéros RTC nationaux.</span><span class="sxs-lookup"><span data-stu-id="c981f-159">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="c981f-160">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="c981f-160">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="c981f-161">L'utilisateur de la conférence ne peut effectuer aucun appel sortant et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="c981f-161">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="c981f-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="c981f-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="c981f-163">Les utilisateurs de la conférence peuvent uniquement appeler les pays et régions de la zone [A](audio-conferencing-zones.md)et effectuer des appels sortants vers des numéros nationaux et internationaux.</span><span class="sxs-lookup"><span data-stu-id="c981f-163">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="c981f-164">Identity='tag:DialoutCPCZoneAPSTN Tagsstic'</span><span class="sxs-lookup"><span data-stu-id="c981f-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="c981f-165">Les utilisateurs de la conférence peuvent uniquement appeler les pays et régions de la zone [A](audio-conferencing-zones.md)et uniquement effectuer des appels sortants vers un numéro PSTN national.</span><span class="sxs-lookup"><span data-stu-id="c981f-165">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="c981f-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="c981f-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="c981f-167">Un utilisateur de la conférence peut uniquement appeler les pays et régions de la zone [A](audio-conferencing-zones.md)et ne peut pas effectuer d’appels sortants vers un numéro PSTN en plus des numéros d’urgence.</span><span class="sxs-lookup"><span data-stu-id="c981f-167">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
