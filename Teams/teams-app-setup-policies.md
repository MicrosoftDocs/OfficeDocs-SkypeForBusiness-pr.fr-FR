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
description: Découvrez comment utiliser et gérer les stratégies de configuration d'application dans Microsoft Teams pour les utilisateurs de votre organisation.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ee50af6dec780480b8efdbf39dabb8e52ff03f3a
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697709"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="e909a-103">Gérer les stratégies de mise en application dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e909a-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="e909a-104">En tant qu'administrateur, vous pouvez utiliser des stratégies de configuration d'application pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="e909a-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="e909a-105">Personnaliser Teams afin de mettre en évidence les applications les plus importantes pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e909a-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="e909a-106">Vous choisissez les applications à épingler et définissez l'ordre dans celui-là.</span><span class="sxs-lookup"><span data-stu-id="e909a-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="e909a-107">L'épinglage d'applications vous permet de présenter les applications dont les utilisateurs de votre organisation ont besoin, y compris les applications conçues par des tiers ou par des développeurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e909a-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="e909a-108">Déterminer si les utilisateurs peuvent épingler des applications à Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="e909a-109">Installer des applications pour le compte des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e909a-109">Install apps on behalf of users.</span></span> <span data-ttu-id="e909a-110">Vous choisissez les applications installées par défaut pour les utilisateurs lorsqu'ils démarrent Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="e909a-111">Gardez à l'esprit que les [](teams-app-permission-policies.md) utilisateurs peuvent toujours installer les applications elles-mêmes si la stratégie d'autorisation d'application qui leur est attribuée le permet.</span><span class="sxs-lookup"><span data-stu-id="e909a-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="e909a-112">Pour les applications installées par les administrateurs, les utilisateurs ne peuvent pas les désinstaller.</span><span class="sxs-lookup"><span data-stu-id="e909a-112">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="e909a-113">Les applications sont épinglées à la barre de l'application, qui est la barre sur le côté du client de bureau Teams et en bas des clients mobiles Teams (iOS et Android).</span><span class="sxs-lookup"><span data-stu-id="e909a-113">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="e909a-114">Client de bureau Teams</span><span class="sxs-lookup"><span data-stu-id="e909a-114">Teams desktop client</span></span>  |<span data-ttu-id="e909a-115">Client mobile Teams</span><span class="sxs-lookup"><span data-stu-id="e909a-115">Teams mobile client</span></span> |
|---------|---------|
|![Client de bureau Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Client mobile Teams](media/mobile-app-ui.png)      |

<span data-ttu-id="e909a-118">Pour voir les applications installées par les administrateurs, dans la barre d'application, les utilisateurs **sélectionnent... Plus d'applications** dans les clients de bureau et Web Teams et balayez vers le haut dans les clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="e909a-118">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="e909a-119">Vous gérez les stratégies de configuration d'application dans le Centre d'administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-119">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e909a-120">Utilisez la stratégie globale (à l'échelle de l'organisation par défaut) ou créez et attribuez des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="e909a-120">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="e909a-121">Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="e909a-121">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="e909a-122">Vous devez être un administrateur général ou un administrateur du service Teams pour gérer ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="e909a-122">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="e909a-123">Vous devez modifier les paramètres de la stratégie globale pour inclure les applications que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="e909a-123">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="e909a-124">Pour personnaliser Teams pour différents groupes d'utilisateurs de votre organisation, créez et attribuez une ou plusieurs stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="e909a-124">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![Page Stratégies de configuration des applications](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="e909a-126">Si vous disposez de Teams pour l'Éducation, il est important de savoir que l'application Devoirs est épinglée par défaut dans la stratégie globale, même si actuellement elle n'est pas répertoriée dans la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="e909a-126">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="e909a-127">Il s'agit de la quatrième application dans la liste des applications épinglées sur les clients Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-127">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="e909a-128">Créer une stratégie de configuration d'application personnalisée</span><span class="sxs-lookup"><span data-stu-id="e909a-128">Create a custom app setup policy</span></span>

