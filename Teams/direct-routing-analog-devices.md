---
title: Routage direct-connexion de périphériques analogiques
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lisez cet article pour découvrir comment utiliser des appareils analogiques avec le routage direct du système Microsoft Phone.
ms.openlocfilehash: 0c6531a29e23e736a84db9bf8571abab2e13942a
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369189"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="08731-103">Utilisation de périphériques analogiques avec le routage direct du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="08731-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="08731-104">Cet article décrit comment utiliser les appareils analogiques avec le routage direct du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="08731-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="08731-105">Pour connecter des appareils analogiques au routage direct, vous devez utiliser une carte de téléphonie analogique (ATA), et cette carte doit être prise en charge par le fournisseur de services de technologie SBC.</span><span class="sxs-lookup"><span data-stu-id="08731-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="08731-106">Lorsqu’un utilisateur effectue un appel à partir d’un appareil analogique, le signalement et le flux multimédia sont acheminés par l’intermédiaire de la carte de téléphonie analogique (ATA) vers l’SBC.</span><span class="sxs-lookup"><span data-stu-id="08731-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="08731-107">La SBC envoie l’appel à un point de terminaison Microsoft teams ou au réseau téléphonique public commuté (RTC) en fonction de la table de routage interne.</span><span class="sxs-lookup"><span data-stu-id="08731-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="08731-108">Lorsqu’un appareil effectue un appel, l’itinéraire qu’il utilise dépend des stratégies de routage créées pour l’appareil.</span><span class="sxs-lookup"><span data-stu-id="08731-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="08731-109">Dans le schéma suivant, le routage direct est configuré de manière à ce que toutes les équipes appelées vers et à partir des numéros compris entre + 1425 4XX XX XX et + 1425 5XX XX XX doivent prendre l’itinéraire rouge (ligne pointillée), et n’importe quel autre numéro à l’exception du 1425 numéro + 1425.</span><span class="sxs-lookup"><span data-stu-id="08731-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="08731-110">![Diagramme montrant une configuration de routage directe](media/direct-routing-analog-device.png)</span><span class="sxs-lookup"><span data-stu-id="08731-110">![Diagram showing Direct Routing configuration](media/direct-routing-analog-device.png)</span></span>

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="08731-111">Exemple : configuration de l’utilisation de périphériques analogiques avec le routage direct</span><span class="sxs-lookup"><span data-stu-id="08731-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="08731-112">Pour configurer l’utilisation de périphériques analogiques avec le routage direct, vous devez connecter la carte de téléphonie analogique à l’SBC et configurer l’SBC pour qu’il fonctionne avec le routage direct.</span><span class="sxs-lookup"><span data-stu-id="08731-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="08731-113">Cet exemple vous guide à travers les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="08731-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="08731-114">Connectez l’SBC au routage direct.</span><span class="sxs-lookup"><span data-stu-id="08731-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="08731-115">Créer une utilisation PSTN ;</span><span class="sxs-lookup"><span data-stu-id="08731-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="08731-116">Créez un itinéraire et associez-le à l’utilisation de PSTN.</span><span class="sxs-lookup"><span data-stu-id="08731-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="08731-117">Attribuez l’itinéraire de la voix à l’utilisation RTC.</span><span class="sxs-lookup"><span data-stu-id="08731-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="08731-118">Activez l’utilisateur en ligne.</span><span class="sxs-lookup"><span data-stu-id="08731-118">Enable the online user.</span></span>
6. <span data-ttu-id="08731-119">Affectez la stratégie d’itinéraire vocale à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="08731-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="08731-120">Créer un itinéraire vocal pour un appareil analogique.</span><span class="sxs-lookup"><span data-stu-id="08731-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="08731-121">Pour plus d’informations sur la connexion d’un disque ATA à un SBC et sur la configuration de l’SBC, voir le Guide de configuration de votre fabricant SBC :</span><span class="sxs-lookup"><span data-stu-id="08731-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>

