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
description: Les administrateurs peuvent contrôler le type d’audioconférence et d’appels PSTN d’utilisateur final qui peuvent être effectués par les utilisateurs.
ms.openlocfilehash: 86622b493fbb8d31f98f600acb7158afc82e15e5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526727"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="53abb-103">Stratégies de restriction des appels sortants pour l’audioconférence et les appels RTC des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="53abb-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="53abb-104">En tant qu’administrateur, vous pouvez utiliser les contrôles d’appel sortant pour restreindre le type d’audioconférence et les appels de réseau téléphonique public commuté (PSTN) d’utilisateurs finaux qui peuvent être effectués par les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="53abb-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end-user Public Switched Telephone Network (PSTN) calls that can be made by users in your organization.</span></span>

<span data-ttu-id="53abb-105">Les contrôles d’appel sortant peuvent être appliqués pour chaque utilisateur ou client et fournir les deux contrôles suivants afin de limiter de manière indépendante chaque type d’appels sortants.</span><span class="sxs-lookup"><span data-stu-id="53abb-105">Outbound call controls can be applied on a per-user basis or on a tenant basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="53abb-106">Par défaut, les deux contrôles sont définis pour autoriser les appels sortants internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="53abb-106">By default, both controls are set to allow international and domestic outbound calls.</span></span>

|<span data-ttu-id="53abb-107">Contrôle</span><span class="sxs-lookup"><span data-stu-id="53abb-107">Control</span></span>|<span data-ttu-id="53abb-108">Description</span><span class="sxs-lookup"><span data-stu-id="53abb-108">Description</span></span>|<span data-ttu-id="53abb-109">Options de contrôle</span><span class="sxs-lookup"><span data-stu-id="53abb-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="53abb-110">Appels RTC de conférence audio</span><span class="sxs-lookup"><span data-stu-id="53abb-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="53abb-111">Limite le type de sortie</span><span class="sxs-lookup"><span data-stu-id="53abb-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="53abb-112">les appels autorisés de l'intérieur</span><span class="sxs-lookup"><span data-stu-id="53abb-112">calls that are allowed from within</span></span> </br><span data-ttu-id="53abb-113">réunions organisées par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="53abb-113">meetings organized by a user.</span></span>|<span data-ttu-id="53abb-114">N’importe quelle destination (par défaut)</span><span class="sxs-lookup"><span data-stu-id="53abb-114">Any destination (default)</span></span></br><span data-ttu-id="53abb-115">Dans le même pays ou la même région que l’organisateur</span><span class="sxs-lookup"><span data-stu-id="53abb-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="53abb-116">[Zone A pays ou régions](audio-conferencing-zones.md) uniquement</span><span class="sxs-lookup"><span data-stu-id="53abb-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="53abb-117">Ne pas autoriser</span><span class="sxs-lookup"><span data-stu-id="53abb-117">Don't allow</span></span>|
|<span data-ttu-id="53abb-118">Appels PSTN d’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="53abb-118">End-user PSTN calls</span></span>|<span data-ttu-id="53abb-119">Limite le type d'appels</span><span class="sxs-lookup"><span data-stu-id="53abb-119">Restricts the type of calls</span></span> </br><span data-ttu-id="53abb-120">qui peuvent être effectués par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="53abb-120">that can be made by a user.</span></span>|<span data-ttu-id="53abb-121">International et national (par défaut)</span><span class="sxs-lookup"><span data-stu-id="53abb-121">International and Domestic (default)</span></span></br><span data-ttu-id="53abb-122">Nationaux</span><span class="sxs-lookup"><span data-stu-id="53abb-122">Domestic</span></span></br><span data-ttu-id="53abb-123">Aucun</span><span class="sxs-lookup"><span data-stu-id="53abb-123">None</span></span>|

