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
ms.reviewer: crowe
search.appverid: MET150
description: Page d’accueil de plan d’appels
appliesto:
- Microsoft Teams
ms.openlocfilehash: d27169d5f65fb693ce49453f7e7c965f867198ad
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925585"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="12411-103">Quelle forfait d’appels vous convient le mieux ?</span><span class="sxs-lookup"><span data-stu-id="12411-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="12411-104">Vous avez terminé la mise en [route](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="12411-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="12411-105">Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="12411-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="12411-106">Vous avez peut-être déployé des [réunions & des conférences](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="12411-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="12411-107">Vous êtes maintenant prêt à ajouter des charges de travail vocaux Cloud et vous avez décidé d’utiliser le système Microsoft Phone avec un plan d’appels pour vous connecter au réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="12411-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="12411-108">Cet article décrit les décisions de déploiement principales pour les offres d’appel ainsi que les autres considérations que vous pouvez configurer en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="12411-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="12411-109">Pour plus d’informations sur les services vocaux Cloud de Microsoft, consultez également la [voix Cloud de Microsoft teams](cloud-voice-landing-page.md) .</span><span class="sxs-lookup"><span data-stu-id="12411-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="12411-110">En savoir plus sur les offres d’appels</span><span class="sxs-lookup"><span data-stu-id="12411-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="12411-111">Les articles suivants fournissent des informations supplémentaires sur le déploiement et l’utilisation des plans d’appel Microsoft :</span><span class="sxs-lookup"><span data-stu-id="12411-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="12411-112">Système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="12411-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="12411-113">Forfaits d’appel dans Office 365</span><span class="sxs-lookup"><span data-stu-id="12411-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="12411-114">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="12411-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="12411-115">Décisions liées au déploiement Core</span><span class="sxs-lookup"><span data-stu-id="12411-115">Core deployment decisions</span></span>

<span data-ttu-id="12411-116">Pour utiliser Microsoft comme opérateur de téléphonie, vous devez obtenir les licences de plan d’appel et les affecter aux utilisateurs de votre système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="12411-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="12411-117">Il existe deux types de plans d’appel disponibles :</span><span class="sxs-lookup"><span data-stu-id="12411-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="12411-118">Forfaits d’appels nationaux</span><span class="sxs-lookup"><span data-stu-id="12411-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="12411-119">Forfaits d’appels nationaux et internationaux</span><span class="sxs-lookup"><span data-stu-id="12411-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="12411-120">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="12411-120">Ask yourself</span></span>|<span data-ttu-id="12411-121">Action</span><span class="sxs-lookup"><span data-stu-id="12411-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="12411-122">Les offres d’appels sont-elles disponibles dans ma région ?</span><span class="sxs-lookup"><span data-stu-id="12411-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="12411-123">Quels sont les emplacements des utilisateurs disposant d’un service de plan d’appels ?</span><span class="sxs-lookup"><span data-stu-id="12411-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="12411-124">Pour plus d’informations, consultez [disponibilité du pays et de la région pour les offres d’appels audio et de services d’audioconférence](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="12411-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="12411-125">Mes utilisateurs doivent-ils utiliser les appels internationaux ?</span><span class="sxs-lookup"><span data-stu-id="12411-125">Do my users need international calling?</span></span> | <span data-ttu-id="12411-126">Pour plus d’informations, consultez la section [forfaits d’appels pour Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="12411-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="12411-127">Mes utilisateurs ont-ils des licences offres d’appels ?</span><span class="sxs-lookup"><span data-stu-id="12411-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="12411-128">Pour acheter et attribuer des licences, reportez-vous à la section [étape 2 : acheter et attribuer des licences](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="12411-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="12411-129">Mes utilisateurs ont-ils chacun un numéro de téléphone à composer directe</span><span class="sxs-lookup"><span data-stu-id="12411-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="12411-130">Pour obtenir des numéros de téléphone, reportez-vous à l' [étape 3 : obtenir des numéros de téléphone](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="12411-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="12411-131">Transférer les numéros de téléphone vers Office 365</span><span class="sxs-lookup"><span data-stu-id="12411-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="12411-132">Il est facile de transférer vos numéros de téléphone de votre fournisseur de services actuel vers Teams.</span><span class="sxs-lookup"><span data-stu-id="12411-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="12411-133">Lorsque vous transférez vos numéros de téléphone vers Teams, Microsoft deviendra votre fournisseur de services et vous facturera ces numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="12411-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="12411-134">Pour plus d’informations, consultez la section [transférer des numéros de téléphone vers teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="12411-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="12411-135">Numéros de téléphone et emplacements d'urgence</span><span class="sxs-lookup"><span data-stu-id="12411-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="12411-136">Avec les offres d’appels dans Office 365, chaque utilisateur de votre organisation doit disposer d’un numéro de téléphone unique et d’une adresse de secours validée correspondante.</span><span class="sxs-lookup"><span data-stu-id="12411-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="12411-137">Vous pouvez également spécifier un emplacement d’urgence dans une adresse de secours (par exemple, un numéro de téléphone ou un numéro de téléphone).</span><span class="sxs-lookup"><span data-stu-id="12411-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="12411-138">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="12411-138">Ask yourself</span></span>|<span data-ttu-id="12411-139">Action</span><span class="sxs-lookup"><span data-stu-id="12411-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="12411-140">Comment puis-je obtenir les informations d’adresse de secours et d’emplacement ?</span><span class="sxs-lookup"><span data-stu-id="12411-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="12411-141">Pour plus d’informations, consultez [que sont les emplacements d’urgence, les adresses de secours et le routage des appels ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="12411-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="12411-142">Identité d’appel</span><span class="sxs-lookup"><span data-stu-id="12411-142">Calling identity</span></span>

<span data-ttu-id="12411-143">Par défaut, tous les appels sortants utilisent le numéro de téléphone attribué en tant qu’identité d’appel (ID d’appelant).</span><span class="sxs-lookup"><span data-stu-id="12411-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="12411-144">Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel.</span><span class="sxs-lookup"><span data-stu-id="12411-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="12411-145">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="12411-145">Ask yourself</span></span>|<span data-ttu-id="12411-146">Action</span><span class="sxs-lookup"><span data-stu-id="12411-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="12411-147">Souhaitez-vous masquer ou désactiver l’identification de l’appelant ?</span><span class="sxs-lookup"><span data-stu-id="12411-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="12411-148">Pour modifier ou bloquer l’ID de l’appelant, voir [définir l’ID d’appelant d’un utilisateur](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="12411-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