- [<span data-ttu-id="08731-122">Documentation de configuration de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="08731-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [<span data-ttu-id="08731-123">Documentation de configuration du ruban</span><span class="sxs-lookup"><span data-stu-id="08731-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="08731-124">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="08731-124">Step 1.</span></span>  <span data-ttu-id="08731-125">Connecter l’SBC au routage direct</span><span class="sxs-lookup"><span data-stu-id="08731-125">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="08731-126">La commande suivante configure la connexion SBC comme suit :</span><span class="sxs-lookup"><span data-stu-id="08731-126">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="08731-127">Nom de domaine complet sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08731-127">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="08731-128">Port de signalisation 5068</span><span class="sxs-lookup"><span data-stu-id="08731-128">Signaling port 5068</span></span>
- <span data-ttu-id="08731-129">Mode de contournement de média</span><span class="sxs-lookup"><span data-stu-id="08731-129">Media bypass mode</span></span>
- <span data-ttu-id="08731-130">Informations de l’historique des appels transmises à l’SBC-</span><span class="sxs-lookup"><span data-stu-id="08731-130">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="08731-131">En-tête P-assertion-Identity (PAI) transmis en même temps que l’appel</span><span class="sxs-lookup"><span data-stu-id="08731-131">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="08731-132">Étape 2 : créer une utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="08731-132">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="08731-133">La commande Next crée une utilisation PSTN vide.</span><span class="sxs-lookup"><span data-stu-id="08731-133">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="08731-134">Les utilisations RTC en ligne sont des valeurs de chaîne utilisées pour l’autorisation d’appels.</span><span class="sxs-lookup"><span data-stu-id="08731-134">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="08731-135">Une utilisation RTC en ligne relie une politique vocale en ligne à un itinéraire.</span><span class="sxs-lookup"><span data-stu-id="08731-135">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="08731-136">Dans cet exemple, la chaîne « Interop » est ajoutée à la liste actuelle des utilisations RTC disponibles.</span><span class="sxs-lookup"><span data-stu-id="08731-136">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="08731-137">Étape 3 : créez un itinéraire vocal et associez-le à l’utilisation de PSTN :</span><span class="sxs-lookup"><span data-stu-id="08731-137">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="08731-138">Cette commande crée un nouvel itinéraire vocal en ligne avec l’identité « Analog-Interop » pour la plage de numéros + 1425 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="08731-138">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="08731-139">L’itinéraire vocal s’applique à une liste de passerelles en ligne sbc.contoso.com et associe l’itinéraire avec l' « interopérabilité » de l’utilisation RTC en ligne.</span><span class="sxs-lookup"><span data-stu-id="08731-139">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="08731-140">Un itinéraire vocal inclut une expression régulière qui identifie les numéros de téléphone qui doivent être routés par le biais d’un itinéraire vocal donné :</span><span class="sxs-lookup"><span data-stu-id="08731-140">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="08731-141">Étape 4 : affecter l’itinéraire vocal à l’utilisation RTC :</span><span class="sxs-lookup"><span data-stu-id="08731-141">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="08731-142">Cette commande crée une stratégie de routage vocale par utilisateur en utilisant l’identité « AnalogInteropPolicy ».</span><span class="sxs-lookup"><span data-stu-id="08731-142">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="08731-143">Une utilisation RTC en ligne unique est affectée à cette stratégie : « interopérabilité ».</span><span class="sxs-lookup"><span data-stu-id="08731-143">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="08731-144">Étape 5 : activer l’utilisateur en ligne</span><span class="sxs-lookup"><span data-stu-id="08731-144">Step 5: Enable the online user</span></span>

<span data-ttu-id="08731-145">Cette commande modifie le compte d’utilisateur avec l’identité exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="08731-145">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="08731-146">Dans ce cas, le compte est modifié de façon à activer voix entreprise, l’implémentation Microsoft de VoIP, avec la messagerie vocale activée et attribue le numéro + 14255000000 à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="08731-146">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="08731-147">Cette commande doit être exécutée pour chaque utilisateur Teams (à l’exception des utilisateurs d’appareils ATA) dans le client de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="08731-147">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="08731-148">Étape 6 : affecter la stratégie d’itinéraire vocale à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="08731-148">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="08731-149">Cette commande affecte la stratégie de routage vocale AnalogInteropPolicy en ligne par utilisateur à l’utilisateur avec l’identité exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="08731-149">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="08731-150">Cette commande doit être exécutée pour chaque utilisateur Teams (à l’exception des utilisateurs d’appareils ATA) dans le client de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="08731-150">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="08731-151">Étape 7 : créer un itinéraire vocal pour un appareil analogique</span><span class="sxs-lookup"><span data-stu-id="08731-151">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="08731-152">Cette commande crée un itinéraire vocal en ligne avec identité « Analog-Interop » pour le numéro de série + 1425 4XX XX XX applicable à une liste de passerelles sbc.contoso.com et l’associe à l’utilisation RTC en ligne.</span><span class="sxs-lookup"><span data-stu-id="08731-152">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="08731-153">Cette commande doit être exécutée pour chaque appareil analogique dont le modèle de numéro de téléphone est approprié.</span><span class="sxs-lookup"><span data-stu-id="08731-153">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="08731-154">Par ailleurs, il est possible d’utiliser un modèle de nombre approprié pour les appareils analogiques lorsque vous configurez l’itinéraire vocal en ligne au cours de l’une des étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="08731-154">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="08731-155">Considérations</span><span class="sxs-lookup"><span data-stu-id="08731-155">Considerations</span></span>

- <span data-ttu-id="08731-156">Sauf indication contraire, un dispositif analogique est un appareil qui peut envoyer des chiffres DTMF pour effectuer un appel.</span><span class="sxs-lookup"><span data-stu-id="08731-156">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="08731-157">Par exemple, les téléphones analogiques, les télécopieurs et les recharges du temps.</span><span class="sxs-lookup"><span data-stu-id="08731-157">For example, analog phones, fax machines, and overhead pagers.</span></span>

- <span data-ttu-id="08731-158">Les téléphones analogiques connectés à un disque ATA ne peuvent pas être recherchés par Teams.</span><span class="sxs-lookup"><span data-stu-id="08731-158">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="08731-159">Les utilisateurs d’équipes doivent entrer manuellement le numéro de téléphone associé à l’appareil pour appeler cet appareil.</span><span class="sxs-lookup"><span data-stu-id="08731-159">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="08731-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="08731-160">See also</span></span>

[<span data-ttu-id="08731-161">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="08731-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="08731-162">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="08731-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
