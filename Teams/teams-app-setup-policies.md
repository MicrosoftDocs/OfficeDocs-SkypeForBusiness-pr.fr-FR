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
description: Découvrez comment utiliser et gérer les stratégies de configuration d’application dans Microsoft Teams pour les utilisateurs de votre organisation.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: a58cbf682760249ee3b269d1765a265cc58d3022
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615090"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="30051-103">Gérer les stratégies de mise en application dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="30051-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="30051-104">Si vous avez activé le paramètre de l’application à l’échelle de l’organisation, autoriser **l’interaction** avec les applications personnalisées, vous ne verrez peut-être pas encore les stratégies de configuration d’application dans le Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you might not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="30051-105">Il est en cours de déployé et sera bientôt disponible dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="30051-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="30051-106">En tant qu’administrateur, vous pouvez utiliser des stratégies de configuration d’application pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="30051-106">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="30051-107">Personnaliser Teams afin de mettre en évidence les applications les plus importantes pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="30051-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="30051-108">Vous choisissez les applications à épingler et définissez l’ordre dans celui-là.</span><span class="sxs-lookup"><span data-stu-id="30051-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="30051-109">L’épinglage d’applications vous permet de présenter les applications dont les utilisateurs de votre organisation ont besoin, y compris les applications conçues par des tiers ou par des développeurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="30051-109">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="30051-110">Déterminer si les utilisateurs peuvent épingler des applications à Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="30051-111">Installer des applications pour le compte des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="30051-111">Install apps on behalf of users.</span></span> <span data-ttu-id="30051-112">Vous choisissez les applications installées par défaut pour les utilisateurs lorsqu’ils démarrent Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="30051-113">Gardez à l’esprit que les [](teams-app-permission-policies.md) utilisateurs peuvent toujours installer les applications elles-mêmes si la stratégie d’autorisation d’application qui leur est attribuée le permet.</span><span class="sxs-lookup"><span data-stu-id="30051-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="30051-114">Pour les applications installées par les administrateurs, les utilisateurs ne peuvent pas les désinstaller.</span><span class="sxs-lookup"><span data-stu-id="30051-114">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="30051-115">Les applications sont épinglées à la barre de l’application, qui est la barre sur le côté du client de bureau Teams et en bas des clients mobiles Teams (iOS et Android).</span><span class="sxs-lookup"><span data-stu-id="30051-115">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="30051-116">Client de bureau Teams</span><span class="sxs-lookup"><span data-stu-id="30051-116">Teams desktop client</span></span>  |<span data-ttu-id="30051-117">Client mobile Teams</span><span class="sxs-lookup"><span data-stu-id="30051-117">Teams mobile client</span></span> |
|---------|---------|
|![Client de bureau Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Client mobile Teams](media/mobile-app-ui.png)      |

<span data-ttu-id="30051-120">Pour voir les applications installées par les administrateurs, dans la barre d’application, les utilisateurs **sélectionnent... Plus d’applications** dans les clients de bureau et Web Teams et balayez vers le haut dans les clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="30051-120">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="30051-121">Vous gérez les stratégies de configuration d’application dans le Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-121">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="30051-122">Utilisez la stratégie globale (à l’échelle de l’organisation par défaut) ou créez et attribuez des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="30051-122">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="30051-123">Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="30051-123">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="30051-124">Vous devez être un administrateur général ou un administrateur du service Teams pour gérer ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="30051-124">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="30051-125">Vous devez modifier les paramètres de la stratégie globale pour inclure les applications que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="30051-125">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="30051-126">Pour personnaliser Teams pour différents groupes d’utilisateurs de votre organisation, créez et attribuez une ou plusieurs stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="30051-126">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![Page Stratégies de configuration des applications](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="30051-128">Si vous disposez de Teams pour l’Éducation, il est important de savoir que l’application Devoirs est épinglée par défaut dans la stratégie globale, même si actuellement elle n’est pas répertoriée dans la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="30051-128">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="30051-129">Il s’agit de la quatrième application dans la liste des applications épinglées sur les clients Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-129">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="30051-130">Créer une stratégie de configuration d’application personnalisée</span><span class="sxs-lookup"><span data-stu-id="30051-130">Create a custom app setup policy</span></span>

