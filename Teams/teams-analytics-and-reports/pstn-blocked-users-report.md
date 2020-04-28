---
title: Rapport sur les utilisateurs bloqués RTC de Microsoft teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Utilisez le rapport RTC blocage des utilisateurs dans le centre d’administration de Microsoft teams pour obtenir une vue d’ensemble des utilisateurs d’équipes de votre organisation qui ne peuvent pas passer d’appels RTC.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 511485fa156ba448368809edf54728ada1b80be7
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904906"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="d56a6-103">Rapport sur les utilisateurs bloqués RTC de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="d56a6-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="d56a6-104">Le rapport sur les utilisateurs bloqués RTC dans le centre d’administration Microsoft teams vous indique les utilisateurs de votre organisation qui ne peuvent pas passer d’appels RTC dans Teams.</span><span class="sxs-lookup"><span data-stu-id="d56a6-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="d56a6-105">Vous pouvez afficher des informations supplémentaires sur chaque utilisateur bloqué, y compris son numéro de téléphone et la raison pour laquelle il a été bloqué.</span><span class="sxs-lookup"><span data-stu-id="d56a6-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="d56a6-106">Afficher le rapport sur les utilisateurs bloqués RTC</span><span class="sxs-lookup"><span data-stu-id="d56a6-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="d56a6-107">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **analyse &** > rapports d'**utilisation**des rapports.</span><span class="sxs-lookup"><span data-stu-id="d56a6-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="d56a6-108">Dans l' **onglet Afficher les rapports** , sous **rapport**, sélectionnez **utilisateurs bloqués RTC**, puis cliquez sur **exécuter un rapport**.</span><span class="sxs-lookup"><span data-stu-id="d56a6-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="d56a6-109">![Capture d’écran du rapport de rapport sur les utilisateurs bloqués RTC dans le centre d’administration](../media/teams-reports-pstn-blocked-users-with-callouts.png "Capture d’écran du rapport sur les utilisateurs bloqués RTC dans le centre d’administration Microsoft teams avec des légendes numérotées")</span><span class="sxs-lookup"><span data-stu-id="d56a6-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="d56a6-110">Interpréter le rapport</span><span class="sxs-lookup"><span data-stu-id="d56a6-110">Interpret the report</span></span>

|<span data-ttu-id="d56a6-111">Légende</span><span class="sxs-lookup"><span data-stu-id="d56a6-111">Callout</span></span> |<span data-ttu-id="d56a6-112">Description</span><span class="sxs-lookup"><span data-stu-id="d56a6-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="d56a6-113">**1**</span><span class="sxs-lookup"><span data-stu-id="d56a6-113">**1**</span></span>   |<span data-ttu-id="d56a6-114">Date de génération de chaque rapport.</span><span class="sxs-lookup"><span data-stu-id="d56a6-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="d56a6-115">Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité.</span><span class="sxs-lookup"><span data-stu-id="d56a6-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="d56a6-116">**2**</span><span class="sxs-lookup"><span data-stu-id="d56a6-116">**2**</span></span>   |<span data-ttu-id="d56a6-117">L’axe X correspond à la date.</span><span class="sxs-lookup"><span data-stu-id="d56a6-117">The X axis is the date.</span></span> <span data-ttu-id="d56a6-118">L’axe Y indique le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d56a6-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="d56a6-119">Pointez sur le point d’une date donnée pour afficher le nombre d’utilisateurs bloqués à cette date.</span><span class="sxs-lookup"><span data-stu-id="d56a6-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="d56a6-120">**3**</span><span class="sxs-lookup"><span data-stu-id="d56a6-120">**3**</span></span>   |<span data-ttu-id="d56a6-121">Le tableau fournit une répartition de tous les utilisateurs qui ne peuvent pas passer d’appels RTC.</span><span class="sxs-lookup"><span data-stu-id="d56a6-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="d56a6-122">Il affiche tous les utilisateurs disposant d’un système téléphonique ou d’une audioconférence attribué et vous donne des informations supplémentaires sur chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d56a6-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="d56a6-123">**Nom complet** est le nom d’affichage de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d56a6-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="d56a6-124">Vous pouvez cliquer sur le nom d’affichage pour accéder à la page de paramètres de l’utilisateur dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d56a6-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="d56a6-125">**Téléphone** correspond au numéro attribué à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d56a6-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="d56a6-126">**Raison du blocage** est la raison pour laquelle l’utilisateur est empêché d’effectuer des appels.</span><span class="sxs-lookup"><span data-stu-id="d56a6-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="d56a6-127">L' **action bloqué** vous indique si l’utilisateur est bloqué ou débloqué pour passer des appels RTC dans Teams.</span><span class="sxs-lookup"><span data-stu-id="d56a6-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="d56a6-128">Le **temps bloqué** est la date et l’heure (UTC) auxquelles l’utilisateur a été empêché de passer des appels.</span><span class="sxs-lookup"><span data-stu-id="d56a6-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="d56a6-129">Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.</span><span class="sxs-lookup"><span data-stu-id="d56a6-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="d56a6-130">**4**</span><span class="sxs-lookup"><span data-stu-id="d56a6-130">**4**</span></span>   |<span data-ttu-id="d56a6-131">Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="d56a6-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="d56a6-132">**5**</span><span class="sxs-lookup"><span data-stu-id="d56a6-132">**5**</span></span>   |<span data-ttu-id="d56a6-133">Pour afficher le rapport en mode plein écran, sélectionnez **plein écran** .</span><span class="sxs-lookup"><span data-stu-id="d56a6-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="d56a6-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d56a6-134">Related topics</span></span>

- [<span data-ttu-id="d56a6-135">Analyses et rapports Teams</span><span class="sxs-lookup"><span data-stu-id="d56a6-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)