---
title: Routage direct - Connexion de périphériques analogiques
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
description: Lisez cet article pour découvrir comment utiliser des périphériques analogiques avec Téléphone Microsoft routage direct de système informatique.
ms.openlocfilehash: dc49c22dceffda6905d1f57652fd14d584d02cf6
ms.sourcegitcommit: 9d446485aa842abbdcd34d946b247166c2bf1610
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52642094"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="222bc-103">Utilisation de dispositifs analogiques avec un Système téléphonique direct</span><span class="sxs-lookup"><span data-stu-id="222bc-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="222bc-104">Cet article décrit comment utiliser des périphériques analogiques avec un Système téléphonique direct.</span><span class="sxs-lookup"><span data-stu-id="222bc-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="222bc-105">Pour connecter des périphériques analogiques au routage direct, vous devez utiliser un adaptateur de téléphonie analogique, qui doit être pris en charge par le fournisseur de contrôleur de session en bordure certifié (SBC).</span><span class="sxs-lookup"><span data-stu-id="222bc-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="222bc-106">Lorsqu’un utilisateur effectue un appel à partir d’un appareil analogique, le trafic de signalisation et le trafic de médias circulent entre la carte téléphonique analogique (ATA) et le SBC.</span><span class="sxs-lookup"><span data-stu-id="222bc-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="222bc-107">Le SBC envoie l’appel à un point de terminaison Microsoft Teams public ou au réseau téléphonique commuté (PSTN) basé sur la table de routage interne.</span><span class="sxs-lookup"><span data-stu-id="222bc-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="222bc-108">Quand un appareil effectue un appel, l’itinéraire qu’il prend dépend des stratégies de routage créées pour l’appareil.</span><span class="sxs-lookup"><span data-stu-id="222bc-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="222bc-109">Dans le diagramme suivant, le routage direct est configuré de façon à ce que les appels Teams vers et à partir des numéros entre +1425 4XX XX XX et +1425 5XX XX XX doivent suivre l’itinéraire rouge (ligne en pointillés), et les appels PSTN entre +1425 4XX XX XX et tout autre nombre à l’exception de la plage de numéros +1425 5XX XX XX doivent prendre le itinéraire bleu (trait plein).</span><span class="sxs-lookup"><span data-stu-id="222bc-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="222bc-110">![Diagramme montrant la configuration du routage direct](media/direct-routing-analog-device.png)</span><span class="sxs-lookup"><span data-stu-id="222bc-110">![Diagram showing Direct Routing configuration](media/direct-routing-analog-device.png)</span></span>

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="222bc-111">Exemple : configuration de l’utilisation de dispositifs analogiques avec le routage direct</span><span class="sxs-lookup"><span data-stu-id="222bc-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="222bc-112">Pour configurer l’utilisation de dispositifs analogiques avec un routage direct, vous devez connecter la carte de téléphonie analogique au SBC et configurer ce dernier pour qu’il fonctionne avec le routage direct.</span><span class="sxs-lookup"><span data-stu-id="222bc-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="222bc-113">Cet exemple vous fait suivre les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="222bc-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="222bc-114">Connecter le routage SBC vers direct.</span><span class="sxs-lookup"><span data-stu-id="222bc-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="222bc-115">Créez l’utilisation PSTN.</span><span class="sxs-lookup"><span data-stu-id="222bc-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="222bc-116">Créez un itinéraire vocal et associez-le à l’utilisation PSTN.</span><span class="sxs-lookup"><span data-stu-id="222bc-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="222bc-117">Affectez l’itinéraire vocal à l’utilisation PSTN.</span><span class="sxs-lookup"><span data-stu-id="222bc-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="222bc-118">Activez l’utilisateur en ligne.</span><span class="sxs-lookup"><span data-stu-id="222bc-118">Enable the online user.</span></span>
6. <span data-ttu-id="222bc-119">Affectez la stratégie de route vocale à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="222bc-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="222bc-120">Créez une route vocale pour un appareil analogique.</span><span class="sxs-lookup"><span data-stu-id="222bc-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="222bc-121">Pour plus d’informations sur la connexion d’un contrôle d’accès (ATA) à un SBC et la configuration de ce dernier, consultez le guide de configuration du fabricant SBC :</span><span class="sxs-lookup"><span data-stu-id="222bc-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>

