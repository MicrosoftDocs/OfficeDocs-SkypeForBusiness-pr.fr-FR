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
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas de voix dans teams pour les entreprises à plusieurs nationaux
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701222"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="e48bc-103">Étude de cas contoso : vue d’ensemble de la migration teams Voice</span><span class="sxs-lookup"><span data-stu-id="e48bc-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="e48bc-104">Cet article présente une étude de cas concernant la façon dont une entreprise fictive multipoint, contoso, a implémenté une solution vocale teams pour son organisation.</span><span class="sxs-lookup"><span data-stu-id="e48bc-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="e48bc-105">Contoso a déployé Microsoft 365 entreprise et résolu les principales décisions relatives à la conception et aux informations d’implémentation pour les éléments suivants : mise en réseau, identité, Windows 10 entreprise, Office 365 ProPlus, gestion des appareils mobiles, protection des informations, sécurité, mise à niveau de Skype entreprise vers équipes, système téléphonique et audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e48bc-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="e48bc-106">Cet article décrit la façon dont Contoso a migré ses utilisateurs locaux vers des équipes de communication, de collaboration et de voix unifiées.</span><span class="sxs-lookup"><span data-stu-id="e48bc-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="e48bc-107">Pour plus d’informations sur la façon dont Contoso a accéléré sa transformation numérique à l’aide des services Cloud de Microsoft, voir tous les articles principaux à partir de la [vue d’ensemble de l’étude de cas contoso](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="e48bc-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="e48bc-108">Dans les articles principaux, vous trouverez des informations sur les points suivants :</span><span class="sxs-lookup"><span data-stu-id="e48bc-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="e48bc-109">Besoins d’infrastructure informatique de contoso</span><span class="sxs-lookup"><span data-stu-id="e48bc-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="e48bc-110">Réseau</span><span class="sxs-lookup"><span data-stu-id="e48bc-110">Networking</span></span>
- <span data-ttu-id="e48bc-111">Identity </span><span class="sxs-lookup"><span data-stu-id="e48bc-111">Identity</span></span>
- <span data-ttu-id="e48bc-112">Windows 10 entreprise</span><span class="sxs-lookup"><span data-stu-id="e48bc-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="e48bc-113">Office 365 Pro plus</span><span class="sxs-lookup"><span data-stu-id="e48bc-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="e48bc-114">Gestion des appareils mobiles</span><span class="sxs-lookup"><span data-stu-id="e48bc-114">Mobile device management</span></span>
- <span data-ttu-id="e48bc-115">Protection des informations</span><span class="sxs-lookup"><span data-stu-id="e48bc-115">Information protection</span></span>
- <span data-ttu-id="e48bc-116">Résumé de la sécurité Microsoft 365 entreprise</span><span class="sxs-lookup"><span data-stu-id="e48bc-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="e48bc-117">Équipe pour un projet de secret principal</span><span class="sxs-lookup"><span data-stu-id="e48bc-117">Team for a top-secret project</span></span>
- <span data-ttu-id="e48bc-118">Site SharePoint Online pour des ressources numériques hautement confidentielles</span><span class="sxs-lookup"><span data-stu-id="e48bc-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="e48bc-119">Pour plus d’informations sur la planification d’une mise à niveau, vous pouvez commencer par commencer à [effectuer la mise à niveau de Microsoft teams](upgrade-start-here.md).</span><span class="sxs-lookup"><span data-stu-id="e48bc-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="e48bc-120">Buts stratégiques de contoso pour les équipes</span><span class="sxs-lookup"><span data-stu-id="e48bc-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="e48bc-121">Pour migrer leurs utilisateurs locaux vers des équipes de communication, de collaboration et de voix unifiées, Contoso a déterminé les objectifs commerciaux suivants :</span><span class="sxs-lookup"><span data-stu-id="e48bc-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="e48bc-122">Activation de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e48bc-122">Teams enablement</span></span> 

  <span data-ttu-id="e48bc-123">L’équipe de collaboration et de communication unifiée de Contoso a pu équiper les équipes possédant les stratégies appropriées pour gérer et activer une collaboration interne et externe sécurisée.</span><span class="sxs-lookup"><span data-stu-id="e48bc-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="e48bc-124">Mise à niveau de Skype Entreprise vers Teams</span><span class="sxs-lookup"><span data-stu-id="e48bc-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="e48bc-125">Skype entreprise a été largement déployé dans contoso.</span><span class="sxs-lookup"><span data-stu-id="e48bc-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="e48bc-126">En raison de la nécessité de sortir des systèmes hérités, Contoso a décidé de mettre à niveau leurs utilisateurs Skype entreprise vers Teams.</span><span class="sxs-lookup"><span data-stu-id="e48bc-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="e48bc-127">Pour plus d’informations, consultez l' [étude de cas contoso : plan de mise à niveau des équipes](voice-case-study-migration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="e48bc-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="e48bc-128">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="e48bc-128">Phone System</span></span>  

  <span data-ttu-id="e48bc-129">Skype entreprise avec Enterprise Voice a été largement déployé dans contoso.</span><span class="sxs-lookup"><span data-stu-id="e48bc-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="e48bc-130">En raison de la nécessité de sortir des systèmes hérités qui étaient le tronçon suivant pour leurs serveurs de médiation, Contoso a migré leurs utilisateurs vocaux Skype entreprise vers un système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="e48bc-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="e48bc-131">Les sites contoso utilisaient un forfait d’appel Microsoft, le routage direct de votre système téléphonique ou une combinaison des deux.</span><span class="sxs-lookup"><span data-stu-id="e48bc-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="e48bc-132">Pour plus d’informations, reportez-vous à la rubrique [étude de cas contoso : système téléphonique](voice-case-study-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="e48bc-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="e48bc-133">Routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="e48bc-133">Location-Based Routing</span></span> 

  <span data-ttu-id="e48bc-134">Dans les pays réglementés par la téléphonie, Contoso a besoin de recréer le routage Location-Based présent dans Skype entreprise pour le déploiement de votre système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="e48bc-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="e48bc-135">Pour plus d’informations, reportez-vous à la rubrique [étude de cas contoso : Location-Based routage](voice-case-study-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="e48bc-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="e48bc-136">Appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="e48bc-136">Emergency Calling</span></span> 

  <span data-ttu-id="e48bc-137">Lorsque le routage direct a été implémenté, Contoso a configuré les appels d’urgence avec des tierces parties approuvées.</span><span class="sxs-lookup"><span data-stu-id="e48bc-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="e48bc-138">Pour plus d’informations, reportez-vous à la rubrique [étude de cas contoso : appels d’urgence](voice-case-study-emergency-calling.md).</span><span class="sxs-lookup"><span data-stu-id="e48bc-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="e48bc-139">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="e48bc-139">Audio Conferencing</span></span> 

  <span data-ttu-id="e48bc-140">Contoso configurez des numéros de service d’audioconférence hébergés sur le Trunk SIP de leur fournisseur PSTN.</span><span class="sxs-lookup"><span data-stu-id="e48bc-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="e48bc-141">Pour plus d’informations, consultez l' [étude de cas contoso : audioconférence](voice-case-study-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="e48bc-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="e48bc-142">Optimisation des éléments multimédias locaux</span><span class="sxs-lookup"><span data-stu-id="e48bc-142">Local Media Optimization</span></span> 

  <span data-ttu-id="e48bc-143">Contoso a bénéficié de l’optimisation des contenus multimédias locaux dans les emplacements où il existait un Trunk de routage direct vers un système Microsoft Phone qui était utilisé par des sites distants.</span><span class="sxs-lookup"><span data-stu-id="e48bc-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="e48bc-144">Pour plus d’informations, reportez-vous à la rubrique [planification de l’optimisation des médias locaux](direct-routing-media-optimization.md) et configuration de l' [optimisation des médias locaux](direct-routing-media-optimization-configure.md).</span><span class="sxs-lookup"><span data-stu-id="e48bc-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="e48bc-145">Standards automatiques et files d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="e48bc-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="e48bc-146">Dans le cadre de COVID-19, contoso voulait fournir la prise en charge du réceptionniste lorsque son équipe travaille à distance.</span><span class="sxs-lookup"><span data-stu-id="e48bc-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="e48bc-147">Contoso a utilisé des standards automatiques et des files d’attente pour gérer les appels entrants sur le numéro de téléphone de votre réceptionniste.</span><span class="sxs-lookup"><span data-stu-id="e48bc-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="e48bc-148">Pour plus d’informations, consultez l' [étude de cas contoso : standards automatiques et files d’attente d’appels](voice-case-study-call-queues.md).</span><span class="sxs-lookup"><span data-stu-id="e48bc-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


