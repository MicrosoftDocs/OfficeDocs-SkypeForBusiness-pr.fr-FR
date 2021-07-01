---
title: Conférence sur réseau pour l’audioconférence
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Les suivantes décrivent le réseau pour l’audioconférence.
ms.openlocfilehash: b7851bd2457debe8ee0de3144e24a15edb521222
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230561"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="6b98a-103">Conférence sur réseau pour l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="6b98a-103">On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="6b98a-104">Les conférences sur réseau permettent aux organisations d’envoyer des appels d’audioconférence entrants et sortants à des numéros de connexion Microsoft par le biais d’un routage direct.</span><span class="sxs-lookup"><span data-stu-id="6b98a-104">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="6b98a-105">Cette fonctionnalité n’est pas destinée à étendre la prise en charge de l’audioconférence à des numéros d’accès tiers.</span><span class="sxs-lookup"><span data-stu-id="6b98a-105">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="6b98a-106">La fonction de conférence sur réseau n’est pas prise en charge si elle est utilisée pour router les appels entrants vers le service d’audioconférence par le biais de numéros de téléphone tiers ou d’appels sortants vers le réseau PSTN à partir du pont de conférence audio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6b98a-106">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audio Conferencing Bridge.</span></span> 

<span data-ttu-id="6b98a-107">Cet article décrit les conditions préalables et les étapes de configuration requises pour activer la conférence sur réseau pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6b98a-107">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b98a-108">La conférence sur réseau ne doit PAS être déployée avec n’importe quel équipement téléphonique en Inde.</span><span class="sxs-lookup"><span data-stu-id="6b98a-108">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="6b98a-109">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="6b98a-109">Prerequisites</span></span>

