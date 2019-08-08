---
title: Configurer le serveur Video Interop dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Résumé: configurez le rôle serveur d’interopérabilité vidéo (a) dans Skype entreprise Server.'
ms.openlocfilehash: 9ac7b64b33c48bd4010c1431b5c0d658f223599a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235680"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="d9f20-103">Configurer le serveur Video Interop dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d9f20-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="d9f20-104">**Résumé:** Configurez le rôle serveur d’interopérabilité vidéo (a) dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d9f20-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="d9f20-105">Configurez les paramètres qui seront associés aux Trunks vidéo à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9f20-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="d9f20-106">Une configuration de Trunk vidéo avec étendue globale est créée une fois le service à l’aide de l’installation.</span><span class="sxs-lookup"><span data-stu-id="d9f20-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="d9f20-107">Cette configuration de Trunk vidéo est appliquée par le biais de tous les Trunks qui n’ont pas de configuration de Trunk vidéo avec une étendue plus spécifique.</span><span class="sxs-lookup"><span data-stu-id="d9f20-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="d9f20-108">Notez que la configuration de Trunk vidéo est une collection de paramètres applicables aux Trunks vidéo.</span><span class="sxs-lookup"><span data-stu-id="d9f20-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="d9f20-109">Configurer le tronçon vidéo et le plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="d9f20-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="d9f20-110">Utilisez les commandes Windows PowerShell suivantes pour spécifier la configuration de Trunk vidéo et le plan de numérotation à associer aux liaisons nouvellement définies définies dans le document topologique entre le VIS et toutes les passerelles vidéo.</span><span class="sxs-lookup"><span data-stu-id="d9f20-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="d9f20-111">Tous ces paramètres sont configurables aux niveaux global, du site ou du service (passerelle vidéo).</span><span class="sxs-lookup"><span data-stu-id="d9f20-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="d9f20-112">Un plan de numérotation avec étendue globale est créé par déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d9f20-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="d9f20-113">Ce plan de numérotation est appliqué par tous les ISL qui n’ont pas de plan de numérotation ayant une étendue plus précise.</span><span class="sxs-lookup"><span data-stu-id="d9f20-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="d9f20-114">Configurer l’utilisation de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9f20-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="d9f20-115">Créez une nouvelle configuration de Trunk vidéo (collection de paramètres) à utiliser sur le Trunk entre le directeur des communications unifiées (CallManager ou CUCM), à l’aide de l’applet de commande Windows PowerShell suivante:</span><span class="sxs-lookup"><span data-stu-id="d9f20-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="d9f20-116">S’il existe déjà un Trunk vidéo qui doit être modifié, utilisez l’applet de commande Windows PowerShell suivante:</span><span class="sxs-lookup"><span data-stu-id="d9f20-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="d9f20-117">Pour afficher les paramètres associés à une configuration de Trunk vidéo particulière, utilisez l’applet de commande Windows PowerShell suivante:</span><span class="sxs-lookup"><span data-stu-id="d9f20-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="d9f20-118">Pour supprimer une configuration de Trunk vidéo particulière, utilisez l’applet de commande Windows PowerShell suivante (Notez que la configuration de Trunk vidéo avec étendue globale) est appliquée si une configuration de Trunk vidéo de niveau supérieur n’est pas spécifiquement définie pour un Trunk particulier.</span><span class="sxs-lookup"><span data-stu-id="d9f20-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="d9f20-119">Établissez un plan de numérotation à associer au Trunk, à l’aide des applets de commande Windows PowerShell suivantes:</span><span class="sxs-lookup"><span data-stu-id="d9f20-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="d9f20-120">La commande **Remove-CsVoiceNormalizationRule** est nécessaire pour remplacer une règle par défaut afin qu’elle n’interfère pas avec l’interaction CUCM ou du VIS attendue.</span><span class="sxs-lookup"><span data-stu-id="d9f20-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="d9f20-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) peut être utilisé pour supprimer un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="d9f20-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="d9f20-122">Dans le cas d’un appel vidéo en ligne SIP à partir d’une passerelle vidéo dont l’URI de la demande contient un numéro non-E. 164, l’accent lira le nom du plan de numérotation associé au Trunk associé et inclura le nom du plan de numérotation dans la partie contexte du téléphone de l’URI de la requête S envoie au premier plan.</span><span class="sxs-lookup"><span data-stu-id="d9f20-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="d9f20-123">L’application de traduction sur le front end extrait et applique les règles de normalisation associées au plan de numérotation à l’URI de requête.</span><span class="sxs-lookup"><span data-stu-id="d9f20-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="d9f20-124">Options de configuration de tronçon</span><span class="sxs-lookup"><span data-stu-id="d9f20-124">Trunk configuration options</span></span>

