---
title: Gérer les modèles Teams dans le Centre d’administration
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment gérer les modèles Teams dans le Centre d’administration
ms.openlocfilehash: b32be22dc7a57e65c6ec8d901ae6e7b004ce4b6c
ms.sourcegitcommit: 3db994f3d26b05071d84b2004892a2ca2ff26d25
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/13/2021
ms.locfileid: "50765827"
---
# <a name="manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="83baa-103">Gérer les modèles Teams dans le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="83baa-103">Manage Teams templates in the admin center</span></span>

<span data-ttu-id="83baa-104">Gérez les modèles Teams que vos utilisateurs finaux voient en créant des stratégies de modèles dans le Centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="83baa-104">Manage the Teams templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="83baa-105">Dans chaque stratégie de modèle, vous pouvez désigner les modèles affichés ou masqués.</span><span class="sxs-lookup"><span data-stu-id="83baa-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="83baa-106">Affectez différents utilisateurs à différentes stratégies de modèle afin que vos utilisateurs ne visualisent que le sous-ensemble de modèles Teams spécifiés.</span><span class="sxs-lookup"><span data-stu-id="83baa-106">Assign different users to different template policies so that your users view only the subset of Teams templates specified.</span></span>

<span data-ttu-id="83baa-107">Regardez cette courte vidéo pour découvrir comment gérer les stratégies de modèle.</span><span class="sxs-lookup"><span data-stu-id="83baa-107">Watch this short video to learn how to manage template policies.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="83baa-108">Créer des stratégies de modèle et attribuer des modèles disponibles</span><span class="sxs-lookup"><span data-stu-id="83baa-108">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="83baa-109">Connectez-vous au Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="83baa-109">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="83baa-110">Développer les  >  **stratégies des modèles** Teams.</span><span class="sxs-lookup"><span data-stu-id="83baa-110">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="83baa-111">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="83baa-111">Select **Add**.</span></span>

    ![Les stratégies de modèle sont sélectionnées et l’ajout est mis en évidence](media/template-policies-1.png)

1. <span data-ttu-id="83baa-113">Dans la section **Paramètres de stratégies de modèles,** remplissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="83baa-113">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="83baa-114">Nom de la stratégie modèles</span><span class="sxs-lookup"><span data-stu-id="83baa-114">Templates Policy name</span></span>

    - <span data-ttu-id="83baa-115">Brève description de la stratégie de modèles</span><span class="sxs-lookup"><span data-stu-id="83baa-115">Templates Policy short description</span></span>

2. <span data-ttu-id="83baa-116">Dans la table **Modèles consultables,** sélectionnez les modèles que vous voulez masquer, puis **Masquer.**</span><span class="sxs-lookup"><span data-stu-id="83baa-116">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![Les modèles sélectionnés avec Masquer mis en évidence](media/template-policies-2.png)

    <span data-ttu-id="83baa-118">Vous pouvez voir les modèles que vous avez sélectionnés pour masquer dans la table **Modèles masqués.**</span><span class="sxs-lookup"><span data-stu-id="83baa-118">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="83baa-119">Pour voir certains modèles, faites défiler jusqu’à la table **Modèles masqués.**</span><span class="sxs-lookup"><span data-stu-id="83baa-119">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="83baa-120">Sélectionnez les modèles à afficher, puis **sélectionnez Afficher.**</span><span class="sxs-lookup"><span data-stu-id="83baa-120">Select the templates to unhide, and then select **Show**.</span></span>

   ![Les modèles sélectionnés qui ne sont pas masqués](media/template-policies-3.png)

   <span data-ttu-id="83baa-122">Les modèles sélectionnés apparaissent dans votre table **de modèles consultables.**</span><span class="sxs-lookup"><span data-stu-id="83baa-122">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="83baa-123">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="83baa-123">Select **Save**.</span></span>

   <span data-ttu-id="83baa-124">Votre nouvelle stratégie de modèle s’affiche dans la liste **Stratégies de** modèles.</span><span class="sxs-lookup"><span data-stu-id="83baa-124">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="83baa-125">Attribuer des utilisateurs aux stratégies de modèle</span><span class="sxs-lookup"><span data-stu-id="83baa-125">Assign users to the template policies</span></span>

<span data-ttu-id="83baa-126">Les utilisateurs affectés à une stratégie pourront uniquement afficher les modèles consultables dans cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="83baa-126">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="83baa-127">À partir **de Stratégies de modèles,** sélectionnez une stratégie, puis **sélectionnez Gérer les utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="83baa-127">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="83baa-128">Tapez les utilisateurs à affecter à cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="83baa-128">Type the users to assign to this policy.</span></span>

   ![Attribuer des utilisateurs à une stratégie de modèle](media/template-policies-4.png)

3. <span data-ttu-id="83baa-130">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="83baa-130">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="83baa-131">L’application de votre nouvelle stratégie pour les utilisateurs finaux peut prendre jusqu’à 24 heures.</span><span class="sxs-lookup"><span data-stu-id="83baa-131">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="83baa-132">Limites de taille pour les stratégies de modèle</span><span class="sxs-lookup"><span data-stu-id="83baa-132">Size limits for Template policies</span></span>

<span data-ttu-id="83baa-133">Vous pouvez masquer jusqu’à 100 modèles par stratégie.</span><span class="sxs-lookup"><span data-stu-id="83baa-133">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="83baa-134">Le **bouton** Masquer est désactivé si la stratégie donnée a déjà 100 modèles masqués.</span><span class="sxs-lookup"><span data-stu-id="83baa-134">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="83baa-135">Forum aux questions</span><span class="sxs-lookup"><span data-stu-id="83baa-135">Frequently asked questions</span></span>

