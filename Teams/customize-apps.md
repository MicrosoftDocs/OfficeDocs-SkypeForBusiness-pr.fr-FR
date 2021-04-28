---
title: Personnaliser les applications Microsoft dans Teams
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
ms.openlocfilehash: 100a01c541c79ab62f10f3e11f086cdef5a11996
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059178"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="5d144-103">Personnaliser des applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d144-103">Customize apps in Microsoft Teams</span></span>

 <span data-ttu-id="5d144-104">Microsoft Teams offre une personnalisation des applications pour améliorer l'expérience Teams.</span><span class="sxs-lookup"><span data-stu-id="5d144-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="5d144-105">Certains développeurs d'applications autorisent la personnalisation d'une application par l'administrateur Teams. L'administrateur peut personnaliser ou renommer les propriétés de l'application en fonction des besoins de l'organisation à l'aide de la page Gérer les applications du **centre d'administration Teams.**</span><span class="sxs-lookup"><span data-stu-id="5d144-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="5d144-106">Les détails que vous pouvez personnaliser sont les autres :</span><span class="sxs-lookup"><span data-stu-id="5d144-106">The details you can customize are:</span></span>

- <span data-ttu-id="5d144-107">Nom court</span><span class="sxs-lookup"><span data-stu-id="5d144-107">Short name</span></span>
- <span data-ttu-id="5d144-108">Brève description</span><span class="sxs-lookup"><span data-stu-id="5d144-108">Short description</span></span>
- <span data-ttu-id="5d144-109">Description complète</span><span class="sxs-lookup"><span data-stu-id="5d144-109">Full description</span></span>
- <span data-ttu-id="5d144-110">URL de la politique de confidentialité</span><span class="sxs-lookup"><span data-stu-id="5d144-110">Privacy policy URL</span></span>
- <span data-ttu-id="5d144-111">URL du site web</span><span class="sxs-lookup"><span data-stu-id="5d144-111">Website URL</span></span>
- <span data-ttu-id="5d144-112">URL des conditions d'utilisation</span><span class="sxs-lookup"><span data-stu-id="5d144-112">Terms of use URL</span></span>
- <span data-ttu-id="5d144-113">Icône de couleur</span><span class="sxs-lookup"><span data-stu-id="5d144-113">Color icon</span></span>
- <span data-ttu-id="5d144-114">Icône Plan</span><span class="sxs-lookup"><span data-stu-id="5d144-114">Outline icon</span></span>
- <span data-ttu-id="5d144-115">Couleur d'accentuage</span><span class="sxs-lookup"><span data-stu-id="5d144-115">Accent color</span></span>

