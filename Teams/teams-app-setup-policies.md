---
title: Gérer les stratégies de mise en application dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
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
description: Découvrez comment utiliser et gérer les stratégies de configuration d’Microsoft Teams pour les utilisateurs de votre organisation.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ebfcff8ce7215e34e3c17e9c09f3a56d249d5b40
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059198"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="55e47-103">Gérer les stratégies de mise en application dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55e47-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="55e47-104">En tant qu’administrateur, vous pouvez utiliser des stratégies de configuration d’application pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="55e47-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="55e47-105">Personnaliser Teams afin de mettre en évidence les applications les plus importantes pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="55e47-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="55e47-106">Vous choisissez les applications à épingler et définissez l’ordre dans celui-là.</span><span class="sxs-lookup"><span data-stu-id="55e47-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="55e47-107">L’épinglage d’applications vous permet de présenter les applications dont les utilisateurs de votre organisation ont besoin, y compris les applications conçues par des tiers ou par des développeurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="55e47-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="55e47-108">Déterminer si les utilisateurs peuvent épingler des applications à Teams.</span><span class="sxs-lookup"><span data-stu-id="55e47-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="55e47-109">Installer des applications pour le compte des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="55e47-109">Install apps on behalf of users.</span></span> <span data-ttu-id="55e47-110">Vous choisissez les applications installées par défaut pour les utilisateurs lorsqu’ils démarrent Teams.</span><span class="sxs-lookup"><span data-stu-id="55e47-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="55e47-111">Gardez à l’esprit que les [](teams-app-permission-policies.md) utilisateurs peuvent toujours installer les applications elles-mêmes si la stratégie d’autorisation d’application qui leur est attribuée le permet.</span><span class="sxs-lookup"><span data-stu-id="55e47-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="55e47-112">Pour les applications installées par les administrateurs, les utilisateurs ne peuvent pas les désinstaller.</span><span class="sxs-lookup"><span data-stu-id="55e47-112">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="55e47-113">Les applications sont épinglées à la barre de l’application, qui est la barre sur le côté du client de bureau Teams et en bas des clients mobiles Teams (iOS et Android).</span><span class="sxs-lookup"><span data-stu-id="55e47-113">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="55e47-114">Teams de bureau</span><span class="sxs-lookup"><span data-stu-id="55e47-114">Teams desktop client</span></span>  |<span data-ttu-id="55e47-115">Client mobile Teams</span><span class="sxs-lookup"><span data-stu-id="55e47-115">Teams mobile client</span></span> |
|---------|---------|
|![Le client Teams bureau](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Le client Teams mobile](media/mobile-app-ui.png)      |

