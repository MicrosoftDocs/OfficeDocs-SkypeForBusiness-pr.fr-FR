---
title: Configurer des jours fériés dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.holidays.overview
- seo-marvel-apr2020
description: Apprenez à configurer les jours fériés dans Microsoft teams pour les utiliser avec vos standards automatiques.
ms.openlocfilehash: ff87a3888bc98e1794f8074052aae4c0bbe3545d
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993470"
---
# <a name="set-up-holidays-in-microsoft-teams"></a><span data-ttu-id="19e5b-103">Configurer des jours fériés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19e5b-103">Set up holidays in Microsoft Teams</span></span>

<span data-ttu-id="19e5b-104">Vous pouvez utiliser la fonction des jours fériés de teams pour fournir des messages et des heures de remplacement aux appelants pour des dates et heures spécifiques lorsque les services, les files d’attente d’appels ou les membres de votre organisation suivent des heures de travail différentes ou ne seront pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="19e5b-104">You can use the Teams Holidays feature to provide alternate messages and routing to callers for specific dates and times when departments, call queues or people in your organization will be following different working hours or won't be available.</span></span> <span data-ttu-id="19e5b-105">Par exemple, il se peut que vous deviez créer un congé pour le jour de l’année en cours lorsque votre organisation peut être fermée.</span><span class="sxs-lookup"><span data-stu-id="19e5b-105">For example, you might create a holiday for New Year's day when your organization may be closed.</span></span>

<span data-ttu-id="19e5b-106">Les jours fériés que vous créez ici sont disponibles lorsque vous [configurez un standard automatique](create-a-phone-system-auto-attendant.md), qui dispose de ses propres paramètres d’accueil et d’acheminement des appels.</span><span class="sxs-lookup"><span data-stu-id="19e5b-106">The holidays you create here are available when you [set up an auto attendant](create-a-phone-system-auto-attendant.md), each with its own greeting and call routing settings.</span></span>

## <a name="create-a-holiday"></a><span data-ttu-id="19e5b-107">Créer un jour férié</span><span class="sxs-lookup"><span data-stu-id="19e5b-107">Create a holiday</span></span>

<span data-ttu-id="19e5b-108">Pour créer un jour férié</span><span class="sxs-lookup"><span data-stu-id="19e5b-108">To create a holiday</span></span>

1. <span data-ttu-id="19e5b-109">Dans le centre d’administration de Microsoft Teams, accédez à la **section**  >  **jours fériés**.</span><span class="sxs-lookup"><span data-stu-id="19e5b-109">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="19e5b-110">Sélectionnez **nouveau jour férié**.</span><span class="sxs-lookup"><span data-stu-id="19e5b-110">Select **New holiday**.</span></span>

3. <span data-ttu-id="19e5b-111">Entrez le nom du jour férié.</span><span class="sxs-lookup"><span data-stu-id="19e5b-111">Enter a name for the holiday.</span></span>

4. <span data-ttu-id="19e5b-112">Sélectionnez **Ajouter une nouvelle date**.</span><span class="sxs-lookup"><span data-stu-id="19e5b-112">Select **Add new date**.</span></span>

5. <span data-ttu-id="19e5b-113">Sous **heure de début** , sélectionnez l’icône calendrier et choisissez la date à laquelle vous voulez que le jour férié commence.</span><span class="sxs-lookup"><span data-stu-id="19e5b-113">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

6. <span data-ttu-id="19e5b-114">Utilisez la liste déroulante pour sélectionner une heure de début pour le jour férié.</span><span class="sxs-lookup"><span data-stu-id="19e5b-114">Use the drop-down list to select a start time for the holiday.</span></span>

7. <span data-ttu-id="19e5b-115">Sous **heure de fin** , sélectionnez l’icône de calendrier et choisissez la date à laquelle vous voulez que le jour férié se termine.</span><span class="sxs-lookup"><span data-stu-id="19e5b-115">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span>

