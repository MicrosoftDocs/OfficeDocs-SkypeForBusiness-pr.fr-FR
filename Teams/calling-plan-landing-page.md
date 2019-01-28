---
title: Plans d’appel dans les équipes Microsoft
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: crowe
search.appverid: MET150
description: Appel de Plan de page d’accueil
appliesto:
- Microsoft Teams
ms.openlocfilehash: d3299460eeb504c53737d163a6026081775fce5d
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/28/2019
ms.locfileid: "29595387"
---
# <a name="phone-system-with-calling-plans"></a><span data-ttu-id="6bb00-103">Système téléphonique avec forfaits d’appels</span><span class="sxs-lookup"><span data-stu-id="6bb00-103">Phone System with Calling Plans</span></span> 

<span data-ttu-id="6bb00-104">Vous avez terminé la [mise en route](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="6bb00-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="6bb00-105">Vous avez déployées avec la [conversation, les équipes, les canaux, applications &](deploy-chat-teams-channels-microsoft-teams-landing-page.md) équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6bb00-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="6bb00-106">Peut-être que vous avez déployé la [conférence & de réunions](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="6bb00-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="6bb00-107">Vous êtes maintenant prêt à ajouter des charges de travail de voix dans le cloud, et vous avez décidé d’utiliser le système téléphonique de Microsoft avec l’appel de planifier pour se connecter à la Public téléphone réseau commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="6bb00-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="6bb00-108">Cet article décrit les décisions de déploiement principaux pour appeler des Plans ainsi que les considérations supplémentaires que vous souhaiterez peut-être configurer, en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6bb00-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="6bb00-109">Vous devez également lire [Cloud vocale dans les équipes Microsoft](cloud-voice-landing-page.md) pour plus d’informations sur les offres de voix de cloud de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6bb00-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="6bb00-110">Pour plus d’informations sur les Plans de l’appel</span><span class="sxs-lookup"><span data-stu-id="6bb00-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="6bb00-111">Les articles suivants fournissent plus d’informations sur le déploiement et à l’aide de l’appel des Plans de Microsoft :</span><span class="sxs-lookup"><span data-stu-id="6bb00-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="6bb00-112">Système téléphonique d'Office 365</span><span class="sxs-lookup"><span data-stu-id="6bb00-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="6bb00-113">Forfaits d'appels pour Office 365</span><span class="sxs-lookup"><span data-stu-id="6bb00-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="6bb00-114">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="6bb00-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="6bb00-115">Décisions de déploiement principaux</span><span class="sxs-lookup"><span data-stu-id="6bb00-115">Core deployment decisions</span></span>

<span data-ttu-id="6bb00-116">Pour utiliser Microsoft en tant que votre opérateur de téléphonie, vous devez obtenir des licences de l’appel de planifier et les attribuer aux utilisateurs de votre système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="6bb00-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="6bb00-117">Il existe deux types de Plans de l’appel :</span><span class="sxs-lookup"><span data-stu-id="6bb00-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="6bb00-118">Plans d’appel interne</span><span class="sxs-lookup"><span data-stu-id="6bb00-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="6bb00-119">Plans d’appel nationales et internationales</span><span class="sxs-lookup"><span data-stu-id="6bb00-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="6bb00-120">Posez-vous</span><span class="sxs-lookup"><span data-stu-id="6bb00-120">Ask yourself</span></span>|<span data-ttu-id="6bb00-121">Action</span><span class="sxs-lookup"><span data-stu-id="6bb00-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="6bb00-122">Sont des Plans de l’appel de disponibles dans mon domaine ?</span><span class="sxs-lookup"><span data-stu-id="6bb00-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="6bb00-123">Les emplacements de l’utilisateur aura l’appel de planifier le service ?</span><span class="sxs-lookup"><span data-stu-id="6bb00-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="6bb00-124">Pour plus d’informations, voir [disponibilité pays et aux régions de conférence Audio et des Plans de l’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="6bb00-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="6bb00-125">Les utilisateurs doivent-ils appels internationaux ?</span><span class="sxs-lookup"><span data-stu-id="6bb00-125">Do my users need international calling?</span></span> | <span data-ttu-id="6bb00-126">Pour plus d’informations, voir [Appel Plans pour Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="6bb00-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="6bb00-127">Mes utilisateurs ont-ils des Plans de l’appel de licences ?</span><span class="sxs-lookup"><span data-stu-id="6bb00-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="6bb00-128">Pour acheter et affecter des licences, voir [étape 2 : acheter et attribuer des licences](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="6bb00-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="6bb00-129">Mes utilisateurs ont les directe à l’intérieur de numérotation de numéro de téléphone (DID) ?</span><span class="sxs-lookup"><span data-stu-id="6bb00-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="6bb00-130">Pour obtenir les numéros de téléphone, voir [étape 3 : obtenir les numéros de téléphone](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="6bb00-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="6bb00-131">Transférer des numéros de téléphone vers Office 365</span><span class="sxs-lookup"><span data-stu-id="6bb00-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="6bb00-132">Il est facile à transférer vos numéros de téléphone de votre fournisseur de services en cours vers les équipes.</span><span class="sxs-lookup"><span data-stu-id="6bb00-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="6bb00-133">Une fois que vous le port vos numéros de téléphone aux équipes, Microsoft deviendra votre fournisseur de services et vous facture pour ces numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="6bb00-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="6bb00-134">Pour plus d’informations, voir [transférer des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="6bb00-134">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="6bb00-135">Numéros de téléphone et emplacements d'urgence</span><span class="sxs-lookup"><span data-stu-id="6bb00-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="6bb00-136">Avec des Plans de l’appel dans Office 365, tous les utilisateurs de votre organisation doit disposer d’un unique SDA direct (SDA) numéro de téléphone une adresse d’urgence validée correspondante.</span><span class="sxs-lookup"><span data-stu-id="6bb00-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="6bb00-137">Vous pouvez également spécifier un emplacement d’urgence au sein de l’adresse d’urgence (par exemple, un numéro de bureau ou numéro d’étage).</span><span class="sxs-lookup"><span data-stu-id="6bb00-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="6bb00-138">Posez-vous</span><span class="sxs-lookup"><span data-stu-id="6bb00-138">Ask yourself</span></span>|<span data-ttu-id="6bb00-139">Action</span><span class="sxs-lookup"><span data-stu-id="6bb00-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="6bb00-140">Niveau de détail voulez-vous les informations d’adresse et l’emplacement d’urgence à ?</span><span class="sxs-lookup"><span data-stu-id="6bb00-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="6bb00-141">Pour plus d’informations, voir [Quels sont les emplacements d’urgence, les adresses et le routage des appels ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="6bb00-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="6bb00-142">Identité d'appel</span><span class="sxs-lookup"><span data-stu-id="6bb00-142">Calling identity</span></span>

<span data-ttu-id="6bb00-143">Par défaut, tous les appels sortants utilisent le numéro de téléphone affecté comme identité de l’appelante (ID de l’appelant).</span><span class="sxs-lookup"><span data-stu-id="6bb00-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="6bb00-144">Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel.</span><span class="sxs-lookup"><span data-stu-id="6bb00-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="6bb00-145">Posez-vous</span><span class="sxs-lookup"><span data-stu-id="6bb00-145">Ask yourself</span></span>|<span data-ttu-id="6bb00-146">Action</span><span class="sxs-lookup"><span data-stu-id="6bb00-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="6bb00-147">Je veux masquer ou désactiver l’ID de l’appelant</span><span class="sxs-lookup"><span data-stu-id="6bb00-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="6bb00-148">Pour modifier ou bloquer l’ID d’appelant, voir [définir l’ID d’appelant pour un utilisateur](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="6bb00-148">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||




