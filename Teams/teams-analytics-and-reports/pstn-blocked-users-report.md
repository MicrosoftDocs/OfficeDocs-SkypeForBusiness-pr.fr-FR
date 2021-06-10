---
title: Microsoft Teams Rapport sur le blocage d’utilisateurs PSTN
author: cichur
ms.author: v-cichur
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
description: Utilisez le rapport sur le blocage d’utilisateurs PSTN dans le Centre d’administration Microsoft Teams pour obtenir une vue d’ensemble des utilisateurs Teams de votre organisation qui ne peuvent pas passer d’appels PSTN.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809334"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="fb618-103">Microsoft Teams Rapport sur le blocage d’utilisateurs PSTN</span><span class="sxs-lookup"><span data-stu-id="fb618-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="fb618-104">Le rapport sur le blocage d’utilisateurs PSTN dans le Centre d’administration Microsoft Teams affiche les utilisateurs de votre organisation qui sont bloqués et ne peuvent plus effectuer d’appels PSTN dans Teams.</span><span class="sxs-lookup"><span data-stu-id="fb618-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="fb618-105">Vous pouvez afficher plus d’informations sur chaque utilisateur bloqué, y compris son numéro de téléphone affecté et la raison pour laquelle il a été bloqué.</span><span class="sxs-lookup"><span data-stu-id="fb618-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="fb618-106">Afficher le rapport sur le blocage d’utilisateurs PSTN</span><span class="sxs-lookup"><span data-stu-id="fb618-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="fb618-107">Dans la barre de navigation gauche du Centre Microsoft Teams’administration, cliquez sur **Analyse & rapports**  >  **d’utilisation.**</span><span class="sxs-lookup"><span data-stu-id="fb618-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="fb618-108">Sous **l’onglet Afficher les rapports,** sous **Rapport,** sélectionnez **Utilisateurs PSTN** bloqués, puis cliquez sur **Exécuter le rapport.**</span><span class="sxs-lookup"><span data-stu-id="fb618-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="fb618-109">![Rapport sur le blocage d’utilisateurs PSTN dans le Centre d’administration](../media/teams-reports-pstn-blocked-users-with-callouts.png "Capture d’écran du rapport sur le blocage d’utilisateurs PSTN dans le Centre d Microsoft Teams d’administration Microsoft Teams des appels numéroés")</span><span class="sxs-lookup"><span data-stu-id="fb618-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="fb618-110">Interpréter le rapport</span><span class="sxs-lookup"><span data-stu-id="fb618-110">Interpret the report</span></span>

|<span data-ttu-id="fb618-111">Légende</span><span class="sxs-lookup"><span data-stu-id="fb618-111">Callout</span></span> |<span data-ttu-id="fb618-112">Description</span><span class="sxs-lookup"><span data-stu-id="fb618-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="fb618-113">**1**</span><span class="sxs-lookup"><span data-stu-id="fb618-113">**1**</span></span>   |<span data-ttu-id="fb618-114">Chaque rapport indique la date à laquelle il a été généré.</span><span class="sxs-lookup"><span data-stu-id="fb618-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="fb618-115">Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité.</span><span class="sxs-lookup"><span data-stu-id="fb618-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="fb618-116">**2**</span><span class="sxs-lookup"><span data-stu-id="fb618-116">**2**</span></span>   |<span data-ttu-id="fb618-117">L’axe X est la date.</span><span class="sxs-lookup"><span data-stu-id="fb618-117">The X axis is the date.</span></span> <span data-ttu-id="fb618-118">L’axe Y est le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fb618-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="fb618-119">Pointez sur le point à une date donnée pour voir le nombre d’utilisateurs bloqués à cette date.</span><span class="sxs-lookup"><span data-stu-id="fb618-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="fb618-120">**3**</span><span class="sxs-lookup"><span data-stu-id="fb618-120">**3**</span></span>   |<span data-ttu-id="fb618-121">Le tableau détailne tous les utilisateurs bloqués et ne peuvent plus effectuer d’appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="fb618-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="fb618-122">Il affiche tous les utilisateurs Système téléphonique ou l’audioconférence et vous donne des informations supplémentaires sur chacun d’eux.</span><span class="sxs-lookup"><span data-stu-id="fb618-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="fb618-123">**Le nom d’affichage** est le nom d’affichage de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fb618-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="fb618-124">Vous pouvez cliquer sur le nom d’affichage pour aller à la page de paramètres de l’utilisateur dans le Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="fb618-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="fb618-125">**Téléphone** est le numéro affecté à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fb618-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="fb618-126">**La raison du blocage** est la raison pour laquelle l’utilisateur est bloqué et ne peut plus effectuer d’appels.</span><span class="sxs-lookup"><span data-stu-id="fb618-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="fb618-127">**L’action** bloquée vous indique si l’utilisateur est bloqué ou débloqué contre les appels PSTN dans Teams.</span><span class="sxs-lookup"><span data-stu-id="fb618-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="fb618-128">**L’heure** bloquée est la date et l’heure (UTC) à laquelle l’utilisateur a été bloqué.</span><span class="sxs-lookup"><span data-stu-id="fb618-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="fb618-129">Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.</span><span class="sxs-lookup"><span data-stu-id="fb618-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="fb618-130">**4**</span><span class="sxs-lookup"><span data-stu-id="fb618-130">**4**</span></span>   |<span data-ttu-id="fb618-131">Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="fb618-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="fb618-132">**5**</span><span class="sxs-lookup"><span data-stu-id="fb618-132">**5**</span></span>   |<span data-ttu-id="fb618-133">Sélectionnez **Plein écran** pour afficher le rapport en mode Plein écran.</span><span class="sxs-lookup"><span data-stu-id="fb618-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="fb618-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb618-134">Related topics</span></span>

- [<span data-ttu-id="fb618-135">Analyses et rapports Teams</span><span class="sxs-lookup"><span data-stu-id="fb618-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)