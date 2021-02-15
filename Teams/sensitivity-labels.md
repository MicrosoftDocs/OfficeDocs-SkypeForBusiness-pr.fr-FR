---
title: Étiquettes de sensibilité pour Microsoft Teams
ms.author: mikeplum
author: cabailey
manager: laurawi
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser des étiquettes de sensibilité pour protéger vos équipes dans Microsoft Teams.
ms.openlocfilehash: 3b994bd7f1aa8fbc1fde13aaf49b195a1698695a
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937526"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="86fc2-103">Étiquettes de sensibilité pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86fc2-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="86fc2-104">[Les étiquettes de sensibilité](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permettent aux administrateurs Teams de protéger et de réguler l’accès au contenu d’organisation sensible créé lors de la collaboration au sein d’équipes.</span><span class="sxs-lookup"><span data-stu-id="86fc2-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="86fc2-105">Après avoir configuré les étiquettes de confidentialité avec les stratégies associées dans le Centre de conformité [Microsoft,](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)ces étiquettes peuvent être appliquées aux équipes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="86fc2-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="86fc2-106">Les étiquettes de sensibilité ne sont actuellement pas pris en compte pour les clients qui utilisent les S SKUS Teams Éducation.</span><span class="sxs-lookup"><span data-stu-id="86fc2-106">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span> <span data-ttu-id="86fc2-107">Pour en savoir plus sur les licences, consultez [la description du service Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="86fc2-107">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="86fc2-108">Quelle est la différence entre les étiquettes de sensibilité et les étiquettes de classification Teams ?</span><span class="sxs-lookup"><span data-stu-id="86fc2-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="86fc2-109">Les étiquettes de sensibilité sont différentes des étiquettes de classification, également appelées classification de groupe Azure AD.</span><span class="sxs-lookup"><span data-stu-id="86fc2-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="86fc2-110">Les étiquettes de classification sont des chaînes de texte qui peuvent être associées à un groupe Microsoft 365, mais qui ne sont associées à aucune stratégie réelle.</span><span class="sxs-lookup"><span data-stu-id="86fc2-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="86fc2-111">Vous utilisez des étiquettes de classification comme métadonnées, puis vous devez utiliser d’autres méthodes, telles que des outils et scripts internes, pour appliquer des stratégies.</span><span class="sxs-lookup"><span data-stu-id="86fc2-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="86fc2-112">L’utilisation d’étiquettes de confidentialité permet d’appliquer automatiquement leurs stratégies de bout en bout via une combinaison de la plateforme Microsoft 365 Groups, du centre de conformité et des services Teams.</span><span class="sxs-lookup"><span data-stu-id="86fc2-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="86fc2-113">Les étiquettes de confidentialité fournissent une prise en charge puissante de l’infrastructure pour sécuriser les données sensibles de votre organisation et assurer le respect de vos politiques ou réglementations internes.</span><span class="sxs-lookup"><span data-stu-id="86fc2-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="86fc2-114">Si vous utilisez actuellement des étiquettes de classification, consultez la documentation suivante pour plus d’informations et des instructions sur leur migration vers des étiquettes de sensibilité : Classification de groupe [Azure AD classique.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)</span><span class="sxs-lookup"><span data-stu-id="86fc2-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="86fc2-115">Exemples de scénarios pour les étiquettes de sensibilité</span><span class="sxs-lookup"><span data-stu-id="86fc2-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="86fc2-116">Exemples de scénarios d’utilisation d’étiquettes de sensibilité avec Teams dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="86fc2-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="86fc2-117">Définir le niveau de confidentialité (public ou privé) pour les équipes</span><span class="sxs-lookup"><span data-stu-id="86fc2-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="86fc2-118">Contrôler l’accès invité aux équipes</span><span class="sxs-lookup"><span data-stu-id="86fc2-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="86fc2-119">Définir le niveau de confidentialité des équipes</span><span class="sxs-lookup"><span data-stu-id="86fc2-119">Set the privacy level for teams</span></span>

<span data-ttu-id="86fc2-120">Vous pouvez créer et configurer une étiquette de confidentialité qui, lorsqu’elle est appliquée lors de la création de l’équipe, permet aux utilisateurs de créer des équipes avec un paramètre de confidentialité spécifique (public ou privé).</span><span class="sxs-lookup"><span data-stu-id="86fc2-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="86fc2-121">Par exemple, vous créez et publiez une étiquette de confidentialité nommée « Confidentiel » dont l’option de confidentialité est configurée comme **Privée.**</span><span class="sxs-lookup"><span data-stu-id="86fc2-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="86fc2-122">Par conséquent, toute équipe créée avec cette étiquette doit être privée.</span><span class="sxs-lookup"><span data-stu-id="86fc2-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="86fc2-123">Lorsqu’un utilisateur crée une équipe  et sélectionne l’étiquette Confidentiel, la seule option de confidentialité disponible pour l’utilisateur est **Privé.**</span><span class="sxs-lookup"><span data-stu-id="86fc2-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="86fc2-124">D’autres options de confidentialité, telles que Publique et À l’échelle de l’organisation, ne peuvent pas être sélectionnées par l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="86fc2-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![Capture d’écran de l’étiquette confidentiel](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="86fc2-126">De même, vous créez et publiez une étiquette de confidentialité nommée « Général » qui a l’option de confidentialité de l’étiquette configurée en tant que **Public.**</span><span class="sxs-lookup"><span data-stu-id="86fc2-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="86fc2-127">Lorsqu’un utilisateur crée une équipe, il ne peut créer des équipes publiques ou à l’échelle de l’organisation que s’ils sélectionnent cette étiquette :</span><span class="sxs-lookup"><span data-stu-id="86fc2-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![Capture d’écran de l’étiquette de sensibilité Général](media/sensitivity-labels-general-example.png)

