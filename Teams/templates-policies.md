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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: bcb99538ebd129e02e511c8260dc3bfa101bff9d
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50507967"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="61f11-103">Créer et gérer des modèles Teams dans le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="61f11-103">Create and manage Teams templates in the admin center</span></span>

<span data-ttu-id="61f11-104">Gérez les modèles Teams que vos utilisateurs finaux voient en créant des stratégies de modèles dans le Centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="61f11-104">Manage the Teams templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="61f11-105">Dans chaque stratégie de modèle, vous pouvez désigner les modèles affichés ou masqués.</span><span class="sxs-lookup"><span data-stu-id="61f11-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="61f11-106">Affectez différents utilisateurs à différentes stratégies de modèle afin que vos utilisateurs ne visualisent que le sous-ensemble de modèles Teams spécifiés.</span><span class="sxs-lookup"><span data-stu-id="61f11-106">Assign different users to different template policies so that your users only view the subset of Teams templates specified.</span></span>

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="61f11-107">Créer des stratégies de modèle et attribuer des modèles disponibles</span><span class="sxs-lookup"><span data-stu-id="61f11-107">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="61f11-108">Connectez-vous au Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="61f11-108">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="61f11-109">Développer les  >  **stratégies des modèles** Teams.</span><span class="sxs-lookup"><span data-stu-id="61f11-109">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="61f11-110">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="61f11-110">Select **Add**.</span></span>

    ![Les stratégies de modèle sont sélectionnées et l’ajout est mis en évidence](media/template-policies-1.png)

1. <span data-ttu-id="61f11-112">Dans la section **Paramètres de stratégies de modèles,** remplissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="61f11-112">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="61f11-113">Nom de la stratégie modèles</span><span class="sxs-lookup"><span data-stu-id="61f11-113">Templates Policy name</span></span>

    - <span data-ttu-id="61f11-114">Brève description de la stratégie de modèles</span><span class="sxs-lookup"><span data-stu-id="61f11-114">Templates Policy short description</span></span>

2. <span data-ttu-id="61f11-115">Dans la table **Modèles consultables,** sélectionnez les modèles que vous voulez masquer, puis **Masquer.**</span><span class="sxs-lookup"><span data-stu-id="61f11-115">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![Modèles sélectionnés avec Masquer mis en évidence](media/template-policies-2.png)

    <span data-ttu-id="61f11-117">Vous pouvez voir les modèles que vous avez sélectionnés pour masquer dans la table **Modèles masqués.**</span><span class="sxs-lookup"><span data-stu-id="61f11-117">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="61f11-118">Pour voir certains modèles, faites défiler jusqu’à la table **Modèles masqués.**</span><span class="sxs-lookup"><span data-stu-id="61f11-118">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="61f11-119">Sélectionnez les modèles à afficher, puis **sélectionnez Afficher.**</span><span class="sxs-lookup"><span data-stu-id="61f11-119">Select the templates to unhide, and then select **Show**.</span></span>

   ![Les modèles sélectionnés qui ne sont pas masqués](media/template-policies-3.png)

   <span data-ttu-id="61f11-121">Les modèles sélectionnés apparaissent dans votre table **de modèles consultables.**</span><span class="sxs-lookup"><span data-stu-id="61f11-121">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="61f11-122">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61f11-122">Select **Save**.</span></span>

   <span data-ttu-id="61f11-123">Votre nouvelle stratégie de modèle est affichée dans la liste **Stratégies de** modèles.</span><span class="sxs-lookup"><span data-stu-id="61f11-123">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="61f11-124">Attribuer des utilisateurs aux stratégies de modèle</span><span class="sxs-lookup"><span data-stu-id="61f11-124">Assign users to the template policies</span></span>

<span data-ttu-id="61f11-125">Les utilisateurs affectés à une stratégie pourront uniquement afficher les modèles consultables dans cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="61f11-125">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="61f11-126">À partir **de Stratégies de modèles,** sélectionnez une stratégie, puis **sélectionnez Gérer les utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="61f11-126">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="61f11-127">Tapez les utilisateurs à affecter à cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="61f11-127">Type the users to assign to this policy.</span></span>

   ![Attribuer des utilisateurs à une stratégie de modèle](media/template-policies-4.png)

3. <span data-ttu-id="61f11-129">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="61f11-129">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="61f11-130">L’application de votre nouvelle stratégie pour les utilisateurs finaux peut prendre jusqu’à 24 heures.</span><span class="sxs-lookup"><span data-stu-id="61f11-130">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="61f11-131">Limites de taille pour les stratégies de modèle</span><span class="sxs-lookup"><span data-stu-id="61f11-131">Size limits for Template policies</span></span>

<span data-ttu-id="61f11-132">Vous pouvez masquer jusqu’à 100 modèles par stratégie.</span><span class="sxs-lookup"><span data-stu-id="61f11-132">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="61f11-133">Le **bouton** Masquer est désactivé si la stratégie donnée a déjà 100 modèles masqués.</span><span class="sxs-lookup"><span data-stu-id="61f11-133">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="61f11-134">Forum aux questions</span><span class="sxs-lookup"><span data-stu-id="61f11-134">Frequently asked questions</span></span>

