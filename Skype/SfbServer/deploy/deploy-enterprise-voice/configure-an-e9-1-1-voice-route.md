---
title: Configuration d’un itinéraire des communications vocales E9-1-1 dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configurer des itinéraires de voix E9-1-1 dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 17614a4daedfdfe437a09858649972ca1c3e779d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server-2015"></a><span data-ttu-id="ca5bd-103">Configuration d’un itinéraire des communications vocales E9-1-1 dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="ca5bd-103">Configure an E9-1-1 voice route in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ca5bd-104">Configurer des itinéraires de voix E9-1-1 dans Skype pour Business Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="ca5bd-105">Pour déployer E9-1-1, vous devez d’abord configurer un itinéraire des communications vocales pour les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="ca5bd-106">Pour plus d’informations sur la création d’itinéraires de la voix, consultez [créer ou modifier un itinéraire de voix dans Skype pour 2015 de Business](create-or-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="ca5bd-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business 2015](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="ca5bd-107">Vous pouvez définir plusieurs itinéraires si, par exemple, votre déploiement comporte une jonction SIP (Session Initiation Protocol) principale et une jonction SIP secondaire.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ca5bd-108">Pour inclure des informations d’emplacement dans une invitation de E9-1-1, vous devez configurer le SIP trunk qui se connecte au fournisseur de services pour acheminer les appels d’urgence via la passerelle E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="ca5bd-109">Pour ce faire, définissez l’indicateur EnablePIDFLOSupport sur l’applet de commande **Set-CsTrunkConfiguration** à True.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="ca5bd-110">La valeur par défaut de EnablePIDFLOSupport a la valeur False.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="ca5bd-111">Par exemple : `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` il n’est pas nécessaire d’activer les emplacements de réception pour le secours commuté passerelles réseau (RTPC) de téléphone et numéro d’Identification de secours emplacement (ELIN).</span><span class="sxs-lookup"><span data-stu-id="ca5bd-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="ca5bd-112">Pour configurer un itinéraire des communications vocales E9-1-1</span><span class="sxs-lookup"><span data-stu-id="ca5bd-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="ca5bd-113">Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’administration CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="ca5bd-114">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ca5bd-115">Exécutez l’applet de commande ci-dessous pour créer un enregistrement d’utilisation RTC.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="ca5bd-116">Ce nom doit être identique à celui que vous utiliserez pour le paramètre **RTC** de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="ca5bd-117">Si votre déploiement comporte plusieurs enregistrements d’utilisation téléphonique, l’exemple ci-dessous ajoute « Emergency Usage » (Utilisation d’urgence) à la liste actuelle des utilisations RTC disponibles.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="ca5bd-118">Pour plus d’informations, consultez [configurer les stratégies de voix, les enregistrements d’utilisation de TLS et les itinéraires de voix dans Skype pour entreprise 2015](voice-and-pstn.md).</span><span class="sxs-lookup"><span data-stu-id="ca5bd-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015](voice-and-pstn.md).</span></span>
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="ca5bd-119">Exécutez l’applet de commande ci-dessous pour créer un itinéraire des communications vocales à l’aide de l’enregistrement d’utilisation RTC créé lors de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="ca5bd-120">Le modèle de numéro doit être identique à celui utilisé dans le paramètre **Chaîne de numérotation d’urgence** de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="ca5bd-121">Un signe « + » est nécessaire parce que Skype pour entreprise ajoute « + » pour les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="ca5bd-122">« Co1-pstngateway-1 » est l’ID du service de jonction SIP (Session Initiation Protocol) pour le fournisseur de services E9-1-1 ou l’ID du service de passerelle ELIN.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="ca5bd-123">L’exemple ci-dessous utilise « EmergencyRoute » comme nom de l’itinéraire des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

   ```

5. <span data-ttu-id="ca5bd-124">Éventuellement, pour les connexions de jonction SIP, nous vous conseillons d’exécuter l’applet de commande suivante pour créer un itinéraire local pour les appels qui ne sont pas gérés par trunk SIP du fournisseur de services E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="ca5bd-125">Cet itinéraire est utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="ca5bd-126">L’exemple ci-dessous part du principe que l’utilisateur a une utilisation « locale » dans sa stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="ca5bd-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


