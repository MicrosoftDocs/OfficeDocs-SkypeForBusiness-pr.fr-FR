---
title: Configurer les webinaires dans Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Découvrez comment gérer les stratégies de webinaire pour Teams réunions.
ms.openlocfilehash: 14452b0caeee33f90b59f6581b6fccf4d5e0311b
ms.sourcegitcommit: 4a039550bc5c3a497b6b52c7fed08cadf8268b06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926746"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="27fa4-103">Configurer les webinaires dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="27fa4-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="27fa4-104">Cet article vous aide à configurer votre organisation pour héberger des webinaires.</span><span class="sxs-lookup"><span data-stu-id="27fa4-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="27fa4-105">Que sont les webinaires ?</span><span class="sxs-lookup"><span data-stu-id="27fa4-105">What are webinars?</span></span>

<span data-ttu-id="27fa4-106">Les webinaires sont des réunions structurées où les présentateurs et participants ont des rôles clairs, souvent utilisés à des fins de formation ou de scénarios de marketing de tête de série.</span><span class="sxs-lookup"><span data-stu-id="27fa4-106">Webinars are structured meetings where presenters and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="27fa4-107">Après avoir mis en place des webinaires dans votre organisation, vos utilisateurs peuvent planifier des webinaires et ouvrir l’inscription aux participants.</span><span class="sxs-lookup"><span data-stu-id="27fa4-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="27fa4-108">Contrairement aux réunions traditionnelles qui incluent de nombreuses discussions et l’affectation de tâches, les webinaires sont destinés aux présentations interactives et offrent des outils pour l’analyse des participants.</span><span class="sxs-lookup"><span data-stu-id="27fa4-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="27fa4-109">Autoriser les utilisateurs à planifier des webinaires à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="27fa4-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="27fa4-110">Vous pouvez utiliser les attributs suivants dans la cmdlet Windows PowerShell **Set-CsTeamsMeetingPolicy** pour configurer les webinaires dans Teams.</span><span class="sxs-lookup"><span data-stu-id="27fa4-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="27fa4-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="27fa4-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="27fa4-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="27fa4-112">WhoCanRegister</span></span>
- <span data-ttu-id="27fa4-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="27fa4-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="27fa4-114">Lisez [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) pour plus d’informations sur l’cmdlet.</span><span class="sxs-lookup"><span data-stu-id="27fa4-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="27fa4-115">Avant d’exécuter ces cmdlets, vous devez être connecté à Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27fa4-115">Before you can run these cmdlets you must be connected to Microsoft Teams PowerShell.</span></span> <span data-ttu-id="27fa4-116">Pour plus d’informations, voir [Gérer Teams avec Microsoft Teams PowerShell.](/microsoftteams/teams-powershell-managing-teams)</span><span class="sxs-lookup"><span data-stu-id="27fa4-116">For more information, see [Manage Teams with Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="27fa4-117">Autoriser les utilisateurs à planifier des webinaires</span><span class="sxs-lookup"><span data-stu-id="27fa4-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="27fa4-118">Vous pouvez limiter l’inscription aux seuls utilisateurs de votre organisation ou l’ouvrir à tous les utilisateurs à l’intérieur et à l’extérieur de votre client.</span><span class="sxs-lookup"><span data-stu-id="27fa4-118">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="27fa4-119">Par défaut, **WhoCanRegister** est activé et activé sur **Tout le monde.**</span><span class="sxs-lookup"><span data-stu-id="27fa4-119">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="27fa4-120">Si vous voulez désactiver l’inscription aux réunions, définissez **AllowMeetingRegistration** sur **False.**</span><span class="sxs-lookup"><span data-stu-id="27fa4-120">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27fa4-121">**AllowPrivateMeetingScheduling** doit être réglé sur **True** pour que **AllowMeetingRegistration** fonctionne.</span><span class="sxs-lookup"><span data-stu-id="27fa4-121">**AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="27fa4-122">En outre, les listes Microsoft doivent être définies dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="27fa4-122">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="27fa4-123">Pour en savoir plus, [consultez les paramètres de contrôle pour les listes Microsoft.](/sharepoint/control-lists)</span><span class="sxs-lookup"><span data-stu-id="27fa4-123">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

1. <span data-ttu-id="27fa4-124">Activer l’inscription aux réunions</span><span class="sxs-lookup"><span data-stu-id="27fa4-124">Turn on meeting registration</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. <span data-ttu-id="27fa4-125">Activer la planification de réunions privées</span><span class="sxs-lookup"><span data-stu-id="27fa4-125">Turn on private meeting scheduling</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. <span data-ttu-id="27fa4-126">Configurer les utilisateurs qui peuvent s’inscrire aux webinaires</span><span class="sxs-lookup"><span data-stu-id="27fa4-126">Configure who can register for webinars</span></span>

<span data-ttu-id="27fa4-127">**Autoriser *uniquement les* utilisateurs de votre organisation à s’inscrire aux webinaires**</span><span class="sxs-lookup"><span data-stu-id="27fa4-127">**Allow *only* users in your organization to register for webinars**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="27fa4-128">**Pour autoriser tout le monde, y compris les utilisateurs anonymes, à s’inscrire aux webinaires, exécutez :**</span><span class="sxs-lookup"><span data-stu-id="27fa4-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> <span data-ttu-id="27fa4-129">Si la rejoindre anonyme est désactivée dans les paramètres de réunion, les utilisateurs anonymes ne peuvent pas participer à des webinaires.</span><span class="sxs-lookup"><span data-stu-id="27fa4-129">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="27fa4-130">Pour en savoir plus et activer ce paramètre, consultez [les paramètres de réunion dans Teams.](meeting-settings-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="27fa4-130">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="27fa4-131">Recueillir la participation aux réunions</span><span class="sxs-lookup"><span data-stu-id="27fa4-131">Collect meeting attendance</span></span>

<span data-ttu-id="27fa4-132">Si vous souhaitez que les organisateurs analysent les webinaires inscrits et participé, vous devez activer la stratégie **AllowEngagementReport.**</span><span class="sxs-lookup"><span data-stu-id="27fa4-132">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="27fa4-133">Pour ce faire, exécutez la commande suivante dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27fa4-133">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="27fa4-134">Configurer les paramètres de webinaire</span><span class="sxs-lookup"><span data-stu-id="27fa4-134">Configure webinar settings</span></span>

<span data-ttu-id="27fa4-135">Après l’activation de votre environnement pour les webinaires, aucune autre gestion de l’administrateur n’est requise.</span><span class="sxs-lookup"><span data-stu-id="27fa4-135">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="27fa4-136">La stratégie contrôle les options qui s’affichent pour les organisateurs de webinaires.</span><span class="sxs-lookup"><span data-stu-id="27fa4-136">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="27fa4-137">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="27fa4-137">Related topics</span></span>

- [<span data-ttu-id="27fa4-138">Stratégies de réunion dans Teams - Général</span><span class="sxs-lookup"><span data-stu-id="27fa4-138">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="27fa4-139">Documentation set-CsTeamsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="27fa4-139">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
