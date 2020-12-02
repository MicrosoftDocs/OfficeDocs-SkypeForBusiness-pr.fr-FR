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
ms.openlocfilehash: ab48796f877f6af33b8a3c1b2bc5a3cc56e7bd1e
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530981"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="188f6-104">Préversion publique de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="188f6-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="188f6-p102">Les fonctionnalités incluses dans la préversion ne seront peut-être pas complètes et risquent de subir des modifications avant d’être disponibles dans la version publique. Nous les proposons uniquement à des fins d’évaluation et d’exploration.</span><span class="sxs-lookup"><span data-stu-id="188f6-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="188f6-p103">La préversion publique de Microsoft Teams vous permet d’accéder en avant-première aux fonctionnalités non publiées de Teams. Les préversions vous permettent d’explorer et de tester les fonctionnalités à venir. Nous vous invitons également à nous faire part de vos commentaires sur les fonctionnalités des aperçus publics. La préversion publique est activée pour chaque utilisateur de l’équipe. vous n’avez donc pas besoin de vous soucier de l’ensemble de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="188f6-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled each Teams user, so you don't need to worry about affecting your entire organization.</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="188f6-111">Définir la stratégie de mise à jour</span><span class="sxs-lookup"><span data-stu-id="188f6-111">Set the Update policy</span></span>

 <span data-ttu-id="188f6-112">Nous avons activé la préversion publique pour chaque utilisateur, et une stratégie d’administration permet de contrôler l’option d’activation de cette préversion.</span><span class="sxs-lookup"><span data-stu-id="188f6-112">Public preview is enabled for each user, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="188f6-113">Les stratégies de mise à jour permettent de gérer les utilisateurs des préversions de Teams et d’Office qui auront accès aux fonctionnalités d’avant-publication ou de préversion dans l’application Teams.</span><span class="sxs-lookup"><span data-stu-id="188f6-113">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="188f6-114">Vous pouvez utiliser et personnaliser la stratégie globale (par défaut à l’échelle de l’organisation), ou créer une ou plusieurs stratégies personnalisées pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="188f6-114">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="188f6-115">La stratégie doit être attribuée à des utilisateurs spécifiques car elle ne remplace pas la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="188f6-115">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="188f6-116">Connectez-vous au centre d'administration.</span><span class="sxs-lookup"><span data-stu-id="188f6-116">Sign in to the admin center.</span></span>
2. <span data-ttu-id="188f6-117">Sélectionnez **Teams**>**Stratégies de mise à jour**.</span><span class="sxs-lookup"><span data-stu-id="188f6-117">Select **Teams**>**Update policies**.</span></span>

   ![Sélectionner l’option Stratégies de mise à jour](media/updatePolicies.png)

3. <span data-ttu-id="188f6-119">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="188f6-119">Select **Add**.</span></span>
4. <span data-ttu-id="188f6-120">Nommez la stratégie de mise à jour, ajoutez une description, puis activez **Afficher les fonctionnalités en préversion**.</span><span class="sxs-lookup"><span data-stu-id="188f6-120">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="188f6-121">Vous pouvez également définir la stratégie à l’aide de PowerShell en utilisant le `CsTeamsUpdateManagementPolicy` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="188f6-121">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="188f6-122">Activer la préversion publique</span><span class="sxs-lookup"><span data-stu-id="188f6-122">Enable public preview</span></span>

<span data-ttu-id="188f6-123">Pour activer la préversion publique sur un client de bureau ou web, effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="188f6-123">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="188f6-124">Sélectionnez votre profil pour afficher le menu Teams.</span><span class="sxs-lookup"><span data-stu-id="188f6-124">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="188f6-125">Sélectionnez **À propos** → **Préversion publique**.</span><span class="sxs-lookup"><span data-stu-id="188f6-125">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="188f6-126">Sélectionnez **Basculer vers la préversion publique**.</span><span class="sxs-lookup"><span data-stu-id="188f6-126">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="188f6-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="188f6-127">Related topics</span></span>

[<span data-ttu-id="188f6-128">Préversion publique pour les développeurs</span><span class="sxs-lookup"><span data-stu-id="188f6-128">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
