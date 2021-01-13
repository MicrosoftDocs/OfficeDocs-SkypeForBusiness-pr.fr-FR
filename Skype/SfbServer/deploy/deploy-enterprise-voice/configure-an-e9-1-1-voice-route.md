---
title: Configurer un itinéraire de voix E9-1-1 dans Skype Entreprise Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configurez les itinéraires de communication vocale E9-1-1 dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: b5f3d12bb586a65fc1c553a021c1a27efb0c7f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804174"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="49ba7-103">Configurer un itinéraire de voix E9-1-1 dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="49ba7-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="49ba7-104">Configurez les itinéraires de communication vocale E9-1-1 dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="49ba7-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="49ba7-105">Pour déployer E9-1-1, vous devez d’abord configurer un itinéraire des communications vocales pour les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="49ba7-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="49ba7-106">Pour plus d’informations sur la création d’itinéraires de communication vocale, voir [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="49ba7-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="49ba7-107">Vous pouvez définir plusieurs itinéraires si, par exemple, votre déploiement comporte une jonction SIP principale et une jonction SIP secondaire.</span><span class="sxs-lookup"><span data-stu-id="49ba7-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="49ba7-108">Pour inclure les informations d’emplacement dans une E9-1-1 INVITE, vous devez configurer la jonction SIP qui établit la connexion avec le fournisseur de services E9-1-1 pour acheminer les appels d’urgence par l’intermédiaire de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="49ba7-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="49ba7-109">Pour ce faire, affectez à l’indicateur EnablePIDFLOSupport de l’applet de commande **Set-CsTrunkConfiguration** la valeur True.</span><span class="sxs-lookup"><span data-stu-id="49ba7-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="49ba7-110">La valeur par défaut de EnablePIDFLOSupport est False.</span><span class="sxs-lookup"><span data-stu-id="49ba7-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="49ba7-111">Par exemple : il n’est pas nécessaire d’activer la réception d’emplacements pour les passerelles de réseau téléphonique commuté (PSTN) de secours et les `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` passerelles ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="49ba7-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="49ba7-112">Pour configurer un itinéraire des communications vocales E9-1-1</span><span class="sxs-lookup"><span data-stu-id="49ba7-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="49ba7-113">Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’administration CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="49ba7-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="49ba7-114">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="49ba7-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="49ba7-115">Exécutez l’applet de commande suivante pour créer un nouvel enregistrement d’utilisation PSTN.</span><span class="sxs-lookup"><span data-stu-id="49ba7-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="49ba7-116">Ce nom doit être identique à celui que vous utiliserez pour le paramètre **PSTN** de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="49ba7-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="49ba7-117">Si votre déploiement comporte plusieurs enregistrements d’utilisation téléphonique, l’exemple suivant ajoute « Emergency Usage » (Utilisation d’urgence) à la liste actuelle des utilisations PSTN disponibles.</span><span class="sxs-lookup"><span data-stu-id="49ba7-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="49ba7-118">Pour plus d’informations, voir [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span><span class="sxs-lookup"><span data-stu-id="49ba7-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="49ba7-119">Exécutez l’applet de commande suivante pour créer un itinéraire des communications vocales à l’aide de l’enregistrement d’utilisation PSTN créé à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="49ba7-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="49ba7-120">Le modèle de numéro doit être identique à celui utilisé dans le paramètre **Chaîne de numérotation d’urgence** de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="49ba7-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="49ba7-121">Un signe « + » est nécessaire, car Skype Entreprise ajoute « + » aux appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="49ba7-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="49ba7-122">« Co1-pstngateway-1 » est l’ID du service de jonction SIP pour le fournisseur de services E9-1-1 ou l’ID du service de passerelle ELIN.</span><span class="sxs-lookup"><span data-stu-id="49ba7-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="49ba7-123">L’exemple suivant utilise « EmergencyRoute » comme nom de l’itinéraire des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="49ba7-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="49ba7-124">Si vous le souhaitez, pour les connexions de trunk SIP, nous vous recommandons d’exécuter l’cmdlet suivante pour créer un itinéraire local pour les appels qui ne sont pas gérés par la liaison SIP du fournisseur de services E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="49ba7-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="49ba7-125">Cet itinéraire est utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="49ba7-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="49ba7-126">L’exemple suivant part du principe que l’utilisateur a une utilisation « locale » dans sa stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="49ba7-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