<span data-ttu-id="86fc2-129">Lorsqu’une équipe est créée, l’étiquette de sensibilité est visible dans le coin supérieur droit des canaux de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="86fc2-129">When a team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Capture d’écran de l’étiquette de sensibilité dans le canal d’équipe](media/sensitivity-labels-channel.png)

<span data-ttu-id="86fc2-131">Un propriétaire d’équipe peut modifier l’étiquette de confidentialité et le paramètre de confidentialité de l’équipe à tout moment en se rendre à l’équipe, puis en cliquant **sur Modifier l’équipe.**</span><span class="sxs-lookup"><span data-stu-id="86fc2-131">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![Capture d’écran de l’étiquette de sensibilité dans les propriétés de l’équipe](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="86fc2-133">Contrôler l’accès invité aux équipes</span><span class="sxs-lookup"><span data-stu-id="86fc2-133">Control guest access to teams</span></span>

<span data-ttu-id="86fc2-134">Vous pouvez utiliser des étiquettes de sensibilité pour contrôler l’accès invité à vos équipes.</span><span class="sxs-lookup"><span data-stu-id="86fc2-134">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="86fc2-135">Les équipes créées avec une étiquette qui n’autorise pas l’accès invité sont uniquement disponibles pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="86fc2-135">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="86fc2-136">Des personnes extérieures à votre organisation ne peuvent pas être ajoutées à l’équipe.</span><span class="sxs-lookup"><span data-stu-id="86fc2-136">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="86fc2-137">Centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86fc2-137">Microsoft Teams admin center</span></span>

<span data-ttu-id="86fc2-138">Vous pouvez appliquer des étiquettes de sensibilité lorsque vous créez ou modifiez une équipe dans le Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="86fc2-138">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="86fc2-139">Les étiquettes de sensibilité sont également visibles dans les propriétés des équipes et dans la colonne **Classification** de la page **Gérer** les équipes du Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="86fc2-139">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="86fc2-140">Limitations</span><span class="sxs-lookup"><span data-stu-id="86fc2-140">Limitations</span></span>

<span data-ttu-id="86fc2-141">Avant d’utiliser des étiquettes de sensibilité pour Teams, faites attention aux limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="86fc2-141">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="86fc2-142">**Les noms des étiquettes parents ne sont pas affichés pour les sous-étiquettes**</span><span class="sxs-lookup"><span data-stu-id="86fc2-142">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="86fc2-143">Teams prend en charge les sous-titres, mais n’affiche pas le nom de l’étiquette parente.</span><span class="sxs-lookup"><span data-stu-id="86fc2-143">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="86fc2-144">Par exemple, **Confidentiel** \\ **tous les employés s’affiche** comme Tous les **employés.**</span><span class="sxs-lookup"><span data-stu-id="86fc2-144">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="86fc2-145">**Les étiquettes de sensibilité ne sont pas pris en charge par les API Teams Graph, les cmdlets PowerShell et les modèles**</span><span class="sxs-lookup"><span data-stu-id="86fc2-145">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="86fc2-146">Les utilisateurs ne peuvent pas appliquer d’étiquettes de sensibilité sur les équipes qui sont créées directement via les API Teams Graph, les cmdlets Teams PowerShell et les modèles Teams.</span><span class="sxs-lookup"><span data-stu-id="86fc2-146">Users won't be able to apply sensitivity labels on teams that are created directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span>

- <span data-ttu-id="86fc2-147">**Prise en charge des canaux privés**</span><span class="sxs-lookup"><span data-stu-id="86fc2-147">**Support for private channels**</span></span>
    
    <span data-ttu-id="86fc2-148">Les canaux privés créés dans une équipe héritent de l’étiquette de sensibilité appliquée à une équipe.</span><span class="sxs-lookup"><span data-stu-id="86fc2-148">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="86fc2-149">La même étiquette s’applique automatiquement à la collection de sites SharePoint pour le canal privé.</span><span class="sxs-lookup"><span data-stu-id="86fc2-149">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="86fc2-150">Toutefois, si un utilisateur modifie directement l’étiquette de sensibilité sur un site SharePoint pour un canal privé, ce changement n’est pas reflété dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="86fc2-150">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="86fc2-151">Dans ce scénario, les utilisateurs continuent à voir l’étiquette de sensibilité d’origine appliquée à l’équipe dans l’en-tête du canal privé.</span><span class="sxs-lookup"><span data-stu-id="86fc2-151">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="86fc2-152">Créer et configurer des étiquettes de sensibilité pour Teams</span><span class="sxs-lookup"><span data-stu-id="86fc2-152">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="86fc2-153">Utilisez les instructions de la documentation Microsoft 365 pour créer et configurer des étiquettes de sensibilité pour Teams :</span><span class="sxs-lookup"><span data-stu-id="86fc2-153">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="86fc2-154">[Utilisez des étiquettes de sensibilité pour protéger le contenu dans Microsoft Teams, les groupes Microsoft 365 et les sites SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)</span><span class="sxs-lookup"><span data-stu-id="86fc2-154">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