<span data-ttu-id="61f11-135">**Q : Puis-je affecter par lots des utilisateurs à des stratégies de modèles d’équipe ?**</span><span class="sxs-lookup"><span data-stu-id="61f11-135">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="61f11-136">R : Oui, nous prise en charge l’affectation de lots pour une stratégie de modèle dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61f11-136">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="61f11-137">Le type de stratégie pour cette action est TeamsTemplatePermissionPolicy.</span><span class="sxs-lookup"><span data-stu-id="61f11-137">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="61f11-138">Pour en savoir plus</span><span class="sxs-lookup"><span data-stu-id="61f11-138">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

<span data-ttu-id="61f11-139">**Q : Les groupes peuvent-ils être affectés à des stratégies de modèles d’équipe ?**</span><span class="sxs-lookup"><span data-stu-id="61f11-139">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="61f11-140">R : Actuellement non.</span><span class="sxs-lookup"><span data-stu-id="61f11-140">A: Currently no.</span></span> <span data-ttu-id="61f11-141">Cette fonctionnalité sera disponible ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="61f11-141">This functionality will be available in the future.</span></span>

<span data-ttu-id="61f11-142">**Q : Si un modèle est créé, le modèle sera-t-il inclus dans mes stratégies ?**</span><span class="sxs-lookup"><span data-stu-id="61f11-142">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="61f11-143">R : Tous les nouveaux modèles sont visibles par défaut.</span><span class="sxs-lookup"><span data-stu-id="61f11-143">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="61f11-144">Vous pouvez choisir de masquer le modèle dans le Centre d’administration dans la section Stratégies de modèles.</span><span class="sxs-lookup"><span data-stu-id="61f11-144">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="61f11-145">**Q : Que se passe-t-il en cas de suppression d’un modèle ?**</span><span class="sxs-lookup"><span data-stu-id="61f11-145">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="61f11-146">R : Tous les modèles supprimés ne seront plus présents dans les stratégies de modèles.</span><span class="sxs-lookup"><span data-stu-id="61f11-146">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="61f11-147">**Q : Puis-je attribuer plusieurs utilisateurs à une stratégie de modèle dans le Centre d’administration Teams ?**</span><span class="sxs-lookup"><span data-stu-id="61f11-147">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="61f11-148">R : Oui.</span><span class="sxs-lookup"><span data-stu-id="61f11-148">A: Yes.</span></span>

1. <span data-ttu-id="61f11-149">Dans le Centre d’administration, voir **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="61f11-149">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="61f11-150">Dans la table Liste d’utilisateurs, sélectionnez les utilisateurs que vous voulez affecter à une certaine stratégie de modèles.</span><span class="sxs-lookup"><span data-stu-id="61f11-150">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="61f11-151">Sélectionnez Modifier les paramètres, puis modifiez le champ De stratégies Templates.</span><span class="sxs-lookup"><span data-stu-id="61f11-151">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="61f11-152">Sélectionnez Appliquer.</span><span class="sxs-lookup"><span data-stu-id="61f11-152">Select apply.</span></span>
   <span data-ttu-id="61f11-153">En savoir plus [Sur l’affectation de stratégies à vos utilisateurs dans Microsoft Teams - Microsoft Teams \| Microsoft Docs.](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)</span><span class="sxs-lookup"><span data-stu-id="61f11-153">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="61f11-154">**Q : Comment afficher tous les utilisateurs affectés à une stratégie spécifique ?**</span><span class="sxs-lookup"><span data-stu-id="61f11-154">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="61f11-155">R : Dans le Centre d’administration :</span><span class="sxs-lookup"><span data-stu-id="61f11-155">A: In the Admin center:</span></span>

1. <span data-ttu-id="61f11-156">Allez à la section **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="61f11-156">Go to the **Users** section.</span></span>
2. <span data-ttu-id="61f11-157">Sélectionnez le filtre dans la table Liste des utilisateurs et filtrez la stratégie de modèle Teams.</span><span class="sxs-lookup"><span data-stu-id="61f11-157">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="61f11-158">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="61f11-158">Select **Apply**.</span></span>

![Stratégie de modèle sélectionnée et afficher les utilisateurs](media/template-policies-5.png)

<span data-ttu-id="61f11-160">**Q : Puis-je gérer les stratégies de modèles via PowerShell ?**</span><span class="sxs-lookup"><span data-stu-id="61f11-160">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="61f11-161">R : Non, la gestion des modèles dans PowerShell n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="61f11-161">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="61f11-162">**Q : Les stratégies de modèles sont-elles applicables à l’éducation ?**</span><span class="sxs-lookup"><span data-stu-id="61f11-162">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="61f11-163">R : Non, les stratégies de modèle pour EDU ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="61f11-163">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="61f11-164">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="61f11-164">Related topics</span></span>

- [<span data-ttu-id="61f11-165">Utiliser des modèles d’équipe dans le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="61f11-165">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="61f11-166">Créer un modèle d’équipe personnalisé</span><span class="sxs-lookup"><span data-stu-id="61f11-166">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="61f11-167">Créer un modèle à partir d’une équipe existante</span><span class="sxs-lookup"><span data-stu-id="61f11-167">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="61f11-168">Créer un modèle d’équipe à partir d’un modèle d’équipe existant</span><span class="sxs-lookup"><span data-stu-id="61f11-168">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="61f11-169">Attribuer des stratégies à vos utilisateurs dans Microsoft Teams - Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="61f11-169">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="61f11-170">Affecter des utilisateurs par lots à une stratégie</span><span class="sxs-lookup"><span data-stu-id="61f11-170">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)