<span data-ttu-id="5d144-116">Pour plus [d'informations](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) sur les champs que vous pouvez personnaliser, consultez le schéma de manifeste Teams.</span><span class="sxs-lookup"><span data-stu-id="5d144-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> [!NOTE]
> <span data-ttu-id="5d144-117">La personnalisation des applications n'est actuellement pas prise en charge dans GCCH (Government Community Cloud High) ou le Service de la défense (DoD).</span><span class="sxs-lookup"><span data-stu-id="5d144-117">Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="5d144-118">Personnaliser les détails de l'application</span><span class="sxs-lookup"><span data-stu-id="5d144-118">Customize the app's details</span></span>

<span data-ttu-id="5d144-119">Pour commencer à personnaliser une application, terminez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="5d144-119">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="5d144-120">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5d144-120">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="5d144-121">Développez **les applications Teams,** puis **sélectionnez Gérer les applications.**</span><span class="sxs-lookup"><span data-stu-id="5d144-121">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="5d144-122">Consultez **la colonne Personnalisable** de la liste des applications et t triez par applications personnalisables.</span><span class="sxs-lookup"><span data-stu-id="5d144-122">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![La colonne de personnalisation triée](media/customize-column.png)

   <span data-ttu-id="5d144-124">Trois points d'entrée vous sont accessibles pour accéder à la fonctionnalité personnaliser :</span><span class="sxs-lookup"><span data-stu-id="5d144-124">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="5d144-125">Sélectionnez en côté de l'application que vous voulez personnaliser, puis **sélectionnez Personnaliser.**</span><span class="sxs-lookup"><span data-stu-id="5d144-125">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![Option personnaliser la sélection 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="5d144-127">Sélectionnez le nom de l'application, **puis Personnalisable.**</span><span class="sxs-lookup"><span data-stu-id="5d144-127">Select the app name and then **Customizable**.</span></span>

     ![Option personnaliser la sélection 2](media/app-details-customizable.png)

   - <span data-ttu-id="5d144-129">Sélectionnez le nom de l'application, puis **sélectionnez** Personnaliser dans la dropdown **Actions.**</span><span class="sxs-lookup"><span data-stu-id="5d144-129">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![Option personnaliser la sélection 3](media/customize-action-menu.png)

4. <span data-ttu-id="5d144-131">Développez la section **Détails** et personnalisez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="5d144-131">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="5d144-132">Nom court</span><span class="sxs-lookup"><span data-stu-id="5d144-132">Short name</span></span>
    - <span data-ttu-id="5d144-133">Brève description</span><span class="sxs-lookup"><span data-stu-id="5d144-133">Short description</span></span>
    - <span data-ttu-id="5d144-134">Description complète</span><span class="sxs-lookup"><span data-stu-id="5d144-134">Full description</span></span>
    - <span data-ttu-id="5d144-135">Site web</span><span class="sxs-lookup"><span data-stu-id="5d144-135">Website</span></span>
    - <span data-ttu-id="5d144-136">URL de la politique de confidentialité</span><span class="sxs-lookup"><span data-stu-id="5d144-136">Privacy policy URL</span></span>
    - <span data-ttu-id="5d144-137">URL des conditions d'utilisation</span><span class="sxs-lookup"><span data-stu-id="5d144-137">Terms of use URL</span></span>

   ![Personnaliser les paramètres](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="5d144-139">Seuls les champs que le développeur de l'application a attribués comme personnalisables seront visibles.</span><span class="sxs-lookup"><span data-stu-id="5d144-139">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="5d144-140">Développez la section **Icône.**</span><span class="sxs-lookup"><span data-stu-id="5d144-140">Expand the **Icon** section.</span></span>

   <span data-ttu-id="5d144-141">a.</span><span class="sxs-lookup"><span data-stu-id="5d144-141">a.</span></span> <span data-ttu-id="5d144-142">Téléchargez une icône.</span><span class="sxs-lookup"><span data-stu-id="5d144-142">Upload an icon.</span></span> <span data-ttu-id="5d144-143">Utilisez une icône en couleur (192 x 192 pixels) au format PNG.</span><span class="sxs-lookup"><span data-stu-id="5d144-143">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="5d144-144">b.</span><span class="sxs-lookup"><span data-stu-id="5d144-144">b.</span></span> <span data-ttu-id="5d144-145">Choisissez une couleur de contour d'icône.</span><span class="sxs-lookup"><span data-stu-id="5d144-145">Choose an icon outline color.</span></span> <span data-ttu-id="5d144-146">Utilisez un contour transparent (32 x 32) pixels au format PNG.</span><span class="sxs-lookup"><span data-stu-id="5d144-146">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="5d144-147">c.</span><span class="sxs-lookup"><span data-stu-id="5d144-147">c.</span></span> <span data-ttu-id="5d144-148">Sélectionnez une couleur d'accentuage de l'application qui correspond à l'icône.</span><span class="sxs-lookup"><span data-stu-id="5d144-148">Select an app accent color that matches the icon.</span></span>

    ![Personnaliser les options de couleur du panneau d'icônes](media/customize-app-colors.png)

6. <span data-ttu-id="5d144-150">Une fois votre application personnalisée, sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="5d144-150">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="5d144-151">**Sélectionnez** Publier pour publier l'application personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5d144-151">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="5d144-152">L'application personnalisée est désormais répertoriée dans votre page **Gérer les applications.**</span><span class="sxs-lookup"><span data-stu-id="5d144-152">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="5d144-153">Vous n'aurez qu'une version de l'application, car la personnalisation des fonctionnalités de l'application ne crée pas de copie de l'application.</span><span class="sxs-lookup"><span data-stu-id="5d144-153">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="5d144-154">Les utilisateurs finaux de Teams peuvent désormais ouvrir leur client Teams pour voir l'application personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5d144-154">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Application personnalisée dans le client Teams](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="5d144-156">Considérations particulières pour la personnalisation d'une application</span><span class="sxs-lookup"><span data-stu-id="5d144-156">Special considerations for customizing an app</span></span>

<span data-ttu-id="5d144-157">La note suivante contient des détails importants sur la personnalisation d'une application.</span><span class="sxs-lookup"><span data-stu-id="5d144-157">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="5d144-158">Lorsque vous personnalisez des applications et toute description liée à une application, veillez à respecter les instructions de personnalisation fournies par l'éditeur dans leur documentation ou conditions d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="5d144-158">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="5d144-159">Vous devez également respecter les droits d'autres personnes concernant les images tierces que vous pourriez utiliser.</span><span class="sxs-lookup"><span data-stu-id="5d144-159">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="5d144-160">Les données de personnalisation fournies par l'administrateur sont stockées dans la région la plus proche.</span><span class="sxs-lookup"><span data-stu-id="5d144-160">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="5d144-161">Il vous faut s'assurer que les liens vers les conditions d'utilisation ou la politique de confidentialité sont valides.</span><span class="sxs-lookup"><span data-stu-id="5d144-161">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="5d144-162">Si l'éditeur de l'application n'autorise plus la personnalisation d'un champ, un message s'affiche sur la page des détails de l'application pour informer l'administrateur des champs qui ne peuvent plus être personnalisés.</span><span class="sxs-lookup"><span data-stu-id="5d144-162">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="5d144-163">Toutes les modifications apportées à ce champ seront de retour aux valeurs d'origine.</span><span class="sxs-lookup"><span data-stu-id="5d144-163">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="5d144-164">Les modifications apportées à la marque peuvent nécessiter jusqu'à 24 heures pour que les utilisateurs voient ces modifications.</span><span class="sxs-lookup"><span data-stu-id="5d144-164">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="5d144-165">Passer en revue les détails de l'application</span><span class="sxs-lookup"><span data-stu-id="5d144-165">Review app details</span></span>

<span data-ttu-id="5d144-166">Vous souhaitez peut-être consulter les détails de l'application pour examiner les informations.</span><span class="sxs-lookup"><span data-stu-id="5d144-166">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="5d144-167">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5d144-167">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="5d144-168">Développez **Applications Teams** et sélectionnez **Gérer les applications**.</span><span class="sxs-lookup"><span data-stu-id="5d144-168">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="5d144-169">Sélectionnez le nom de l'application.</span><span class="sxs-lookup"><span data-stu-id="5d144-169">Select the app name.</span></span>

4. <span data-ttu-id="5d144-170">Afficher les détails de l'application, y compris le nom d'origine de l'application **Short name from publisher.**</span><span class="sxs-lookup"><span data-stu-id="5d144-170">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![Personnaliser le nom de l'application du panneau d'icônes](media/original-app-version.png)

   <span data-ttu-id="5d144-172">Le **champ Nom court de l'éditeur** n'est visible que si vous avez modifié le nom court de l'application.</span><span class="sxs-lookup"><span data-stu-id="5d144-172">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="5d144-173">Rétablir les détails de l'application par défaut</span><span class="sxs-lookup"><span data-stu-id="5d144-173">Reset app details to default</span></span>

<span data-ttu-id="5d144-174">À tout moment, vous pouvez rétablir les paramètres d'origine des détails de l'application.</span><span class="sxs-lookup"><span data-stu-id="5d144-174">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="5d144-175">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5d144-175">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="5d144-176">Développez **les applications Teams,** puis **sélectionnez Gérer les applications.**</span><span class="sxs-lookup"><span data-stu-id="5d144-176">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="5d144-177">Sélectionnez le nom de l'application.</span><span class="sxs-lookup"><span data-stu-id="5d144-177">Select the app name.</span></span>

4. <span data-ttu-id="5d144-178">Sélectionnez **Rétablir la valeur par défaut** dans la dropdown **Actions.**</span><span class="sxs-lookup"><span data-stu-id="5d144-178">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![Sélectionnez Rétablir la valeur par défaut mise en évidence](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="5d144-180">Foire aux questions</span><span class="sxs-lookup"><span data-stu-id="5d144-180">Frequently asked questions</span></span>

<span data-ttu-id="5d144-181">**Combien de temps faut-il à mes utilisateurs pour voir l'application personnalisée ?**</span><span class="sxs-lookup"><span data-stu-id="5d144-181">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="5d144-182">Bien que l'administrateur puisse immédiatement voir les modifications dans le Centre d'administration Teams, les modifications peuvent prendre jusqu'à 24 heures pour que les utilisateurs finaux les voient.</span><span class="sxs-lookup"><span data-stu-id="5d144-182">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="5d144-183">**Le fournisseur de l'application peut-il personnaliser l'application pour ses clients ?**</span><span class="sxs-lookup"><span data-stu-id="5d144-183">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="5d144-184">Non, l'administrateur d'un client doit personnaliser l'application pour son client à l'aide du Centre d'administration Teams.</span><span class="sxs-lookup"><span data-stu-id="5d144-184">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="5d144-185">**L'application personnalisée sera-t-elle déployée automatiquement pour remplacer mon application personnalisée actuelle dans un client ?**</span><span class="sxs-lookup"><span data-stu-id="5d144-185">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="5d144-186">Non, les administrateurs de client devront supprimer manuellement une application personnalisée et publier la version personnalisée de l'application.</span><span class="sxs-lookup"><span data-stu-id="5d144-186">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="5d144-187">Si vous avez personnalisé une application et l'avez publiée comme application personnalisée, la nouvelle application personnalisée à l'aide de la fonctionnalité de personnalisation de l'application ne remplacera pas l'application personnalisée actuelle.</span><span class="sxs-lookup"><span data-stu-id="5d144-187">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="5d144-188">**Le rapport d'utilisation des applications affichera-t-il également les valeurs personnalisées telles que le nom court personnalisé ?**</span><span class="sxs-lookup"><span data-stu-id="5d144-188">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="5d144-189">Non, le rapport d'utilisation des applications indique toujours le nom d'origine de l'application envoyée par l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="5d144-189">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="5d144-190">**Quelles applications puis-je personnaliser à l'aide de la fonctionnalité de personnalisation des applications ?**</span><span class="sxs-lookup"><span data-stu-id="5d144-190">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="5d144-191">Vous pouvez seulement personnaliser les applications qui ont été autorisées à être personnalisables par l'éditeur de l'application.</span><span class="sxs-lookup"><span data-stu-id="5d144-191">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="5d144-192">L'éditeur de l'application devra s'y rendre pour permettre à ses clients de personnaliser l'application.</span><span class="sxs-lookup"><span data-stu-id="5d144-192">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="5d144-193">**Les propriétés personnalisées s'afficheront-elle sur l'écran d'autorisation graphique ?**</span><span class="sxs-lookup"><span data-stu-id="5d144-193">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="5d144-194">Non, l'écran d'autorisation affiche toujours la valeur d'origine envoyée par l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="5d144-194">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="5d144-195">Article connexe</span><span class="sxs-lookup"><span data-stu-id="5d144-195">Related article</span></span>

- [<span data-ttu-id="5d144-196">Gérer les applications</span><span class="sxs-lookup"><span data-stu-id="5d144-196">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="5d144-197">Personnaliser votre Magasin d'applications</span><span class="sxs-lookup"><span data-stu-id="5d144-197">Customize your app store</span></span>](customize-your-app-store.md)
