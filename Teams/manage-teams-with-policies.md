---
title: Gérer les équipes avec des stratégies
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad39b24ee177e8e8282c6ad948b69fbdf866aa56
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347677"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="38a96-102">Gérer les équipes avec des stratégies</span><span class="sxs-lookup"><span data-stu-id="38a96-102">Manage teams with policies</span></span>

<span data-ttu-id="38a96-103">Les stratégies sont un élément important de la gestion de Teams.</span><span class="sxs-lookup"><span data-stu-id="38a96-103">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="38a96-104">Utilisez cet article pour naviguer dans l’utilisation des stratégies au profit de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="38a96-104">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="38a96-105">Utilisation des stratégies pour</span><span class="sxs-lookup"><span data-stu-id="38a96-105">What you use policies for</span></span>

<span data-ttu-id="38a96-106">Les stratégies sont utilisées pour effectuer de nombreuses tâches au sein de votre organisation dans différents domaines tels que la messagerie, les réunions et les applications.</span><span class="sxs-lookup"><span data-stu-id="38a96-106">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="38a96-107">Vous pouvez notamment autoriser les utilisateurs à planifier des réunions dans un canal Teams, permettre aux utilisateurs de modifier les messages envoyés et contrôler si les utilisateurs peuvent épingler des applications à la barre de l’application Teams.</span><span class="sxs-lookup"><span data-stu-id="38a96-107">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="38a96-108">Comment affecter des stratégies</span><span class="sxs-lookup"><span data-stu-id="38a96-108">How to assign policies</span></span>

<span data-ttu-id="38a96-109">Les stratégies peuvent être affectées de différentes manières en fonction de ce que votre organisation tente d’accomplir.</span><span class="sxs-lookup"><span data-stu-id="38a96-109">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="38a96-110">Vous pouvez effectuer et afficher des devoirs dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="38a96-110">You can make and view assignments in the Teams admin center.</span></span>

![Capture d’écran de l’affectation d’une stratégie de groupe.](media/group-policy-assignment.png)

<span data-ttu-id="38a96-112">Pour en savoir plus sur l’attribution de [stratégies, cliquez ici.](assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="38a96-112">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="38a96-113">Comment gérer les stratégies</span><span class="sxs-lookup"><span data-stu-id="38a96-113">How to manage policies</span></span>

<span data-ttu-id="38a96-114">Les stratégies sont gérées avec le Centre d’administration Microsoft Teams ou [à l’aide de PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="38a96-114">Policies are managed with the Microsoft Teams admin center or [using PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell).</span></span>

<span data-ttu-id="38a96-115">Par exemple, une stratégie de configuration d’application peut vous permettre de permettre aux utilisateurs de télécharger des applications personnalisées, d’installer des applications pour le compte de vos utilisateurs et d’épingler des applications à la barre de l’application Teams.</span><span class="sxs-lookup"><span data-stu-id="38a96-115">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="38a96-116">Ces stratégies sont configurées dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="38a96-116">These policies are configured in the Teams admin center.</span></span>

![Capture d’écran de la stratégie de configuration de l’application.](media/app-setup-policy.png)

<span data-ttu-id="38a96-118">En outre, une stratégie de réunion peut être utilisée pour contrôler les paramètres audio et vidéo dans les réunions Teams, tels que les transcriptions, les enregistrements cloud et les enregistrements IP audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="38a96-118">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![Capture d’écran de la stratégie de réunion.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="38a96-120">Teams pour l’éducation</span><span class="sxs-lookup"><span data-stu-id="38a96-120">Teams for Education</span></span>

<span data-ttu-id="38a96-121">Vous pouvez également utiliser [l’Assistant Stratégie](easy-policy-setup-edu.md) de Teams pour l’Éducation pour configurer et gérer facilement des stratégies pour votre environnement d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="38a96-121">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Capture d’écran de l’Assistant Stratégie de Teams pour l’Éducation.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="38a96-123">Types de stratégies</span><span class="sxs-lookup"><span data-stu-id="38a96-123">Types of policies</span></span>

<span data-ttu-id="38a96-124">Les stratégies suivantes peuvent être gérées avec Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="38a96-124">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="38a96-125">Type de stratégie</span><span class="sxs-lookup"><span data-stu-id="38a96-125">Policy type</span></span> | <span data-ttu-id="38a96-126">Description</span><span class="sxs-lookup"><span data-stu-id="38a96-126">Description</span></span>
------------|------------
[<span data-ttu-id="38a96-127">Packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="38a96-127">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="38a96-128">Un package de stratégie dans Microsoft Teams est un ensemble de stratégies et de paramètres prédéfinés que vous pouvez affecter aux utilisateurs ayant des rôles similaires dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="38a96-128">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="38a96-129">Stratégies de réunion</span><span class="sxs-lookup"><span data-stu-id="38a96-129">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="38a96-130">Une stratégie de réunion permet de contrôler les fonctionnalités disponibles pour les participants à la réunion prévues par les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="38a96-130">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="38a96-131">Les stratégies de réunion incluent les sujets suivants.</span><span class="sxs-lookup"><span data-stu-id="38a96-131">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="38a96-132">- Stratégies audio et vidéo</span><span class="sxs-lookup"><span data-stu-id="38a96-132">- Audio and video policies</span></span><br> <span data-ttu-id="38a96-133">- Stratégies de partage de contenu et d’écran</span><span class="sxs-lookup"><span data-stu-id="38a96-133">- Content and screen sharing policies</span></span><br> <span data-ttu-id="38a96-134">- Stratégies d’accès, participants et invités</span><span class="sxs-lookup"><span data-stu-id="38a96-134">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="38a96-135">- Politiques générales</span><span class="sxs-lookup"><span data-stu-id="38a96-135">- General policies</span></span>
[<span data-ttu-id="38a96-136">Stratégies de voix et d’appel</span><span class="sxs-lookup"><span data-stu-id="38a96-136">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="38a96-137">Les stratégies de voix et d’appel gèrent ces paramètres via les équipes, telles que les appels d’urgence, le routage des appels et l’ID d’appelant.</span><span class="sxs-lookup"><span data-stu-id="38a96-137">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="38a96-138">Stratégies d’application</span><span class="sxs-lookup"><span data-stu-id="38a96-138">App policies</span></span>](app-policies.md)| <span data-ttu-id="38a96-139">Les stratégies d’application servent à contrôler les applications dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="38a96-139">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="38a96-140">Les administrateurs peuvent autoriser ou bloquer les applications que les utilisateurs peuvent installer, épingler des applications à la barre d’application Teams d’un utilisateur et installer une application pour le compte de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="38a96-140">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="38a96-141">Stratégies de messagerie</span><span class="sxs-lookup"><span data-stu-id="38a96-141">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="38a96-142">Les stratégies de messagerie contrôlent la disponibilité des fonctionnalités de conversation et de canal.</span><span class="sxs-lookup"><span data-stu-id="38a96-142">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="38a96-143">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="38a96-143">Related topics</span></span>

* [<span data-ttu-id="38a96-144">Gérer les stratégies de commentaires dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38a96-144">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="38a96-145">Gérer les stratégies teams dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38a96-145">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="38a96-146">Configurer des événements en direct dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38a96-146">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="38a96-147">Stratégies et packages de stratégies Teams pour l’Éducation</span><span class="sxs-lookup"><span data-stu-id="38a96-147">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)