<span data-ttu-id="83baa-136">**Q : Puis-je affecter par lots des utilisateurs à des stratégies de modèles d’équipe ?**</span><span class="sxs-lookup"><span data-stu-id="83baa-136">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="83baa-137">R : Oui, nous prise en charge l’affectation de lots pour une stratégie de modèle dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83baa-137">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="83baa-138">Le type de stratégie pour cette action est TeamsTemplatePermissionPolicy.</span><span class="sxs-lookup"><span data-stu-id="83baa-138">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="83baa-139">Pour en savoir plus</span><span class="sxs-lookup"><span data-stu-id="83baa-139">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)

<span data-ttu-id="83baa-140">**Q : Les groupes peuvent-ils être affectés à des stratégies de modèles d’équipe ?**</span><span class="sxs-lookup"><span data-stu-id="83baa-140">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="83baa-141">R : Actuellement non.</span><span class="sxs-lookup"><span data-stu-id="83baa-141">A: Currently no.</span></span> <span data-ttu-id="83baa-142">Cette fonctionnalité sera disponible ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="83baa-142">This functionality will be available in the future.</span></span>

<span data-ttu-id="83baa-143">**Q : Si un modèle est créé, le modèle sera-t-il inclus dans mes stratégies ?**</span><span class="sxs-lookup"><span data-stu-id="83baa-143">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="83baa-144">R : Tous les nouveaux modèles sont visibles par défaut.</span><span class="sxs-lookup"><span data-stu-id="83baa-144">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="83baa-145">Vous pouvez choisir de masquer le modèle dans le Centre d’administration dans la section Stratégies de modèles.</span><span class="sxs-lookup"><span data-stu-id="83baa-145">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="83baa-146">**Q : Que se passe-t-il en cas de suppression d’un modèle ?**</span><span class="sxs-lookup"><span data-stu-id="83baa-146">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="83baa-147">R : Tous les modèles supprimés ne seront plus présents dans les stratégies de modèles.</span><span class="sxs-lookup"><span data-stu-id="83baa-147">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="83baa-148">**Q : Puis-je attribuer plusieurs utilisateurs à une stratégie de modèle dans le Centre d’administration Teams ?**</span><span class="sxs-lookup"><span data-stu-id="83baa-148">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="83baa-149">R : Oui.</span><span class="sxs-lookup"><span data-stu-id="83baa-149">A: Yes.</span></span>

1. <span data-ttu-id="83baa-150">Dans le Centre d’administration, voir **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="83baa-150">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="83baa-151">Dans la table Liste d’utilisateurs, sélectionnez les utilisateurs que vous voulez affecter à une certaine stratégie de modèles.</span><span class="sxs-lookup"><span data-stu-id="83baa-151">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="83baa-152">Sélectionnez Modifier les paramètres, puis modifiez le champ Stratégies templates.</span><span class="sxs-lookup"><span data-stu-id="83baa-152">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="83baa-153">Sélectionnez Appliquer.</span><span class="sxs-lookup"><span data-stu-id="83baa-153">Select apply.</span></span>
   <span data-ttu-id="83baa-154">En savoir plus [Sur l’affectation de stratégies à vos utilisateurs dans Microsoft Teams - Microsoft Teams \| Microsoft Docs.](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)</span><span class="sxs-lookup"><span data-stu-id="83baa-154">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="83baa-155">**Q : Comment afficher tous les utilisateurs affectés à une stratégie spécifique ?**</span><span class="sxs-lookup"><span data-stu-id="83baa-155">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="83baa-156">R : Dans le Centre d’administration :</span><span class="sxs-lookup"><span data-stu-id="83baa-156">A: In the Admin center:</span></span>

1. <span data-ttu-id="83baa-157">Allez à la section **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="83baa-157">Go to the **Users** section.</span></span>
2. <span data-ttu-id="83baa-158">Sélectionnez le filtre dans la table Liste des utilisateurs et filtrez la stratégie de modèle Teams.</span><span class="sxs-lookup"><span data-stu-id="83baa-158">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="83baa-159">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="83baa-159">Select **Apply**.</span></span>

![Stratégie de modèle sélectionnée et afficher les utilisateurs](media/template-policies-5.png)

<span data-ttu-id="83baa-161">**Q : Puis-je gérer les stratégies de modèles via PowerShell ?**</span><span class="sxs-lookup"><span data-stu-id="83baa-161">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="83baa-162">R : Non, la gestion des modèles dans PowerShell n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="83baa-162">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="83baa-163">**Q : Les stratégies de modèles sont-elles applicables à l’éducation ?**</span><span class="sxs-lookup"><span data-stu-id="83baa-163">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="83baa-164">R : Non, les stratégies de modèle pour EDU ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="83baa-164">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="83baa-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83baa-165">Related topics</span></span>

- [<span data-ttu-id="83baa-166">Utiliser des modèles d’équipe dans le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="83baa-166">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="83baa-167">Créer un modèle d’équipe personnalisé</span><span class="sxs-lookup"><span data-stu-id="83baa-167">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="83baa-168">Créer un modèle à partir d’une équipe existante</span><span class="sxs-lookup"><span data-stu-id="83baa-168">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="83baa-169">Créer un modèle d’équipe à partir d’un modèle d’équipe existant</span><span class="sxs-lookup"><span data-stu-id="83baa-169">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="83baa-170">Attribuer des stratégies à vos utilisateurs dans Microsoft Teams - Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="83baa-170">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="83baa-171">Affecter des utilisateurs par lots à une stratégie</span><span class="sxs-lookup"><span data-stu-id="83baa-171">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
