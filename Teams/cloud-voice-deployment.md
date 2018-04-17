---
title: Déploiement de la fonctionnalité vocale cloud
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 04/10/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Guide pratique pour le déploiement de la fonctionnalité vocale cloud dans Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4828cb7c27c53387e0efae800167cef1b53dd4b6
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="fad6b-103">Déploiement de la fonctionnalité vocale cloud</span><span class="sxs-lookup"><span data-stu-id="fad6b-103">Cloud voice deployment</span></span>

<span data-ttu-id="fad6b-104">Teams de Microsoft, le concentrateur pour le travail d’équipe et les communications dans Office 365, fournit à présent audioconférence et système téléphonique avec les Plans d’appel de fonctionnalités pour répondre à des besoins supplémentaires en étendant la réunion équipes expérience à inclure en appelant les parties externes connectés via le réseau téléphonique public commuté (RTPC).</span><span class="sxs-lookup"><span data-stu-id="fad6b-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>
 
<span data-ttu-id="fad6b-105">Cette page sera mise à jour au fur et à mesure du lancement de fonctionnalités vocales cloud supplémentaires dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fad6b-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="fad6b-106">Audioconférence dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fad6b-106">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="fad6b-107">L’audioconférence dans Office 365 permet aux participants de rejoindre vos réunions Teams depuis n’importe quel téléphone.</span><span class="sxs-lookup"><span data-stu-id="fad6b-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="fad6b-108">Voici les avantages de [l’audioconférence](https://go.microsoft.com/fwlink/?linkid=858992) dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="fad6b-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="fad6b-109">Système de téléphone avec les Plans d’appel dans des équipes de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fad6b-109">Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="fad6b-110">La fonctionnalité de système téléphonique d'Office 365 permet de gérer le routage des appels, les stratégies et l'affectation d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fad6b-110">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="fad6b-111">Cela inclut le système de gestion des appels téléphoniques, le routage des appels et le contrôle des appels.</span><span class="sxs-lookup"><span data-stu-id="fad6b-111">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="fad6b-112">Les forfaits d'appels Office 365 constituent un service complémentaire de la fonctionnalité de système téléphonique fournie via Teams et Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="fad6b-112">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="fad6b-113">Plans d’appel fournissent les personnes de votre entreprise avec un numéro de téléphone principal numéro et leur permettant d’effectuer et de recevoir des appels téléphoniques à l’extérieur de votre organisation via le réseau RTPC.</span><span class="sxs-lookup"><span data-stu-id="fad6b-113">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="fad6b-114">Pour en savoir plus, consultez [Voici les avantages du système téléphonique d'Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) et [En quoi consiste les forfaits d'appels dans Office 365 ?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span><span class="sxs-lookup"><span data-stu-id="fad6b-114">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>


## <a name="practical-guidance-for-audio-conferencing-and-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="fad6b-115">Conseils pratiques pour les conférences Audio et système téléphonique avec appel de Plans dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fad6b-115">Practical guidance for Audio Conferencing and Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="fad6b-116">Ce guide pratique est organisé en utilisant l’infrastructure de transport du client Office 365 FastTrack et ses trois phases&mdash;Envision, à bord et la valeur de lecteur.</span><span class="sxs-lookup"><span data-stu-id="fad6b-116">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="fad6b-117">Elle est destinée à vous aider à planifier, livrer et utiliser une audioconférence ou le système téléphonique réussie avec la mise en oeuvre des Plans d’appel.</span><span class="sxs-lookup"><span data-stu-id="fad6b-117">It's intended to help you plan, deliver, and operate a successful Audio Conferencing or Phone System with Calling Plans implementation.</span></span>

|<span data-ttu-id="fad6b-118">Concevoir</span><span class="sxs-lookup"><span data-stu-id="fad6b-118">Envision</span></span>  |<span data-ttu-id="fad6b-119">Intégrer</span><span class="sxs-lookup"><span data-stu-id="fad6b-119">Onboard</span></span>  |<span data-ttu-id="fad6b-120">Générer une valeur ajoutée</span><span class="sxs-lookup"><span data-stu-id="fad6b-120">Drive Value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="fad6b-121">Définir ma réussite</span><span class="sxs-lookup"><span data-stu-id="fad6b-121">Define my success</span></span> <br> <span data-ttu-id="fad6b-122">Prendre des décisions de mon service</span><span class="sxs-lookup"><span data-stu-id="fad6b-122">Make my service decisions</span></span> <br> <span data-ttu-id="fad6b-123">Évaluer mon environnement</span><span class="sxs-lookup"><span data-stu-id="fad6b-123">Evaluate my environment</span></span> <br> <span data-ttu-id="fad6b-124">Planification de la gestion de mon service</span><span class="sxs-lookup"><span data-stu-id="fad6b-124">Plan my service management</span></span> <br> <span data-ttu-id="fad6b-125">Plan d’expérience de mes utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fad6b-125">Plan my users' experience</span></span> <br> <span data-ttu-id="fad6b-126">Mon plan de réussite de documents</span><span class="sxs-lookup"><span data-stu-id="fad6b-126">Document my success plan</span></span>    | <span data-ttu-id="fad6b-127">Préparer mon service</span><span class="sxs-lookup"><span data-stu-id="fad6b-127">Prepare my service</span></span> <br> <span data-ttu-id="fad6b-128">Préparer les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fad6b-128">Prepare my users</span></span> <br> <span data-ttu-id="fad6b-129">Déployer mon service</span><span class="sxs-lookup"><span data-stu-id="fad6b-129">Deploy my service</span></span>  <br> <br> <br> <br>     | <span data-ttu-id="fad6b-130">Utiliser mon service</span><span class="sxs-lookup"><span data-stu-id="fad6b-130">Operate my service</span></span> <br> <span data-ttu-id="fad6b-131">Améliorer mon service</span><span class="sxs-lookup"><span data-stu-id="fad6b-131">Enhance my service</span></span> <br> <br> <br> <br> <br>      |

<span data-ttu-id="fad6b-132">Le contenu est présenté de manière ordonnée et est conçu pour vous faire un voyage de déploiement de bout en bout du début à la fin.</span><span class="sxs-lookup"><span data-stu-id="fad6b-132">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="fad6b-133">Si vous déployez déjà activement, nous encourageons toujours vous permet de référencer les zones de contenu applicables.</span><span class="sxs-lookup"><span data-stu-id="fad6b-133">If you're already actively deploying, we still encourage you to reference the applicable content areas.</span></span>



> [!TIP]
> <span data-ttu-id="fad6b-134">Dans ce guide pratique, nous vous fournissons l’exemple, pour chaque activité et une discussion de clé.</span><span class="sxs-lookup"><span data-stu-id="fad6b-134">In this practical guidance, we're providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="fad6b-135">Les exemples dans ce document sont placés à l’intérieur des légendes de Conseil, et qu’ils servent un modèle que vous pouvez réutiliser.</span><span class="sxs-lookup"><span data-stu-id="fad6b-135">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="fad6b-136">« TBA » (à ajouter) est affiché en regard des informations que vous devez remplir dans le cadre de votre processus de planification.</span><span class="sxs-lookup"><span data-stu-id="fad6b-136">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>