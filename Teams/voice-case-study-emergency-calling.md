---
title: Étude de cas de voix contoso teams
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
description: Étude de cas de voix dans teams pour les entreprises à plusieurs nationaux
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786027"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="78653-103">Étude de cas contoso : appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="78653-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="78653-104">Pour mieux comprendre la disponibilité des appels d’urgence et la terminologie liée aux appels d’urgence &mdash; , au lieu, à l’emplacement d’urgence et à l’adresse enregistrée que contoso a &mdash; examiné gérer les appels d' [urgence](what-are-emergency-locations-addresses-and-call-routing.md) et [planifier et configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md).</span><span class="sxs-lookup"><span data-stu-id="78653-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="78653-105">Dans Office 365, un utilisateur de plan d’appel est automatiquement activé pour les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="78653-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="78653-106">Toutefois, seuls les utilisateurs de plan d’appels aux États-Unis peuvent utiliser des emplacements dynamiques pour le routage des appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="78653-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="78653-107">Pour le routage direct, Contoso a appris qu’une configuration supplémentaire est nécessaire pour acheminer les appels d’urgence et éventuellement pour la connectivité des partenaires.</span><span class="sxs-lookup"><span data-stu-id="78653-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="78653-108">L’administrateur doit configurer la connexion à un fournisseur de services de routage d’urgence (ERSP) (États-Unis) ou configurer le contrôleur de bordure de session (SBC) pour une application de type ELIN (Emergency location identification).</span><span class="sxs-lookup"><span data-stu-id="78653-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="78653-109">Contoso dispose de bureaux aux États-Unis et hors des États-Unis :</span><span class="sxs-lookup"><span data-stu-id="78653-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="78653-110">Aux États-Unis, les utilisateurs du plan d’appel de contoso peuvent utiliser des emplacements dynamiques pour le routage des appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="78653-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="78653-111">Hors des États-Unis, contoso dispose de sites qui utilisent des plans d’appel et des sites qui sont connectés au système téléphonique via le routage direct.</span><span class="sxs-lookup"><span data-stu-id="78653-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="78653-112">Cas d’utilisation des appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="78653-112">Emergency calling use cases</span></span>