<span data-ttu-id="53abb-124">Pour savoir quels pays et quelles régions sont considérés comme zone A, consultez les zones pays et région pour [l’audioconférence.](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="53abb-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="53abb-125">Un appel est considéré comme national si le numéro composé se trouve dans le pays dans lequel Microsoft 365 ou Office 365 a été définie pour l’organisateur de la réunion (en cas d’audioconférence) ou l’utilisateur final (en cas d’appels PSTN de l’utilisateur final).</span><span class="sxs-lookup"><span data-stu-id="53abb-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="53abb-126">Restreindre les appels sortants de conférence audio</span><span class="sxs-lookup"><span data-stu-id="53abb-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="53abb-127">![Logo Microsoft Teams’aide ](media/teams-logo-30x30.png) **du Centre d’Microsoft Teams’administration**</span><span class="sxs-lookup"><span data-stu-id="53abb-127">![the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="53abb-128">Dans la barre de navigation de gauche, **sélectionnez** Utilisateurs, puis le nom d’affichage de l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="53abb-128">In the left navigation, select **Users**, and then select the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="53abb-129">En plus de **l’audioconférence,** sélectionnez **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="53abb-129">Next to **Audio Conferencing**, select **Edit**.</span></span>

4. <span data-ttu-id="53abb-130">Sous **Appel sortant de réunions,** sélectionnez l’option de restriction d’appel sortant de votre choix.</span><span class="sxs-lookup"><span data-stu-id="53abb-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="53abb-131">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="53abb-131">Select **Save**.</span></span>

<span data-ttu-id="53abb-132">![Icône affichant le logo Skype Entreprise](media/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="53abb-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="53abb-133">Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, sélectionnez Utilisateurs de l’audioconférence, puis sélectionnez l’utilisateur dans la liste des   >  utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="53abb-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="53abb-134">Dans le volet Action, sélectionnez **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="53abb-134">In the Action pane, select **Edit**.</span></span>

3.  <span data-ttu-id="53abb-135">Sous **Restrictions de numérotation des réunions de cet utilisateur**, sélectionnez l’option de restriction d’appel sortant souhaitée.</span><span class="sxs-lookup"><span data-stu-id="53abb-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![Les restrictions aux options de numérotation](media/restrictions-to-dial-outs.png)

4. <span data-ttu-id="53abb-137">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="53abb-137">Select **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="53abb-138">**Utiliser PowerShell**</span><span class="sxs-lookup"><span data-stu-id="53abb-138">**Using PowerShell**</span></span>

<span data-ttu-id="53abb-139">Les restrictions d’appels sortants sont contrôlées par une stratégie unique appelée OnlineDialOutPolicy, qui possède un attribut de restriction pour chacune d’elles.</span><span class="sxs-lookup"><span data-stu-id="53abb-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy, which has a restriction attribute for each.</span></span> <span data-ttu-id="53abb-140">La stratégie ne peut pas être personnalisée, mais il existe des instances de stratégie prédéfinies pour chaque combinaison de paramètres.</span><span class="sxs-lookup"><span data-stu-id="53abb-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span>

<span data-ttu-id="53abb-141">Vous pouvez utiliser l'Get-CSOnlineDialOutPolicy cmdlet pour afficher les stratégies d’appels sortants et utiliser la commande suivante pour la configuration.</span><span class="sxs-lookup"><span data-stu-id="53abb-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and use the following command for the setup.</span></span>

<span data-ttu-id="53abb-142">**Définissez la stratégie au niveau utilisateur avec l’cmdlet suivante.**</span><span class="sxs-lookup"><span data-stu-id="53abb-142">**Set the policy on a per-user level with the following cmdlet**.</span></span> <span data-ttu-id="53abb-143">(La cmdlet Grant ne contient pas le mot « En ligne » comme le fait la cmdlet Get.)</span><span class="sxs-lookup"><span data-stu-id="53abb-143">(The Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span>

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

<span data-ttu-id="53abb-144">**Définissez la stratégie au niveau du client avec l’cmdlet suivante.**</span><span class="sxs-lookup"><span data-stu-id="53abb-144">**Set the policy on the tenant level with the following cmdlet**.</span></span>

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

<span data-ttu-id="53abb-145">Tous les utilisateurs du client qui n’ont pas de stratégie de numérotation seront affectés à cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="53abb-145">All users of the tenant who don't have any dialout policy assigned will get this policy.</span></span> <span data-ttu-id="53abb-146">Les autres utilisateurs demeurent avec leur stratégie actuelle.</span><span class="sxs-lookup"><span data-stu-id="53abb-146">Other users remain with their current policy.</span></span>

<span data-ttu-id="53abb-147">Le tableau suivant fournit une vue d’ensemble de chaque stratégie.</span><span class="sxs-lookup"><span data-stu-id="53abb-147">The following table provides an overview of each policy.</span></span>

|<span data-ttu-id="53abb-148">Cmdlet PowerShell</span><span class="sxs-lookup"><span data-stu-id="53abb-148">PowerShell cmdlet</span></span>|<span data-ttu-id="53abb-149">Description</span><span class="sxs-lookup"><span data-stu-id="53abb-149">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="53abb-150">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="53abb-150">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="53abb-151">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur peut également passer des appels vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="53abb-151">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="53abb-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="53abb-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="53abb-153">L'utilisateur de la conférence peut uniquement composer des numéros nationaux et cet utilisateur peut passer des appels vers des numéros internationaux et nationaux.</span><span class="sxs-lookup"><span data-stu-id="53abb-153">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="53abb-154">Identité = 'tag : DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="53abb-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="53abb-155">Les utilisateurs de la conférence ne peuvent pas composer l’appel sortant. Cet utilisateur peut effectuer des appels sortants vers des numéros nationaux et internationaux.</span><span class="sxs-lookup"><span data-stu-id="53abb-155">User in the conference can't dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="53abb-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="53abb-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="53abb-157">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux, et cet utilisateur ne peut passer que des appels sortants vers un numéro RTC national.</span><span class="sxs-lookup"><span data-stu-id="53abb-157">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="53abb-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="53abb-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="53abb-159">L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur ne peut pas effectuer d'appels sortants vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="53abb-159">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="53abb-160">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="53abb-160">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="53abb-161">L'utilisateur de la conférence ne peut appeler que des numéros nationaux, et cet utilisateur ne peut émettre que des appels vers des numéros RTC nationaux.</span><span class="sxs-lookup"><span data-stu-id="53abb-161">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="53abb-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="53abb-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="53abb-163">L'utilisateur de la conférence peut uniquement composer des numéros nationaux, et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.</span><span class="sxs-lookup"><span data-stu-id="53abb-163">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="53abb-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="53abb-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="53abb-165">Les utilisateurs de la conférence ne peuvent pas composer l’appel sortant, et il ne peut effectuer un appel sortant que vers des numéros PSTN nationaux.</span><span class="sxs-lookup"><span data-stu-id="53abb-165">User in the conference can't dial out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="53abb-166">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="53abb-166">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="53abb-167">Les utilisateurs de la conférence ne peuvent pas appeler et ne peuvent pas appeler un numéro PSTN en plus des numéros d’urgence.</span><span class="sxs-lookup"><span data-stu-id="53abb-167">User in the conference can't dial out, and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="53abb-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="53abb-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="53abb-169">Les utilisateurs de la conférence peuvent uniquement appeler les pays et régions de la zone [A](audio-conferencing-zones.md)et effectuer des appels sortants vers des numéros nationaux et internationaux.</span><span class="sxs-lookup"><span data-stu-id="53abb-169">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="53abb-170">Identity='tag:DialoutCPCZoneAPSTN Tagsstic'</span><span class="sxs-lookup"><span data-stu-id="53abb-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="53abb-171">Les utilisateurs de la conférence peuvent uniquement appeler les pays et régions de la zone [A](audio-conferencing-zones.md)et uniquement effectuer des appels sortants vers un numéro PSTN national.</span><span class="sxs-lookup"><span data-stu-id="53abb-171">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="53abb-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="53abb-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="53abb-173">Un utilisateur de la conférence peut uniquement appeler les pays et régions de la zone [A](audio-conferencing-zones.md)et ne peut pas effectuer d’appels sortants vers un numéro PSTN en plus des numéros d’urgence.</span><span class="sxs-lookup"><span data-stu-id="53abb-173">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
