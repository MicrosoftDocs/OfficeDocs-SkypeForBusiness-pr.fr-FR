---
title: Personnaliser des applications dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
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
description: Découvrez comment personnaliser des applications dans Microsoft Teams.
ms.openlocfilehash: 6ef38c613151ece58591cf395add35276cb55c03
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796858"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="03704-103">Personnaliser des applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="03704-103">Customize apps in Microsoft Teams</span></span>

 <span data-ttu-id="03704-104">Microsoft Teams fournit des personnalisations d’application pour améliorer Teams expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="03704-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="03704-105">Certains développeurs d’applications autorisent la personnalisation d’une application par l Teams administrateur. L’administrateur peut personnaliser ou renommer les propriétés de l’application en fonction des besoins de l’organisation à l’aide de la page Teams d’administration **Gérer les applications.**</span><span class="sxs-lookup"><span data-stu-id="03704-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="03704-106">Les détails que vous pouvez personnaliser sont les autres :</span><span class="sxs-lookup"><span data-stu-id="03704-106">The details you can customize are:</span></span>

- <span data-ttu-id="03704-107">Nom court</span><span class="sxs-lookup"><span data-stu-id="03704-107">Short name</span></span>
- <span data-ttu-id="03704-108">Brève description</span><span class="sxs-lookup"><span data-stu-id="03704-108">Short description</span></span>
- <span data-ttu-id="03704-109">Description complète</span><span class="sxs-lookup"><span data-stu-id="03704-109">Full description</span></span>
- <span data-ttu-id="03704-110">URL de la politique de confidentialité</span><span class="sxs-lookup"><span data-stu-id="03704-110">Privacy policy URL</span></span>
- <span data-ttu-id="03704-111">URL du site web</span><span class="sxs-lookup"><span data-stu-id="03704-111">Website URL</span></span>
- <span data-ttu-id="03704-112">URL des conditions d’utilisation</span><span class="sxs-lookup"><span data-stu-id="03704-112">Terms of use URL</span></span>
- <span data-ttu-id="03704-113">Icône de couleur</span><span class="sxs-lookup"><span data-stu-id="03704-113">Color icon</span></span>
- <span data-ttu-id="03704-114">Icône Plan</span><span class="sxs-lookup"><span data-stu-id="03704-114">Outline icon</span></span>
- <span data-ttu-id="03704-115">Couleur d’accentuage</span><span class="sxs-lookup"><span data-stu-id="03704-115">Accent color</span></span>