<span data-ttu-id="78653-113">Après avoir décidé du mode de connexion de contoso au système téléphonique, Contoso a identifié les cas d’utilisation des appels d’urgence suivants :</span><span class="sxs-lookup"><span data-stu-id="78653-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="78653-114">Utilisateur de plan d’appels aux États-Unis</span><span class="sxs-lookup"><span data-stu-id="78653-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="78653-115">Utilisateur de plan d’appel hors des États-Unis</span><span class="sxs-lookup"><span data-stu-id="78653-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="78653-116">Utilisateur qui se connecte au système téléphonique via le routage direct</span><span class="sxs-lookup"><span data-stu-id="78653-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="78653-117">Utilisateur de plan d’appels aux États-Unis</span><span class="sxs-lookup"><span data-stu-id="78653-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="78653-118">La configuration requise pour le numéro de téléphone à un emplacement d’urgence est requise.</span><span class="sxs-lookup"><span data-stu-id="78653-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="78653-119">Pour mieux comprendre ces exigences, nous avons examiné les considérations en matière [de contoso pour les offres d’appels](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="78653-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="78653-120">Sur la base de ces exigences, Contoso a décidé d’associer l’emplacement avec le numéro de téléphone lorsqu’un numéro est attribué à un utilisateur aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="78653-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="78653-121">Utilisateur de plan d’appel hors des États-Unis</span><span class="sxs-lookup"><span data-stu-id="78653-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="78653-122">Pour savoir à quel moment un numéro de téléphone doit être associé à un emplacement d’urgence, [les considérations relatives aux offres d’appels](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)sont examinées par contoso.</span><span class="sxs-lookup"><span data-stu-id="78653-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="78653-123">Selon la configuration requise, Contoso a déterminé les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="78653-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="78653-124">Contoso associe l’emplacement avec le numéro de téléphone lorsque le numéro est attribué à un utilisateur au Canada.</span><span class="sxs-lookup"><span data-stu-id="78653-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="78653-125">Contoso affectera un emplacement d’urgence lorsque le numéro de téléphone sera acquis auprès d’Office 365 ou qu’un numéro sera transféré à partir d’un autre fournisseur ou opérateur de services.</span><span class="sxs-lookup"><span data-stu-id="78653-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="78653-126">Utilisateur qui se connecte au système téléphonique via le routage direct</span><span class="sxs-lookup"><span data-stu-id="78653-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="78653-127">Pour planifier le routage d’urgence pour ce cas d’utilisation, des [considérations relatives au routage direct](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)sont examinées par contoso.</span><span class="sxs-lookup"><span data-stu-id="78653-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="78653-128">Dans la mesure où les utilisateurs de routage direct ne reçoivent pas les appels d’urgence de la même manière que les utilisateurs d’un plan d’appels, Contoso a décidé de fournir les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="78653-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="78653-129">Le routage direct peut être connecté à un fournisseur de services de routage d’urgence (ERSP).</span><span class="sxs-lookup"><span data-stu-id="78653-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="78653-130">Le routage direct peut également avoir un SBC incluant un numéro d’identification d’emplacement d’urgence (ELIN).</span><span class="sxs-lookup"><span data-stu-id="78653-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="78653-131">Considérations relatives au fournisseur de services de routage d’urgence (ERSP)</span><span class="sxs-lookup"><span data-stu-id="78653-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="78653-132">Les fournisseurs de services de routage d’urgence (ERSPs) peuvent diriger automatiquement les appels d’urgence en fonction de l’emplacement de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="78653-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="78653-133">Si un fournisseur de service de routage d’urgence est intégré à un déploiement de routage directe, les appels d’urgence disposant d’un emplacement d’acquisition dynamique seront automatiquement routés vers le point d’accès de sécurité publique (PSAPI) qui dessert cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="78653-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="78653-134">Les appels d’urgence sans emplacement acquis de manière dynamique sont d’abord prédéfinis pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel au centre de répartition approprié en fonction de l’emplacement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="78653-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="78653-135">ELIN considérations</span><span class="sxs-lookup"><span data-stu-id="78653-135">ELIN considerations</span></span>

<span data-ttu-id="78653-136">Si une application SBC ELIN est intégrée à un déploiement de routage direct, des étapes de configuration supplémentaires doivent se produire pour associer les adresses d’urgence aux numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="78653-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="78653-137">Contoso a décidé d’utiliser des contrôleurs de frontière de session qui incluent des applications d’identification d’emplacement d’urgence (ELIN).</span><span class="sxs-lookup"><span data-stu-id="78653-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="78653-138">Notification du centre de sécurité</span><span class="sxs-lookup"><span data-stu-id="78653-138">Security desk notification</span></span>

<span data-ttu-id="78653-139">La possibilité de notifier le support technique lors de la mise en place d’un appel d’urgence est disponible pour les plans d’appel Microsoft et le routage direct du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="78653-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="78653-140">Contoso a examiné les détails dans la notification du support technique pour déterminer si cela doit être configuré au bureau.</span><span class="sxs-lookup"><span data-stu-id="78653-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="78653-141">Contoso a décidé d’utiliser la notification du support technique.</span><span class="sxs-lookup"><span data-stu-id="78653-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="78653-142">Configuration</span><span class="sxs-lookup"><span data-stu-id="78653-142">Configuration</span></span> 

<span data-ttu-id="78653-143">Contoso a suivi les étapes décrites dans [configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md) pour :</span><span class="sxs-lookup"><span data-stu-id="78653-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="78653-144">Attribution d’adresses de secours</span><span class="sxs-lookup"><span data-stu-id="78653-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="78653-145">Configurer les paramètres réseau</span><span class="sxs-lookup"><span data-stu-id="78653-145">Configure network settings</span></span> 

- <span data-ttu-id="78653-146">Configurer le service d’information d’emplacement</span><span class="sxs-lookup"><span data-stu-id="78653-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="78653-147">Configurer des stratégies d’urgence</span><span class="sxs-lookup"><span data-stu-id="78653-147">Configure emergency policies</span></span> 

- <span data-ttu-id="78653-148">Activer les utilisateurs et les sites</span><span class="sxs-lookup"><span data-stu-id="78653-148">Enable users and sites</span></span> 

- <span data-ttu-id="78653-149">Tester les appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="78653-149">Test emergency calling</span></span> 

<span data-ttu-id="78653-150">Une fois les appels d’urgence dynamiques configurés, Contoso a besoin d’affecter l’emplacement à l’utilisateur approprié.</span><span class="sxs-lookup"><span data-stu-id="78653-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="78653-151">Pour ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation, Contoso a suivi les étapes décrites dans [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="78653-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="78653-152">Pour créer des lieux de bâtiment, de planchers et de bureaux, Contoso a suivi les étapes décrites dans [Ajouter, modifier ou supprimer un emplacement pour un emplacement d’urgence](add-change-remove-emergency-place-organization.md) .</span><span class="sxs-lookup"><span data-stu-id="78653-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="78653-153">Pour attribuer un emplacement d’urgence, Contoso a suivi les étapes décrites dans [affecter ou modifier un emplacement d’urgence pour un utilisateur](assign-change-emergency-location-user.md).</span><span class="sxs-lookup"><span data-stu-id="78653-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 