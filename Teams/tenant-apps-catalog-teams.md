---
title: Publier des applications dans le catalogue d’applications client Microsoft teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Conseils pour la publication d’applications dans le catalogue d’applications client Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161613"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a><span data-ttu-id="28a41-103">Publier des applications dans le catalogue d’applications client Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="28a41-103">Publish apps in the Microsoft Teams tenant app catalog</span></span>
=======================================================

<span data-ttu-id="28a41-104">Vous pouvez utiliser le catalogue d’applications client de Microsoft teams pour tester et distribuer des applications métier à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="28a41-104">You can use the Microsoft Teams tenant app catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="28a41-105">Le catalogue d’applications client teams vous permet de distribuer des applications métier qui ont été spécifiquement développées pour votre organisation et dont vous avez l’assurance que vous vous fierez aux fonctions stratégiques de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="28a41-105">The Teams tenant app catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="28a41-106">Pour publier des applications pour votre organisation, connectez-vous au client teams en utilisant un compte doté du rôle administrateur général ou service d’équipe, puis suivez les étapes décrites ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="28a41-106">To publish apps for your organization, sign in to the Teams client using an account with either the global admin or teams service admin role and then follow the steps below.</span></span>

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a><span data-ttu-id="28a41-107">Publier une application dans le catalogue d’applications client à partir du client teams</span><span class="sxs-lookup"><span data-stu-id="28a41-107">Publish an app in the tenant app catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="28a41-108">Ces étapes décrivent la publication d’une application à l’aide du client Teams.</span><span class="sxs-lookup"><span data-stu-id="28a41-108">These steps describe how to publish an app by using the Teams client.</span></span> <span data-ttu-id="28a41-109">Vous pouvez également publier une application sur la page **gérer les applications** dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="28a41-109">You can also publish an app on the **Manage apps** page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="28a41-110">Pour en savoir plus, voir [gérer les applications dans teams](manage-apps.md).</span><span class="sxs-lookup"><span data-stu-id="28a41-110">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="28a41-111">Obtenir un package d’application teams</span><span class="sxs-lookup"><span data-stu-id="28a41-111">Get a Teams app package</span></span>

<span data-ttu-id="28a41-112">Un package d’application teams est créé à l’aide de [teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="28a41-112">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="28a41-113">Une fois le package d’application installé, vous pouvez l’ajouter au catalogue d’applications du client.</span><span class="sxs-lookup"><span data-stu-id="28a41-113">Once you have the app package, you can add it to the tenant app catalog.</span></span> <span data-ttu-id="28a41-114">Même si tous les utilisateurs de votre organisation peuvent afficher le catalogue d’applications, seuls les administrateurs généraux et les administrateurs des services teams ont la possibilité de les publier et de les gérer.</span><span class="sxs-lookup"><span data-stu-id="28a41-114">While all users in your organization can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-app-catalog"></a><span data-ttu-id="28a41-115">Accédez au catalogue d’applications du client.</span><span class="sxs-lookup"><span data-stu-id="28a41-115">Go to the tenant app catalog</span></span>

<span data-ttu-id="28a41-116">Démarrez teams et connectez-vous à l’aide de vos informations d’identification d’administrateur de service ou d’équipe globale.</span><span class="sxs-lookup"><span data-stu-id="28a41-116">Start Teams and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="28a41-117">Sélectionnez **applications** dans la partie gauche de l’application, puis sélectionnez la nouvelle section intitulée pour votre organisation spécifique (dans cet exemple, contoso).</span><span class="sxs-lookup"><span data-stu-id="28a41-117">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="28a41-118">Les utilisateurs de votre organisation peuvent afficher les applications dans le catalogue et les installer pour les équipes dont ils sont membres.</span><span class="sxs-lookup"><span data-stu-id="28a41-118">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a><span data-ttu-id="28a41-120">Ajouter une application au catalogue d’applications du client</span><span class="sxs-lookup"><span data-stu-id="28a41-120">Add an app to the tenant app catalog</span></span>

1. <span data-ttu-id="28a41-121">Dans la page **applications** , sélectionnez **Télécharger un** > **chargement d’application personnalisé pour Contoso**.</span><span class="sxs-lookup"><span data-stu-id="28a41-121">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image02.png)

    <span data-ttu-id="28a41-123">(Vous pouvez également choisir **Télécharger pour moi ou mes équipes**, qui s’appelle *chargement indépendant*.</span><span class="sxs-lookup"><span data-stu-id="28a41-123">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="28a41-124">Chargement indépendant rend l’application disponible uniquement pour vos équipes ou pour les équipes que vous sélectionnez.)</span><span class="sxs-lookup"><span data-stu-id="28a41-124">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="28a41-125">Accédez au package d’application et sélectionnez-le, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="28a41-125">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image03.png)

