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
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas Voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701222"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="58d8f-103">Étude de cas Contoso : Vue d’ensemble de la migration vocale Teams</span><span class="sxs-lookup"><span data-stu-id="58d8f-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="58d8f-104">Cet article présente une étude de cas sur la façon dont une entreprise multinationale fictive, Contoso, implémente une solution vocale Teams pour leur organisation.</span><span class="sxs-lookup"><span data-stu-id="58d8f-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="58d8f-105">Contoso a déployé Microsoft 365 Entreprise et a pris en compte les principales décisions de conception et les détails d’implémentation suivants : mise en réseau, identité, Windows 10 Entreprise, Office 365 ProPlus, gestion des appareils mobiles, protection des informations, sécurité, mise à niveau de Skype Entreprise vers Teams, système téléphonique et audioconférence.</span><span class="sxs-lookup"><span data-stu-id="58d8f-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="58d8f-106">Cet article explique comment Contoso a migré ses utilisateurs locaux vers Teams pour unifier la communication, la collaboration et la voix.</span><span class="sxs-lookup"><span data-stu-id="58d8f-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="58d8f-107">Pour obtenir des informations de base sur l’accélération de la transformation numérique par Contoso à l’aide des services cloud de Microsoft, consultez tous les articles principaux, dont la vue d’ensemble de l’étude de cas [Contoso.](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="58d8f-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="58d8f-108">Dans les articles principaux, vous trouverez des informations sur les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="58d8f-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="58d8f-109">Besoins en matière d’infrastructure informatique de Contoso</span><span class="sxs-lookup"><span data-stu-id="58d8f-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="58d8f-110">Réseau</span><span class="sxs-lookup"><span data-stu-id="58d8f-110">Networking</span></span>
- <span data-ttu-id="58d8f-111">Identity </span><span class="sxs-lookup"><span data-stu-id="58d8f-111">Identity</span></span>
- <span data-ttu-id="58d8f-112">Windows 10 Entreprise</span><span class="sxs-lookup"><span data-stu-id="58d8f-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="58d8f-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="58d8f-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="58d8f-114">Gestion des appareils mobiles</span><span class="sxs-lookup"><span data-stu-id="58d8f-114">Mobile device management</span></span>
- <span data-ttu-id="58d8f-115">Protection des informations</span><span class="sxs-lookup"><span data-stu-id="58d8f-115">Information protection</span></span>
- <span data-ttu-id="58d8f-116">Résumé de la sécurité microsoft 365 Entreprise</span><span class="sxs-lookup"><span data-stu-id="58d8f-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="58d8f-117">Équipe pour un projet top secret</span><span class="sxs-lookup"><span data-stu-id="58d8f-117">Team for a top-secret project</span></span>
- <span data-ttu-id="58d8f-118">Site SharePoint Online pour les ressources numériques hautement confidentielles</span><span class="sxs-lookup"><span data-stu-id="58d8f-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="58d8f-119">Pour plus d’informations sur la planification d’une mise à niveau, vous pouvez commencer avec la mise à [niveau de Microsoft Teams.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="58d8f-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="58d8f-120">Objectifs professionnels de Contoso pour Teams</span><span class="sxs-lookup"><span data-stu-id="58d8f-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="58d8f-121">Pour migrer leurs utilisateurs locaux vers Teams pour la communication unifiée, la collaboration et la voix, Contoso a décidé des objectifs professionnels suivants :</span><span class="sxs-lookup"><span data-stu-id="58d8f-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="58d8f-122">Activer Teams</span><span class="sxs-lookup"><span data-stu-id="58d8f-122">Teams enablement</span></span> 

  <span data-ttu-id="58d8f-123">L’équipe unifiée de communication et de collaboration de Contoso a permis à Teams d’avoir les stratégies correctes pour régir et activer la collaboration interne et externe sécurisée.</span><span class="sxs-lookup"><span data-stu-id="58d8f-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="58d8f-124">Mise à niveau de Skype Entreprise vers Teams</span><span class="sxs-lookup"><span data-stu-id="58d8f-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="58d8f-125">Skype Entreprise a été largement déployé dans Contoso.</span><span class="sxs-lookup"><span data-stu-id="58d8f-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="58d8f-126">En raison de la nécessité de déplacer des systèmes hérités, Contoso a décidé de mettre à niveau ses utilisateurs Skype Entreprise vers Teams.</span><span class="sxs-lookup"><span data-stu-id="58d8f-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="58d8f-127">Pour plus d’informations, [voir l’étude de cas Contoso : Plan de mise à niveau de Teams.](voice-case-study-migration-plan.md)</span><span class="sxs-lookup"><span data-stu-id="58d8f-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="58d8f-128">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="58d8f-128">Phone System</span></span>  

  <span data-ttu-id="58d8f-129">Skype Entreprise avec voix Entreprise a été largement déployé dans Contoso.</span><span class="sxs-lookup"><span data-stu-id="58d8f-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="58d8f-130">Avec la nécessité de déplacer les systèmes hérités qui étaient le saut suivant pour leurs serveurs de médiation, Contoso a migré ses utilisateurs voix Skype Entreprise vers phone system.</span><span class="sxs-lookup"><span data-stu-id="58d8f-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="58d8f-131">Les sites Contoso utilisaient le plan d’appels Microsoft, le routage direct du système téléphonique ou une combinaison des deux.</span><span class="sxs-lookup"><span data-stu-id="58d8f-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="58d8f-132">Pour plus d’informations, [voir étude de cas Contoso : Phone System.](voice-case-study-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="58d8f-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="58d8f-133">Routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="58d8f-133">Location-Based Routing</span></span> 

  <span data-ttu-id="58d8f-134">Les emplacements de bureau dans les pays régulés par téléphone, Contoso devait recréer le routage Location-Based présent dans Skype Entreprise dans le cadre du déploiement de son système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="58d8f-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="58d8f-135">Pour plus d’informations, [voir étude de cas Contoso : Location-Based routage.](voice-case-study-location-based-routing.md)</span><span class="sxs-lookup"><span data-stu-id="58d8f-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="58d8f-136">Appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="58d8f-136">Emergency Calling</span></span> 

  <span data-ttu-id="58d8f-137">Lorsque le routage direct a été implémenté, Contoso a installé les appels d’urgence avec des tiers approuvés.</span><span class="sxs-lookup"><span data-stu-id="58d8f-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="58d8f-138">Pour plus d’informations, [voir l’étude de cas Contoso : Appels d’urgence.](voice-case-study-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="58d8f-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="58d8f-139">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="58d8f-139">Audio Conferencing</span></span> 

  <span data-ttu-id="58d8f-140">Contoso a installé pour son fournisseur PSTN des numéros de service d’audioconférence hébergés sur sa ligne SIP.</span><span class="sxs-lookup"><span data-stu-id="58d8f-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="58d8f-141">Pour plus d’informations, [consultez l’étude de cas Contoso : Audioconférence.](voice-case-study-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="58d8f-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="58d8f-142">Optimisation des médias locaux</span><span class="sxs-lookup"><span data-stu-id="58d8f-142">Local Media Optimization</span></span> 

  <span data-ttu-id="58d8f-143">Contoso a tirer parti de l’optimisation des médias locaux dans les emplacements où il avait une ligne de route directe vers Microsoft Phone System qui était exploitable par des sites distants.</span><span class="sxs-lookup"><span data-stu-id="58d8f-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="58d8f-144">Pour plus d’informations, voir [Planifier l’optimisation des](direct-routing-media-optimization.md) médias locaux et [configurer l’optimisation des médias locaux.](direct-routing-media-optimization-configure.md)</span><span class="sxs-lookup"><span data-stu-id="58d8f-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="58d8f-145">Attendants automatiques et files d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="58d8f-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="58d8f-146">Covid-19 souhaitait offrir un support à la réception alors que son personnel travaillait à distance.</span><span class="sxs-lookup"><span data-stu-id="58d8f-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="58d8f-147">Contoso utilisait des files d’attente automatiques et des files d’attente pour gérer les appels entrants vers le numéro de téléphone de leur appelant.</span><span class="sxs-lookup"><span data-stu-id="58d8f-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="58d8f-148">Pour plus d’informations, [voir l’étude de cas Contoso : Attendant automatiques et Files d’attente d’appels.](voice-case-study-call-queues.md)</span><span class="sxs-lookup"><span data-stu-id="58d8f-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