<span data-ttu-id="6b98a-110">Avant de configurer la conférence sur réseau, assurez-vous que votre organisation répond aux conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="6b98a-110">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="6b98a-111">Assurez-vous que tous les utilisateurs de votre organisation qui sont activés ou seront activés pour l’audioconférence utilisent des Teams pour toutes les réunions.</span><span class="sxs-lookup"><span data-stu-id="6b98a-111">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="6b98a-112">Le routage des appels d’audioconférence entrants et sortants via la conférence réseau est pris en charge uniquement pour Teams réunions.</span><span class="sxs-lookup"><span data-stu-id="6b98a-112">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="6b98a-113">Attribuez des licences d’audioconférence à tous les utilisateurs qui utiliseront la conférence sur réseau.</span><span class="sxs-lookup"><span data-stu-id="6b98a-113">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="6b98a-114">Configurer le service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="6b98a-114">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="6b98a-115">Pour plus d’informations, [consultez Configurer l’audioconférence pour Microsoft Teams.](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="6b98a-115">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="6b98a-116">Configurer votre contrôleur de session border controller (SBC) pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="6b98a-116">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="6b98a-117">Pour plus d’informations, [voir Planifier le routage direct](direct-routing-plan.md) et Configurer le [routage direct.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="6b98a-117">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="6b98a-118">Si vous configurationnez le routage direct uniquement dans le cadre de l’audioconférence, vous devez seulement effectuer l'« étape 1 : Connecter SBC » pour la conférence sur réseau.</span><span class="sxs-lookup"><span data-stu-id="6b98a-118">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="6b98a-119">Activer le routage des appels d’accès vers l’audioconférence Microsoft par le biais d’un routage direct</span><span class="sxs-lookup"><span data-stu-id="6b98a-119">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="6b98a-120">Pour router les appels d’accès effectués par vos utilisateurs locaux vers le service d’audioconférence via un routage direct, vous devez configurer les règles de routage appropriées pour vos SBCs et vos Exchange privés (PBX).</span><span class="sxs-lookup"><span data-stu-id="6b98a-120">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="6b98a-121">Vous devez configurer l’équipement téléphonique de vos sites pour router les appels vers n’importe quel numéro de service du pont de conférence de votre organisation via une ligne de routage direct.</span><span class="sxs-lookup"><span data-stu-id="6b98a-121">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="6b98a-122">Vous trouverez les numéros de service dans le Centre d’administration Teams sous Réunions **-> Ponts** de conférence ou à l’aide de l’cmdlet PowerShell Skype Entreprise Online Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="6b98a-122">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="6b98a-123">Pour plus d’informations, consultez la liste des numéros [d’audioconférence Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="6b98a-123">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6b98a-124">Cette fonctionnalité n’est pas disponible pour les utilisateurs titulaires d’une licence d’audioconférence à la minute.</span><span class="sxs-lookup"><span data-stu-id="6b98a-124">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="6b98a-125">Activer le routage des appels Teams des appels sortants d’une réunion via un routage direct</span><span class="sxs-lookup"><span data-stu-id="6b98a-125">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="6b98a-126">Teams appels sortants de réunion sont lancés à partir d’une réunion de votre organisation vers des numéros PSTN, y compris les appels de m’appeler et les appels pour amener de nouveaux participants à une réunion.</span><span class="sxs-lookup"><span data-stu-id="6b98a-126">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="6b98a-127">Pour activer Teams routage d’appels sortants de réunion via un routage direct vers des utilisateurs du réseau, vous devez créer et affecter une stratégie de routage audioconférence nommée « OnlineAudioConferencingRoutingPolicy ».</span><span class="sxs-lookup"><span data-stu-id="6b98a-127">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="6b98a-128">La stratégie OnlineAudioConferencingRoutingPolicy équivaut à la stratégie CsOnlineVoiceRoutingPolicy pour les appels PSTN 1:1 via un routage direct.</span><span class="sxs-lookup"><span data-stu-id="6b98a-128">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="6b98a-129">La stratégie OnlineAudioConferencingRoutingPolicy peut être gérée à l’aide des cmdlets suivantes :</span><span class="sxs-lookup"><span data-stu-id="6b98a-129">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="6b98a-130">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="6b98a-130">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="6b98a-131">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="6b98a-131">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="6b98a-132">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="6b98a-132">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="6b98a-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="6b98a-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="6b98a-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="6b98a-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="6b98a-135">Pour plus d’informations sur le routage pour le routage direct, voir [Configurer le routage vocal pour le routage direct.](direct-routing-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="6b98a-135">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="6b98a-136">Pour activer le routage des appels sortants de réunion via un routage direct, vous devez :</span><span class="sxs-lookup"><span data-stu-id="6b98a-136">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="6b98a-137">Configurer les stratégies de routage de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="6b98a-137">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="6b98a-138">Configurer le routage sur l’équipement téléphonique de votre organisation</span><span class="sxs-lookup"><span data-stu-id="6b98a-138">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="6b98a-139">(Facultatif) Configurer un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="6b98a-139">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="6b98a-140">Les appels sortants des Teams sont issus du numéro de service par défaut sur le pont de conférence.</span><span class="sxs-lookup"><span data-stu-id="6b98a-140">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="6b98a-141">Pour plus d’informations sur le numéro de service par défaut de votre pont d’audioconférence, consultez Modifier les numéros de téléphone de votre pont [d’audioconférence.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="6b98a-141">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="6b98a-142">Configurer les stratégies de routage de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="6b98a-142">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="6b98a-143">La stratégie de routage de l’audioconférence OnlineAudioConferencingRoutingPolicy détermine les appels sortants de réunion qui sont acheminés vers des itinéraires de routage direct.</span><span class="sxs-lookup"><span data-stu-id="6b98a-143">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="6b98a-144">Si vous êtes familiarisé avec la stratégie CsOnlineVoiceRoutingPolicy, cette stratégie fonctionne de façon très similaire.</span><span class="sxs-lookup"><span data-stu-id="6b98a-144">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="6b98a-145">Les étapes suivantes sont nécessaires pour configurer les stratégies de routage des audioconférences :</span><span class="sxs-lookup"><span data-stu-id="6b98a-145">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="6b98a-146">Créer des utilisations PSTN</span><span class="sxs-lookup"><span data-stu-id="6b98a-146">Create PSTN usages</span></span>
2.  <span data-ttu-id="6b98a-147">Configurer les itinéraires vocables</span><span class="sxs-lookup"><span data-stu-id="6b98a-147">Configure voice routes</span></span>
3.  <span data-ttu-id="6b98a-148">Créer des stratégies de routage audioconférence</span><span class="sxs-lookup"><span data-stu-id="6b98a-148">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="6b98a-149">Affecter une stratégie à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6b98a-149">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="6b98a-150">Créer des utilisations PSTN</span><span class="sxs-lookup"><span data-stu-id="6b98a-150">Create PSTN usages</span></span>

<span data-ttu-id="6b98a-151">Les utilisations PSTN sont des collections d’itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="6b98a-151">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="6b98a-152">Lorsqu’un appel sortant est lancé à partir de la réunion d’un organisateur donné, les itinéraires vocaux sont utilisés pour déterminer l’itinéraire de routage de l’appel en fonction des utilisations PSTN qui sont associées à l’utilisateur via la stratégie de routage vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6b98a-152">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="6b98a-153">Vous pouvez créer une utilisation PSTN à l’aide de l’cmdlet « Set-CsOnlinePstnUsage ».</span><span class="sxs-lookup"><span data-stu-id="6b98a-153">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="6b98a-154">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6b98a-154">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="6b98a-155">Configurer les itinéraires vocables</span><span class="sxs-lookup"><span data-stu-id="6b98a-155">Configure voice routes</span></span>

<span data-ttu-id="6b98a-156">Les itinéraires vocux déterminent la passerelle PSTN à utiliser pour router un appel en fonction du numéro de téléphone qui est composé à partir d’Teams réunion.</span><span class="sxs-lookup"><span data-stu-id="6b98a-156">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="6b98a-157">Les itinéraires vocux déterminent la passerelle PSTN qui doit être utilisée pour router un appel donné en faisant correspondre le numéro de téléphone composé à partir d’une réunion Teams avec un modèle de regex.</span><span class="sxs-lookup"><span data-stu-id="6b98a-157">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="6b98a-158">Lors de la création d’un itinéraire vocal, l’itinéraire doit être associé à une ou plusieurs utilisations PSTN.</span><span class="sxs-lookup"><span data-stu-id="6b98a-158">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="6b98a-159">Vous pouvez créer un itinéraire vocal et définir les regex et passerelles à associer à l’itinéraire vocal à l’aide de l’cmdlet « New-CsOnlineVoiceRoute ».</span><span class="sxs-lookup"><span data-stu-id="6b98a-159">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="6b98a-160">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6b98a-160">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="6b98a-161">Créer des stratégies de routage audioconférence</span><span class="sxs-lookup"><span data-stu-id="6b98a-161">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="6b98a-162">Les stratégies de routage audio de l’audioconférence déterminent les itinéraires possibles qui peuvent être utilisés pour router un appel en provenance des réunions d’un organisateur en fonction du numéro de téléphone cible de l’appel sortant de la réunion.</span><span class="sxs-lookup"><span data-stu-id="6b98a-162">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="6b98a-163">Les stratégies de routage audio de l’audioconférence sont associées à une ou plusieurs utilisations PSTN, qui, à leur tour, déterminent les itinéraires possibles à utiliser pour les appels sortants de réunion des organisateurs associés à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="6b98a-163">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="6b98a-164">Vous pouvez créer une stratégie de routage audio de conférence audio à l’aide de l’cmdlet « New- CsOnlineAudioConferencingRoutingPolicy ».</span><span class="sxs-lookup"><span data-stu-id="6b98a-164">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="6b98a-165">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6b98a-165">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="6b98a-166">Une fois la stratégie affectée à un utilisateur et lorsqu’un appel sortant de réunion est lancé à partir de l’une des réunions de l’utilisateur, les itinéraires vocaux dans les utilisations PSTN associés à l’organisateur via la stratégie de routage vocal de l’utilisateur sont évalués.</span><span class="sxs-lookup"><span data-stu-id="6b98a-166">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="6b98a-167">Si la destination d’appel sortant de la réunion correspond à une connexion regex dans l’un des itinéraires vocaux associés à l’organisateur, l’appel sortant de la réunion est acheminé vers la passerelle PSTN définie dans l’itinéraire vocal.</span><span class="sxs-lookup"><span data-stu-id="6b98a-167">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="6b98a-168">Si la destination d’appel sortant de la réunion ne correspond pas aux itinéraires vocux associés à l’organisateur, l’appel sortant de la réunion est acheminé par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6b98a-168">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="6b98a-169">Affecter une stratégie à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6b98a-169">Assign a policy to your users</span></span>

<span data-ttu-id="6b98a-170">Une fois les stratégies de routage d’audioconférence définies, vous pouvez les affecter aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6b98a-170">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="6b98a-171">Une fois les stratégies affectées, les appels sortants de la réunion sont évalués par rapport à celui-ci afin de déterminer leur itinéraire de routage.</span><span class="sxs-lookup"><span data-stu-id="6b98a-171">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="6b98a-172">Les stratégies de routage des audioconférences sont toujours évaluées sur la base de l’organisateur de la réunion, indépendamment de l’utilisateur qui déclenche un appel sortant de réunion.</span><span class="sxs-lookup"><span data-stu-id="6b98a-172">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="6b98a-173">Vous pouvez affecter une stratégie de routage audio de conférence audio à un utilisateur à l’aide de l’cmdlet « Grant-CsOnlineAudioConferencingRoutingPolicy ».</span><span class="sxs-lookup"><span data-stu-id="6b98a-173">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="6b98a-174">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6b98a-174">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="6b98a-175">Configurer le routage sur l’équipement téléphonique de votre organisation</span><span class="sxs-lookup"><span data-stu-id="6b98a-175">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="6b98a-176">Sur l’équipement téléphonique de votre organisation, vous devez vous assurer que les appels sortants de la réunion acheminés via le routage direct sont acheminés vers la destination réseau prévue.</span><span class="sxs-lookup"><span data-stu-id="6b98a-176">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="6b98a-177">(Facultatif) Configurer un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="6b98a-177">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="6b98a-178">Un plan de numérotation est un ensemble de règles de normalisation qui traduisent les numéros de téléphone composés par un utilisateur individuel dans un autre format (généralement E.164) pour l’autorisation et le routage des appels.</span><span class="sxs-lookup"><span data-stu-id="6b98a-178">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="6b98a-179">Par défaut, Teams utilisateurs peuvent appeler des numéros PSTN au format E.164, c’est-à-dire + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="6b98a-179">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="6b98a-180">Toutefois, les plans de numérotation peuvent être utilisés pour permettre aux utilisateurs de composer des numéros de téléphone dans d’autres formats, par exemple des extensions à 4 chiffres.</span><span class="sxs-lookup"><span data-stu-id="6b98a-180">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="6b98a-181">Si vous souhaitez activer la numérotation basée sur un numéro de poste par le biais de conférences réseau, vous pouvez configurer des plans de numérotation pour qu’ils correspondent au modèle de numérotation de poste et aux plages de numéros de téléphone du numéro de téléphone de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6b98a-181">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="6b98a-182">Pour configurer des plans de numérotation, voir [Créer et gérer des plans de numérotation.](create-and-manage-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="6b98a-182">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6b98a-183">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="6b98a-183">Related topics</span></span>


