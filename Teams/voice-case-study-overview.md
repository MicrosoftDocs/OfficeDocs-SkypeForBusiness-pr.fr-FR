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
description: Étude de cas voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097490"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="9b144-103">Étude de cas Contoso : Vue d’ensemble de la migration vocale Teams</span><span class="sxs-lookup"><span data-stu-id="9b144-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="9b144-104">Cet article présente une étude de cas sur la façon dont une entreprise multinationale fictive, Contoso, implémente une solution vocale Teams pour leur organisation.</span><span class="sxs-lookup"><span data-stu-id="9b144-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="9b144-105">Contoso a déployé Microsoft 365 Entreprise et a pris en compte les principales décisions de conception et les détails d’implémentation suivants : mise en réseau, identité, Windows 10 Entreprise, Office 365 ProPlus, gestion des appareils mobiles, protection des informations, sécurité, mise à niveau de Skype Entreprise vers Teams, système téléphonique et audioconférence.</span><span class="sxs-lookup"><span data-stu-id="9b144-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="9b144-106">Cet article explique comment Contoso a migré ses utilisateurs locaux vers Teams pour unifier la communication, la collaboration et la voix.</span><span class="sxs-lookup"><span data-stu-id="9b144-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="9b144-107">Pour obtenir des informations de base sur l’accélération de la transformation numérique par Contoso à l’aide des services cloud de Microsoft, consultez tous les articles principaux, dont la vue d’ensemble de l’étude de cas [Contoso.](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="9b144-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="9b144-108">Dans les articles principaux, vous trouverez des informations sur les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="9b144-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="9b144-109">Besoins en matière d’infrastructure informatique de Contoso</span><span class="sxs-lookup"><span data-stu-id="9b144-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="9b144-110">Réseau</span><span class="sxs-lookup"><span data-stu-id="9b144-110">Networking</span></span>
- <span data-ttu-id="9b144-111">Identity </span><span class="sxs-lookup"><span data-stu-id="9b144-111">Identity</span></span>
- <span data-ttu-id="9b144-112">Windows 10 Entreprise</span><span class="sxs-lookup"><span data-stu-id="9b144-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="9b144-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="9b144-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="9b144-114">Gestion des appareils mobiles</span><span class="sxs-lookup"><span data-stu-id="9b144-114">Mobile device management</span></span>
- <span data-ttu-id="9b144-115">Protection des informations</span><span class="sxs-lookup"><span data-stu-id="9b144-115">Information protection</span></span>
- <span data-ttu-id="9b144-116">Résumé de la sécurité microsoft 365 Entreprise</span><span class="sxs-lookup"><span data-stu-id="9b144-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="9b144-117">Équipe pour un projet top secret</span><span class="sxs-lookup"><span data-stu-id="9b144-117">Team for a top-secret project</span></span>
- <span data-ttu-id="9b144-118">Site SharePoint Online pour les ressources numériques hautement confidentielles</span><span class="sxs-lookup"><span data-stu-id="9b144-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="9b144-119">Pour plus d’informations sur la planification d’une mise à niveau, vous pouvez commencer avec la mise à [niveau de Microsoft Teams.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="9b144-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="9b144-120">Objectifs professionnels de Contoso pour Teams</span><span class="sxs-lookup"><span data-stu-id="9b144-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="9b144-121">Pour migrer leurs utilisateurs locaux vers Teams pour la communication unifiée, la collaboration et la voix, Contoso a décidé des objectifs professionnels suivants :</span><span class="sxs-lookup"><span data-stu-id="9b144-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="9b144-122">Activer Teams</span><span class="sxs-lookup"><span data-stu-id="9b144-122">Teams enablement</span></span> 

  <span data-ttu-id="9b144-123">L’équipe unifiée de communication et de collaboration de Contoso a permis à Teams de mettre en place les stratégies correctes pour régir et activer la collaboration interne et externe sécurisée.</span><span class="sxs-lookup"><span data-stu-id="9b144-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="9b144-124">Mise à niveau de Skype Entreprise vers Teams</span><span class="sxs-lookup"><span data-stu-id="9b144-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="9b144-125">Skype Entreprise a été largement déployé dans Contoso.</span><span class="sxs-lookup"><span data-stu-id="9b144-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="9b144-126">En raison de la nécessité de déplacer des systèmes hérités, Contoso a décidé de mettre à niveau ses utilisateurs Skype Entreprise vers Teams.</span><span class="sxs-lookup"><span data-stu-id="9b144-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="9b144-127">Pour plus d’informations, [voir l’étude de cas Contoso : Plan de mise à niveau de Teams.](voice-case-study-migration-plan.md)</span><span class="sxs-lookup"><span data-stu-id="9b144-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="9b144-128">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="9b144-128">Phone System</span></span>  

  <span data-ttu-id="9b144-129">Skype Entreprise avec voix Entreprise a été largement déployé dans Contoso.</span><span class="sxs-lookup"><span data-stu-id="9b144-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="9b144-130">Avec la nécessité de déplacer les systèmes hérités qui étaient le prochain saut pour leurs serveurs de médiation, Contoso a migré ses utilisateurs Voix Entreprise Skype Entreprise vers Phone System.</span><span class="sxs-lookup"><span data-stu-id="9b144-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="9b144-131">Les sites Contoso utilisaient le plan d’appels Microsoft, le routage direct du système téléphonique ou une combinaison des deux.</span><span class="sxs-lookup"><span data-stu-id="9b144-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="9b144-132">Pour plus d’informations, [voir étude de cas Contoso : Phone System.](voice-case-study-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="9b144-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="9b144-133">Routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="9b144-133">Location-Based Routing</span></span> 

  <span data-ttu-id="9b144-134">Les emplacements de bureau dans les pays où la téléphonie est régulée, Contoso devait recréer le routage Location-Based présent dans Skype Entreprise dans le cadre du déploiement de son système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="9b144-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="9b144-135">Pour plus d’informations, [voir étude de cas Contoso : Location-Based routage.](voice-case-study-location-based-routing.md)</span><span class="sxs-lookup"><span data-stu-id="9b144-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="9b144-136">Appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="9b144-136">Emergency Calling</span></span> 

  <span data-ttu-id="9b144-137">Lorsque le routage direct a été implémenté, Contoso a installé les appels d’urgence avec des tiers approuvés.</span><span class="sxs-lookup"><span data-stu-id="9b144-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="9b144-138">Pour plus d’informations, [voir l’étude de cas Contoso : Appels d’urgence.](voice-case-study-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="9b144-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="9b144-139">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="9b144-139">Audio Conferencing</span></span> 

  <span data-ttu-id="9b144-140">Contoso a installé pour son fournisseur PSTN des numéros de service d’audioconférence hébergés sur sa ligne SIP.</span><span class="sxs-lookup"><span data-stu-id="9b144-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="9b144-141">Pour plus d’informations, [consultez l’étude de cas Contoso : Audioconférence.](voice-case-study-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="9b144-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="9b144-142">Optimisation des médias locaux</span><span class="sxs-lookup"><span data-stu-id="9b144-142">Local Media Optimization</span></span> 

  <span data-ttu-id="9b144-143">Contoso a tirer parti de l’optimisation des médias locaux dans les emplacements où il avait une ligne de route directe vers Microsoft Phone System qui était exploitable par des sites distants.</span><span class="sxs-lookup"><span data-stu-id="9b144-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="9b144-144">Pour plus d’informations, voir [Planifier l’optimisation des](direct-routing-media-optimization.md) médias locaux et [configurer l’optimisation des médias locaux.](direct-routing-media-optimization-configure.md)</span><span class="sxs-lookup"><span data-stu-id="9b144-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="9b144-145">Attendants automatiques et files d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="9b144-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="9b144-146">Covid-19 souhaitait offrir un support à la réception alors que son personnel travaillait à distance.</span><span class="sxs-lookup"><span data-stu-id="9b144-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="9b144-147">Contoso utilisait des files d’attente automatiques et des files d’attente pour gérer les appels entrants vers le numéro de téléphone de leur appelant.</span><span class="sxs-lookup"><span data-stu-id="9b144-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="9b144-148">Pour plus d’informations, [voir l’étude de cas Contoso : Attendant automatiques et Files d’attente d’appels.](voice-case-study-call-queues.md)</span><span class="sxs-lookup"><span data-stu-id="9b144-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>