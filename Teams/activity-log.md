---
title: Afficher vos affectations de stratégie dans le journal d’activité dans le centre d’administration Microsoft teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment afficher les activités d’affectation de stratégie dans le journal d’activité dans le centre d’administration Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f85899869a8578df59516d0e0d702f8e36bd951
ms.sourcegitcommit: 47637ed816b471fe689e7bdac27b73e6efced60c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374292"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="899f4-103">Afficher vos affectations de stratégie dans le journal d’activité</span><span class="sxs-lookup"><span data-stu-id="899f4-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="899f4-104">Lorsque vous attribuez des stratégies aux utilisateurs dans le centre d’administration Microsoft Teams, vous pouvez afficher l’état de ces affectations de stratégie dans le journal d’activité.</span><span class="sxs-lookup"><span data-stu-id="899f4-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="899f4-105">Le journal d’activité affiche les affectations de stratégie aux lots de plus de 20 utilisateurs par le biais du centre d’administration Microsoft teams depuis les 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="899f4-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="899f4-106">Gardez à l’esprit que le journal d’activité ne montre pas les affectations de packages de stratégie, les affectations de stratégie aux lots de moins de 20 utilisateurs via le centre d’administration Microsoft teams ou les affectations de stratégie via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="899f4-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Capture d’écran de la page Journal d’activité](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="899f4-108">Afficher vos activités d’attribution de stratégie dans le journal d’activité</span><span class="sxs-lookup"><span data-stu-id="899f4-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="899f4-109">Pour afficher vos affectations de stratégie dans le journal d’activité :</span><span class="sxs-lookup"><span data-stu-id="899f4-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="899f4-110">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez au **tableau de bord**, puis sous **Journal d’activité**, sélectionnez Afficher les **Détails**.</span><span class="sxs-lookup"><span data-stu-id="899f4-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="899f4-111">Vous pouvez afficher toutes les affectations de stratégie ou filtrer la liste par État pour afficher uniquement les affectations **non commencées**, **en cours**ou **achevées**.</span><span class="sxs-lookup"><span data-stu-id="899f4-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="899f4-112">Les informations suivantes s’affichent sur chaque affectation :</span><span class="sxs-lookup"><span data-stu-id="899f4-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="899f4-113">**Nom**: nom de l’affectation de stratégie.</span><span class="sxs-lookup"><span data-stu-id="899f4-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="899f4-114">Cliquez sur le lien pour afficher plus de détails.</span><span class="sxs-lookup"><span data-stu-id="899f4-114">Click the link to view more details.</span></span> <span data-ttu-id="899f4-115">Il s’agit du nombre d’utilisateurs auxquels la stratégie a été affectée et du nombre d’affectations achevées, en cours et non démarrées.</span><span class="sxs-lookup"><span data-stu-id="899f4-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="899f4-116">Vous pouvez également afficher la liste des utilisateurs dans le lot et l’État et le résultat de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="899f4-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="899f4-117">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="899f4-117">Here's an example:</span></span>

        ![Capture d’écran du](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="899f4-119">**Envoyé**: date et heure de soumission de l’affectation de stratégie.</span><span class="sxs-lookup"><span data-stu-id="899f4-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="899f4-120">**Heure de fin**: date et heure de fin de l’affectation de stratégie.</span><span class="sxs-lookup"><span data-stu-id="899f4-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="899f4-121">**Impact sur**: nombre d’utilisateurs du lot.</span><span class="sxs-lookup"><span data-stu-id="899f4-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="899f4-122">**État global**: état de l’affectation de stratégie.</span><span class="sxs-lookup"><span data-stu-id="899f4-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="899f4-123">Vous pouvez également accéder au Journal d’activité à partir de la page **utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="899f4-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="899f4-124">Après avoir cliqué sur **appliquer** pour valider une affectation de stratégie en bloc, une bannière apparaît en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="899f4-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="899f4-125">Cliquez sur le lien **Journal d’activité** dans la bannière.</span><span class="sxs-lookup"><span data-stu-id="899f4-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="899f4-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="899f4-126">Related topics</span></span>

- [<span data-ttu-id="899f4-127">Attribution de stratégies aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="899f4-127">Assign policies to users</span></span>](assign-policies.md)