<span data-ttu-id="e909a-129">Vous pouvez utiliser le Centre d'administration Microsoft Teams pour créer une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="e909a-129">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="e909a-130">Dans le panneau de navigation gauche du Centre d'administration Microsoft Teams, voir Stratégies **d'installation des**  >  **applications** Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="e909a-131">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e909a-131">Select **Add**.</span></span>

   ![Page Ajouter des stratégies de configuration d'application](media/app-setup-policies-add.png)

3. <span data-ttu-id="e909a-133">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="e909a-133">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="e909a-134">Activer ou désactiver **l'application personnalisée** Télécharger, selon que vous souhaitez ou non que les utilisateurs téléchargent des applications personnalisées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-134">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="e909a-135">Vous ne pouvez pas modifier ce paramètre **si** l'application autoriser des applications tierces est désactivée dans les paramètres de l'application à l'échelle [de l'organisation.](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="e909a-135">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="e909a-136">Activer ou désactiver l'épinglage d'utilisateurs, selon que vous voulez ou non permettre aux utilisateurs de personnaliser leur barre d'application en épinglage d'applications.</span><span class="sxs-lookup"><span data-stu-id="e909a-136">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e909a-137">Le  paramètre Autoriser l'épinglage d'utilisateur est disponible dans le Centre d'administration Teams dans les environnements Microsoft 365 Government Community Cloud (GCC) (GCC, GCC High et DoD), mais il n'a actuellement aucun effet.</span><span class="sxs-lookup"><span data-stu-id="e909a-137">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="e909a-138">Pour installer des applications pour les utilisateurs, effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="e909a-138">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="e909a-139">Sous **Applications installées,** **sélectionnez Ajouter des applications.**</span><span class="sxs-lookup"><span data-stu-id="e909a-139">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="e909a-140">Dans le **volet Ajouter des applications installées,** recherchez les applications que vous voulez installer automatiquement pour les utilisateurs lorsqu'ils démarrent Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-140">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="e909a-141">Vous pouvez également filtrer les applications par stratégie d'autorisation d'application.</span><span class="sxs-lookup"><span data-stu-id="e909a-141">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="e909a-142">Une fois que vous avez choisi votre liste d'applications, sélectionnez **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="e909a-142">When you've chosen your list of apps, select **Add**.</span></span>

       ![Volet Ajouter des applications installées](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="e909a-144">Pour épingler des applications, vous pouvez suivre les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e909a-144">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="e909a-145">Sous **Applications épinglées,** **sélectionnez Ajouter des applications.**</span><span class="sxs-lookup"><span data-stu-id="e909a-145">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="e909a-146">Dans le **volet Ajouter des applications épinglées,** recherchez les applications que vous voulez ajouter, puis sélectionnez **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="e909a-146">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="e909a-147">Vous pouvez également filtrer les applications par stratégie d'autorisation d'application.</span><span class="sxs-lookup"><span data-stu-id="e909a-147">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="e909a-148">Lorsque vous avez choisi votre liste d'applications à épingler, sélectionnez **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="e909a-148">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![Volet Ajouter des applications épinglées](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="e909a-150">Organisez les applications dans l'ordre dans qui vous voulez qu'elles apparaissent dans Teams, puis sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="e909a-150">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![Section Applications épinglées](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="e909a-152">Modifier une stratégie de configuration d'application</span><span class="sxs-lookup"><span data-stu-id="e909a-152">Edit an app setup policy</span></span>

<span data-ttu-id="e909a-153">Vous pouvez utiliser le Centre d'administration Microsoft Teams pour modifier une stratégie, notamment la stratégie globale (à l'échelle de l'organisation par défaut) et les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="e909a-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="e909a-154">Dans le panneau de navigation gauche du Centre d'administration Microsoft Teams, voir Stratégies **d'installation des**  >  **applications** Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="e909a-155">Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e909a-155">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="e909a-156">À partir de là, apportez les modifications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="e909a-156">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="e909a-157">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e909a-157">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="e909a-158">Affecter une stratégie de configuration d'application personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e909a-158">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="e909a-159">FAQ</span><span class="sxs-lookup"><span data-stu-id="e909a-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="e909a-160">Fonctionnement des stratégies de configuration d'application</span><span class="sxs-lookup"><span data-stu-id="e909a-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e909a-161">Quelles stratégies de configuration d'application intégrées sont incluses dans le Centre d'administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e909a-161">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="e909a-162">**Global (par défaut à l'échelle** de l'organisation) : cette stratégie par défaut s'applique à tous les utilisateurs de votre organisation, sauf si vous attribuez une autre stratégie.</span><span class="sxs-lookup"><span data-stu-id="e909a-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="e909a-163">Modifiez la stratégie globale pour épingler les applications les plus importantes pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e909a-163">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="e909a-164">**FrontlineWorker**: cette stratégie s'agit pour les employés en ligne.</span><span class="sxs-lookup"><span data-stu-id="e909a-164">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="e909a-165">Vous pouvez l'affecter à des employés en ligne de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e909a-165">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="e909a-166">Il est important de savoir que, comme les stratégies personnalisées que vous créez, vous devez affecter la stratégie aux utilisateurs pour que les paramètres soient actifs.</span><span class="sxs-lookup"><span data-stu-id="e909a-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="e909a-167">Pour plus d'informations, voir la section Affecter une stratégie de configuration d'application personnalisée aux [utilisateurs](#assign-a-custom-app-setup-policy-to-users) de cet article.</span><span class="sxs-lookup"><span data-stu-id="e909a-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="e909a-168">Pourquoi ne puis-je pas trouver une application dans le volet Ajouter des applications épinglées ?</span><span class="sxs-lookup"><span data-stu-id="e909a-168">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="e909a-169">Toutes les applications ne peuvent pas être épinglées à Teams via une stratégie de configuration d'application.</span><span class="sxs-lookup"><span data-stu-id="e909a-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="e909a-170">Certaines applications peuvent ne pas prendre en charge cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="e909a-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="e909a-171">Pour rechercher des applications qui peuvent être épinglées, recherchez l'application dans le volet Ajouter des applications épinglées. </span><span class="sxs-lookup"><span data-stu-id="e909a-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="e909a-172">Les onglets qui ont une étendue personnelle (onglets statiques) et bots peuvent être  épinglés au client de bureau Teams. Ces applications sont disponibles dans le volet Ajouter des applications épinglées.</span><span class="sxs-lookup"><span data-stu-id="e909a-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="e909a-173">N'oubliez pas que le magasin d'applications Teams répertorie toutes les applications Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-173">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="e909a-174">Le **volet Ajouter des applications épinglées** inclut uniquement les applications qui peuvent être épinglées à Teams via une stratégie.</span><span class="sxs-lookup"><span data-stu-id="e909a-174">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="e909a-175">Je suis administrateur de Teams pour l'éducation. Que dois-je savoir sur les stratégies de configuration d'application dans Teams pour l'Éducation ?</span><span class="sxs-lookup"><span data-stu-id="e909a-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="e909a-176">L'application Appel n'est pas disponible dans Teams pour l'éducation.</span><span class="sxs-lookup"><span data-stu-id="e909a-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="e909a-177">Lorsque vous créez une stratégie de configuration d'application personnalisée, l'application Appels s'affiche dans la liste des applications.</span><span class="sxs-lookup"><span data-stu-id="e909a-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="e909a-178">Toutefois, l'application n'est pas épinglée aux clients Teams et les utilisateurs de Teams pour l'Éducation ne voient pas l'application Appels dans Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="e909a-179">Combien d'applications épinglées peuvent être ajoutées à une stratégie</span><span class="sxs-lookup"><span data-stu-id="e909a-179">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="e909a-180">Au moins deux applications doivent être épinglées aux clients mobiles Teams (iOS et Android).</span><span class="sxs-lookup"><span data-stu-id="e909a-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="e909a-181">Si une stratégie possède moins de deux applications, les clients mobiles ne reflètent pas les paramètres de stratégie et continueront à utiliser la configuration existante.</span><span class="sxs-lookup"><span data-stu-id="e909a-181">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="e909a-182">Le nombre d'applications épinglées que vous pouvez ajouter à une stratégie n'est pas limité.</span><span class="sxs-lookup"><span data-stu-id="e909a-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="e909a-183">Combien de temps faut-il pour que les modifications de stratégie prennent effet</span><span class="sxs-lookup"><span data-stu-id="e909a-183">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="e909a-184">Après avoir modifié ou attribué une stratégie, l’application des modifications peut prendre quelques heures.</span><span class="sxs-lookup"><span data-stu-id="e909a-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="e909a-185">Expérience utilisateur</span><span class="sxs-lookup"><span data-stu-id="e909a-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="e909a-186">Comment les utilisateurs peuvent-ils voir toutes leurs applications épinglées dans Teams ?</span><span class="sxs-lookup"><span data-stu-id="e909a-186">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="e909a-187">Pour afficher toutes les applications épinglées pour un utilisateur, les utilisateurs doivent peut-être faire les choses suivantes en fonction du nombre d'applications installées et de la taille de la fenêtre de leur client Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-187">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="e909a-188">Client de bureau Teams</span><span class="sxs-lookup"><span data-stu-id="e909a-188">Teams desktop client</span></span> |<span data-ttu-id="e909a-189">Client mobile Teams</span><span class="sxs-lookup"><span data-stu-id="e909a-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="e909a-190">Dans la barre de l'application sur le côté de Teams, sélectionnez **... Autres applications.**</span><span class="sxs-lookup"><span data-stu-id="e909a-190">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="e909a-191">Dans la barre de l'application en bas de Teams, balayez vers le haut.</span><span class="sxs-lookup"><span data-stu-id="e909a-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Plus d'applications dans le client de bureau Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![plus d'applications dans le client mobile Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="e909a-194">Que dois-je savoir sur l'expérience mobile dans Teams ?</span><span class="sxs-lookup"><span data-stu-id="e909a-194">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="e909a-195">Les clients mobiles Teams (iOS et Android) ne peuvent actuellement pas prise en charge les applications personnelles avec les onglets statiques.</span><span class="sxs-lookup"><span data-stu-id="e909a-195">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="e909a-196">Selon les applications définies dans la stratégie, les applications épinglées au client de bureau Teams peuvent ne pas apparaître dans les clients mobiles Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-196">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="e909a-197">Les robots personnels apparaissent toujours dans Conversation sur les clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="e909a-197">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="e909a-198">Avec les clients mobiles Teams, les utilisateurs voient les principales applications Teams telles que Activité, Conversation et Teams, et vous pouvez épingler certaines applications tierces de Microsoft, telles que Shifts.</span><span class="sxs-lookup"><span data-stu-id="e909a-198">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="e909a-199">Les utilisateurs peuvent-ils modifier l'ordre des applications épinglées via une stratégie ?</span><span class="sxs-lookup"><span data-stu-id="e909a-199">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="e909a-200">Les utilisateurs peuvent modifier l'ordre de leurs applications épinglées sur les clients de bureau et mobiles Teams si l'option Autoriser **l'épinglage** utilisateur est désactivée.</span><span class="sxs-lookup"><span data-stu-id="e909a-200">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="e909a-201">Les utilisateurs ne peuvent pas modifier l'ordre de leurs applications épinglées sur les clients web Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-201">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="e909a-202">L'épinglage des utilisateurs a-t-il la priorité ?</span><span class="sxs-lookup"><span data-stu-id="e909a-202">Does user pinning take precedence</span></span>

<span data-ttu-id="e909a-203">Les épingles administrateur sont toujours prioritaire.</span><span class="sxs-lookup"><span data-stu-id="e909a-203">Admin pins always take precedence.</span></span> <span data-ttu-id="e909a-204">Si **l'option Autoriser l'épinglage** d'utilisateur est désactivée, les utilisateurs conservent leurs applications épinglées sous les applications épinglées par l'administrateur.</span><span class="sxs-lookup"><span data-stu-id="e909a-204">If the **Allow user pinning** option is turned on, then users will retain their pinned apps below admin pinned apps.</span></span> <span data-ttu-id="e909a-205">Si **l'option** Autoriser l'épinglage d'utilisateur est désactivée, les utilisateurs perdent leurs épingles existantes et seules les applications épinglées par l'administrateur sont présentes dans la barre d'application.</span><span class="sxs-lookup"><span data-stu-id="e909a-205">If the **Allow user pinning** option is turned off, then users will lose their pre-existing pins, and only admin-pinned apps will be present in the app bar.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="e909a-206">Applications Teams personnalisées</span><span class="sxs-lookup"><span data-stu-id="e909a-206">Custom Teams apps</span></span>

<span data-ttu-id="e909a-207">Mon organisation a créé une application Teams personnalisée et l'a publiée sur AppSource ou le catalogue des applications client, mais l'icône d'application ne s'affiche pas comme prévu lorsque l'application est épinglée à la barre d'application dans Teams.</span><span class="sxs-lookup"><span data-stu-id="e909a-207">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="e909a-208">Comment puis-je résoudre le problème ?</span><span class="sxs-lookup"><span data-stu-id="e909a-208">How do I fix it</span></span>

<span data-ttu-id="e909a-209">Veillez à respecter les instructions relatives au logo avant de soumettre l'application.</span><span class="sxs-lookup"><span data-stu-id="e909a-209">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="e909a-210">Pour en savoir plus, consultez [la liste de contrôle de l'envoi du tableau de bord du vendeur.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="e909a-210">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e909a-211">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="e909a-211">Related topics</span></span>

[<span data-ttu-id="e909a-212">Paramètres d’administration pour les applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e909a-212">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="e909a-213">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e909a-213">Assign policies to your users in Teams</span></span>](assign-policies.md)
