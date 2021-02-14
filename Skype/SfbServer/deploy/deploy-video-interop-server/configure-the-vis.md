---
title: Configurer le serveur d’opation vidéo dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Résumé : Configurez le rôle serveur d’accès vidéo (VIS) dans Skype Entreprise Server.'
ms.openlocfilehash: 84ab821249ae388bc1ba0dc41cb980c90d4f0853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820694"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="ba9b1-103">Configurer le serveur d’opation vidéo dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ba9b1-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="ba9b1-104">**Résumé :** Configurez le rôle VIS (Video Interop Server) dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="ba9b1-105">Configurez les paramètres que le VIS associera aux trunks vidéo à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="ba9b1-106">Une fois le service VIS installé, une configuration de trunk vidéo avec une étendue globale est créée.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="ba9b1-107">Cette configuration de trunk vidéo est appliquée par le VIS à toutes les trunks qui n’ont pas de configuration de trunk vidéo avec une portée plus spécifique.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="ba9b1-108">Notez que la configuration de la vidéoconférente est une collection de paramètres applicables aux trunks vidéo.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="ba9b1-109">Configurer le plan de numérotation et le système de numérotation de la vidéo</span><span class="sxs-lookup"><span data-stu-id="ba9b1-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="ba9b1-110">Utilisez les commandes de Windows PowerShell suivantes pour spécifier la configuration de la vidéo et le plan de numérotation à associer aux nouvelles connexions définies dans le document de topologie entre le VIS et toutes les passerelles vidéo.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="ba9b1-111">Tous ces paramètres peuvent être définies aux niveaux global, site ou service (passerelle vidéo).</span><span class="sxs-lookup"><span data-stu-id="ba9b1-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="ba9b1-112">Un plan de numérotation avec une étendue globale est créé par déploiement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="ba9b1-113">Ce plan de numérotation est appliqué par le VIS à toutes les connexions qui n’ont pas de plan de numérotation avec une étendue plus spécifique.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="ba9b1-114">Configurer le VIS à l’aide Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba9b1-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="ba9b1-115">Créez une configuration de trunk vidéo (collection de paramètres) à utiliser sur la ligne entre le VIS et Cisco Unified Communications Manager (CallManager, ou CUCM), à l’aide de l’Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="ba9b1-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="ba9b1-116">Si une trunk vidéo existante doit être modifiée, utilisez l’Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="ba9b1-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="ba9b1-117">Pour afficher les paramètres associés à une configuration de trunk vidéo particulière, utilisez l’Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="ba9b1-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="ba9b1-118">Pour supprimer une configuration de vidéoconférente particulière, utilisez l’cmdlet Windows PowerShell suivante (notez que la configuration de la trunk vidéo de portée globale sera appliquée s’il n’existe pas de configuration de trunk vidéo plus spécifique pour une trunke particulière) :</span><span class="sxs-lookup"><span data-stu-id="ba9b1-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="ba9b1-119">Établissez un plan de numérotation à associer à la trunk, à l’aide des cmdlets Windows PowerShell suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba9b1-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="ba9b1-120">La **commande Remove-CsVoiceNormalizationRule** est nécessaire pour remplacer une règle par défaut qui interfère avec l’interaction VIS et CUCM attendue.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="ba9b1-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) peut être utilisé pour supprimer un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="ba9b1-122">Pour un appel de connexion SIP vidéo à partir d’une passerelle vidéo dont l’URI de demande contient un numéro autre que E.164, le VIS lit le nom du plan de numérotation associé à la connexion associée et inclut le nom du plan de numérotation dans le composant de contexte téléphonique de l’URI de demande dans l’invitation que le VIS envoie au frontal.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="ba9b1-123">L’application de traduction sur le frontal extrait et applique les règles de normalisation associées au plan de numérotation à l’URI de demande.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="ba9b1-124">Options de configuration de la trunk</span><span class="sxs-lookup"><span data-stu-id="ba9b1-124">Trunk configuration options</span></span>

<span data-ttu-id="ba9b1-125">Les Windows PowerShell cmdlets pour la configuration de la vidéoconférente mentionnées précédemment étaient nouvelles dans Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="ba9b1-126">Les paramètres associés à la configuration de la vidéoconférente nécessitent une brève explication.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="ba9b1-127">**GatewaySendsRtcpForActiveCalls** Ce paramètre détermine si des paquets RTCP sont envoyés du VTC au VIS pour les appels actifs.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="ba9b1-128">Un appel actif dans ce contexte désigne un appel qui est autorisé à voyager dans au moins une direction.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="ba9b1-129">Si GatewaySendsRtcpForActiveCalls est définie sur True, le VIS peut mettre fin à un appel s’il ne reçoit pas de paquets RTCP pendant une période supérieure à 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="ba9b1-130">La valeur par défaut est **True**.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-130">The default is **True**.</span></span>
  
 <span data-ttu-id="ba9b1-131">**GatewaySendsRtcpForCallsOnHold** Ce paramètre détermine si les paquets RTCP continuent d’être envoyés sur le secteur pour les appels qui ont été mis en attente et si aucun paquet multimédia n’est censé circuler dans les deux sens.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="ba9b1-132">Le VIS peut mettre fin à l’appel s’il n’y a aucun paquet RTCP qui circule du VTC au VIS pendant l’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="ba9b1-133">La valeur par défaut est **True**.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-133">The default is **True**.</span></span> <span data-ttu-id="ba9b1-134">Lorsque le protocole SIPTransport est définie sur TCP, ce paramètre est ignoré.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="ba9b1-135">**EnableMediaEncryptionForSipOverTls** Ce paramètre active ou désactive SRTP pour les médias lorsque le protocole SIPTransport est paramétrant sur TLS.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="ba9b1-136">La valeur par défaut est **True**.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-136">The default is **True**.</span></span> <span data-ttu-id="ba9b1-137">Lorsque le protocole SIPTransport est définie sur TCP, ce paramètre est ignoré.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="ba9b1-138">**EnableSessionTimer** Ce paramètre active ou désactive les timers de session côté VIS pour chaque boîte de dialogue SIP associée à la session SIP vidéo.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="ba9b1-139">La valeur par défaut est **False**.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-139">The default is **False**.</span></span>
  
 <span data-ttu-id="ba9b1-140">**ForwardErrorCorrectionType** Ce paramètre permet de déterminer si la correction des erreurs de retour (FEC) pour les flux vidéo doit être appliquée sur la partie entre le serveur d’opation vidéo et une passerelle vidéo.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="ba9b1-141">La définition de ForwardErrorCorrectionType sur « None » dés éteint le FEC entre le VIS et la passerelle vidéo/VTC.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="ba9b1-142">La définition de ForwardErrorCorrectionType sur « Cisco » active la compatibilité FEC avec les passerelles vidéo de Cisco, telles que Cisco Unified Communications Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="ba9b1-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="ba9b1-143">La valeur par défaut **est Aucun**.</span><span class="sxs-lookup"><span data-stu-id="ba9b1-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ba9b1-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba9b1-144">See also</span></span>

[<span data-ttu-id="ba9b1-145">Configurer CUCM pour l’interopération avec Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ba9b1-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