<span data-ttu-id="30051-131">Vous pouvez utiliser le Centre d’administration Microsoft Teams pour créer une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="30051-131">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="30051-132">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, voir Stratégies **d’installation des**  >  **applications** Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-132">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="30051-133">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="30051-133">Select **Add**.</span></span>

   ![Page Ajouter des stratégies de configuration d’application](media/app-setup-policies-add.png)

3. <span data-ttu-id="30051-135">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="30051-135">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="30051-136">Activer ou désactiver **l’application personnalisée Télécharger,** selon que vous souhaitez ou non que les utilisateurs téléchargent des applications personnalisées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-136">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="30051-137">Vous ne pouvez pas modifier ce paramètre **si** l’application autoriser des applications tierces est désactivée dans les paramètres de l’application à l’échelle [de l’organisation.](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="30051-137">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="30051-138">Activer ou désactiver l’épinglage d’utilisateurs, selon que vous voulez ou non permettre aux utilisateurs de personnaliser leur barre d’application en épinglage d’applications.</span><span class="sxs-lookup"><span data-stu-id="30051-138">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="30051-139">Le  paramètre Autoriser l’épinglage d’utilisateur est disponible dans le Centre d’administration Teams dans les environnements Microsoft 365 Government Community Cloud (GCC) (GCC, GCC High et DoD), mais il n’a actuellement aucun effet.</span><span class="sxs-lookup"><span data-stu-id="30051-139">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="30051-140">Pour installer des applications pour les utilisateurs, effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="30051-140">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="30051-141">Sous **Applications installées,** **sélectionnez Ajouter des applications.**</span><span class="sxs-lookup"><span data-stu-id="30051-141">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="30051-142">Dans le **volet Ajouter des applications installées,** recherchez les applications que vous voulez installer automatiquement pour les utilisateurs lorsqu’ils démarrent Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-142">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="30051-143">Vous pouvez également filtrer les applications par stratégie d’autorisation d’application.</span><span class="sxs-lookup"><span data-stu-id="30051-143">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="30051-144">Une fois que vous avez choisi votre liste d’applications, sélectionnez **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="30051-144">When you've chosen your list of apps, select **Add**.</span></span>

       ![Volet Ajouter des applications installées](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="30051-146">Pour épingler des applications, vous pouvez suivre les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="30051-146">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="30051-147">Sous **Applications épinglées,** **sélectionnez Ajouter des applications.**</span><span class="sxs-lookup"><span data-stu-id="30051-147">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="30051-148">Dans le **volet Ajouter des applications épinglées,** recherchez les applications que vous voulez ajouter, puis sélectionnez **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="30051-148">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="30051-149">Vous pouvez également filtrer les applications par stratégie d’autorisation d’application.</span><span class="sxs-lookup"><span data-stu-id="30051-149">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="30051-150">Lorsque vous avez choisi votre liste d’applications à épingler, sélectionnez **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="30051-150">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![Volet Ajouter des applications épinglées](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="30051-152">Organisez les applications dans l’ordre dans qui vous voulez qu’elles apparaissent dans Teams, puis sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="30051-152">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![Section Applications épinglées](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="30051-154">Modifier une stratégie de configuration d’application</span><span class="sxs-lookup"><span data-stu-id="30051-154">Edit an app setup policy</span></span>

<span data-ttu-id="30051-155">Vous pouvez utiliser le Centre d’administration Microsoft Teams pour modifier une stratégie, notamment la stratégie globale (à l’échelle de l’organisation par défaut) et les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="30051-155">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="30051-156">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, voir Stratégies **d’installation des**  >  **applications** Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-156">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="30051-157">Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="30051-157">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="30051-158">À partir de là, apportez les modifications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="30051-158">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="30051-159">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="30051-159">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="30051-160">Affecter une stratégie de configuration d’application personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="30051-160">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="30051-161">FAQ</span><span class="sxs-lookup"><span data-stu-id="30051-161">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="30051-162">Fonctionnement des stratégies de configuration d’application</span><span class="sxs-lookup"><span data-stu-id="30051-162">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="30051-163">Quelles stratégies de configuration d’application intégrées sont incluses dans le Centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="30051-163">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="30051-164">**Global (par défaut à l’échelle** de l’organisation) : cette stratégie par défaut s’applique à tous les utilisateurs de votre organisation, sauf si vous attribuez une autre stratégie.</span><span class="sxs-lookup"><span data-stu-id="30051-164">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="30051-165">Modifiez la stratégie globale pour épingler les applications les plus importantes pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="30051-165">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="30051-166">**FrontlineWorker**: cette stratégie s’agit pour les employés en ligne.</span><span class="sxs-lookup"><span data-stu-id="30051-166">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="30051-167">Vous pouvez l’affecter à des employés en ligne de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="30051-167">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="30051-168">Il est important de savoir que, comme les stratégies personnalisées que vous créez, vous devez affecter la stratégie aux utilisateurs pour que les paramètres soient actifs.</span><span class="sxs-lookup"><span data-stu-id="30051-168">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="30051-169">Pour plus d’informations, voir la section Affecter une stratégie de configuration d’application personnalisée aux [utilisateurs](#assign-a-custom-app-setup-policy-to-users) de cet article.</span><span class="sxs-lookup"><span data-stu-id="30051-169">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="30051-170">Pourquoi ne puis-je pas trouver une application dans le volet Ajouter des applications épinglées ?</span><span class="sxs-lookup"><span data-stu-id="30051-170">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="30051-171">Toutes les applications ne peuvent pas être épinglées à Teams via une stratégie de configuration d’application.</span><span class="sxs-lookup"><span data-stu-id="30051-171">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="30051-172">Certaines applications peuvent ne pas prendre en charge cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="30051-172">Some apps may not support this functionality.</span></span> <span data-ttu-id="30051-173">Pour rechercher des applications qui peuvent être épinglées, recherchez l’application dans le volet Ajouter des applications épinglées. </span><span class="sxs-lookup"><span data-stu-id="30051-173">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="30051-174">Les onglets qui ont une étendue personnelle (onglets statiques) et bots peuvent être  épinglés au client de bureau Teams. Ces applications sont disponibles dans le volet Ajouter des applications épinglées.</span><span class="sxs-lookup"><span data-stu-id="30051-174">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="30051-175">N’oubliez pas que le magasin d’applications Teams répertorie toutes les applications Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-175">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="30051-176">Le **volet Ajouter des applications épinglées** inclut uniquement les applications qui peuvent être épinglées à Teams via une stratégie.</span><span class="sxs-lookup"><span data-stu-id="30051-176">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="30051-177">Je suis administrateur de Teams pour l’éducation. Que dois-je savoir sur les stratégies de configuration d’application dans Teams pour l’Éducation ?</span><span class="sxs-lookup"><span data-stu-id="30051-177">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="30051-178">L’application Appel n’est pas disponible dans Teams pour l’éducation.</span><span class="sxs-lookup"><span data-stu-id="30051-178">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="30051-179">Lorsque vous créez une stratégie de configuration d’application personnalisée, l’application Appels s’affiche dans la liste des applications.</span><span class="sxs-lookup"><span data-stu-id="30051-179">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="30051-180">Toutefois, l’application n’est pas épinglée aux clients Teams et les utilisateurs de Teams pour l’Éducation ne voient pas l’application Appels dans Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-180">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="30051-181">Combien d’applications épinglées peuvent être ajoutées à une stratégie</span><span class="sxs-lookup"><span data-stu-id="30051-181">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="30051-182">Au moins deux applications doivent être épinglées aux clients mobiles Teams (iOS et Android).</span><span class="sxs-lookup"><span data-stu-id="30051-182">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="30051-183">Si une stratégie possède moins de deux applications, les clients mobiles ne reflètent pas les paramètres de stratégie et continueront à utiliser la configuration existante.</span><span class="sxs-lookup"><span data-stu-id="30051-183">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="30051-184">Le nombre d’applications épinglées que vous pouvez ajouter à une stratégie n’est pas limité.</span><span class="sxs-lookup"><span data-stu-id="30051-184">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="30051-185">Combien de temps faut-il pour que les modifications de stratégie prennent effet</span><span class="sxs-lookup"><span data-stu-id="30051-185">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="30051-186">Après avoir modifié ou attribué une stratégie, l’application des modifications peut prendre quelques heures.</span><span class="sxs-lookup"><span data-stu-id="30051-186">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="30051-187">Expérience utilisateur</span><span class="sxs-lookup"><span data-stu-id="30051-187">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="30051-188">Comment les utilisateurs peuvent-ils voir toutes leurs applications épinglées dans Teams ?</span><span class="sxs-lookup"><span data-stu-id="30051-188">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="30051-189">Pour afficher toutes les applications épinglées pour un utilisateur, les utilisateurs doivent peut-être faire les choses suivantes en fonction du nombre d’applications installées et de la taille de la fenêtre de leur client Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-189">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="30051-190">Client de bureau Teams</span><span class="sxs-lookup"><span data-stu-id="30051-190">Teams desktop client</span></span> |<span data-ttu-id="30051-191">Client mobile Teams</span><span class="sxs-lookup"><span data-stu-id="30051-191">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="30051-192">Dans la barre de l’application sur le côté de Teams, sélectionnez **... Autres applications.**</span><span class="sxs-lookup"><span data-stu-id="30051-192">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="30051-193">Dans la barre de l’application en bas de Teams, balayez vers le haut.</span><span class="sxs-lookup"><span data-stu-id="30051-193">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Plus d’applications dans le client de bureau Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![plus d’applications dans le client mobile Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="30051-196">Que dois-je savoir sur l’expérience mobile dans Teams ?</span><span class="sxs-lookup"><span data-stu-id="30051-196">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="30051-197">Les clients mobiles Teams (iOS et Android) ne peuvent actuellement pas prise en charge les applications personnelles avec les onglets statiques.</span><span class="sxs-lookup"><span data-stu-id="30051-197">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="30051-198">Selon les applications définies dans la stratégie, les applications épinglées au client de bureau Teams peuvent ne pas apparaître dans les clients mobiles Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-198">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="30051-199">Les robots personnels apparaissent toujours dans conversation sur les clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="30051-199">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="30051-200">Avec les clients mobiles Teams, les utilisateurs voient les principales applications Teams telles que Activité, Conversation et Teams, et vous pouvez épingler certaines applications tierces de Microsoft, telles que Shifts.</span><span class="sxs-lookup"><span data-stu-id="30051-200">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="30051-201">Les utilisateurs peuvent-ils modifier l’ordre des applications épinglées via une stratégie ?</span><span class="sxs-lookup"><span data-stu-id="30051-201">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="30051-202">Les utilisateurs peuvent modifier l’ordre de leurs applications épinglées sur les clients de bureau et mobiles Teams si l’option Autoriser **l’épinglage** utilisateur est désactivée.</span><span class="sxs-lookup"><span data-stu-id="30051-202">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="30051-203">Les utilisateurs ne peuvent pas modifier l’ordre de leurs applications épinglées sur les clients web Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-203">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="30051-204">L’épinglage des utilisateurs a-t-il la priorité ?</span><span class="sxs-lookup"><span data-stu-id="30051-204">Does user pinning take precedence</span></span>

<span data-ttu-id="30051-205">Si la stratégie de configuration de l’application attribuée à l’utilisateur est modifiée pour bloquer l’épinglage d’application utilisateur, Teams supprime toutes les applications épinglées à la barre de l’application.</span><span class="sxs-lookup"><span data-stu-id="30051-205">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="30051-206">Si la stratégie est ensuite modifiée pour autoriser l’épinglage d’applications utilisateur, les utilisateurs doivent épinglage à leur application précédemment épinglée.</span><span class="sxs-lookup"><span data-stu-id="30051-206">If the policy is then changed to allow user app pinning, users must repin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="30051-207">Applications Teams personnalisées</span><span class="sxs-lookup"><span data-stu-id="30051-207">Custom Teams apps</span></span>

<span data-ttu-id="30051-208">Mon organisation a créé une application Teams personnalisée et l’a publiée sur AppSource ou le catalogue des applications client, mais l’icône d’application ne s’affiche pas comme prévu lorsque l’application est épinglée à la barre d’application dans Teams.</span><span class="sxs-lookup"><span data-stu-id="30051-208">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="30051-209">Comment puis-je résoudre le problème ?</span><span class="sxs-lookup"><span data-stu-id="30051-209">How do I fix it</span></span>

<span data-ttu-id="30051-210">Veillez à respecter les instructions relatives au logo avant de soumettre l’application.</span><span class="sxs-lookup"><span data-stu-id="30051-210">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="30051-211">Pour en savoir plus, consultez [la liste de contrôle de l’envoi du tableau de bord du vendeur.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="30051-211">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="30051-212">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="30051-212">Related topics</span></span>

[<span data-ttu-id="30051-213">Paramètres d’administration pour les applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="30051-213">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="30051-214">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="30051-214">Assign policies to your users in Teams</span></span>](assign-policies.md)
