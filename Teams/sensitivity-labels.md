---
title: Étiquettes de confidentialité de Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment définir et utiliser des étiquettes de sensibilité dans Microsoft Teams.
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653575"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="e5464-103">Étiquettes de confidentialité de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e5464-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="e5464-104">Les [étiquettes de sensibilité](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permettent aux administrateurs d’équipes de réguler l’accès au contenu d’organisation sensible créé lors de la collaboration au sein d’équipes.</span><span class="sxs-lookup"><span data-stu-id="e5464-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="e5464-105">Vous pouvez définir des étiquettes de sensibilité et leurs politiques associées dans le [Centre de sécurité & conformité](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="e5464-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="e5464-106">Celles-ci s’appliquent automatiquement aux équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e5464-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="e5464-107">Quelle est la différence entre les étiquettes de sensibilité et les étiquettes de classification d’équipe ?</span><span class="sxs-lookup"><span data-stu-id="e5464-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="e5464-108">Les étiquettes de sensibilité diffèrent des étiquettes de classification qui nécessitent que vous les créez à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5464-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="e5464-109">Les étiquettes de classification sont des chaînes de texte qui peuvent être associées à un groupe, mais qui ne sont associées à aucune stratégie réelle.</span><span class="sxs-lookup"><span data-stu-id="e5464-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="e5464-110">Vous utilisez des étiquettes de classification en tant que métadonnées pour appliquer manuellement des stratégies par le biais d’outils et de scripts internes.</span><span class="sxs-lookup"><span data-stu-id="e5464-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="e5464-111">En revanche, les étiquettes de sensibilité et leurs politiques sont automatiquement appliquées de bout en bout par le biais d’une combinaison de la plateforme de groupes, du centre de sécurité & de conformité et des services d’équipe.</span><span class="sxs-lookup"><span data-stu-id="e5464-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="e5464-112">Les étiquettes de sensibilité fournissent un puissant support d’infrastructure pour la sécurisation des données sensibles de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e5464-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="e5464-113">Créer et publier des étiquettes de confidentialité pour teams</span><span class="sxs-lookup"><span data-stu-id="e5464-113">Create and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="e5464-114">Pour plus d’informations sur l’activation, la création et la publication d’étiquettes de sensibilité pour les équipes, voir [utiliser des étiquettes de sensibilité avec Microsoft Teams, les groupes Office 365 et les sites SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="e5464-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="e5464-115">Utilisation d’étiquettes de sensibilité avec teams</span><span class="sxs-lookup"><span data-stu-id="e5464-115">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="e5464-116">Voici quelques exemples illustrant comment utiliser les étiquettes de sensibilité avec les équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e5464-116">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="e5464-117">Paramètre de confidentialité de teams</span><span class="sxs-lookup"><span data-stu-id="e5464-117">Privacy setting of teams</span></span>

<span data-ttu-id="e5464-118">Vous pouvez créer une étiquette de critère de diffusion qui, lorsqu’elle est appliquée au cours de la création d’une équipe, permet aux utilisateurs de créer des équipes ayant un paramètre de confidentialité (privée ou privée) spécifique.</span><span class="sxs-lookup"><span data-stu-id="e5464-118">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="e5464-119">Par exemple, vous créez une étiquette nommée « confidentiel » dans le centre de sécurité & conformité et vous configurez des équipes de sorte que toutes les équipes créées avec cette étiquette doivent être une équipe privée.</span><span class="sxs-lookup"><span data-stu-id="e5464-119">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="e5464-120">Lorsqu’un utilisateur crée une nouvelle équipe et sélectionne l’étiquette **confidentiel** , la seule option de confidentialité disponible pour l’utilisateur est **privée**.</span><span class="sxs-lookup"><span data-stu-id="e5464-120">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="e5464-121">D’autres options de protection de la vie privée, telles que le public et l’organisation, sont désactivées pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e5464-121">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Capture d’écran d’une étiquette de confidentialité confidentiel](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="e5464-123">De même, si l’utilisateur sélectionne **général** lors de la création d’une équipe, il peut uniquement créer des équipes publiques ou à l’échelle de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="e5464-123">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Capture d’écran d’une étiquette de critère de diffusion générale](media/sensitivity-labels-general-example.png)

<span data-ttu-id="e5464-125">Lors de la création de l’équipe, l’étiquette de sensibilité est visible dans le coin supérieur droit de la page canaux de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="e5464-125">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Capture d’écran d’une étiquette de critère de diffusion dans un canal d’équipe](media/sensitivity-labels-channel.png)

