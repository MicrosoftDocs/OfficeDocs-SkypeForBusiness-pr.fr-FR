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
ms.openlocfilehash: aafa7b57eea1228fa5565bb4d5e95304b42751a3
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718045"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="c3aeb-103">Configurer les webinaires dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3aeb-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="c3aeb-104">Cet article vous aide à configurer votre organisation pour héberger des webinaires.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="c3aeb-105">Que sont les webinaires ?</span><span class="sxs-lookup"><span data-stu-id="c3aeb-105">What are webinars?</span></span>

<span data-ttu-id="c3aeb-106">Les webinaires sont des réunions structurées où les instructeurs et les participants ont des rôles clairs, souvent utilisés à des fins de formation ou de scénarios de marketing de tête de série.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-106">Webinars are structured meetings where instructors and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="c3aeb-107">Après avoir mis en place des webinaires dans votre organisation, vos utilisateurs peuvent planifier des webinaires et ouvrir l’inscription aux participants.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="c3aeb-108">Contrairement aux réunions traditionnelles qui incluent de nombreuses discussions et l’affectation de tâches, les webinaires sont destinés aux présentations interactives et fournissent des outils pour l’analyse des participants.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="c3aeb-109">Autoriser les utilisateurs à planifier des webinaires à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3aeb-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="c3aeb-110">Vous pouvez utiliser les attributs suivants dans la cmdlet Windows PowerShell **Set-CsTeamsMeetingPolicy** pour configurer les webinaires dans Teams.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="c3aeb-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="c3aeb-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="c3aeb-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="c3aeb-112">WhoCanRegister</span></span>
- <span data-ttu-id="c3aeb-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c3aeb-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="c3aeb-114">Lisez [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) pour plus d’informations sur l’cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="c3aeb-115">Avant d’exécuter ces cmdlets, vous devez être connecté à Skype Entreprise PowerShell en ligne.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-115">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="c3aeb-116">Pour plus d’informations, voir Gérer Skype Entreprise Online avec [Microsoft 365 ou Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="c3aeb-116">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="c3aeb-117">Autoriser les utilisateurs à planifier des webinaires</span><span class="sxs-lookup"><span data-stu-id="c3aeb-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="c3aeb-118">Pour autoriser les utilisateurs de votre organisation à planifier des webinaires, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c3aeb-118">To allow users in your organization to schedule webinars, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```
### <a name="configure-who-can-register-for-webinars"></a><span data-ttu-id="c3aeb-119">Configurer les utilisateurs qui peuvent s’inscrire aux webinaires</span><span class="sxs-lookup"><span data-stu-id="c3aeb-119">Configure who can register for webinars</span></span>

<span data-ttu-id="c3aeb-120">Vous pouvez limiter l’inscription aux seuls utilisateurs de votre organisation ou l’ouvrir à tous les utilisateurs à l’intérieur et à l’extérieur de votre client.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-120">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="c3aeb-121">Par défaut, **WhoCanRegister** est activé et activé sur **Tout le monde.**</span><span class="sxs-lookup"><span data-stu-id="c3aeb-121">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="c3aeb-122">Si vous voulez désactiver l’inscription aux réunions, définissez **AllowMeetingRegistration** sur **False.**</span><span class="sxs-lookup"><span data-stu-id="c3aeb-122">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3aeb-123">N’oubliez **pas que AllowPrivateMeetingScheduling** doit être réglé sur **True** pour que **AllowMeetingRegistration** fonctionne.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-123">Keep in mind that **AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="c3aeb-124">En outre, les listes Microsoft doivent être définies dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-124">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="c3aeb-125">Pour en savoir plus, [consultez les paramètres de contrôle pour les listes Microsoft.](/sharepoint/control-lists)</span><span class="sxs-lookup"><span data-stu-id="c3aeb-125">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

<span data-ttu-id="c3aeb-126">**Pour autoriser uniquement *les utilisateurs* de votre organisation à s’inscrire aux webinaires, exécutez :**</span><span class="sxs-lookup"><span data-stu-id="c3aeb-126">**To allow *only* users in your organization to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

<span data-ttu-id="c3aeb-127">Exécutez ensuite :</span><span class="sxs-lookup"><span data-stu-id="c3aeb-127">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="c3aeb-128">**Pour autoriser tout le monde, y compris les utilisateurs anonymes, à s’inscrire aux webinaires, exécutez :**</span><span class="sxs-lookup"><span data-stu-id="c3aeb-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

<span data-ttu-id="c3aeb-129">Exécutez ensuite :</span><span class="sxs-lookup"><span data-stu-id="c3aeb-129">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
> <span data-ttu-id="c3aeb-130">Si la rejoindre anonyme est désactivée dans les paramètres de réunion, les utilisateurs anonymes ne peuvent pas participer à des webinaires.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-130">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="c3aeb-131">Pour en savoir plus et activer ce paramètre, consultez [les paramètres de réunion dans Teams.](meeting-settings-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="c3aeb-131">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="c3aeb-132">Recueillir la participation aux réunions</span><span class="sxs-lookup"><span data-stu-id="c3aeb-132">Collect meeting attendance</span></span>

<span data-ttu-id="c3aeb-133">Si vous souhaitez que les organisateurs analysent les webinaires inscrits et participé, vous devez activer la stratégie **AllowEngagementReport.**</span><span class="sxs-lookup"><span data-stu-id="c3aeb-133">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="c3aeb-134">Pour ce faire, exécutez la commande suivante dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-134">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="c3aeb-135">Configurer les paramètres de webinaire</span><span class="sxs-lookup"><span data-stu-id="c3aeb-135">Configure webinar settings</span></span>

<span data-ttu-id="c3aeb-136">Après l’activation de votre environnement pour les webinaires, aucune autre gestion de l’administrateur n’est requise.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-136">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="c3aeb-137">La stratégie contrôle les options qui s’affichent pour les organisateurs de webinaires.</span><span class="sxs-lookup"><span data-stu-id="c3aeb-137">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3aeb-138">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="c3aeb-138">Related topics</span></span>

- [<span data-ttu-id="c3aeb-139">Stratégies de réunion dans Teams - Général</span><span class="sxs-lookup"><span data-stu-id="c3aeb-139">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="c3aeb-140">Documentation set-CsTeamsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="c3aeb-140">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