8. <span data-ttu-id="19e5b-116">Utilisez la liste déroulante pour sélectionner une heure de fin pour le jour férié.</span><span class="sxs-lookup"><span data-stu-id="19e5b-116">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="19e5b-117">L' **heure de fin** doit être ultérieure au **début**.</span><span class="sxs-lookup"><span data-stu-id="19e5b-117">The **End time** must be after the **Start time**.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="19e5b-118">S’il s’agit d’une journée entière (c’est-à-dire une période de 24 heures), l' **heure de fin** doit être définie au jour suivant et au temps de 12:00 AM.</span><span class="sxs-lookup"><span data-stu-id="19e5b-118">If the holiday is for one full day (i.e., a 24 hour period), the **End time** should be set to the next day and the time to 12:00 AM.</span></span> <span data-ttu-id="19e5b-119">Par exemple, si votre organisation est clôturée le 1er janvier pour le jour de l’année, définissez l' **heure de début** sur le mois de janvier 1 12:00 et définissez l' **heure de fin** sur 2 janvier 12:00 AM.</span><span class="sxs-lookup"><span data-stu-id="19e5b-119">For example, if your organization is closed on January 1 for New Year's day, set the **Start time** to January 1 12:00 AM and set the **End time** to January 2 @ 12:00 AM.</span></span>

9. <span data-ttu-id="19e5b-120">Vous pouvez également ajouter d’autres dates aux jours fériés récurrents.</span><span class="sxs-lookup"><span data-stu-id="19e5b-120">Optionally, add more dates for recurring holidays.</span></span>

10. <span data-ttu-id="19e5b-121">Sélectionnez **Save (enregistrer** ).</span><span class="sxs-lookup"><span data-stu-id="19e5b-121">Select **Save**.</span></span>

    ![Capture d’écran de l’interface utilisateur des jours fériés avec dates configurées pour trois années](media/holidays-set-up.png)

## <a name="change-a-holiday"></a><span data-ttu-id="19e5b-123">Modification d’un jour férié</span><span class="sxs-lookup"><span data-stu-id="19e5b-123">Change a holiday</span></span>

<span data-ttu-id="19e5b-124">Pour changer un jour férié</span><span class="sxs-lookup"><span data-stu-id="19e5b-124">To change a holiday</span></span>

1. <span data-ttu-id="19e5b-125">Dans le centre d’administration de Microsoft Teams, accédez à la **section**  >  **jours fériés**.</span><span class="sxs-lookup"><span data-stu-id="19e5b-125">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="19e5b-126">Sélectionnez les jours fériés dans la liste.</span><span class="sxs-lookup"><span data-stu-id="19e5b-126">Select the holiday from the list.</span></span>

3. <span data-ttu-id="19e5b-127">Sous **heure de début** , sélectionnez l’icône calendrier et choisissez la date à laquelle vous voulez que le jour férié commence.</span><span class="sxs-lookup"><span data-stu-id="19e5b-127">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

4. <span data-ttu-id="19e5b-128">Utilisez la liste déroulante pour sélectionner une heure de début pour le jour férié.</span><span class="sxs-lookup"><span data-stu-id="19e5b-128">Use the drop-down list to select a start time for the holiday.</span></span>

5. <span data-ttu-id="19e5b-129">Sous **heure de fin** , sélectionnez l’icône de calendrier et choisissez la date à laquelle vous voulez que le jour férié se termine.</span><span class="sxs-lookup"><span data-stu-id="19e5b-129">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span> 

6. <span data-ttu-id="19e5b-130">Utilisez la liste déroulante pour sélectionner une heure de fin pour le jour férié.</span><span class="sxs-lookup"><span data-stu-id="19e5b-130">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="19e5b-131">L' **heure de fin** doit être ultérieure au **début**.</span><span class="sxs-lookup"><span data-stu-id="19e5b-131">The **End time** must be after the **Start time**.</span></span>  

7. <span data-ttu-id="19e5b-132">Sélectionnez **Save (enregistrer** ).</span><span class="sxs-lookup"><span data-stu-id="19e5b-132">Select **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="19e5b-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="19e5b-133">Related topics</span></span>

<span data-ttu-id="19e5b-134">[Plan pour les standards automatiques des équipes et les files d’attente d’appels](plan-auto-attendant-call-queue.md)?</span><span class="sxs-lookup"><span data-stu-id="19e5b-134">[Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md)?</span></span>
