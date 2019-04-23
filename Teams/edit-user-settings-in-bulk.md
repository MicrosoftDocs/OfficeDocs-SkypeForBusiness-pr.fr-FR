---
title: Modifier les paramètres d’utilisateurs Microsoft Teams en bloc
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment gérer les paramètres utilisateur de Microsoft Teams en bloc dans le centre d’administration Microsoft Teams.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c1dfba0bdaec642b0ea078d7f10ba022c8514da
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2019
ms.locfileid: "31988972"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="85d90-103">Modifier les paramètres utilisateur de Microsoft Teams en bloc</span><span class="sxs-lookup"><span data-stu-id="85d90-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="85d90-104">En tant qu’administrateur, gérer les paramètres utilisateur d’équipes dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="85d90-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="85d90-105">Dans la page **utilisateurs** , vous pouvez afficher les informations de compte et les détails de licence et modifier les paramètres de stratégie et autres.</span><span class="sxs-lookup"><span data-stu-id="85d90-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="85d90-106">Vous pouvez modifier les paramètres pour les utilisateurs individuellement ou pour plusieurs utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="85d90-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="85d90-107">Modifier les paramètres utilisateur en bloc</span><span class="sxs-lookup"><span data-stu-id="85d90-107">Edit user settings in bulk</span></span>

<span data-ttu-id="85d90-108">Utiliser le centre d’administration Microsoft Teams pour modifier les paramètres pour plusieurs utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="85d90-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="85d90-109">Nous vous recommandons de modification des paramètres pour les utilisateurs de 20 à la fois.</span><span class="sxs-lookup"><span data-stu-id="85d90-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="85d90-110">Pour modifier les paramètres pour un grand nombre d’utilisateurs, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85d90-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="85d90-111">Pour plus d’informations, voir [Vue d’ensemble de PowerShell équipes](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="85d90-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="85d90-112">Dans la navigation de gauche du centre d’administration Microsoft Teams, sélectionnez **les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="85d90-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="85d90-113">Recherche pour les utilisateurs que vous souhaitez modifier ou filtrer l’affichage pour afficher les utilisateurs à modifier.</span><span class="sxs-lookup"><span data-stu-id="85d90-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="85d90-114">Dans la **& #x 2713 ;** colonne (case à cocher), sélectionnez les utilisateurs en effectuant l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="85d90-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="85d90-115">Sélectionnez les utilisateurs un à la fois.</span><span class="sxs-lookup"><span data-stu-id="85d90-115">Select users one at a time.</span></span> <span data-ttu-id="85d90-116">Un **& #x 2713 ;** s’affiche en regard de chaque utilisateur que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="85d90-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="85d90-117">Si vous sélectionnez plus de 20 utilisateurs, vous ne sera pas bloqué, mais n’oubliez pas que les utilisateurs plus que vous sélectionnez, prend plus de temps pour effectuer l’opération.</span><span class="sxs-lookup"><span data-stu-id="85d90-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the operation will take longer to complete.</span></span>

        ![Capture d’écran de la page utilisateurs affichant la sélection de l’utilisateur](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="85d90-119">Cliquez sur le & #x 2713 ; (coche) en haut de la table pour sélectionner tous les utilisateurs (jusqu'à un maximum de 20 utilisateurs), puis cliquez sur **Continuer sélectionner tout** pour terminer la sélection dans la boîte de dialogue **limiter la sélection** .</span><span class="sxs-lookup"><span data-stu-id="85d90-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="85d90-120">![Capture d’écran de la page utilisateurs, en affichant la limite de sélection](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="85d90-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="85d90-121">Un **& #x 2713 ;** s’affiche en regard des utilisateurs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="85d90-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![Capture d’écran de la page utilisateurs, en affichant les 20 utilisateurs sélectionnés](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="85d90-123">Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="85d90-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![Capture d’écran du volet Modifier les paramètres](media/bulk-edit-user-settings-edit-settings.png)
