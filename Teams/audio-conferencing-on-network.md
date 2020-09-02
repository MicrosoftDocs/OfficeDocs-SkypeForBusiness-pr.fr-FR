---
title: Audioconférence sur réseau pour les conférences audio
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Les rubriques suivantes décrivent les fonctionnalités d’aperçu ouvert pour l’audioconférence sur le réseau.
ms.openlocfilehash: 3b33c67cc79f79d36cf2a11213dc934103b026fb
ms.sourcegitcommit: 19662d4bc4070f6031084d93e8794e0e02decd2b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321793"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="b800b-103">Aperçu avant impression de l’audioconférence sur réseau pour les conférences audio</span><span class="sxs-lookup"><span data-stu-id="b800b-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="b800b-104">L’aperçu avant ouverture des conférences sur réseau est disponible pour tous les clients.</span><span class="sxs-lookup"><span data-stu-id="b800b-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="b800b-105">Les conférences sur réseau permettent aux organisations d’envoyer des appels de conférence rendez-vous entrants et sortants vers des numéros de connexion Microsoft par le biais du routage direct.</span><span class="sxs-lookup"><span data-stu-id="b800b-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="b800b-106">Cette fonctionnalité n’est pas destinée à étendre la prise en charge de l’audioconférence aux numéros d’accès tiers.</span><span class="sxs-lookup"><span data-stu-id="b800b-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="b800b-107">L’audioconférence sur réseau n’est pas prise en charge si elle est utilisée pour diriger les appels entrants vers le service d’audioconférence via des numéros de téléphone tiers.</span><span class="sxs-lookup"><span data-stu-id="b800b-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="b800b-108">Cet article décrit les prérequis et les étapes de configuration nécessaires à l’activation de conférences sur le réseau pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b800b-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b800b-109">L’audioconférence sur réseau ne doit pas être déployée avec un équipement de téléphonie en Inde.</span><span class="sxs-lookup"><span data-stu-id="b800b-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="b800b-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="b800b-110">Prerequisites</span></span>

