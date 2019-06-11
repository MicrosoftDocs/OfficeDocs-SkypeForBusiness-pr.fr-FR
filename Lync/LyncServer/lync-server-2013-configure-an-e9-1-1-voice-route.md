---
title: 'Lync Server 2013: configuration d’une voie vocale E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59f4e2a6707d270f66a66663b19f975ac69961c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a><span data-ttu-id="492a1-102">Configurer un itinéraire vocal E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="492a1-102">Configure an E9-1-1 voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="492a1-103">_**Dernière modification de la rubrique:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="492a1-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="492a1-104">Pour déployer E9-1-1, vous devez d’abord configurer un itinéraire des communications vocales pour les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="492a1-104">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="492a1-105">Pour plus d’informations sur la création d’itinéraires vocaux, voir [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="492a1-105">For details about creating voice routes, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span> <span data-ttu-id="492a1-106">Vous pouvez définir plusieurs itinéraires si, par exemple, votre déploiement comporte une jonction SIP (Session Initiation Protocol) principale et une jonction SIP secondaire.</span><span class="sxs-lookup"><span data-stu-id="492a1-106">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="492a1-107">Pour inclure des informations d’emplacement dans une invitation E9-1-1, vous devez configurer le Trunk SIP qui se connecte au fournisseur de services E9-1-1 pour diriger les appels d’urgence par le biais de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="492a1-107">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="492a1-108">Pour ce faire, définissez l’indicateur EnablePIDFLOSupport sur la cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> sur true.</span><span class="sxs-lookup"><span data-stu-id="492a1-108">To do this, set the EnablePIDFLOSupport flag on the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to True.</span></span> <span data-ttu-id="492a1-109">La valeur par défaut de EnablePIDFLOSupport est false.</span><span class="sxs-lookup"><span data-stu-id="492a1-109">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="492a1-110">Par exemple:<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span><span class="sxs-lookup"><span data-stu-id="492a1-110">For example: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span></span><BR><span data-ttu-id="492a1-111">Il n’est pas nécessaire d’activer la réception des emplacements pour les passerelles du réseau téléphonique commuté (RTC) et les passerelles ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="492a1-111">It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>



</div>

<span data-ttu-id="492a1-112">Pour plus d’informations sur l’utilisation des itinéraires vocaux, voir la documentation Lync Server Management Shell pour les applets de commande suivantes:</span><span class="sxs-lookup"><span data-stu-id="492a1-112">For details about working with voice routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="492a1-113">**Set-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="492a1-113">**Set-CsPstnUsage**</span></span>

  - <span data-ttu-id="492a1-114">**Get-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="492a1-114">**Get-CsPstnUsage**</span></span>

  - <span data-ttu-id="492a1-115">**Nouveau-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="492a1-115">**New-CsVoiceRoute**</span></span>

  - <span data-ttu-id="492a1-116">**Get-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="492a1-116">**Get-CsVoiceRoute**</span></span>

  - <span data-ttu-id="492a1-117">**Set-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="492a1-117">**Set-CsVoiceRoute**</span></span>

  - <span data-ttu-id="492a1-118">**Remove-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="492a1-118">**Remove-CsVoiceRoute**</span></span>

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="492a1-119">Pour configurer un itinéraire des communications vocales E9-1-1</span><span class="sxs-lookup"><span data-stu-id="492a1-119">To configure an E9-1-1 voice route</span></span>

1.  <span data-ttu-id="492a1-120">Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’administration CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="492a1-120">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>

2.  <span data-ttu-id="492a1-121">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="492a1-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="492a1-122">Exécutez l’applet de commande ci-dessous pour créer un enregistrement d’utilisation RTC.</span><span class="sxs-lookup"><span data-stu-id="492a1-122">Run the following cmdlet to create a new PSTN usage record.</span></span>
    
    <span data-ttu-id="492a1-123">Ce nom doit être identique à celui que vous utiliserez pour le paramètre **RTC** de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="492a1-123">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="492a1-124">Si votre déploiement comporte plusieurs enregistrements d’utilisation téléphonique, l’exemple ci-dessous ajoute « Emergency Usage » (Utilisation d’urgence) à la liste actuelle des utilisations RTC disponibles.</span><span class="sxs-lookup"><span data-stu-id="492a1-124">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="492a1-125">Pour plus d’informations, reportez-vous [à configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités et privilèges d’utilisation dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="492a1-125">For details, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  <span data-ttu-id="492a1-126">Exécutez l’applet de commande ci-dessous pour créer un itinéraire des communications vocales à l’aide de l’enregistrement d’utilisation RTC créé lors de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="492a1-126">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="492a1-127">Le modèle de numéro doit être identique à celui utilisé dans le paramètre **Chaîne de numérotation d’urgence** de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="492a1-127">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="492a1-128">Le signe "+" est nécessaire car Lync ajoute "+" aux appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="492a1-128">A "+" sign is needed because Lync adds "+" to emergency calls.</span></span> <span data-ttu-id="492a1-129">« Co1-pstngateway-1 » est l’ID du service de jonction SIP (Session Initiation Protocol) pour le fournisseur de services E9-1-1 ou l’ID du service de passerelle ELIN.</span><span class="sxs-lookup"><span data-stu-id="492a1-129">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="492a1-130">L’exemple ci-dessous utilise « EmergencyRoute » comme nom de l’itinéraire des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="492a1-130">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  <span data-ttu-id="492a1-p105">Pour les connexions à une jonction SIP (Session Initiation Protocol), nous vous conseillons éventuellement d’exécuter l’applet de commande ci-dessous pour créer un itinéraire local pour les appels qui ne sont pas gérés par la jonction SIP du fournisseur de services E9-1-1. Cet itinéraire est utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="492a1-p105">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available.</span></span>
    
    <span data-ttu-id="492a1-133">L’exemple ci-dessous part du principe que l’utilisateur a une utilisation « locale » dans sa stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="492a1-133">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

