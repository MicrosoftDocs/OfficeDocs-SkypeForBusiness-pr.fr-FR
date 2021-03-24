---
title: Plans d’appel dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Déterminez quel plan d’appel système Microsoft Phone sera le plus efficace pour votre organisation sur Cloud Voice dans Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102730"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="41cd5-103">Quelle forfait d’appels vous convient le mieux ?</span><span class="sxs-lookup"><span data-stu-id="41cd5-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="41cd5-104">Vous avez terminé la [mise en place.](get-started-with-teams-quick-start.md)</span><span class="sxs-lookup"><span data-stu-id="41cd5-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="41cd5-105">Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="41cd5-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="41cd5-106">Vous avez peut-être déployé [des réunions & conférences.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="41cd5-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="41cd5-107">Vous êtes maintenant prêt à ajouter des charges de travail vocales dans le cloud et vous avez décidé d’utiliser Microsoft Phone System avec le plan d’appel pour vous connecter au réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="41cd5-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="41cd5-108">Cet article décrit les principales décisions de déploiement pour les plans d’appels, ainsi que des considérations supplémentaires que vous pouvez configurer en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="41cd5-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="41cd5-109">Pour plus d’informations sur les offres vocales cloud de Microsoft, vous devez également lire cloud Voice dans [Microsoft Teams.](cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="41cd5-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="41cd5-110">En savoir plus sur les forfaits d’appels</span><span class="sxs-lookup"><span data-stu-id="41cd5-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="41cd5-111">Les articles suivants fournissent des informations supplémentaires sur le déploiement et l’utilisation des plans d’appel Microsoft :</span><span class="sxs-lookup"><span data-stu-id="41cd5-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="41cd5-112">Système téléphonique dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="41cd5-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="41cd5-113">Forfaits d’appels pour Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="41cd5-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="41cd5-114">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="41cd5-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="41cd5-115">Décisions liées au déploiement Core</span><span class="sxs-lookup"><span data-stu-id="41cd5-115">Core deployment decisions</span></span>

<span data-ttu-id="41cd5-116">Pour utiliser Microsoft comme opérateur de téléphonie, vous devez obtenir des licences Forfait d’appels et les affecter à vos utilisateurs Phone System.</span><span class="sxs-lookup"><span data-stu-id="41cd5-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="41cd5-117">Deux types de forfaits d’appels sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="41cd5-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="41cd5-118">Forfaits d’appels nationaux</span><span class="sxs-lookup"><span data-stu-id="41cd5-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="41cd5-119">Forfaits d’appels nationaux et internationaux</span><span class="sxs-lookup"><span data-stu-id="41cd5-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="41cd5-120">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="41cd5-120">Ask yourself</span></span>|<span data-ttu-id="41cd5-121">Action</span><span class="sxs-lookup"><span data-stu-id="41cd5-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="41cd5-122">Des forfaits d’appels sont-ils disponibles dans ma région ?</span><span class="sxs-lookup"><span data-stu-id="41cd5-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="41cd5-123">Quels emplacements utilisateur auront le service Forfait d’appels ?</span><span class="sxs-lookup"><span data-stu-id="41cd5-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="41cd5-124">Pour plus d’informations, consultez la disponibilité des pays et régions pour les plans [d’audioconférence et d’appel.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="41cd5-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="41cd5-125">Mes utilisateurs ont-ils besoin d’appels internationaux ?</span><span class="sxs-lookup"><span data-stu-id="41cd5-125">Do my users need international calling?</span></span> | <span data-ttu-id="41cd5-126">Pour plus d’informations, [voir Forfaits d’appels pour Microsoft 365 ou Office 365.](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="41cd5-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="41cd5-127">Mes utilisateurs ont-ils des licences Forfaits d’appels ?</span><span class="sxs-lookup"><span data-stu-id="41cd5-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="41cd5-128">Pour acheter et attribuer des licences, voir [l’étape 2 : acheter et attribuer des licences.](set-up-calling-plans.md#step-2-buy-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="41cd5-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="41cd5-129">Mes utilisateurs ont-ils chacun un numéro de téléphone directement vers l’intérieur ?</span><span class="sxs-lookup"><span data-stu-id="41cd5-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="41cd5-130">Pour obtenir des numéros de téléphone, voir [l’étape 3 : obtenir des numéros de téléphone.](set-up-calling-plans.md#step-3-get-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="41cd5-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="41cd5-131">Transférer des numéros de téléphone vers Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="41cd5-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="41cd5-132">Il est facile de transférer vos numéros de téléphone de votre fournisseur de services actuel vers Teams.</span><span class="sxs-lookup"><span data-stu-id="41cd5-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="41cd5-133">Une fois vos numéros de téléphone portés vers Teams, Microsoft devient votre fournisseur de services et vous facture pour ces numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="41cd5-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="41cd5-134">Pour plus d’informations, voir [Transférer des numéros de téléphone dans Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="41cd5-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="41cd5-135">Numéros de téléphone et emplacements d'urgence</span><span class="sxs-lookup"><span data-stu-id="41cd5-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="41cd5-136">Avec les forfaits d’appels dans Microsoft 365 ou Office 365, chaque utilisateur de votre organisation doit avoir un numéro de téléphone à composer directement vers l’intérieur et une adresse de secours validée correspondante.</span><span class="sxs-lookup"><span data-stu-id="41cd5-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="41cd5-137">Vous pouvez également spécifier un emplacement d’urgence à l’intérieur de l’adresse de secours (par exemple, un numéro de bureau ou un numéro d’étage).</span><span class="sxs-lookup"><span data-stu-id="41cd5-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="41cd5-138">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="41cd5-138">Ask yourself</span></span>|<span data-ttu-id="41cd5-139">Action</span><span class="sxs-lookup"><span data-stu-id="41cd5-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="41cd5-140">Comment puis-je obtenir les informations détaillées sur l’adresse d’urgence et l’emplacement ?</span><span class="sxs-lookup"><span data-stu-id="41cd5-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="41cd5-141">Pour plus d’informations, voir Que sont les [emplacements d’urgence,](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)les adresses de secours et le routage des appels ?</span><span class="sxs-lookup"><span data-stu-id="41cd5-141">For more information, see [What are emergency locations, addresses, and call routing?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="41cd5-142">Identité d’appel</span><span class="sxs-lookup"><span data-stu-id="41cd5-142">Calling identity</span></span>

<span data-ttu-id="41cd5-143">Par défaut, tous les appels sortants utilisent le numéro de téléphone affecté comme identité d’appel (ID de l’appelant).</span><span class="sxs-lookup"><span data-stu-id="41cd5-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="41cd5-144">Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel.</span><span class="sxs-lookup"><span data-stu-id="41cd5-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="41cd5-145">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="41cd5-145">Ask yourself</span></span>|<span data-ttu-id="41cd5-146">Action</span><span class="sxs-lookup"><span data-stu-id="41cd5-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="41cd5-147">Dois-je masquer ou désactiver l’ID de l’appelant ?</span><span class="sxs-lookup"><span data-stu-id="41cd5-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="41cd5-148">Pour modifier ou bloquer l’ID d’appelant, consultez définir l’ID d’appelant [d’un utilisateur.](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="41cd5-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||