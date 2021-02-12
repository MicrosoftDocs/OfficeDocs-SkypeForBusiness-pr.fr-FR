---
title: Étude de cas Teams voix Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786027"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="88011-103">Étude de cas Contoso : appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="88011-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="88011-104">Pour comprendre la disponibilité des appels d’urgence et la terminologie relatives aux appels d’urgence: Adresse d’urgence, Emplacement, Emplacement d’urgence et Adresse enregistrée. Contoso a examiné Gérer les appels d’urgence et Planifier et configurer les appels d’urgence &mdash; &mdash; [dynamiques.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="88011-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="88011-105">Dans Office 365, un utilisateur du plan d’appels est automatiquement activé pour les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="88011-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="88011-106">Seuls les utilisateurs aux États-Unis peuvent utiliser des emplacements dynamiques pour router des appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="88011-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="88011-107">Pour le routage direct, Contoso a appris que des configurations supplémentaires sont nécessaires pour router des appels d’urgence et éventuellement pour la connectivité partenaire.</span><span class="sxs-lookup"><span data-stu-id="88011-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="88011-108">L’administrateur doit configurer la connexion à un fournisseur de services de routage d’urgence (ERSP) (États-Unis) OU configurer le contrôleur de session border Controller (SBC) pour une application ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="88011-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="88011-109">Contoso a des bureaux aux États-Unis et en dehors des États-Unis :</span><span class="sxs-lookup"><span data-stu-id="88011-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="88011-110">Aux États-Unis, les utilisateurs du plan d’appels Contoso peuvent utiliser des emplacements dynamiques pour router des appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="88011-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="88011-111">En dehors des États-Unis, Contoso possède des sites qui utilisent des forfaits d’appels et d’autres qui sont connectés à Phone System via un routage direct.</span><span class="sxs-lookup"><span data-stu-id="88011-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="88011-112">Cas d’utilisation des appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="88011-112">Emergency calling use cases</span></span>

<span data-ttu-id="88011-113">Après avoir décidé comment Contoso se connectera au système téléphonique, Contoso a identifié les cas d’utilisation des appels d’urgence suivants :</span><span class="sxs-lookup"><span data-stu-id="88011-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="88011-114">Utilisateur d’un forfait d’appels aux États-Unis</span><span class="sxs-lookup"><span data-stu-id="88011-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="88011-115">Utilisateur d’un forfait d’appels en dehors des États-Unis</span><span class="sxs-lookup"><span data-stu-id="88011-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="88011-116">Utilisateur qui se connecte au système téléphonique via un routage direct</span><span class="sxs-lookup"><span data-stu-id="88011-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="88011-117">Utilisateur d’un forfait d’appels aux États-Unis</span><span class="sxs-lookup"><span data-stu-id="88011-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="88011-118">Des exigences s’offrent à vous lorsque le numéro de téléphone doit être associé à un emplacement d’urgence.</span><span class="sxs-lookup"><span data-stu-id="88011-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="88011-119">Pour comprendre ces exigences, Contoso a examiné les considérations relatives [aux forfaits d’appels.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="88011-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="88011-120">En fonction de ces exigences, Contoso a décidé d’associer l’emplacement au numéro de téléphone lorsqu’un numéro est affecté à un utilisateur aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="88011-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="88011-121">Utilisateur d’un forfait d’appels en dehors des États-Unis</span><span class="sxs-lookup"><span data-stu-id="88011-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="88011-122">Pour comprendre quand un numéro de téléphone doit être associé à un emplacement d’urgence, Contoso a examiné les considérations pour [les plans d’appels.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="88011-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="88011-123">En se basant sur les exigences, Contoso a décidé des choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="88011-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="88011-124">Contoso associe l’emplacement au numéro de téléphone lorsqu’un numéro est affecté à un utilisateur au Canada.</span><span class="sxs-lookup"><span data-stu-id="88011-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="88011-125">Contoso attribue un emplacement d’urgence lorsque le numéro de téléphone est acquis à partir d’Office 365 ou lorsqu’un numéro est transféré à partir d’un autre opérateur ou fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="88011-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="88011-126">Utilisateur qui se connecte au système téléphonique via un routage direct</span><span class="sxs-lookup"><span data-stu-id="88011-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="88011-127">Pour planifier le routage d’urgence pour ce cas d’utilisation, Contoso a examiné les considérations en relation avec [le routage direct.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="88011-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="88011-128">Étant donné que les utilisateurs du routage direct ne reçoivent pas les appels d’urgence de la même manière que les utilisateurs du plan d’appel, Contoso a dû décider comment fournir les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="88011-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="88011-129">Le routage direct peut être connecté à un fournisseur de services de routage d’urgence.</span><span class="sxs-lookup"><span data-stu-id="88011-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="88011-130">Le routage direct peut également avoir un SBC qui inclut un numéro d’identification de l’emplacement d’urgence (ELIN).</span><span class="sxs-lookup"><span data-stu-id="88011-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="88011-131">Considérations en considérations du fournisseur de services de routage d’urgence (ERSP)</span><span class="sxs-lookup"><span data-stu-id="88011-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="88011-132">Les fournisseurs de services de routage d’urgence peuvent router automatiquement les appels d’urgence en fonction de l’emplacement de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="88011-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="88011-133">Si un fournisseur de services de routage d’urgence est intégré à un déploiement de routage direct, les appels d’urgence ayant acquis dynamiquement un emplacement sont automatiquement acheminés vers le point de réponse de sécurité publique (PUBLIC Safety Answering Point) de cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="88011-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="88011-134">Les appels d’urgence sans emplacement dynamiquement acquis sont d’abord filés pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel au centre d’urgence approprié en fonction de l’emplacement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="88011-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="88011-135">Considérations ELIN</span><span class="sxs-lookup"><span data-stu-id="88011-135">ELIN considerations</span></span>

<span data-ttu-id="88011-136">Si une application ELIN SBC est intégrée dans un déploiement de routage direct, des étapes de configuration supplémentaires doivent être nécessaires pour associer les adresses de secours aux numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="88011-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="88011-137">Contoso a décidé d’utiliser des contrôleurs de session avec numéro d’identification de l’emplacement d’urgence (ELIN).</span><span class="sxs-lookup"><span data-stu-id="88011-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="88011-138">Notification du service de sécurité</span><span class="sxs-lookup"><span data-stu-id="88011-138">Security desk notification</span></span>

<span data-ttu-id="88011-139">La possibilité d’avertir le service de sécurité lorsqu’un appel d’urgence est passé est disponible pour les plans d’appels Microsoft et le routage direct du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="88011-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="88011-140">Contoso a examiné les détails de la notification du service de sécurité pour déterminer si cette configuration doit être configurée sur leur bureau</span><span class="sxs-lookup"><span data-stu-id="88011-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="88011-141">Contoso a décidé d’utiliser la notification de service de sécurité.</span><span class="sxs-lookup"><span data-stu-id="88011-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="88011-142">Configuration</span><span class="sxs-lookup"><span data-stu-id="88011-142">Configuration</span></span> 

<span data-ttu-id="88011-143">Contoso a suivi les étapes de la procédure [Configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md) pour :</span><span class="sxs-lookup"><span data-stu-id="88011-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="88011-144">Affecter des adresses de secours</span><span class="sxs-lookup"><span data-stu-id="88011-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="88011-145">Configurer les paramètres réseau</span><span class="sxs-lookup"><span data-stu-id="88011-145">Configure network settings</span></span> 

- <span data-ttu-id="88011-146">Configurer le service Informations sur l’emplacement</span><span class="sxs-lookup"><span data-stu-id="88011-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="88011-147">Configurer des stratégies d’urgence</span><span class="sxs-lookup"><span data-stu-id="88011-147">Configure emergency policies</span></span> 

- <span data-ttu-id="88011-148">Activer les utilisateurs et les sites</span><span class="sxs-lookup"><span data-stu-id="88011-148">Enable users and sites</span></span> 

- <span data-ttu-id="88011-149">Tester les appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="88011-149">Test emergency calling</span></span> 

<span data-ttu-id="88011-150">Une fois les appels d’urgence dynamiques configurés, Contoso doit affecter l’emplacement à l’utilisateur approprié.</span><span class="sxs-lookup"><span data-stu-id="88011-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="88011-151">Pour ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation, Contoso a suivi les étapes de l’étape Ajouter, modifier ou supprimer un emplacement d’urgence [pour votre organisation.](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="88011-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="88011-152">Pour créer des bâtiments, des étages et des bureaux, Contoso a suivi les étapes de l’étape Ajouter, modifier ou supprimer un emplacement [d’urgence.](add-change-remove-emergency-place-organization.md)</span><span class="sxs-lookup"><span data-stu-id="88011-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="88011-153">Pour affecter un emplacement d’urgence, Contoso a suivi les étapes de l’affectation ou de la modification d’un emplacement [d’urgence pour un utilisateur.](assign-change-emergency-location-user.md)</span><span class="sxs-lookup"><span data-stu-id="88011-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 