<span data-ttu-id="03704-116">Consultez le [Teams de manifeste pour](/microsoftteams/platform/resources/schema/manifest-schema) plus d’informations sur les champs que vous pouvez personnaliser.</span><span class="sxs-lookup"><span data-stu-id="03704-116">See the [Teams Manifest schema](/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> [!NOTE]
> <span data-ttu-id="03704-117">La personnalisation des applications n’est pas prise en Cloud de la communauté du secteur public du département de la défense (GCCH) ou du département de la défense (DoD).</span><span class="sxs-lookup"><span data-stu-id="03704-117">Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="03704-118">Personnaliser les détails de l’application</span><span class="sxs-lookup"><span data-stu-id="03704-118">Customize the app's details</span></span>

<span data-ttu-id="03704-119">Pour commencer à personnaliser une application, terminez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="03704-119">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="03704-120">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="03704-120">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="03704-121">Développez **Teams Applications et** **sélectionnez Gérer les applications.**</span><span class="sxs-lookup"><span data-stu-id="03704-121">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="03704-122">Consultez **la colonne Personnalisable** de la liste des applications et t triez par applications personnalisables.</span><span class="sxs-lookup"><span data-stu-id="03704-122">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![La colonne de personnalisation triée](media/customize-column.png)

   <span data-ttu-id="03704-124">Trois points d’entrée vous sont accessibles pour accéder à la fonctionnalité personnaliser :</span><span class="sxs-lookup"><span data-stu-id="03704-124">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="03704-125">Sélectionnez en côté de l’application que vous voulez personnaliser, puis **sélectionnez Personnaliser.**</span><span class="sxs-lookup"><span data-stu-id="03704-125">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![Option personnaliser la sélection 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="03704-127">Sélectionnez le nom de l’application, **puis Personnalisable.**</span><span class="sxs-lookup"><span data-stu-id="03704-127">Select the app name and then **Customizable**.</span></span>

     ![Option personnaliser la sélection 2](media/app-details-customizable.png)

   - <span data-ttu-id="03704-129">Sélectionnez le nom de l’application, puis **sélectionnez** Personnaliser dans la dropdown **Actions.**</span><span class="sxs-lookup"><span data-stu-id="03704-129">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![Option personnaliser la sélection 3](media/customize-action-menu.png)

4. <span data-ttu-id="03704-131">Développez la section **Détails** et personnalisez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="03704-131">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="03704-132">Nom court</span><span class="sxs-lookup"><span data-stu-id="03704-132">Short name</span></span>
    - <span data-ttu-id="03704-133">Brève description</span><span class="sxs-lookup"><span data-stu-id="03704-133">Short description</span></span>
    - <span data-ttu-id="03704-134">Description complète</span><span class="sxs-lookup"><span data-stu-id="03704-134">Full description</span></span>
    - <span data-ttu-id="03704-135">Site web</span><span class="sxs-lookup"><span data-stu-id="03704-135">Website</span></span>
    - <span data-ttu-id="03704-136">URL de la politique de confidentialité</span><span class="sxs-lookup"><span data-stu-id="03704-136">Privacy policy URL</span></span>
    - <span data-ttu-id="03704-137">URL des conditions d’utilisation</span><span class="sxs-lookup"><span data-stu-id="03704-137">Terms of use URL</span></span>

   ![Personnaliser les paramètres](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="03704-139">Seuls les champs que le développeur de l’application a attribués comme personnalisables seront visibles.</span><span class="sxs-lookup"><span data-stu-id="03704-139">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="03704-140">Développez la section **Icône.**</span><span class="sxs-lookup"><span data-stu-id="03704-140">Expand the **Icon** section.</span></span>

   <span data-ttu-id="03704-141">a.</span><span class="sxs-lookup"><span data-stu-id="03704-141">a.</span></span> <span data-ttu-id="03704-142">Télécharger une icône.</span><span class="sxs-lookup"><span data-stu-id="03704-142">Upload an icon.</span></span> <span data-ttu-id="03704-143">Utilisez une icône en couleur (192 x 192 pixels) au format PNG.</span><span class="sxs-lookup"><span data-stu-id="03704-143">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="03704-144">b.</span><span class="sxs-lookup"><span data-stu-id="03704-144">b.</span></span> <span data-ttu-id="03704-145">Choisissez une couleur de contour d’icône.</span><span class="sxs-lookup"><span data-stu-id="03704-145">Choose an icon outline color.</span></span> <span data-ttu-id="03704-146">Utilisez un contour transparent (32 x 32) pixels au format PNG.</span><span class="sxs-lookup"><span data-stu-id="03704-146">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="03704-147">c.</span><span class="sxs-lookup"><span data-stu-id="03704-147">c.</span></span> <span data-ttu-id="03704-148">Sélectionnez une couleur d’accentuage de l’application qui correspond à l’icône.</span><span class="sxs-lookup"><span data-stu-id="03704-148">Select an app accent color that matches the icon.</span></span>

    ![Personnaliser les options de couleur du panneau d’icônes](media/customize-app-colors.png)

6. <span data-ttu-id="03704-150">Une fois votre application personnalisée, sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="03704-150">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="03704-151">**Sélectionnez** Publier pour publier l’application personnalisée.</span><span class="sxs-lookup"><span data-stu-id="03704-151">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="03704-152">L’application personnalisée est désormais répertoriée dans votre page **Gérer les applications.**</span><span class="sxs-lookup"><span data-stu-id="03704-152">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="03704-153">Vous n’aurez qu’une version de l’application, car la personnalisation des fonctionnalités de l’application ne crée pas de copie de l’application.</span><span class="sxs-lookup"><span data-stu-id="03704-153">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="03704-154">Vos utilisateurs finaux Teams désormais ouvrir leur client Teams client pour voir l’application personnalisée.</span><span class="sxs-lookup"><span data-stu-id="03704-154">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Application personnalisée dans Teams client](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="03704-156">Considérations particulières pour la personnalisation d’une application</span><span class="sxs-lookup"><span data-stu-id="03704-156">Special considerations for customizing an app</span></span>

<span data-ttu-id="03704-157">La note suivante contient des détails importants sur la personnalisation d’une application.</span><span class="sxs-lookup"><span data-stu-id="03704-157">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="03704-158">Lorsque vous personnalisez des applications et toute description liée à une application, veillez à respecter les instructions de personnalisation fournies par l’éditeur dans leur documentation ou conditions d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="03704-158">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="03704-159">Vous devez également respecter les droits d’autres personnes concernant les images tierces que vous pourriez utiliser.</span><span class="sxs-lookup"><span data-stu-id="03704-159">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="03704-160">Les données de personnalisation fournies par l’administrateur sont stockées dans la région la plus proche.</span><span class="sxs-lookup"><span data-stu-id="03704-160">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="03704-161">Il vous faut s’assurer que les liens vers les conditions d’utilisation ou la politique de confidentialité sont valides.</span><span class="sxs-lookup"><span data-stu-id="03704-161">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="03704-162">Si l’éditeur de l’application n’autorise plus la personnalisation d’un champ, un message s’affiche sur la page des détails de l’application pour informer l’administrateur des champs qui ne peuvent plus être personnalisés.</span><span class="sxs-lookup"><span data-stu-id="03704-162">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="03704-163">Toutes les modifications apportées à ce champ seront de retour aux valeurs d’origine.</span><span class="sxs-lookup"><span data-stu-id="03704-163">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="03704-164">Nous vous recommandons de tester les modifications de personnalisation d’application Teams client de test avant d’apporter ces modifications dans votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="03704-164">We recommend testing app customization changes in a Teams test tenant before making these changes in your production environment.</span></span>
> - <span data-ttu-id="03704-165">Les modifications apportées à la marque peuvent nécessiter jusqu’à 24 heures pour que les utilisateurs voient ces modifications.</span><span class="sxs-lookup"><span data-stu-id="03704-165">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="03704-166">Passer en revue les détails de l’application</span><span class="sxs-lookup"><span data-stu-id="03704-166">Review app details</span></span>

<span data-ttu-id="03704-167">Vous souhaitez peut-être consulter les détails de l’application pour examiner les informations.</span><span class="sxs-lookup"><span data-stu-id="03704-167">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="03704-168">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="03704-168">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="03704-169">Développez **Applications Teams** et sélectionnez **Gérer les applications**.</span><span class="sxs-lookup"><span data-stu-id="03704-169">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="03704-170">Sélectionnez le nom de l’application.</span><span class="sxs-lookup"><span data-stu-id="03704-170">Select the app name.</span></span>

4. <span data-ttu-id="03704-171">Afficher les détails de l’application, y compris le nom d’origine de l’application **Short name from publisher.**</span><span class="sxs-lookup"><span data-stu-id="03704-171">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![Personnaliser le nom de l’application du panneau d’icônes](media/original-app-version.png)

   <span data-ttu-id="03704-173">Le **champ Nom court de l’éditeur** n’est visible que si vous avez modifié le nom court de l’application.</span><span class="sxs-lookup"><span data-stu-id="03704-173">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="03704-174">Rétablir les détails de l’application par défaut</span><span class="sxs-lookup"><span data-stu-id="03704-174">Reset app details to default</span></span>

<span data-ttu-id="03704-175">À tout moment, vous pouvez rétablir les paramètres d’origine des détails de l’application.</span><span class="sxs-lookup"><span data-stu-id="03704-175">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="03704-176">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="03704-176">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="03704-177">Développez **Teams Applications et** **sélectionnez Gérer les applications.**</span><span class="sxs-lookup"><span data-stu-id="03704-177">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="03704-178">Sélectionnez le nom de l’application.</span><span class="sxs-lookup"><span data-stu-id="03704-178">Select the app name.</span></span>

4. <span data-ttu-id="03704-179">Sélectionnez **Rétablir la valeur par défaut** dans la dropdown **Actions.**</span><span class="sxs-lookup"><span data-stu-id="03704-179">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![Sélectionnez Rétablir la valeur par défaut mise en évidence](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="03704-181">Foire aux questions</span><span class="sxs-lookup"><span data-stu-id="03704-181">Frequently asked questions</span></span>

<span data-ttu-id="03704-182">**Combien de temps faut-il à mes utilisateurs pour voir l’application personnalisée ?**</span><span class="sxs-lookup"><span data-stu-id="03704-182">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="03704-183">Bien que l’administrateur puisse immédiatement voir les modifications dans Teams d’administration, les modifications peuvent prendre jusqu’à 24 heures pour que les utilisateurs finaux les voient.</span><span class="sxs-lookup"><span data-stu-id="03704-183">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="03704-184">**Le fournisseur de l’application peut-il personnaliser l’application pour ses clients ?**</span><span class="sxs-lookup"><span data-stu-id="03704-184">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="03704-185">Non, l’administrateur d’un client doit personnaliser l’application pour son client à l’aide du Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="03704-185">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="03704-186">**L’application personnalisée sera-t-elle déployée automatiquement pour remplacer mon application personnalisée actuelle dans un client ?**</span><span class="sxs-lookup"><span data-stu-id="03704-186">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="03704-187">Non, les administrateurs de client devront supprimer manuellement une application personnalisée et publier la version personnalisée de l’application.</span><span class="sxs-lookup"><span data-stu-id="03704-187">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="03704-188">Si vous avez personnalisé une application et l’avez publiée comme application personnalisée, la nouvelle application personnalisée à l’aide de la fonctionnalité de personnalisation de l’application ne remplacera pas l’application personnalisée actuelle.</span><span class="sxs-lookup"><span data-stu-id="03704-188">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="03704-189">**Le rapport d’utilisation des applications affichera-t-il également les valeurs personnalisées telles que le nom court personnalisé ?**</span><span class="sxs-lookup"><span data-stu-id="03704-189">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="03704-190">Non, le rapport d’utilisation des applications indique toujours le nom d’origine de l’application envoyée par l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="03704-190">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="03704-191">**Quelles applications puis-je personnaliser à l’aide de la fonctionnalité de personnalisation des applications ?**</span><span class="sxs-lookup"><span data-stu-id="03704-191">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="03704-192">Vous pouvez seulement personnaliser les applications qui ont été autorisées à être personnalisables par l’éditeur de l’application.</span><span class="sxs-lookup"><span data-stu-id="03704-192">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="03704-193">L’éditeur de l’application devra s’y rendre pour permettre à ses clients de personnaliser l’application.</span><span class="sxs-lookup"><span data-stu-id="03704-193">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="03704-194">**Les propriétés personnalisées s’afficheront-elle sur l’écran d’autorisation graphique ?**</span><span class="sxs-lookup"><span data-stu-id="03704-194">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="03704-195">Non, l’écran d’autorisation affiche toujours la valeur d’origine envoyée par l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="03704-195">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="03704-196">Article connexe</span><span class="sxs-lookup"><span data-stu-id="03704-196">Related article</span></span>

- [<span data-ttu-id="03704-197">Gérer les applications</span><span class="sxs-lookup"><span data-stu-id="03704-197">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="03704-198">Personnaliser votre Magasin d’applications</span><span class="sxs-lookup"><span data-stu-id="03704-198">Customize your app store</span></span>](customize-your-app-store.md)
- [<span data-ttu-id="03704-199">Renommer vos applications</span><span class="sxs-lookup"><span data-stu-id="03704-199">Rebrand your apps</span></span>](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
