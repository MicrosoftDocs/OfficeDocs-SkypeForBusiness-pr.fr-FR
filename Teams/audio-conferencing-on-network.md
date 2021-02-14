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
description: L’article suivant décrit la fonctionnalité Open Preview pour le réseau pour l’audioconférence.
ms.openlocfilehash: 1ae61034ef083c89e14c67cef0effa1c105de758
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031860"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="fdb5a-103">Aperçu de la conférence sur réseau pour l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="fdb5a-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="fdb5a-104">La prévisualisation ouverte de la conférence sur réseau est disponible pour tous les clients.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="fdb5a-105">Les conférences sur réseau permettent aux organisations d’envoyer des appels d’audioconférence entrants et sortants à des numéros de connexion Microsoft par le biais d’un routage direct.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="fdb5a-106">Cette fonctionnalité n’est pas destinée à étendre la prise en charge de l’audioconférence à des numéros d’accès tiers.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="fdb5a-107">La fonction de conférence sur réseau n’est pas prise en charge si elle est utilisée pour router les appels entrants vers le service d’audioconférence via des numéros de téléphone tiers.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="fdb5a-108">Cet article décrit les conditions préalables et les étapes de configuration requises pour activer la conférence sur réseau pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fdb5a-109">La conférence sur réseau ne doit PAS être déployée avec n’importe quel équipement téléphonique en Inde.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="fdb5a-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="fdb5a-110">Prerequisites</span></span>