- [<span data-ttu-id="222bc-122">Documentation sur la configuration de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="222bc-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [<span data-ttu-id="222bc-123">Documentation sur la configuration du ruban</span><span class="sxs-lookup"><span data-stu-id="222bc-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [<span data-ttu-id="222bc-124">Documentation sur la configuration d’Oracle</span><span class="sxs-lookup"><span data-stu-id="222bc-124">Oracle configuration documentation</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="222bc-125">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="222bc-125">Step 1.</span></span>  <span data-ttu-id="222bc-126">Connecter le routage SBC vers direct</span><span class="sxs-lookup"><span data-stu-id="222bc-126">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="222bc-127">La commande suivante configure la connexion SBC comme suit :</span><span class="sxs-lookup"><span data-stu-id="222bc-127">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="222bc-128">Sbc.contoso.com de sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="222bc-128">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="222bc-129">Port de signalisation 5068</span><span class="sxs-lookup"><span data-stu-id="222bc-129">Signaling port 5068</span></span>
- <span data-ttu-id="222bc-130">Mode de dérivation média</span><span class="sxs-lookup"><span data-stu-id="222bc-130">Media bypass mode</span></span>
- <span data-ttu-id="222bc-131">Informations de l’historique des appels transmis au dossier SBC-</span><span class="sxs-lookup"><span data-stu-id="222bc-131">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="222bc-132">En-tête P-Ed-Identity (NT) transmis avec l’appel</span><span class="sxs-lookup"><span data-stu-id="222bc-132">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="222bc-133">Étape 2 : créer l’utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="222bc-133">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="222bc-134">La commande suivante crée une utilisation PSTN vide.</span><span class="sxs-lookup"><span data-stu-id="222bc-134">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="222bc-135">Les utilisations PSTN en ligne sont des valeurs de chaîne utilisées pour l’autorisation d’appel.</span><span class="sxs-lookup"><span data-stu-id="222bc-135">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="222bc-136">Une utilisation PSTN en ligne lie une stratégie vocale en ligne à un itinéraire.</span><span class="sxs-lookup"><span data-stu-id="222bc-136">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="222bc-137">Cet exemple ajoute la chaîne « Interop » à la liste actuelle des utilisations PSTN disponibles.</span><span class="sxs-lookup"><span data-stu-id="222bc-137">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="222bc-138">Étape 3 : créez un itinéraire vocal et associez-le à l’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="222bc-138">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="222bc-139">Cette commande crée une nouvelle route vocale en ligne avec l’identité « analogique-interop » pour la plage de nombres +1425 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="222bc-139">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="222bc-140">L’itinéraire vocal est applicable à une liste de passerelles en sbc.contoso.com et associe l’itinéraire à l’utilisation PSTN en ligne « Interop ».</span><span class="sxs-lookup"><span data-stu-id="222bc-140">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="222bc-141">Une route vocale inclut une expression régulière qui identifie les numéros de téléphone qui seront acheminés via une route vocale donnée :</span><span class="sxs-lookup"><span data-stu-id="222bc-141">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="222bc-142">Étape 4 : affecter la route vocale à l’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="222bc-142">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="222bc-143">Cette commande crée une stratégie de routage voix en ligne par utilisateur avec l’identité « AnalogInteropPolicy ».</span><span class="sxs-lookup"><span data-stu-id="222bc-143">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="222bc-144">Cette stratégie n’a qu’une utilisation PSTN en ligne : « Interop ».</span><span class="sxs-lookup"><span data-stu-id="222bc-144">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="222bc-145">Étape 5 : activer l’utilisateur en ligne</span><span class="sxs-lookup"><span data-stu-id="222bc-145">Step 5: Enable the online user</span></span>

<span data-ttu-id="222bc-146">Cette commande modifie le compte d’utilisateur avec le groupe de exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="222bc-146">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="222bc-147">Dans ce cas, le compte est modifié pour activer Voix Entreprise, implémentation Microsoft de VoIP, avec la messagerie vocale activée et affecte le numéro +1425500000 à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="222bc-147">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="222bc-148">Cette commande doit être exécuté pour chaque Teams utilisateur (à l’exception des utilisateurs d’appareils ATA) dans le client de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="222bc-148">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="222bc-149">Étape 6 : affecter la stratégie de route vocale à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="222bc-149">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="222bc-150">Cette commande affecte la stratégie de routage vocal en ligne per-user AnalogInteropPolicy à l’utilisateur ayant le exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="222bc-150">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="222bc-151">Cette commande doit être exécuté pour chaque Teams utilisateur (à l’exception des utilisateurs d’appareils ATA) dans le client de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="222bc-151">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="222bc-152">Étape 7 : créer une route vocale pour un appareil analogique</span><span class="sxs-lookup"><span data-stu-id="222bc-152">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="222bc-153">Cette commande crée un itinéraire vocal en ligne avec l’identité « analogique-interop » pour la plage de nombres +1425 4XX XX XX applicable à une liste de passerelles en ligne sbc.contoso.com et l’associe à l’utilisation PSTN en ligne « Interop ».</span><span class="sxs-lookup"><span data-stu-id="222bc-153">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="222bc-154">Cette commande doit être exécuté pour chaque appareil analogique ayant un modèle de numéro de téléphone approprié.</span><span class="sxs-lookup"><span data-stu-id="222bc-154">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="222bc-155">Vous pouvez également utiliser un modèle de nombre approprié pour les dispositifs analogiques lors de la configuration de la route vocale en ligne au cours de l’une des étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="222bc-155">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="222bc-156">Considérations</span><span class="sxs-lookup"><span data-stu-id="222bc-156">Considerations</span></span>

- <span data-ttu-id="222bc-157">Sauf indication contraire, un appareil analogique est tout appareil qui peut envoyer des chiffres DTMF pour passer un appel.</span><span class="sxs-lookup"><span data-stu-id="222bc-157">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="222bc-158">Par exemple, des téléphones analogiques, des télécopieurs et des pages généraux.</span><span class="sxs-lookup"><span data-stu-id="222bc-158">For example, analog phones, fax machines, and overhead pagers.</span></span>

- <span data-ttu-id="222bc-159">Les téléphones analogiques connectés à un ata ne peuvent pas faire l’objet d’Teams.</span><span class="sxs-lookup"><span data-stu-id="222bc-159">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="222bc-160">Teams utilisateurs doivent entrer manuellement le numéro de téléphone associé à l’appareil pour appeler ce périphérique.</span><span class="sxs-lookup"><span data-stu-id="222bc-160">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="222bc-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="222bc-161">See also</span></span>

[<span data-ttu-id="222bc-162">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="222bc-162">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="222bc-163">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="222bc-163">Configure Direct Routing</span></span>](direct-routing-configure.md)
