---
title: Configurer le serveur d’interopérabilité vidéo dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Résumé : Configurez le rôle de serveur d’interopérabilité vidéo (VIS) dans Skype pour Business Server.'
ms.openlocfilehash: 64a3baa9374b819fc16a77a12a18a906c8e09225
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894527"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="f9aeb-103">Configurer le serveur d’interopérabilité vidéo dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="f9aeb-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="f9aeb-104">**Résumé :** Configurez le rôle de serveur d’interopérabilité vidéo (VIS) dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="f9aeb-105">Configurer les paramètres du rapport associer des jonctions vidéo à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="f9aeb-106">Une configuration de jonction vidéo avec une étendue globale est créée une fois que le service de rapport est installé.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="f9aeb-107">Cette configuration de jonction vidéo est appliquée à l’égard à toutes les jonctions qui n’ont pas de configuration de jonction vidéo avec une étendue plus spécifique.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="f9aeb-108">Notez que la configuration de tronçon vidéo est une collection de paramètres qui s’applique à jonctions vidéo.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="f9aeb-109">Configurer le tronçon vidéo et le plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="f9aeb-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="f9aeb-110">Utiliser les commandes Windows PowerShell suivantes pour spécifier la configuration de jonction vidéo et la numérotation plan sera associé à la trunk(s) nouvellement défini définis dans le Document de topologie entre les VIS et toutes les passerelles vidéo.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="f9aeb-111">Tous ces paramètres sont configurables aux niveaux global, du site ou du service (passerelle vidéo).</span><span class="sxs-lookup"><span data-stu-id="f9aeb-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="f9aeb-112">Un plan de numérotation avec une étendue globale est créé par Skype pour le déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="f9aeb-113">Ce plan de numérotation est appliqué par rapport à toutes les jonctions qui ne disposent pas d’un accès à planifier avec une étendue plus spécifique.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="f9aeb-114">Configurer le rapport à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9aeb-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="f9aeb-115">Créer une nouvelle configuration de jonction vidéo (une collection de paramètres) afin d’utiliser sur la jonction entre la VIS et Cisco Unified Communications Manager (CallManager ou CUCM), à l’aide de l’applet de commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="f9aeb-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="f9aeb-116">S’il existe une jonction existante vidéo qui doit être modifié, utilisez l’applet de commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="f9aeb-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="f9aeb-117">Pour afficher les paramètres associés à une configuration de tronçon vidéo particulier, utilisez l’applet de commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="f9aeb-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="f9aeb-118">Pour supprimer une configuration de tronçon vidéo particulier, utilisez l’applet de commande Windows PowerShell suivante (Notez que la configuration de tronçon vidéo global sera appliquée si n’est pas une configuration de jonction vidéo plus précisément étendue définie pour un tronçon particulier) :</span><span class="sxs-lookup"><span data-stu-id="f9aeb-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="f9aeb-119">Établissez un plan de numérotation à associer à la jonction, à l’aide des applets de commande Windows PowerShell suivantes :</span><span class="sxs-lookup"><span data-stu-id="f9aeb-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="f9aeb-120">La commande **Remove-CsVoiceNormalizationRule** est nécessaire pour remplacer une règle par défaut afin qu’elle n’interfère pas avec l’interaction CUCM ou du VIS attendue.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="f9aeb-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) peut être utilisée pour supprimer un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="f9aeb-122">Pour un appel vidéo de jonction SIP à partir d’une passerelle vidéo dont URI de demande contient un numéro non E.164, VIS ne lit pas le nom du plan de numérotation associé à la jonction associé et inclut le nom de plan de numérotation dans le composant de contexte téléphonique de l’URI demandé dans l’invitation que VI S envoie vers le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="f9aeb-123">L’Application de traduction sur le serveur frontal extrait et applique les règles de normalisation associées au plan de numérotation à l’URI de demande.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="f9aeb-124">Options de configuration de tronçon</span><span class="sxs-lookup"><span data-stu-id="f9aeb-124">Trunk configuration options</span></span>

<span data-ttu-id="f9aeb-125">Les applets de commande Windows PowerShell pour la configuration de jonction vidéo indiqué précédemment ont été Nouveautés Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="f9aeb-126">Les paramètres associés à la configuration de tronçon vidéo requièrent une brève explication.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="f9aeb-127">**GatewaySendsRtcpForActiveCalls** Ce paramètre détermine si des paquets RTCP sont envoyés à partir de la VTC à l’égard pour les appels actifs.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="f9aeb-128">Un appel actif dans ce contexte désigne un appel qui est autorisé à voyager dans au moins une direction.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="f9aeb-129">Si le paramètre GatewaySendsRtcpForActiveCalls est défini sur True, le serveur d’interopérabilité vidéo (VIS) peut mettre fin à un appel s’il ne reçoit aucun paquet RTCP dans un délai de plus de 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="f9aeb-130">La valeur par défaut est **True**.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-130">The default is **True**.</span></span>
  
 <span data-ttu-id="f9aeb-131">**GatewaySendsRtcpForCallsOnHold** Ce paramètre détermine si des paquets RTCP continuent d’être envoyés sur le tronçon pour les appels qui ont été mis en attente et aucune paquets de médias ne sont attendus dans les deux directions.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="f9aeb-132">Le serveur d’interopérabilité vidéo (VIS) peut mettre fin à l’appel s’il ne reçoit aucun paquet RTCP du système de vidéoconférence (VTC) lorsque l’appel est en attente.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="f9aeb-133">La valeur par défaut est **True**.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-133">The default is **True**.</span></span> <span data-ttu-id="f9aeb-134">Lorsque le protocole SIPTransport est défini sur TCP, ce paramètre est ignoré.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="f9aeb-135">**EnableMediaEncryptionForSipOverTls** Ce paramètre Active ou désactive le chiffrement SRTP pour le média lorsque le protocole SIPTransport est défini sur TLS.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="f9aeb-136">La valeur par défaut est **True**.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-136">The default is **True**.</span></span> <span data-ttu-id="f9aeb-137">Lorsque le protocole SIPTransport est défini sur TCP, ce paramètre est ignoré.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="f9aeb-138">**EnableSessionTimer** Ce paramètre Active ou désactive les temporisateurs de session sur le côté de VIS pour chaque boîte de dialogue SIP associé à la jonction SIP vidéo.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="f9aeb-139">La valeur par défaut est **False**.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-139">The default is **False**.</span></span>
  
 <span data-ttu-id="f9aeb-140">**ForwardErrorCorrectionType** Ce paramètre est utilisé pour déterminer si FEC Forward Error Correction () pour le flux vidéo doit être appliquée sur le segment entre le serveur d’interopérabilité vidéo et une passerelle vidéo.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="f9aeb-141">Paramètre ForwardErrorCorrectionType sur « None » désactive FEC entre VIS et vidéo passerelle/VTC.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="f9aeb-142">ForwardErrorCorrectionType à « Cisco » permet d’activer FEC compatible avec les passerelles vidéo par Cisco, tels que Cisco Unified Communications Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="f9aeb-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="f9aeb-143">La valeur par défaut est **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="f9aeb-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f9aeb-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f9aeb-144">See also</span></span>

[<span data-ttu-id="f9aeb-145">Configurer CUCM pour l’interopérabilité avec Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="f9aeb-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