<span data-ttu-id="e5464-127">Le propriétaire d’une équipe peut changer l’étiquette de diffusion et le paramètre de confidentialité de l’équipe à tout moment en accédant à l’équipe et en cliquant sur **modifier l’équipe**.</span><span class="sxs-lookup"><span data-stu-id="e5464-127">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Capture d’écran d’une étiquette de critère de diffusion dans un canal d’équipe](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="e5464-129">Accès invité aux équipes</span><span class="sxs-lookup"><span data-stu-id="e5464-129">Guest access to teams</span></span>

<span data-ttu-id="e5464-130">Vous pouvez spécifier si une équipe créée avec une étiquette spécifique autorise l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="e5464-130">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="e5464-131">Les équipes créées avec une étiquette qui ne permet pas l’accès invité ne sont accessibles qu’aux utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e5464-131">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="e5464-132">Les personnes externes à votre organisation ne peuvent pas être ajoutées à l’équipe.</span><span class="sxs-lookup"><span data-stu-id="e5464-132">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="e5464-133">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="e5464-133">Known issues</span></span>

<span data-ttu-id="e5464-134">**Support pour les étiquettes de sensibilité dans le centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="e5464-134">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="e5464-135">Pour l’instant, les étiquettes de sensibilité ne sont pas prises en charge dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e5464-135">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e5464-136">Si vous utilisez des étiquettes de sensibilité, vous ne pourrez pas définir les étiquettes de sensibilité lors de la création ou de la modification d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="e5464-136">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="e5464-137">Les étiquettes de sensibilité sont également invisibles dans les propriétés d’équipe et ne sont pas visibles dans la colonne **classification** du centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e5464-137">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="e5464-138">**Prise en charge des étiquettes de sensibilité dans les API du graphique Teams, les cmdlets PowerShell et les modèles**</span><span class="sxs-lookup"><span data-stu-id="e5464-138">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="e5464-139">Pour le moment, les utilisateurs ne seront pas en mesure d’appliquer des étiquettes de sensibilité aux équipes créées directement par le biais d’API de graphique, de cmdlets PowerShell et de modèles.</span><span class="sxs-lookup"><span data-stu-id="e5464-139">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="e5464-140">**Modification directe des étiquettes de sensibilité sur une collection de sites SharePoint pour les canaux privés**</span><span class="sxs-lookup"><span data-stu-id="e5464-140">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="e5464-141">Les canaux privés créés dans une équipe héritent de l’étiquette de sensibilité appliquée au sein d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="e5464-141">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="e5464-142">Par ailleurs, la même étiquette est appliquée automatiquement sur la collection de sites SharePoint pour le canal privé.</span><span class="sxs-lookup"><span data-stu-id="e5464-142">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="e5464-143">Si un utilisateur met à jour directement l’étiquette de critère de diffusion sur une collection de sites SharePoint pour un canal privé, cette étiquette n’est pas mise à jour dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="e5464-143">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="e5464-144">Dans ce scénario, les utilisateurs continuent de voir l’étiquette de sensibilité appliquée à une équipe dans l’en-tête de canal privé.</span><span class="sxs-lookup"><span data-stu-id="e5464-144">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="e5464-145">**Temps de propagation des modifications appliquées aux étiquettes de sensibilité en dehors de l’application teams**</span><span class="sxs-lookup"><span data-stu-id="e5464-145">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="e5464-146">Les modifications apportées aux étiquettes de sensibilité en dehors de l’application teams peuvent prendre jusqu’à 24 heures pour refléter dans l’application Teams.</span><span class="sxs-lookup"><span data-stu-id="e5464-146">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="e5464-147">Cela s’applique aux modifications apportées à l’activation ou à la désactivation d’étiquettes pour un client, aux modifications apportées aux noms des étiquettes, aux paramètres et aux stratégies.</span><span class="sxs-lookup"><span data-stu-id="e5464-147">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="e5464-148">De plus, les modifications apportées à une étiquette apportées directement à un groupe ou une collection de sites SharePoint qui stocke l’équipe peuvent prendre jusqu’à 24 heures avant d’être propagées à l’application Teams.</span><span class="sxs-lookup"><span data-stu-id="e5464-148">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>