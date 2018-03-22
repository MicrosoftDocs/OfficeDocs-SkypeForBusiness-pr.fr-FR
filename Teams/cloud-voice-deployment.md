---
title: Déploiement de la fonctionnalité vocale cloud
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 12/13/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Guide pratique pour le déploiement de la fonctionnalité vocale cloud dans Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45528d71dc04b96d77b454d5db402648779c1ac9
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
#<a name="cloud-voice-deployment"></a><span data-ttu-id="ba37e-103">Déploiement de la fonctionnalité vocale cloud</span><span class="sxs-lookup"><span data-stu-id="ba37e-103">Cloud voice deployment</span></span>

<span data-ttu-id="ba37e-104">Microsoft Teams, la plateforme dédiée au travail en équipe et aux communications dans Office 365, fournit désormais des fonctionnalités d'audioconférence et de système téléphonique avec des forfaits d’appels, afin de satisfaire les besoins supplémentaires en étendant l'expérience d'appel et de réunions Microsoft Teams et d'inclure les participants externes qui s'y joignent via le réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="ba37e-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the Public Switched Telephone Network (PSTN).</span></span>
 
<span data-ttu-id="ba37e-105">Cette page sera mise à jour au fur et à mesure du lancement de fonctionnalités vocales cloud supplémentaires dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ba37e-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>


##<a name="practical-guidance-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="ba37e-106">Guide pratique pour l’audioconférence dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba37e-106">Practical guidance for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="ba37e-107">L’audioconférence dans Office 365 permet aux participants de rejoindre vos réunions Teams depuis n’importe quel téléphone.</span><span class="sxs-lookup"><span data-stu-id="ba37e-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="ba37e-108">Voici les avantages de [l’audioconférence](https://go.microsoft.com/fwlink/?linkid=858992) dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="ba37e-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

<span data-ttu-id="ba37e-109">Ce guide pratique vous oriente dans la structure du client FastTrack d'Office 365 et ses trois phases, planifier, intégrer et générer une valeur ajoutée, pour vous aider à planifier, livrer et exécuter une implémentation réussie de l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="ba37e-109">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases, Envision, Onboard, and Drive Value, to help you plan, deliver, and operate an Audio Conferencing implementation towards succesful business outcomes.</span></span>

> [!TIP]
> <span data-ttu-id="ba37e-110">Dans ce guide pratique, nous fournissons des exemples de résultats pour chaque activité et theme principal.</span><span class="sxs-lookup"><span data-stu-id="ba37e-110">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="ba37e-111">Les exemples fournis tout au long de ce document sont intégrés aux légendes des astuces et peuvent être utilisés comme modèles.</span><span class="sxs-lookup"><span data-stu-id="ba37e-111">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="ba37e-112">« TBA » (à ajouter) est affiché en regard des informations que vous devez remplir dans le cadre de votre processus de planification.</span><span class="sxs-lookup"><span data-stu-id="ba37e-112">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

##<a name="practical-guidance-for-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="ba37e-113">Guide pratique des systèmes téléphoniques avec forfaits d'appels dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba37e-113">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="ba37e-114">La fonctionnalité de système téléphonique d'Office 365 permet de gérer le routage des appels, les stratégies et l'affectation d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ba37e-114">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="ba37e-115">Cela inclut le système de gestion des appels téléphoniques, le routage des appels et le contrôle des appels.</span><span class="sxs-lookup"><span data-stu-id="ba37e-115">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="ba37e-116">Les forfaits d'appels Office 365 constituent un service complémentaire de la fonctionnalité de système téléphonique fournie via Teams et Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="ba37e-116">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="ba37e-117">Les forfaits d'appels confèrent à vos employés un numéro de téléphone principal leur permettant de passer et de recevoir des appels téléphoniques à l'extérieur de votre organisation via le réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="ba37e-117">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="ba37e-118">Pour en savoir plus, consultez [Voici les avantages du système téléphonique d'Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) et [En quoi consiste les forfaits d'appels dans Office 365 ?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span><span class="sxs-lookup"><span data-stu-id="ba37e-118">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>

<span data-ttu-id="ba37e-119">Ce guide pratique vous oriente dans la structure du client FastTrack d'Office 365 et ses trois phases, planifier, intégrer et générer une valeur ajoutée, pour vous aider à programmer, fournir et utiliser une implémentation réussie d'un système téléphonique avec forfaits d'appels.</span><span class="sxs-lookup"><span data-stu-id="ba37e-119">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases - Envision, Onboard, and Drive Value - to help you plan, deliver, and operate a successful Phone System with Calling Plans implementation.</span></span>

> [!TIP]
> <span data-ttu-id="ba37e-120">Dans ce guide pratique, nous fournissons des exemples de résultats pour chaque activité et theme principal.</span><span class="sxs-lookup"><span data-stu-id="ba37e-120">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="ba37e-121">Les exemples fournis tout au long de ce document sont intégrés aux légendes des astuces et peuvent être utilisés comme modèles.</span><span class="sxs-lookup"><span data-stu-id="ba37e-121">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="ba37e-122">« TBA » (à ajouter) est affiché en regard des informations que vous devez remplir dans le cadre de votre processus de planification.</span><span class="sxs-lookup"><span data-stu-id="ba37e-122">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>