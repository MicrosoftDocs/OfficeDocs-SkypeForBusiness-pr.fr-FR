---
title: Modifier les paramètres d’utilisateurs Microsoft Teams en bloc
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment gérer les paramètres utilisateur de Microsoft teams en bloc dans le centre d’administration Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6177a463bee481812323b2334461f20e7021af84
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832644"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="2835c-103">Modification des paramètres utilisateur de Microsoft teams en bloc</span><span class="sxs-lookup"><span data-stu-id="2835c-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="2835c-104">En tant qu’administrateur, vous pouvez gérer les paramètres utilisateur de teams dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2835c-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2835c-105">Dans la page **utilisateurs** , vous pouvez afficher des informations telles que les détails du compte et de la licence, ainsi que la stratégie d’édition et d’autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="2835c-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="2835c-106">Vous pouvez modifier les paramètres pour les utilisateurs individuellement ou pour plusieurs utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="2835c-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="2835c-107">Modification des paramètres utilisateur en bloc</span><span class="sxs-lookup"><span data-stu-id="2835c-107">Edit user settings in bulk</span></span>

<span data-ttu-id="2835c-108">Utilisez le centre d’administration de Microsoft teams pour modifier les paramètres de plusieurs utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="2835c-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="2835c-109">Nous vous recommandons de modifier les paramètres de 20 utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="2835c-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="2835c-110">Pour modifier les paramètres d’un grand nombre d’utilisateurs, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2835c-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="2835c-111">Pour plus d’informations, voir [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2835c-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="2835c-112">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="2835c-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="2835c-113">Recherchez les utilisateurs que vous souhaitez modifier ou filtrez l’affichage pour afficher les utilisateurs que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="2835c-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="2835c-114">Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs en effectuant l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2835c-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="2835c-115">Sélectionner des utilisateurs un par un.</span><span class="sxs-lookup"><span data-stu-id="2835c-115">Select users one at a time.</span></span> <span data-ttu-id="2835c-116">Un **&#x2713;** est affiché en regard de chaque utilisateur que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="2835c-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="2835c-117">Si vous sélectionnez plus de 20 utilisateurs, vous ne serez pas bloqué, mais n’oubliez pas que plus le nombre d’utilisateurs que vous sélectionnez est long, plus l’opération sera terminée.</span><span class="sxs-lookup"><span data-stu-id="2835c-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the longer the operation will take to complete.</span></span>

        ![Capture d’écran de la page utilisateurs montrant la sélection de l’utilisateur](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="2835c-119">Cliquez sur la &#x2713; (coche) en haut du tableau pour sélectionner tous les utilisateurs (jusqu’à 20 utilisateurs maximum), puis dans la boîte de dialogue **limiter la sélection** , cliquez sur **Continuer tout sélectionner** pour terminer la sélection.</span><span class="sxs-lookup"><span data-stu-id="2835c-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="2835c-120">![Capture d’écran de la page utilisateurs montrant la limite de sélection](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="2835c-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="2835c-121">Un **&#x2713;** est affiché en regard des utilisateurs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="2835c-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![Capture d’écran de la page utilisateurs montrant 20 utilisateurs sélectionnés](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="2835c-123">Cliquez sur **modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2835c-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![Capture d’écran du volet modifier les paramètres](media/bulk-edit-user-settings-edit-settings.png)