<span data-ttu-id="28a41-127">Lorsque vous revenez à votre catalogue d’applications client, la nouvelle application d’entreprise est disponible.</span><span class="sxs-lookup"><span data-stu-id="28a41-127">When you go back to your tenant app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="28a41-128">N’oubliez pas que seuls les membres de votre organisation et vous avez accès à ce catalogue d’applications.</span><span class="sxs-lookup"><span data-stu-id="28a41-128">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-app-catalog"></a><span data-ttu-id="28a41-129">Mise à jour d’une application dans le catalogue d’applications du client</span><span class="sxs-lookup"><span data-stu-id="28a41-129">Update an app in the tenant app catalog</span></span>

1. <span data-ttu-id="28a41-130">Dans le catalogue d’applications de votre client, sélectionnez «**...**»</span><span class="sxs-lookup"><span data-stu-id="28a41-130">From your tenant app catalog, select “**…**”</span></span> <span data-ttu-id="28a41-131">dans le coin supérieur droit de l’application que vous voulez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="28a41-131">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="28a41-132">Accédez au package d’application mis à jour, sélectionnez-le, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="28a41-132">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image04.png)

<span data-ttu-id="28a41-134">L’application sera révisée vers la version 2,0.</span><span class="sxs-lookup"><span data-stu-id="28a41-134">The app will be revised to version 2.0.</span></span> <span data-ttu-id="28a41-135">Vous pouvez également supprimer l’application pour votre entreprise dans le menu.</span><span class="sxs-lookup"><span data-stu-id="28a41-135">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a><span data-ttu-id="28a41-136">Utiliser le centre d’administration de Microsoft teams pour gérer le catalogue d’applications locataire</span><span class="sxs-lookup"><span data-stu-id="28a41-136">Use the Microsoft Teams admin center to manage the tenant app catalog</span></span>

<span data-ttu-id="28a41-137">Si vous avez des applications qui ont besoin de résolutions de bogues, vous pouvez désactiver temporairement les applications pour les utilisateurs dans une stratégie d’autorisation d’application.</span><span class="sxs-lookup"><span data-stu-id="28a41-137">If you have apps that need bug fixes, you can temporarily disable apps for users in an app permission policy.</span></span>

1. <span data-ttu-id="28a41-138">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à > **stratégies d’autorisations**des **applications teams**.</span><span class="sxs-lookup"><span data-stu-id="28a41-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="28a41-139">Sélectionnez la stratégie d’autorisation d’application que vous voulez modifier, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="28a41-139">Select the app permission policy that you want to edit, and then click **Edit**.</span></span>
3. <span data-ttu-id="28a41-140">Sous **applications clientes**, sélectionnez **bloquer des applications spécifiques et autoriser tous les autres**, puis ajoutez les applications que vous souhaitez bloquer.</span><span class="sxs-lookup"><span data-stu-id="28a41-140">Under **Tenant apps**, select **Block specific apps and allow all others**, and then add the apps that you want to block.</span></span>

<span data-ttu-id="28a41-141">La désactivation d’une application interdit aux utilisateurs d’interagir avec celle-ci, sans supprimer entièrement l’application.</span><span class="sxs-lookup"><span data-stu-id="28a41-141">Disabling an app blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="28a41-142">Ces contrôles vous offrent une plus grande souplesse et contrôle lors de la gestion des applications au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="28a41-142">These controls give you additional flexibility and control when managing apps in your organization.</span></span>

<span data-ttu-id="28a41-143">Pour en savoir plus, voir [gérer les stratégies d’autorisation d’applications dans Microsoft teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="28a41-143">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>