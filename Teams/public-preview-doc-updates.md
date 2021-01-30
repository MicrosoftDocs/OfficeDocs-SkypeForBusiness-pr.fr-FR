---
title: Préversion publique de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: En savoir plus sur la préversion publique dans Microsoft Teams. Essayez les nouvelles fonctionnalités, puis envoyez vos commentaires.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 6a8d677b4acd56e6de5681d40a1e1aa69008a1ad
ms.sourcegitcommit: 6262deaede6f25b17624d7468eff7a2863eeacf7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50043958"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="6d92f-104">Préversion publique de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d92f-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="6d92f-p102">Les fonctionnalités incluses dans la préversion ne seront peut-être pas complètes et risquent de subir des modifications avant d’être disponibles dans la version publique. Nous les proposons uniquement à des fins d’évaluation et d’exploration.</span><span class="sxs-lookup"><span data-stu-id="6d92f-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="6d92f-p103">La préversion publique de Microsoft Teams vous permet d’accéder en avant-première aux fonctionnalités non publiées de Teams. Les préversions vous permettent d’explorer, puis de tester les fonctionnalités à venir. Nous vous invitons également à nous faire part de vos commentaires sur les fonctionnalités des préversions publiques. La préversion publique est activée pour chaque utilisateur de Teams. Vous n’avez donc pas besoin de vous soucier de l’ensemble de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d92f-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.</span></span>

<span data-ttu-id="6d92f-111">Pour obtenir la liste des ressources disponibles dans la prévisualisation publique Teams, veuillez consulter la rubrique [Notes de publication pour le canal actuel d’Office (Preview)](https://docs.microsoft.com/officeupdates/current-channel-preview).</span><span class="sxs-lookup"><span data-stu-id="6d92f-111">For a list of what's available in the Teams public preview, visit [Release Notes for Office Current Channel (Preview)](https://docs.microsoft.com/officeupdates/current-channel-preview).</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="6d92f-112">Définir la stratégie de mise à jour</span><span class="sxs-lookup"><span data-stu-id="6d92f-112">Set the Update policy</span></span>

<span data-ttu-id="6d92f-113">Nous avons activé la préversion publique par utilisateur, et une stratégie d’administration permet de contrôler l’option d’activation de cette préversion.</span><span class="sxs-lookup"><span data-stu-id="6d92f-113">Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="6d92f-114">Les stratégies de mise à jour permettent de gérer les utilisateurs des préversions de Teams et d’Office qui auront accès aux fonctionnalités d’avant-publication ou de préversion dans l’application Teams.</span><span class="sxs-lookup"><span data-stu-id="6d92f-114">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="6d92f-115">Vous pouvez utiliser et personnaliser la stratégie globale (par défaut à l’échelle de l’organisation), ou créer une ou plusieurs stratégies personnalisées pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6d92f-115">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="6d92f-116">La stratégie doit être attribuée à des utilisateurs spécifiques car elle ne remplace pas la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="6d92f-116">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="6d92f-117">Connectez-vous au centre d'administration.</span><span class="sxs-lookup"><span data-stu-id="6d92f-117">Sign in to the admin center.</span></span>
2. <span data-ttu-id="6d92f-118">Sélectionnez **Teams**>**Stratégies de mise à jour**.</span><span class="sxs-lookup"><span data-stu-id="6d92f-118">Select **Teams**>**Update policies**.</span></span>

   ![Sélectionner l’option Stratégies de mise à jour](media/updatePolicies.png)

3. <span data-ttu-id="6d92f-120">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6d92f-120">Select **Add**.</span></span>
4. <span data-ttu-id="6d92f-121">Nommez la stratégie de mise à jour, ajoutez une description, puis activez **Afficher les fonctionnalités en préversion**.</span><span class="sxs-lookup"><span data-stu-id="6d92f-121">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="6d92f-122">Vous pouvez également définir la stratégie à l’aide de PowerShell en utilisant le `CsTeamsUpdateManagementPolicy` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6d92f-122">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="6d92f-123">Activer la préversion publique</span><span class="sxs-lookup"><span data-stu-id="6d92f-123">Enable public preview</span></span>

<span data-ttu-id="6d92f-124">Pour activer la préversion publique sur un client de bureau ou web, effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d92f-124">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="6d92f-125">Sélectionnez votre profil pour afficher le menu Teams.</span><span class="sxs-lookup"><span data-stu-id="6d92f-125">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="6d92f-126">Sélectionnez **À propos** → **Préversion publique**.</span><span class="sxs-lookup"><span data-stu-id="6d92f-126">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="6d92f-127">Sélectionnez **Basculer vers la préversion publique**.</span><span class="sxs-lookup"><span data-stu-id="6d92f-127">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6d92f-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d92f-128">Related topics</span></span>

[<span data-ttu-id="6d92f-129">Préversion publique pour les développeurs</span><span class="sxs-lookup"><span data-stu-id="6d92f-129">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)