<span data-ttu-id="b800b-111">Avant de configurer une conférence sur le réseau, assurez-vous que votre organisation remplit les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="b800b-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="b800b-112">Assurez-vous que tous les utilisateurs de votre organisation qui sont activés ou seront activés pour les conférences audio en mode équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="b800b-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are in Teams Only mode.</span></span> <span data-ttu-id="b800b-113">Le routage des appels de conférence audio entrants et Outboud par le biais de conférences sur le réseau est uniquement pris en charge pour les réunions Teams.</span><span class="sxs-lookup"><span data-stu-id="b800b-113">The routing of inbound and outboud Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="b800b-114">Attribuez des licences de conférence audio à tous les utilisateurs qui utiliseront une conférence sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="b800b-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="b800b-115">Configurez le service de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="b800b-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="b800b-116">Pour plus d’informations, consultez la rubrique [configurer l’audioconférence pour Microsoft teams](set-up-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b800b-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="b800b-117">Configurez votre contrôleur de bordure de session (SBC) pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="b800b-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="b800b-118">Pour plus d’informations, voir [planifier le routage direct](direct-routing-plan.md) et [configurer le routage direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="b800b-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="b800b-119">Si vous configurez le routage direct uniquement dans le cadre de l’audioconférence, vous n’avez besoin que de l’étape 1 : connecter votre SBC» pour les conférences sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="b800b-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="b800b-120">Activez le routage des appels de conférence rendez-vous dans l’audioconférence Microsoft via le routage direct.</span><span class="sxs-lookup"><span data-stu-id="b800b-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="b800b-121">Pour acheminer les appels de conférence rendez-vous effectuées par vos utilisateurs locaux vers le service d’audioconférence par le biais du routage direct, vous devez configurer les règles de routage appropriées pour les PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="b800b-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="b800b-122">Vous devez configurer l’équipement de téléphonie de vos sites pour diriger les appels vers n’importe quel numéro de service du pont de conférence de votre organisation via un Trunk de routage direct.</span><span class="sxs-lookup"><span data-stu-id="b800b-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="b800b-123">Vous pouvez trouver les numéros de service dans le centre d’administration teams sous **réunions-> des ponts de conférence** ou en utilisant l’applet de cmdlet PowerShell de Skype entreprise Online Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="b800b-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="b800b-124">Pour plus d’informations, reportez-vous à la liste des [numéros de conférence audio dans Microsoft teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b800b-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>


## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="b800b-125">Activez le routage des appels sortants de réunion à l’aide du routage direct.</span><span class="sxs-lookup"><span data-stu-id="b800b-125">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="b800b-126">Les appels sortants de réunion teams sont initiés à partir d’une réunion au sein de votre organisation aux numéros RTC, y compris les appels-moi et les appels pour amener de nouveaux participants à une réunion.</span><span class="sxs-lookup"><span data-stu-id="b800b-126">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="b800b-127">Pour activer le routage de numérotation des réunions teams via le routage direct, vous devez créer et affecter une stratégie de routage de conférence audio nommée « OnlineAudioConferencingRoutingPolicy ».</span><span class="sxs-lookup"><span data-stu-id="b800b-127">To enable Teams meeting dial-out routing through Direct Routing, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="b800b-128">La stratégie OnlineAudioConferencingRoutingPolicy est équivalente au CsOnlineVoiceRoutingPolicy pour les appels RTC 1:1 via le routage direct.</span><span class="sxs-lookup"><span data-stu-id="b800b-128">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="b800b-129">La stratégie OnlineAudioConferencingRoutingPolicy peut être gérée à l’aide des applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="b800b-129">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="b800b-130">Nouveau-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b800b-130">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b800b-131">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b800b-131">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b800b-132">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b800b-132">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b800b-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b800b-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b800b-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b800b-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="b800b-135">Pour plus d’informations sur le routage pour le routage direct, voir [configurer le routage vocal pour le routage direct](direct-routing-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="b800b-135">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="b800b-136">Pour permettre le routage des appels sortants de réunion via le routage direct, vous devez :</span><span class="sxs-lookup"><span data-stu-id="b800b-136">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="b800b-137">Configuration des stratégies de routage de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="b800b-137">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="b800b-138">Configurer le routage sur l’équipement de téléphonie de votre organisation</span><span class="sxs-lookup"><span data-stu-id="b800b-138">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="b800b-139">Facultatif Configurer un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="b800b-139">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="b800b-140">Les appels sortants provenant des réunions teams proviennent du numéro de service par défaut sur le pont de conférence.</span><span class="sxs-lookup"><span data-stu-id="b800b-140">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="b800b-141">Pour plus d’informations sur le numéro de service par défaut de votre pont de conférence audio, voir [modifier les numéros de téléphone de votre pont de conférence audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="b800b-141">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="b800b-142">Configuration des stratégies de routage de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="b800b-142">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="b800b-143">Le OnlineAudioConferencingRoutingPolicy de stratégie de routage de l’audioconférence détermine les appels vers les appels sortants de réunion qui sont routés vers les Trunks de routage directs.</span><span class="sxs-lookup"><span data-stu-id="b800b-143">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="b800b-144">Si vous connaissez bien la politique CsOnlineVoiceRoutingPolicy, cette politique fonctionne de manière très similaire.</span><span class="sxs-lookup"><span data-stu-id="b800b-144">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="b800b-145">Les étapes suivantes sont nécessaires pour configurer les stratégies de routage de l’audioconférence :</span><span class="sxs-lookup"><span data-stu-id="b800b-145">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="b800b-146">Créer des utilisations PSTN</span><span class="sxs-lookup"><span data-stu-id="b800b-146">Create PSTN usages</span></span>
2.  <span data-ttu-id="b800b-147">Configurer des itinéraires vocaux</span><span class="sxs-lookup"><span data-stu-id="b800b-147">Configure voice routes</span></span>
3.  <span data-ttu-id="b800b-148">Créer des stratégies de routage vocal pour les conférences audio</span><span class="sxs-lookup"><span data-stu-id="b800b-148">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="b800b-149">Attribuer une stratégie à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b800b-149">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="b800b-150">Créer des utilisations PSTN</span><span class="sxs-lookup"><span data-stu-id="b800b-150">Create PSTN usages</span></span>

<span data-ttu-id="b800b-151">Les utilisations RTC sont des collections d’itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="b800b-151">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="b800b-152">Lorsqu’un appel sortant est lancé depuis la réunion d’un organisateur donné, les itinéraires vocaux sont utilisés pour déterminer le chemin de routage de l’appel en fonction des utilisations RTC associées à l’utilisateur via la stratégie de routage vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b800b-152">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="b800b-153">Vous pouvez créer une utilisation PSTN à l’aide de l’applet de commande « Set-CsOnlinePstnUsage ».</span><span class="sxs-lookup"><span data-stu-id="b800b-153">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="b800b-154">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b800b-154">For Example:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="b800b-155">Configurer des itinéraires vocaux</span><span class="sxs-lookup"><span data-stu-id="b800b-155">Configure voice routes</span></span>

<span data-ttu-id="b800b-156">Les itinéraires vocaux déterminent la passerelle RTC qui doit être utilisée pour acheminer les appels en fonction du numéro de téléphone composé par le biais d’une réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="b800b-156">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="b800b-157">Les itinéraires vocaux déterminent la passerelle RTC qui doit être utilisée pour acheminer un appel donné en correspondant au numéro de téléphone composé par une réunion teams à l’aide d’un modèle Regex.</span><span class="sxs-lookup"><span data-stu-id="b800b-157">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="b800b-158">Lors de la création d’un itinéraire vocal, l’itinéraire doit être associé à une ou plusieurs utilisations PSTN.</span><span class="sxs-lookup"><span data-stu-id="b800b-158">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="b800b-159">Vous pouvez créer un itinéraire vocal et définir la fonction Regex et les passerelles à associer à l’itinéraire vocal à l’aide de l’applet de nouvelle applet de nouvelle-CsOnlineVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="b800b-159">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="b800b-160">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b800b-160">For Example:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="b800b-161">Créer des stratégies de routage vocal pour les conférences audio</span><span class="sxs-lookup"><span data-stu-id="b800b-161">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="b800b-162">Les stratégies de routage vocal de l’audioconférence déterminent les itinéraires possibles qui peuvent être utilisés pour acheminer un appel provenant des réunions d’un organisateur en fonction du numéro de téléphone cible de l’appel sortant de la réunion.</span><span class="sxs-lookup"><span data-stu-id="b800b-162">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="b800b-163">Les stratégies de routage de la voix de l’audioconférence sont associées à une ou plusieurs utilisations RTC, qui, à leur tour, déterminent les itinéraires possibles qui seront utilisés pour les appels sortants des organisateurs associés à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="b800b-163">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="b800b-164">Vous pouvez créer une stratégie de routage téléphonique de l’audioconférence à l’aide de l’applet de nouvelle applet de nouvelle-CsOnlineAudioConferencingRoutingPolicy.</span><span class="sxs-lookup"><span data-stu-id="b800b-164">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="b800b-165">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b800b-165">For Example:</span></span>

```
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b800b-166">Lorsque la stratégie est attribuée à un utilisateur et qu’un appel sortant de réunion est lancé à partir de l’une des réunions de l’utilisateur, les itinéraires vocaux dans les utilisations RTC associées à l’organisateur via la stratégie de routage vocale de l’utilisateur sont évalués.</span><span class="sxs-lookup"><span data-stu-id="b800b-166">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="b800b-167">Si la destination de l’appel sortant de la réunion correspond à une expression régulière dans l’un des itinéraires vocaux associés à l’organisateur, l’appel sortant de la réunion est acheminé vers la passerelle RTC définie dans l’itinéraire vocal.</span><span class="sxs-lookup"><span data-stu-id="b800b-167">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="b800b-168">Si la destination des appels sortants de la réunion ne correspond à aucun des itinéraires vocaux associés à l’organisateur, l’appel sortant de la réunion est acheminé par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b800b-168">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="b800b-169">Attribuer une stratégie à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b800b-169">Assign a policy to your users</span></span>

<span data-ttu-id="b800b-170">Une fois les stratégies de routage de l’audioconférence définies, vous pouvez désormais les affecter aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b800b-170">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="b800b-171">Une fois les stratégies affectées, les appels sortants de la réunion sont évalués par rapport à cette dernière pour déterminer leur chemin d’acheminement.</span><span class="sxs-lookup"><span data-stu-id="b800b-171">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="b800b-172">Les stratégies de routage de l’audioconférence sont toujours évaluées en fonction de l’organisateur de la réunion, indépendamment de l’utilisateur participant à la réunion qui initie l’appel sortant à une réunion.</span><span class="sxs-lookup"><span data-stu-id="b800b-172">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="b800b-173">Vous pouvez assigner une stratégie de routage téléphonique de l’audioconférence à un utilisateur à l’aide de l’applet de cmdlet « Grant-CsOnlineAudioConferencingRoutingPolicy ».</span><span class="sxs-lookup"><span data-stu-id="b800b-173">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="b800b-174">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b800b-174">For example:</span></span>

```
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="b800b-175">Configurer le routage sur l’équipement de téléphonie de votre organisation</span><span class="sxs-lookup"><span data-stu-id="b800b-175">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="b800b-176">Dans le cadre de l’équipement de téléphonie de votre organisation, vous devez vous assurer que les appels commutés de réunion routés via le routage direct sont routés vers la destination prévue.</span><span class="sxs-lookup"><span data-stu-id="b800b-176">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="b800b-177">Facultatif Configurer un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="b800b-177">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="b800b-178">Un plan de numérotation est un ensemble de règles de normalisation qui permettent de traduire les numéros de téléphone numérotés d’un utilisateur individuel dans un autre format (généralement E. 164) à des fins d’autorisation d’appel et de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="b800b-178">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="b800b-179">Par défaut, les utilisateurs de teams peuvent appeler des numéros RTC au format E. 164, c’est-à-dire + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="b800b-179">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="b800b-180">Toutefois, les plans de numérotation peuvent être utilisés pour permettre aux utilisateurs de composer des numéros de téléphone dans d’autres formats, par exemple des extensions à 4 chiffres.</span><span class="sxs-lookup"><span data-stu-id="b800b-180">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="b800b-181">Si vous souhaitez activer la numérotation basée sur une extension via l’audioconférence sur le réseau, vous pouvez configurer des plans de numérotation pour qu’ils correspondent au modèle de numérotation des numéros de téléphone de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b800b-181">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="b800b-182">Pour configurer des plans de numérotation, reportez-vous à [créer et gérer des plans de numérotation](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="b800b-182">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="b800b-183">Problèmes connus dans l’aperçu ouvert</span><span class="sxs-lookup"><span data-stu-id="b800b-183">Known issues in Open Preview</span></span>

<span data-ttu-id="b800b-184">Vous trouverez ci-dessous une liste des problèmes connus actuellement présents dans la version d’évaluation d’une conférence sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="b800b-184">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="b800b-185">Microsoft travaille actuellement à la résolution de ces problèmes.</span><span class="sxs-lookup"><span data-stu-id="b800b-185">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="b800b-186">Problème</span><span class="sxs-lookup"><span data-stu-id="b800b-186">Issue</span></span> | <span data-ttu-id="b800b-187">Moyens</span><span class="sxs-lookup"><span data-stu-id="b800b-187">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="b800b-188">Les appels entrants avec des ID d’appelant anonyme/caché routés via l’audioconférence sur le réseau ne peuvent pas être connectés à la réunion.</span><span class="sxs-lookup"><span data-stu-id="b800b-188">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="b800b-189">Dans la mesure du possible, définissez une configuration dans votre système PBX ou SBC pour toujours envoyer un ID d’appelant pour les appels routés via une conférence sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="b800b-189">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="b800b-190">Dans certains cas, le message de bienvenue qui est lu aux utilisateurs lorsqu’ils se connectent au service (« Bienvenue dans le service d’audioconférence ») est tronqué et les utilisateurs n’entendent pas le mot « Bienvenue ».</span><span class="sxs-lookup"><span data-stu-id="b800b-190">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="b800b-191">Il n’existe pas de solution de contournement pour ce problème pour le moment.</span><span class="sxs-lookup"><span data-stu-id="b800b-191">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="b800b-192">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b800b-192">Related topics</span></span>