<span data-ttu-id="55e47-118">Pour voir les applications installées par les administrateurs, dans la barre d’application, les utilisateurs **sélectionnent... Plus d’applications** dans Teams clients de bureau et web, puis balayez vers le haut dans les clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="55e47-118">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="55e47-119">Vous gérez les stratégies de configuration d’application dans Microsoft Teams centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="55e47-119">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="55e47-120">Utilisez la stratégie globale (à l’échelle de l’organisation par défaut) ou créez et attribuez des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="55e47-120">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="55e47-121">Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="55e47-121">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="55e47-122">Vous devez être un administrateur général ou un administrateur du service Teams pour gérer ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="55e47-122">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="55e47-123">Vous devez modifier les paramètres de la stratégie globale pour inclure les applications que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="55e47-123">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="55e47-124">Pour personnaliser Teams différents groupes d’utilisateurs de votre organisation, créez et attribuez une ou plusieurs stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="55e47-124">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![Page Stratégies de configuration des applications](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="55e47-126">Si vous avez Teams Éducation, il est important de savoir que l’application Affectations est épinglée par défaut dans la stratégie globale, même si actuellement elle n’est pas répertoriée dans la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="55e47-126">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="55e47-127">Il s’agit de la quatrième application dans la liste des applications épinglées sur Teams clients.</span><span class="sxs-lookup"><span data-stu-id="55e47-127">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="55e47-128">Créer une stratégie de configuration d’application personnalisée</span><span class="sxs-lookup"><span data-stu-id="55e47-128">Create a custom app setup policy</span></span>

<span data-ttu-id="55e47-129">Vous pouvez utiliser le centre Microsoft Teams pour créer une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="55e47-129">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="55e47-130">Dans le panneau de navigation gauche du Microsoft Teams d’administration, voir stratégies **Teams de configuration des**  >  **applications.**</span><span class="sxs-lookup"><span data-stu-id="55e47-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="55e47-131">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="55e47-131">Select **Add**.</span></span>

   ![Page Ajouter des stratégies de configuration d’application](media/app-setup-policies-add.png)

3. <span data-ttu-id="55e47-133">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="55e47-133">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="55e47-134">Activer ou désactiver Télécharger **applications personnalisées,** selon que vous souhaitez ou non que les utilisateurs téléchargent des applications personnalisées Teams.</span><span class="sxs-lookup"><span data-stu-id="55e47-134">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="55e47-135">Vous ne pouvez pas modifier ce paramètre **si** l’application autoriser des applications tierces est désactivée dans les paramètres de l’application à l’échelle [de l’organisation.](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="55e47-135">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="55e47-136">Activer ou désactiver l’épinglage d’utilisateurs, selon que vous voulez ou non permettre aux utilisateurs de personnaliser leur barre d’application en épinglage d’applications.</span><span class="sxs-lookup"><span data-stu-id="55e47-136">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="55e47-137">Le  paramètre Autoriser l’épinglage d’utilisateur est disponible dans le Centre d’administration Teams dans les environnements Microsoft 365 Cloud de la communauté du secteur public (Cloud de la communauté du secteur public) (Cloud de la communauté du secteur public, Cloud de la communauté du secteur public Haute et DoD), mais actuellement, il n’a aucun effet.</span><span class="sxs-lookup"><span data-stu-id="55e47-137">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="55e47-138">Pour installer des applications pour les utilisateurs, effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="55e47-138">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="55e47-139">Sous **Applications installées,** **sélectionnez Ajouter des applications.**</span><span class="sxs-lookup"><span data-stu-id="55e47-139">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="55e47-140">Dans le **volet Ajouter des applications** installées, recherchez les applications que vous voulez installer automatiquement pour les utilisateurs lorsqu’ils démarrent Teams.</span><span class="sxs-lookup"><span data-stu-id="55e47-140">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="55e47-141">Vous pouvez également filtrer les applications par stratégie d’autorisation d’application.</span><span class="sxs-lookup"><span data-stu-id="55e47-141">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="55e47-142">Une fois que vous avez choisi votre liste d’applications, sélectionnez **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="55e47-142">When you've chosen your list of apps, select **Add**.</span></span>

       ![Volet Ajouter des applications installées](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="55e47-144">Pour épingler des applications, vous pouvez suivre les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="55e47-144">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="55e47-145">Sous **Applications épinglées,** **sélectionnez Ajouter des applications.**</span><span class="sxs-lookup"><span data-stu-id="55e47-145">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="55e47-146">Dans le **volet Ajouter des applications épinglées,** recherchez les applications que vous voulez ajouter, puis sélectionnez **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="55e47-146">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="55e47-147">Vous pouvez également filtrer les applications par stratégie d’autorisation d’application.</span><span class="sxs-lookup"><span data-stu-id="55e47-147">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="55e47-148">Lorsque vous avez choisi votre liste d’applications à épingler, sélectionnez **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="55e47-148">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![Volet Ajouter des applications épinglées](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="55e47-150">Organisez les applications dans l’ordre dans l’ordre dans Teams, puis sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="55e47-150">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![Section Applications épinglées](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="55e47-152">Modifier une stratégie de configuration d’application</span><span class="sxs-lookup"><span data-stu-id="55e47-152">Edit an app setup policy</span></span>

<span data-ttu-id="55e47-153">Vous pouvez utiliser le Centre Microsoft Teams d’administration pour modifier une stratégie, y compris la stratégie globale (à l’échelle de l’organisation par défaut) et les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="55e47-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="55e47-154">Dans le panneau de navigation gauche du Microsoft Teams d’administration, voir stratégies **Teams de configuration des**  >  **applications.**</span><span class="sxs-lookup"><span data-stu-id="55e47-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="55e47-155">Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="55e47-155">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="55e47-156">À partir de là, apportez les modifications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="55e47-156">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="55e47-157">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="55e47-157">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="55e47-158">Affecter une stratégie de configuration d’application personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="55e47-158">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="55e47-159">FAQ</span><span class="sxs-lookup"><span data-stu-id="55e47-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="55e47-160">Fonctionnement des stratégies de configuration d’application</span><span class="sxs-lookup"><span data-stu-id="55e47-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="55e47-161">Quelles stratégies de configuration d’application intégrées sont incluses dans le Centre Microsoft Teams’administration de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="55e47-161">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="55e47-162">**Global (par défaut à l’échelle** de l’organisation) : cette stratégie par défaut s’applique à tous les utilisateurs de votre organisation, sauf si vous attribuez une autre stratégie.</span><span class="sxs-lookup"><span data-stu-id="55e47-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="55e47-163">Modifiez la stratégie globale pour épingler les applications les plus importantes pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="55e47-163">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="55e47-164">**FrontlineWorker**: cette stratégie s’agit pour les employés en ligne.</span><span class="sxs-lookup"><span data-stu-id="55e47-164">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="55e47-165">Vous pouvez l’affecter à des employés en ligne de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="55e47-165">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="55e47-166">Il est important de savoir que, comme les stratégies personnalisées que vous créez, vous devez affecter la stratégie aux utilisateurs pour que les paramètres soient actifs.</span><span class="sxs-lookup"><span data-stu-id="55e47-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="55e47-167">Pour plus d’informations, voir la section Affecter une stratégie de configuration d’application personnalisée aux [utilisateurs](#assign-a-custom-app-setup-policy-to-users) de cet article.</span><span class="sxs-lookup"><span data-stu-id="55e47-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="55e47-168">Pourquoi ne puis-je pas trouver une application dans le volet Ajouter des applications épinglées ?</span><span class="sxs-lookup"><span data-stu-id="55e47-168">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="55e47-169">Toutes les applications ne peuvent pas être épinglées Teams via une stratégie de configuration d’application.</span><span class="sxs-lookup"><span data-stu-id="55e47-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="55e47-170">Certaines applications peuvent ne pas prendre en charge cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="55e47-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="55e47-171">Pour rechercher des applications qui peuvent être épinglées, recherchez l’application dans le volet Ajouter des applications épinglées. </span><span class="sxs-lookup"><span data-stu-id="55e47-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="55e47-172">Les onglets qui ont une étendue personnelle (onglets statiques) et bots peuvent être épinglés au client de bureau Teams. Ces applications sont disponibles dans le volet Ajouter des applications épinglées. </span><span class="sxs-lookup"><span data-stu-id="55e47-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="55e47-173">N’oubliez pas que le magasin Teams’application répertorie toutes Teams applications.</span><span class="sxs-lookup"><span data-stu-id="55e47-173">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="55e47-174">Le **volet Ajouter des applications épinglées** inclut uniquement les applications qui peuvent être épinglées à Teams via une stratégie.</span><span class="sxs-lookup"><span data-stu-id="55e47-174">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="55e47-175">Je suis Teams pour l’éducation. Que dois-je savoir sur les stratégies de configuration d’application dans Teams Éducation ?</span><span class="sxs-lookup"><span data-stu-id="55e47-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="55e47-176">L’application Appels n’est pas disponible dans Teams éducation.</span><span class="sxs-lookup"><span data-stu-id="55e47-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="55e47-177">Lorsque vous créez une stratégie de configuration d’application personnalisée, l’application Appels s’affiche dans la liste des applications.</span><span class="sxs-lookup"><span data-stu-id="55e47-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="55e47-178">Toutefois, l’application n’est pas épinglée aux clients Teams et les utilisateurs de Teams Éducation ne voient pas l’application Appels dans Teams.</span><span class="sxs-lookup"><span data-stu-id="55e47-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="55e47-179">Combien d’applications épinglées peuvent être ajoutées à une stratégie</span><span class="sxs-lookup"><span data-stu-id="55e47-179">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="55e47-180">Au moins deux applications doivent être épinglées aux clients Teams mobiles (iOS et Android).</span><span class="sxs-lookup"><span data-stu-id="55e47-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="55e47-181">Si une stratégie possède moins de deux applications, les clients mobiles ne reflètent pas les paramètres de stratégie et continueront à utiliser la configuration existante.</span><span class="sxs-lookup"><span data-stu-id="55e47-181">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="55e47-182">Le nombre d’applications épinglées que vous pouvez ajouter à une stratégie n’est pas limité.</span><span class="sxs-lookup"><span data-stu-id="55e47-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="55e47-183">Combien de temps faut-il pour que les modifications de stratégie prennent effet</span><span class="sxs-lookup"><span data-stu-id="55e47-183">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="55e47-184">Après avoir modifié ou attribué une stratégie, l’application des modifications peut prendre quelques heures.</span><span class="sxs-lookup"><span data-stu-id="55e47-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="55e47-185">Expérience utilisateur</span><span class="sxs-lookup"><span data-stu-id="55e47-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="55e47-186">Comment les utilisateurs peuvent-ils voir toutes leurs applications épinglées dans Teams</span><span class="sxs-lookup"><span data-stu-id="55e47-186">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="55e47-187">Pour afficher toutes les applications épinglées pour un utilisateur, les utilisateurs doivent peut-être faire les choses suivantes en fonction du nombre d’applications installées et de la taille de leur fenêtre cliente Teams client.</span><span class="sxs-lookup"><span data-stu-id="55e47-187">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="55e47-188">Teams de bureau</span><span class="sxs-lookup"><span data-stu-id="55e47-188">Teams desktop client</span></span> |<span data-ttu-id="55e47-189">Client mobile Teams</span><span class="sxs-lookup"><span data-stu-id="55e47-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="55e47-190">Dans la barre de l’application sur le côté Teams, sélectionnez **... Autres applications.**</span><span class="sxs-lookup"><span data-stu-id="55e47-190">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="55e47-191">Dans la barre de l’application au bas de Teams, balayez vers le haut.</span><span class="sxs-lookup"><span data-stu-id="55e47-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Plus d’applications dans Teams client de bureau](media/app-setup-policies-desktop-more-apps.png)<br>   |![plus d’applications dans Teams client mobile](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="55e47-194">Que dois-je savoir sur l’expérience Teams mobile ?</span><span class="sxs-lookup"><span data-stu-id="55e47-194">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="55e47-195">Les Teams clients mobiles (iOS et Android) peuvent utiliser des applications personnelles avec des onglets statiques.</span><span class="sxs-lookup"><span data-stu-id="55e47-195">The Teams mobile clients (iOS and Android) support personal apps with static tabs.</span></span> <span data-ttu-id="55e47-196">Les applications épinglées au client Teams bureau s’affichent dans le Teams clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="55e47-196">Apps pinned to the Teams desktop client will appear in the Teams mobile clients.</span></span> <span data-ttu-id="55e47-197">Les robots personnels apparaissent dans Conversation sur les clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="55e47-197">Personal bots will appear in Chat on mobile clients.</span></span>

<span data-ttu-id="55e47-198">Les applications tierces (qui peuvent être téléchargées à partir du Teams Store) doivent être approuvées avant de s’afficher sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="55e47-198">Third-party apps (which can be downloaded from Teams Store) need to be approved before they show up on mobile.</span></span> <span data-ttu-id="55e47-199">Si un administrateur épingle une application, non apposée par Microsoft pour mobile, elle s’affichera sur le bureau Teams, mais pas sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="55e47-199">If an admin pins an app, which is unapproved by Microsoft for Mobile, it will show up on the Teams Desktop, but not show up on mobile.</span></span> <span data-ttu-id="55e47-200">Pour plus [d’informations,](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) voir clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="55e47-200">See [Mobile clients](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) for more information.</span></span>

<span data-ttu-id="55e47-201">Avec les clients mobiles Teams, les utilisateurs peuvent voir les principales applications de Teams telles que Activité, Conversation et Teams et vous pouvez épingler certaines applications tierces de Microsoft, telles que Shifts.</span><span class="sxs-lookup"><span data-stu-id="55e47-201">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="55e47-202">Les utilisateurs peuvent-ils modifier l’ordre des applications épinglées via une stratégie ?</span><span class="sxs-lookup"><span data-stu-id="55e47-202">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="55e47-203">Les utilisateurs peuvent modifier l’ordre de leurs applications épinglées sur Teams clients de bureau et mobiles si l’option Autoriser **l’épinglage** utilisateur est désactivée.</span><span class="sxs-lookup"><span data-stu-id="55e47-203">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="55e47-204">Les utilisateurs ne peuvent pas modifier l’ordre de leurs applications épinglées sur Teams clients web.</span><span class="sxs-lookup"><span data-stu-id="55e47-204">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="55e47-205">L’épinglage des utilisateurs a-t-il la priorité ?</span><span class="sxs-lookup"><span data-stu-id="55e47-205">Does user pinning take precedence</span></span>

<span data-ttu-id="55e47-206">Les épingles administrateur sont toujours prioritaire.</span><span class="sxs-lookup"><span data-stu-id="55e47-206">Admin pins always take precedence.</span></span> <span data-ttu-id="55e47-207">Si **l’option Autoriser l’épinglage** d’utilisateur est désactivée, les utilisateurs conservent leurs applications épinglées sous les applications épinglées par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="55e47-207">If the **Allow user pinning** option is turned on, then users will retain their pinned apps below admin pinned apps.</span></span> <span data-ttu-id="55e47-208">Si **l’option** Autoriser l’épinglage d’utilisateur est désactivée, les utilisateurs perdent leurs épingles existantes et seules les applications épinglées par l’administrateur sont présentes dans la barre d’application.</span><span class="sxs-lookup"><span data-stu-id="55e47-208">If the **Allow user pinning** option is turned off, then users will lose their pre-existing pins, and only admin-pinned apps will be present in the app bar.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="55e47-209">Applications Teams personnalisées</span><span class="sxs-lookup"><span data-stu-id="55e47-209">Custom Teams apps</span></span>

<span data-ttu-id="55e47-210">Mon organisation a créé une application Teams personnalisée et l’a publiée, dans AppSource ou dans le catalogue des applications client, mais l’icône d’application ne s’affiche pas comme prévu lorsque l’application est épinglée à la barre d’application dans Teams.</span><span class="sxs-lookup"><span data-stu-id="55e47-210">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="55e47-211">Comment puis-je résoudre le problème ?</span><span class="sxs-lookup"><span data-stu-id="55e47-211">How do I fix it</span></span>

<span data-ttu-id="55e47-212">Veillez à respecter les instructions relatives au logo avant de soumettre l’application.</span><span class="sxs-lookup"><span data-stu-id="55e47-212">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="55e47-213">Pour en savoir plus, consultez [la liste de contrôle de l’envoi du tableau de bord du vendeur.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="55e47-213">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="55e47-214">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="55e47-214">Related topics</span></span>

[<span data-ttu-id="55e47-215">Paramètres d’administration pour les applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55e47-215">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="55e47-216">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="55e47-216">Assign policies to your users in Teams</span></span>](assign-policies.md)