<span data-ttu-id="d9f20-125">Les applets de décision Windows PowerShell pour la configuration de Trunk vidéo mentionnées précédemment étaient nouvelles dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d9f20-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="d9f20-126">Les paramètres associés à la configuration de tronçon vidéo requièrent une brève explication.</span><span class="sxs-lookup"><span data-stu-id="d9f20-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="d9f20-127">**GatewaySendsRtcpForActiveCalls** Ce paramètre détermine si les paquets RTCP sont envoyés à partir du VTC à l’envers pour les appels actifs.</span><span class="sxs-lookup"><span data-stu-id="d9f20-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="d9f20-128">Un appel actif dans ce contexte désigne un appel qui est autorisé à voyager dans au moins une direction.</span><span class="sxs-lookup"><span data-stu-id="d9f20-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="d9f20-129">Si le paramètre GatewaySendsRtcpForActiveCalls est défini sur True, le serveur d’interopérabilité vidéo (VIS) peut mettre fin à un appel s’il ne reçoit aucun paquet RTCP dans un délai de plus de 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="d9f20-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="d9f20-130">La valeur par défaut est **True**.</span><span class="sxs-lookup"><span data-stu-id="d9f20-130">The default is **True**.</span></span>
  
 <span data-ttu-id="d9f20-131">**GatewaySendsRtcpForCallsOnHold** Ce paramètre détermine si les paquets RTCP continuent d’être envoyés sur le Trunk pour les appels placés en attente et qu’aucun flux de paquets ne devait être acheminé dans chaque direction.</span><span class="sxs-lookup"><span data-stu-id="d9f20-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="d9f20-132">Le serveur d’interopérabilité vidéo (VIS) peut mettre fin à l’appel s’il ne reçoit aucun paquet RTCP du système de vidéoconférence (VTC) lorsque l’appel est en attente.</span><span class="sxs-lookup"><span data-stu-id="d9f20-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="d9f20-133">La valeur par défaut est **True**.</span><span class="sxs-lookup"><span data-stu-id="d9f20-133">The default is **True**.</span></span> <span data-ttu-id="d9f20-134">Lorsque le protocole SIPTransport est défini sur TCP, ce paramètre est ignoré.</span><span class="sxs-lookup"><span data-stu-id="d9f20-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="d9f20-135">**EnableMediaEncryptionForSipOverTls** Ce paramètre active ou désactive SRTP pour le média lorsque le protocole SIPTransport est défini sur TLS.</span><span class="sxs-lookup"><span data-stu-id="d9f20-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="d9f20-136">La valeur par défaut est **True**.</span><span class="sxs-lookup"><span data-stu-id="d9f20-136">The default is **True**.</span></span> <span data-ttu-id="d9f20-137">Lorsque le protocole SIPTransport est défini sur TCP, ce paramètre est ignoré.</span><span class="sxs-lookup"><span data-stu-id="d9f20-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="d9f20-138">**EnableSessionTimer** Ce paramètre active ou désactive les minuteurs de session à l’extrémité de chaque boîte de dialogue SIP associée au Trunk vidéo SIP.</span><span class="sxs-lookup"><span data-stu-id="d9f20-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="d9f20-139">La valeur par défaut est **False**.</span><span class="sxs-lookup"><span data-stu-id="d9f20-139">The default is **False**.</span></span>
  
 <span data-ttu-id="d9f20-140">**ForwardErrorCorrectionType** Ce paramètre est utilisé pour déterminer si la correction d’erreur de transfert (FEC) pour les flux vidéo doit être appliquée sur la jambe entre le serveur Video Interop et une passerelle vidéo.</span><span class="sxs-lookup"><span data-stu-id="d9f20-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="d9f20-141">La définition de ForwardErrorCorrectionType sur «None» désactive la fonction FEC entre et la passerelle vidéo/VTC.</span><span class="sxs-lookup"><span data-stu-id="d9f20-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="d9f20-142">La définition de ForwardErrorCorrectionType sur «Cisco» autorise la compatibilité FEC avec les passerelles vidéo de Cisco, telles que Cisco Unified Communications Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="d9f20-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="d9f20-143">La valeur par défaut est **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="d9f20-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d9f20-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d9f20-144">See also</span></span>

[<span data-ttu-id="d9f20-145">Configurer CUCM pour l’interopérabilité avec Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d9f20-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
