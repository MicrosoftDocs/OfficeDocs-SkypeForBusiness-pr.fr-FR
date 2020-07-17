---
title: Appel vocal dans le nuage dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: En savoir plus sur la fonctionnalité voix sur le Cloud et comprendre les décisions de déploiement nécessaires.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8106e5ef30b71ec82e9b1ae42f785b7a73b170a5
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158642"
---
# <a name="voice---phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="8c558-103">Options système de téléphonie vocale et connectivité PSTN</span><span class="sxs-lookup"><span data-stu-id="8c558-103">Voice - Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="8c558-104">Vous avez terminé la [Prise en main](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="8c558-105">Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c558-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="8c558-106">Vous avez peut-être déployé des [réunions & des conférences](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="8c558-107">Vous êtes désormais prêt à ajouter des fonctionnalités de voix pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8c558-107">Now you're ready to add voice capabilities for your users.</span></span> 

<span data-ttu-id="8c558-108">Voix fournit des fonctionnalités PBX (Private Branch Exchange) et des options pour la connexion au réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="8c558-108">Voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="8c558-109">Cet article vous permet de déterminer si vous avez besoin de modifier des paramètres vocaux par défaut, en fonction du profil de votre organisation et des besoins de votre entreprise, puis de vous guider dans chaque modification.</span><span class="sxs-lookup"><span data-stu-id="8c558-109">This article helps you decide whether you need to change any of the default voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="8c558-110">Nous avons fractionné les paramètres en deux groupes, en commençant par l’ensemble de [modifications que vous êtes plus susceptible de apporter](#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="8c558-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="8c558-111">Le deuxième groupe inclut les [paramètres supplémentaires](#additional-deployment-decisions) que vous souhaiterez peut-être configurer, en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c558-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="8c558-112">Nous recommandons à toutes les organisations de travailler par le biais des décisions fondamentales puis, si votre organisation a des exigences supplémentaires, de consulter les documents suivants.</span><span class="sxs-lookup"><span data-stu-id="8c558-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-voice"></a><span data-ttu-id="8c558-113">En savoir plus sur la voix</span><span class="sxs-lookup"><span data-stu-id="8c558-113">Learn more about voice</span></span>

<span data-ttu-id="8c558-114">Les articles suivants fournissent des informations supplémentaires sur le déploiement et l’utilisation des fonctionnalités vocales dans teams :</span><span class="sxs-lookup"><span data-stu-id="8c558-114">The following articles provide more information about deploying and using voice features in Teams:</span></span>

- [<span data-ttu-id="8c558-115">Système téléphonique dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="8c558-115">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="8c558-116">Système téléphonique avec forfaits d’appels</span><span class="sxs-lookup"><span data-stu-id="8c558-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="8c558-117">Routage direct via le système téléphonique</span><span class="sxs-lookup"><span data-stu-id="8c558-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="8c558-118">Détails sur les solutions téléphoniques Microsoft Telephony</span><span class="sxs-lookup"><span data-stu-id="8c558-118">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="8c558-119">Pour en savoir plus sur le système téléphonique, voir la session suivante : [Présentation du système téléphonique dans Microsoft teams](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="8c558-119">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="8c558-120">Décisions liées au déploiement Core</span><span class="sxs-lookup"><span data-stu-id="8c558-120">Core deployment decisions</span></span>

<span data-ttu-id="8c558-121">Voici les paramètres que la plupart des organisations veulent modifier (si les paramètres par défaut de Teams ne fonctionnent pas pour l’organisation).</span><span class="sxs-lookup"><span data-stu-id="8c558-121">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="8c558-122">Système téléphonique (Office 365)</span><span class="sxs-lookup"><span data-stu-id="8c558-122">Phone System (Office 365)</span></span>

<span data-ttu-id="8c558-123">Le système téléphonique est la technologie de Microsoft permettant d’activer le contrôle d’appel et les fonctionnalités de branchement privée (PBX) dans le Cloud Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c558-123">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud.</span></span> <span data-ttu-id="8c558-124">Le système téléphonique vous permet de remplacer votre système PBX existant par un ensemble de fonctionnalités directement fournies par Microsoft 365 ou Office 365 et intégré étroitement dans l’environnement de productivité Cloud de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="8c558-124">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Microsoft 365 or Office 365 and tightly integrated into the company's cloud productivity experience.</span></span>


|<span data-ttu-id="8c558-125">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8c558-125">Ask yourself</span></span>|<span data-ttu-id="8c558-126">Action</span><span class="sxs-lookup"><span data-stu-id="8c558-126">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="8c558-127">Pour quels emplacements ou bureaux d’utilisateurs puis-je implémenter un système téléphonique ?</span><span class="sxs-lookup"><span data-stu-id="8c558-127">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="8c558-128">Pour plus d’informations sur le système téléphonique, voir [qu’est-ce que le système téléphonique dans Microsoft 365 ou Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-128">For more information about Phone System, see [What is Phone System in Microsoft 365 or Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="8c558-129">Connexion au réseau téléphonique public commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="8c558-129">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="8c558-130">Pour connecter un système téléphonique au réseau téléphonique commuté (PSTN), afin que les utilisateurs puissent passer des appels téléphoniques partout dans le monde, vous disposez d’options selon les besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="8c558-130">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="8c558-131">Posez-vous les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c558-131">Ask yourself the following:</span></span>


|<span data-ttu-id="8c558-132">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8c558-132">Ask yourself</span></span>|<span data-ttu-id="8c558-133">Action</span><span class="sxs-lookup"><span data-stu-id="8c558-133">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="8c558-134">Voulez-vous utiliser le plan d’appel Microsoft comme opérateur de téléphonie ?</span><span class="sxs-lookup"><span data-stu-id="8c558-134">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="8c558-135">Pour plus d’informations, reportez-vous à la rubrique [système téléphonique avec les offres d’appels](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-135">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="8c558-136">Ai-je besoin d’utiliser mon propre opérateur de téléphonie ?</span><span class="sxs-lookup"><span data-stu-id="8c558-136">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="8c558-137">Pour plus d’informations, reportez-vous [à la rubrique système téléphonique avec routage direct](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-137">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="8c558-138">Décisions de déploiement supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8c558-138">Additional deployment decisions</span></span>

<span data-ttu-id="8c558-139">Vous souhaiterez peut-être modifier les paramètres pour les éléments suivants, en fonction des besoins et de la configuration de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="8c558-139">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="8c558-140">Messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="8c558-140">Voicemail</span></span>
- <span data-ttu-id="8c558-141">Identité d’appel</span><span class="sxs-lookup"><span data-stu-id="8c558-141">Calling identity</span></span>
- <span data-ttu-id="8c558-142">Numéros de téléphone de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8c558-142">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="8c558-143">Plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="8c558-143">Dial plans</span></span>
- <span data-ttu-id="8c558-144">Files d'attente des appels</span><span class="sxs-lookup"><span data-stu-id="8c558-144">Call queues</span></span>
- <span data-ttu-id="8c558-145">Les standards automatiques</span><span class="sxs-lookup"><span data-stu-id="8c558-145">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="8c558-146">Messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="8c558-146">Voicemail</span></span>

<span data-ttu-id="8c558-147">La messagerie vocale Cloud, optimisée par les services de boîte vocale Azure, prend en charge les dépôts de boîte vocale dans les boîtes aux lettres Exchange et ne prend pas en charge les systèmes de courrier tiers.</span><span class="sxs-lookup"><span data-stu-id="8c558-147">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn't support third-party email systems.</span></span> <span data-ttu-id="8c558-148">La messagerie vocale Cloud inclut la transcription de la boîte vocale, qui est activée par défaut pour tous les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c558-148">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="8c558-149">Les besoins de votre entreprise peuvent nécessiter la désactivation de la transcription de la boîte vocale pour des utilisateurs spécifiques ou pour tout le monde au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="8c558-149">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="8c558-150">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8c558-150">Ask yourself</span></span>|<span data-ttu-id="8c558-151">Action</span><span class="sxs-lookup"><span data-stu-id="8c558-151">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="8c558-152">Ai-je besoin d’activer la messagerie vocale Cloud ?</span><span class="sxs-lookup"><span data-stu-id="8c558-152">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="8c558-153">Pour les procédures de configuration de la messagerie vocale, consultez la rubrique [configurer la messagerie vocale Cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-153">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="8c558-154">Ai-je besoin d’activer la transcription de la messagerie vocale pour tout ou partie de mes utilisateurs ?</span><span class="sxs-lookup"><span data-stu-id="8c558-154">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="8c558-155">Pour désactiver la transcription de la boîte vocale, consultez [la rubrique Configuration des stratégies de messagerie vocale au sein de votre organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="8c558-155">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="8c558-156">Identité d’appel</span><span class="sxs-lookup"><span data-stu-id="8c558-156">Calling identity</span></span>

<span data-ttu-id="8c558-157">Par défaut, tous les appels sortants utilisent le numéro de téléphone attribué en tant qu’identité d’appel (ID d’appelant).</span><span class="sxs-lookup"><span data-stu-id="8c558-157">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="8c558-158">Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel.</span><span class="sxs-lookup"><span data-stu-id="8c558-158">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="8c558-159">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8c558-159">Ask yourself</span></span>|<span data-ttu-id="8c558-160">Action</span><span class="sxs-lookup"><span data-stu-id="8c558-160">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="8c558-161">Souhaitez-vous masquer ou désactiver l’identification de l’appelant ?</span><span class="sxs-lookup"><span data-stu-id="8c558-161">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="8c558-162">Pour modifier ou bloquer l’ID de l’appelant, voir [définir l’ID d’appelant d’un utilisateur](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-162">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="8c558-163">Numéros de téléphone de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8c558-163">Phone numbers from Microsoft</span></span>

<span data-ttu-id="8c558-164">Microsoft est doté de deux types de numéros de téléphone : les numéros d' *abonnés* (utilisateurs), qui peuvent être attribués à des utilisateurs de votre organisation et des numéros de *service* , disponibles en tant que numéros de service gratuits ou payants, qui ont une plus grande capacité d’appel simultanée que les numéros d’abonnés, et qui peuvent être attribués à des services tels que les conférences audio</span><span class="sxs-lookup"><span data-stu-id="8c558-164">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="8c558-165">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8c558-165">Ask yourself</span></span>|<span data-ttu-id="8c558-166">Action</span><span class="sxs-lookup"><span data-stu-id="8c558-166">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="8c558-167">Quels sont les emplacements des utilisateurs qui ont besoin de nouveaux numéros de téléphone de Microsoft ?</span><span class="sxs-lookup"><span data-stu-id="8c558-167">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="8c558-168">Pour plus d’informations sur l’affichage des numéros de téléphone, voir [gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) et [obtenir des numéros de téléphone pour vos utilisateurs](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-168">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="8c558-169">Quel type de numéro de téléphone (abonné ou service) ai-je besoin ?</span><span class="sxs-lookup"><span data-stu-id="8c558-169">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="8c558-170">Pour vous aider à choisir le type de numéro de téléphone dont vous avez besoin, voir [différents types de numéros de téléphone utilisés pour les offres d’appels](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-170">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="8c558-171">Comment puis-je porter des numéros de téléphone existants vers teams ?</span><span class="sxs-lookup"><span data-stu-id="8c558-171">How do I port existing phone numbers to Teams?</span></span>|<span data-ttu-id="8c558-172">Pour plus d’informations, reportez-vous à la section [transférer des numéros de téléphone vers Microsoft teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-172">For more information, see [Transfer phone numbers to Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="8c558-173">Plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="8c558-173">Dial plans</span></span>

<span data-ttu-id="8c558-174">Un plan de numérotation dans la fonctionnalité système téléphonique de Microsoft 365 ou d’Office 365 est un ensemble de règles de normalisation qui traduisent les numéros de téléphone numérotés dans un autre format (généralement le format E. 164) pour l’autorisation d’appel et le routage des appels.</span><span class="sxs-lookup"><span data-stu-id="8c558-174">A dial plan in the Phone System feature of Microsoft 365 or Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="8c558-175">Pour plus d'informations sur les plans d'appel, voir [Quels sont les plans de numérotation ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="8c558-175">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="8c558-176">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8c558-176">Ask yourself</span></span>|<span data-ttu-id="8c558-177">Action</span><span class="sxs-lookup"><span data-stu-id="8c558-177">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="8c558-178">Mon organisation a-t-elle besoin d’un plan de numérotation personnalisé ?</span><span class="sxs-lookup"><span data-stu-id="8c558-178">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="8c558-179">Pour savoir si vous avez besoin d’un plan de numérotation personnalisé, voir [planification des plans de numérotation client](what-are-dial-plans.md#planning-for-tenant-dial-plans) .</span><span class="sxs-lookup"><span data-stu-id="8c558-179">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="8c558-180">Quels sont les utilisateurs qui ont besoin d’un plan d’appel personnalisé et quel plan de numérotation client doit être attribué à chaque utilisateur ?</span><span class="sxs-lookup"><span data-stu-id="8c558-180">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="8c558-181">Pour ajouter des utilisateurs à un plan de numérotation personnalisé dans PowerShell, reportez-vous à la rubrique [création et gestion de plans de numérotation](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-181">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="8c558-182">Files d'attente des appels</span><span class="sxs-lookup"><span data-stu-id="8c558-182">Call queues</span></span>

<span data-ttu-id="8c558-183">Les files d’attente d’appels Cloud incluent des messages d’accueil qui sont utilisés lorsque quelqu’un vous appelle pour appeler un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel alors que les personnes qui appellent écoutent de la musique pendant l’attente.</span><span class="sxs-lookup"><span data-stu-id="8c558-183">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="8c558-184">Vous pouvez créer des files d’attente d’appels uniques ou multiples pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c558-184">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="8c558-185">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8c558-185">Ask yourself</span></span>|<span data-ttu-id="8c558-186">Action</span><span class="sxs-lookup"><span data-stu-id="8c558-186">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="8c558-187">Mon organisation a-t-elle besoin d’une file d’attente d’appels ?</span><span class="sxs-lookup"><span data-stu-id="8c558-187">Does my organization need call queues?</span></span> | <span data-ttu-id="8c558-188">Pour plus d’informations, reportez-vous à la rubrique [création d’une file d’attente d’appels Cloud](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) et [configuration de votre système téléphonique](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-188">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="8c558-189">Les standards automatiques</span><span class="sxs-lookup"><span data-stu-id="8c558-189">Auto attendants</span></span>

<span data-ttu-id="8c558-190">Les standards automatiques du Cloud peuvent être utilisés pour créer un système de menus pour votre organisation, qui permet aux appelants externes et internes de se déplacer dans un système de menus afin de localiser et de transférer les appels vers des utilisateurs ou services de la société au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c558-190">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="8c558-191">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8c558-191">Ask yourself</span></span>|<span data-ttu-id="8c558-192">Action</span><span class="sxs-lookup"><span data-stu-id="8c558-192">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="8c558-193">Mon organisation a-t-elle besoin de standards automatiques ?</span><span class="sxs-lookup"><span data-stu-id="8c558-193">Does my organization need auto attendants?</span></span> | <span data-ttu-id="8c558-194">Pour plus d’informations, reportez-vous à [définition des standards automatiques Cloud](what-are-phone-system-auto-attendants.md) et [configuration d’un standard automatique Cloud](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="8c558-194">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="8c558-195">Appareils</span><span class="sxs-lookup"><span data-stu-id="8c558-195">Devices</span></span>

<span data-ttu-id="8c558-196">Pour plus d’informations sur les appareils pris en charge, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c558-196">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="8c558-197">Gérer vos périphériques dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c558-197">Manage your devices in Microsoft Teams</span></span>](devices/device-management.md)
- [<span data-ttu-id="8c558-198">Téléphones IP</span><span class="sxs-lookup"><span data-stu-id="8c558-198">IP Phones</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="8c558-199">Périphériques audio et vidéo USB</span><span class="sxs-lookup"><span data-stu-id="8c558-199">USB audio and video devices</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="8c558-200">Communications intelligentes pour les appareils</span><span class="sxs-lookup"><span data-stu-id="8c558-200">Intelligent communications for devices</span></span>](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


