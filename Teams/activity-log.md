---
title: Afficher vos affectations de stratégie dans le journal d’activité du Centre Microsoft Teams’administration
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment afficher vos activités d’affectation de stratégie dans le journal d’activité du Microsoft Teams d’administration.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821314"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="2e1c7-103">Afficher vos affectations de stratégie dans le journal d’activité</span><span class="sxs-lookup"><span data-stu-id="2e1c7-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="2e1c7-104">Lorsque vous attribuez des stratégies à des utilisateurs dans le Microsoft Teams d’administration, vous pouvez afficher l’état de ces affectations de stratégie dans le journal d’activité.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="2e1c7-105">Le journal d’activité affiche les affectations de stratégie à des lots de plus de 20 utilisateurs via le Centre Microsoft Teams d’administration à partir des 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="2e1c7-106">Gardez à l’esprit que le journal d’activité n’affiche pas les affectations de packages de stratégie, les affectations de stratégie à des lots de moins de 20 utilisateurs via le Centre d’administration Microsoft Teams ou les affectations de stratégies via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Capture d’écran de la page du journal d’activité](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="2e1c7-108">Afficher vos activités d’affectation de stratégie dans le journal d’activité</span><span class="sxs-lookup"><span data-stu-id="2e1c7-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="2e1c7-109">Pour afficher vos affectations de stratégie dans le journal d’activité :</span><span class="sxs-lookup"><span data-stu-id="2e1c7-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="2e1c7-110">Dans le navigation gauche du centre d Microsoft Teams d’administration, allez dans Tableau de **bord,** puis sous Journal d’activité, sélectionnez Afficher les **détails.**</span><span class="sxs-lookup"><span data-stu-id="2e1c7-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="2e1c7-111">Vous pouvez afficher toutes les affectations de stratégie ou filtrer la liste par état pour afficher uniquement les affectations Non **commencées,** En **cours** ou **Terminées.**</span><span class="sxs-lookup"><span data-stu-id="2e1c7-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="2e1c7-112">Vous verrez les informations suivantes sur chaque devoir :</span><span class="sxs-lookup"><span data-stu-id="2e1c7-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="2e1c7-113">**Nom**: nom de l’affectation de stratégie.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="2e1c7-114">Cliquez sur le lien pour afficher plus de détails.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-114">Click the link to view more details.</span></span> <span data-ttu-id="2e1c7-115">Cela inclut le nombre d’utilisateurs à qui la stratégie a été attribuée, ainsi que le nombre d’affectations terminées, en cours et non démarrées.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="2e1c7-116">Vous verrez également la liste des utilisateurs dans le lot, ainsi que l’état et le résultat pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="2e1c7-117">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="2e1c7-117">Here's an example:</span></span>

        ![Capture d’écran du](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="2e1c7-119">**Soumis**: Date et heure de soumettre l’affectation de stratégie.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="2e1c7-120">**Heure d’achèvement**: date et heure d’achèvement de l’affectation de stratégie.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="2e1c7-121">**Impact sur**: nombre d’utilisateurs du lot.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="2e1c7-122">**État global**: état de l’affectation de stratégie.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="2e1c7-123">Vous pouvez également ouvrir le journal d’activité à partir de la page **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="2e1c7-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="2e1c7-124">Après avoir **cliqué sur Appliquer** pour envoyer une affectation de stratégie en bloc, une bannière s’affiche en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="2e1c7-125">Cliquez sur le **lien Journal d’activité** dans la bannière.</span><span class="sxs-lookup"><span data-stu-id="2e1c7-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2e1c7-126">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="2e1c7-126">Related topics</span></span>

- [<span data-ttu-id="2e1c7-127">Attribuer des stratégies aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="2e1c7-127">Assign policies to users</span></span>](assign-policies.md)