<span data-ttu-id="fdb5a-111">Avant de configurer la conférence sur réseau, assurez-vous que votre organisation répond aux conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdb5a-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="fdb5a-112">Assurez-vous que tous les utilisateurs de votre organisation qui sont activés ou seront activés pour l’audioconférence utilisent Teams pour toutes les réunions.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="fdb5a-113">Le routage des appels d’audioconférence entrants et sortants via la conférence sur réseau est uniquement pris en charge pour les réunions Teams.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="fdb5a-114">Attribuez des licences d’audioconférence à tous les utilisateurs qui utiliseront la conférence sur réseau.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="fdb5a-115">Configurer le service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="fdb5a-116">Pour plus d’informations, [voir Configurer l’audioconférence pour Microsoft Teams.](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="fdb5a-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="fdb5a-117">Configurer votre contrôleur de session border controller (SBC) pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="fdb5a-118">Pour plus d’informations, [voir Planifier le routage direct et](direct-routing-plan.md) Configurer le [routage direct.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="fdb5a-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="fdb5a-119">Si vous configurationnez le routage direct uniquement dans le cadre de l’audioconférence, vous devez seulement effectuer l'« étape 1 : connecter votre SBC » pour les conférences sur réseau.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="fdb5a-120">Activer le routage des appels d’accès vers l’audioconférence Microsoft par le biais du routage direct</span><span class="sxs-lookup"><span data-stu-id="fdb5a-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="fdb5a-121">Pour router les appels d’accès effectués par vos utilisateurs locaux vers le service d’audioconférence via un routage direct, vous devez configurer les règles de routage appropriées pour vos SBCs et vos PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="fdb5a-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="fdb5a-122">Vous devez configurer l’équipement téléphonique de vos sites pour router les appels vers n’importe quel numéro de service du pont de conférence de votre organisation via une ligne de routage direct.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="fdb5a-123">Vous trouverez les numéros de service dans le Centre d’administration Teams sous Réunions **-> Ponts** de conférence ou à l’aide de l’cmdlet Skype Entreprise Online PowerShell Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="fdb5a-124">Pour plus d’informations, consultez la liste des numéros [d’audioconférence dans Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="fdb5a-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fdb5a-125">Cette fonctionnalité n’est pas disponible pour les utilisateurs titulaires d’une licence d’audioconférence à la minute.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="fdb5a-126">Activer le routage des appels sortants de réunion Teams via un routage direct</span><span class="sxs-lookup"><span data-stu-id="fdb5a-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="fdb5a-127">Les appels sortants vers des réunions Teams sont lancés depuis une réunion de votre organisation vers des numéros PSTN, y compris les appels d’appel et les appels d’appel pour amener de nouveaux participants à une réunion.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="fdb5a-128">Pour activer le routage des appels sortants de réunion Teams via un routage direct vers les utilisateurs du réseau, vous devez créer et affecter une stratégie de routage audioconférence nommée « OnlineAudioConferencingRoutingPolicy ».</span><span class="sxs-lookup"><span data-stu-id="fdb5a-128">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="fdb5a-129">La stratégie OnlineAudioConferencingRoutingPolicy équivaut à la stratégie CsOnlineVoiceRoutingPolicy pour les appels PSTN 1:1 via un routage direct.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="fdb5a-130">La stratégie OnlineAudioConferencingRoutingPolicy peut être gérée à l’aide des cmdlets suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdb5a-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="fdb5a-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="fdb5a-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="fdb5a-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="fdb5a-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="fdb5a-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="fdb5a-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="fdb5a-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="fdb5a-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="fdb5a-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="fdb5a-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="fdb5a-136">Pour plus d’informations sur le routage pour le routage direct, voir [Configurer le routage vocal pour le routage direct.](direct-routing-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="fdb5a-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="fdb5a-137">Pour permettre le routage des appels sortants de réunion via un routage direct, vous devez :</span><span class="sxs-lookup"><span data-stu-id="fdb5a-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="fdb5a-138">Configurer les stratégies de routage de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="fdb5a-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="fdb5a-139">Configurer le routage sur l’équipement téléphonique de votre organisation</span><span class="sxs-lookup"><span data-stu-id="fdb5a-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="fdb5a-140">(Facultatif) Configurer un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="fdb5a-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="fdb5a-141">Les appels sortants des réunions Teams sont issus du numéro de service par défaut sur le pont de conférence.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="fdb5a-142">Pour plus d’informations sur le numéro de service par défaut de votre pont d’audioconférence, consultez Modifier les numéros de téléphone de votre pont [d’audioconférence.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="fdb5a-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="fdb5a-143">Configurer les stratégies de routage de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="fdb5a-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="fdb5a-144">La stratégie de routage de l’audioconférence OnlineAudioConferencingRoutingPolicy détermine les appels sortants de réunion acheminés vers des itinéraires de routage direct.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="fdb5a-145">Si vous êtes familiarisé avec la stratégie CsOnlineVoiceRoutingPolicy, cette stratégie fonctionne de façon très similaire.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="fdb5a-146">Les étapes suivantes sont nécessaires pour configurer les stratégies de routage des audioconférences :</span><span class="sxs-lookup"><span data-stu-id="fdb5a-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="fdb5a-147">Créer des utilisations PSTN</span><span class="sxs-lookup"><span data-stu-id="fdb5a-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="fdb5a-148">Configurer les itinéraires vocables</span><span class="sxs-lookup"><span data-stu-id="fdb5a-148">Configure voice routes</span></span>
3.  <span data-ttu-id="fdb5a-149">Créer des stratégies de routage audioconférence</span><span class="sxs-lookup"><span data-stu-id="fdb5a-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="fdb5a-150">Affecter une stratégie à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fdb5a-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="fdb5a-151">Créer des utilisations PSTN</span><span class="sxs-lookup"><span data-stu-id="fdb5a-151">Create PSTN usages</span></span>

<span data-ttu-id="fdb5a-152">Les utilisations PSTN sont des collections d’itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="fdb5a-153">Lorsqu’un appel sortant est lancé à partir de la réunion d’un organisateur donné, les itinéraires vocaux sont utilisés pour déterminer l’itinéraire de routage de l’appel en fonction des utilisations PSTN qui sont associées à l’utilisateur via la stratégie de routage vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="fdb5a-154">Vous pouvez créer une utilisation PSTN à l’aide de l’cmdlet « Set-CsOnlinePstnUsage ».</span><span class="sxs-lookup"><span data-stu-id="fdb5a-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="fdb5a-155">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="fdb5a-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="fdb5a-156">Configurer les itinéraires vocables</span><span class="sxs-lookup"><span data-stu-id="fdb5a-156">Configure voice routes</span></span>

<span data-ttu-id="fdb5a-157">Les itinéraires vocux déterminent la passerelle PSTN qui doit être utilisée pour router un appel en fonction du numéro de téléphone qui est composé à partir d’une réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="fdb5a-158">Les itinéraires vocables déterminent la passerelle PSTN qui doit être utilisée pour router un appel donné en faisant correspondre le numéro de téléphone composé à partir d’une réunion Teams avec un modèle de regex.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="fdb5a-159">Lors de la création d’un itinéraire vocal, l’itinéraire doit être associé à une ou plusieurs utilisations PSTN.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="fdb5a-160">Vous pouvez créer un itinéraire vocal et définir les limites et passerelles à associer à l’itinéraire vocal à l’aide de l’cmdlet « New-CsOnlineVoiceRoute ».</span><span class="sxs-lookup"><span data-stu-id="fdb5a-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="fdb5a-161">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="fdb5a-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="fdb5a-162">Créer des stratégies de routage audio de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="fdb5a-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="fdb5a-163">Les stratégies de routage audio de l’audioconférence déterminent les itinéraires possibles qui peuvent être utilisés pour router un appel en provenance des réunions d’un organisateur en fonction du numéro de téléphone cible de l’appel sortant de la réunion.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="fdb5a-164">Les stratégies de routage audio de l’audioconférence sont associées à une ou plusieurs utilisations PSTN, qui, à leur tour, déterminent les itinéraires possibles à utiliser pour les appels sortants de réunion des organisateurs associés à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="fdb5a-165">Vous pouvez créer une stratégie de routage audio de conférence audio à l’aide de l’cmdlet « New- CsOnlineAudioConferencingRoutingPolicy ».</span><span class="sxs-lookup"><span data-stu-id="fdb5a-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="fdb5a-166">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="fdb5a-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="fdb5a-167">Une fois la stratégie affectée à un utilisateur et lorsqu’un appel sortant de réunion est lancé à partir de l’une des réunions de l’utilisateur, les itinéraires vocaux dans les utilisations PSTN associés à l’organisateur via la stratégie de routage vocal de l’utilisateur sont évalués.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="fdb5a-168">Si la destination d’appel sortant de la réunion correspond à une connexion regex dans l’un des itinéraires vocaux associés à l’organisateur, l’appel sortant de la réunion est acheminé vers la passerelle PSTN définie dans l’itinéraire vocal.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="fdb5a-169">Si la destination d’appel sortant de la réunion ne correspond pas aux itinéraires vocux associés à l’organisateur, l’appel sortant de la réunion est acheminé par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="fdb5a-170">Affecter une stratégie à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fdb5a-170">Assign a policy to your users</span></span>

<span data-ttu-id="fdb5a-171">Une fois les stratégies de routage d’audioconférence définies, vous pouvez les affecter aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="fdb5a-172">Une fois les stratégies affectées, les appels sortants de la réunion sont évalués par rapport à celui-ci afin de déterminer leur itinéraire de routage.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="fdb5a-173">Les stratégies de routage des audioconférences sont toujours évaluées sur la base de l’organisateur de la réunion, indépendamment de l’utilisateur qui déclenche un appel sortant de réunion.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="fdb5a-174">Vous pouvez affecter une stratégie de routage audio de conférence audio à un utilisateur à l’aide de l’cmdlet « Grant-CsOnlineAudioConferencingRoutingPolicy ».</span><span class="sxs-lookup"><span data-stu-id="fdb5a-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="fdb5a-175">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="fdb5a-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="fdb5a-176">Configurer le routage sur l’équipement téléphonique de votre organisation</span><span class="sxs-lookup"><span data-stu-id="fdb5a-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="fdb5a-177">Sur l’équipement téléphonique de votre organisation, vous devez vous assurer que les appels sortants de la réunion acheminés via le routage direct sont acheminés vers la destination réseau prévue.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="fdb5a-178">(Facultatif) Configurer un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="fdb5a-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="fdb5a-179">Un plan de numérotation est un ensemble de règles de normalisation qui traduisent les numéros de téléphone composés par un utilisateur individuel dans un autre format (généralement E.164) pour l’autorisation et le routage des appels.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="fdb5a-180">Par défaut, les utilisateurs de Teams peuvent appeler des numéros PSTN au format E.164, c’est-à-dire + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="fdb5a-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="fdb5a-181">Toutefois, les plans de numérotation peuvent être utilisés pour permettre aux utilisateurs de composer des numéros de téléphone dans d’autres formats, par exemple des extensions à 4 chiffres.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="fdb5a-182">Si vous souhaitez activer la numérotation basée sur un numéro de poste par le biais de conférences réseau, vous pouvez configurer des plans de numérotation pour qu’ils correspondent au modèle de numérotation de poste et aux plages de numéros de téléphone du numéro de téléphone de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="fdb5a-183">Pour configurer des plans de numérotation, voir [Créer et gérer des plans de numérotation.](create-and-manage-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="fdb5a-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="fdb5a-184">Problèmes connus dans Open Preview</span><span class="sxs-lookup"><span data-stu-id="fdb5a-184">Known issues in Open Preview</span></span>

<span data-ttu-id="fdb5a-185">Voici une liste des problèmes connus actuellement présents dans la version Open Preview de la conférence sur réseau.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="fdb5a-186">Microsoft travaille à la résoudre.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="fdb5a-187">Problème</span><span class="sxs-lookup"><span data-stu-id="fdb5a-187">Issue</span></span> | <span data-ttu-id="fdb5a-188">Solution de contournement</span><span class="sxs-lookup"><span data-stu-id="fdb5a-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="fdb5a-189">Les appels à composer avec des ID d’appelant anonymes/masqués qui sont acheminés via la conférence réseau ne peuvent pas être connectés à la réunion.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="fdb5a-190">Si possible, définissez une configuration dans votre système PBX ou SBC pour toujours envoyer un ID d’appelant pour les appels acheminés via la conférence réseau.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="fdb5a-191">Dans certains cas, le message d’accueil adressé aux utilisateurs lorsqu’ils composent le numéro de téléphone pour se rendre au service ( « Bienvenue dans le service d’audioconférence... ») est tronqué et les utilisateurs n’entendent pas le mot « Bienvenue ».</span><span class="sxs-lookup"><span data-stu-id="fdb5a-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="fdb5a-192">Il n’existe aucune solution de contournement pour ce problème pour le moment.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="fdb5a-193">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="fdb5a-193">Related topics</span></span>


