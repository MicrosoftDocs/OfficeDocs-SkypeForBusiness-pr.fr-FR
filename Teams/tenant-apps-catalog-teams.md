---
title: Publier des applications dans le catalogue d’applications client Microsoft teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Conseils pour la publication d’applications dans le catalogue d’applications client Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5affe464ac300d0084916ad8ec0044ca74f8fa6b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570079"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="04b63-103">Publier des applications dans le catalogue d’applications client Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="04b63-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="04b63-104">Vous pouvez utiliser le catalogue d’applications client Microsoft teams pour tester et distribuer des applications métier à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="04b63-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="04b63-105">Le catalogue d’applications de locataire teams vous permet de distribuer des applications métier qui ont été spécifiquement développées pour votre organisation et dont vous avez l’assurance que vous vous bamettrez à effectuer les fonctions stratégiques de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="04b63-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="04b63-106">Pour publier des applications pour votre organisation, connectez-vous à votre client teams à l’aide d’un compte disposant des rôles d’administrateur général ou de service Teams, puis suivez les instructions ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="04b63-106">To publish apps for your organization, sign in to your Teams client using an account with the global admin or teams service admin roles and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="04b63-107">Publier une application dans le catalogue d’applications client à partir du client teams</span><span class="sxs-lookup"><span data-stu-id="04b63-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="04b63-108">Vous devez être connecté au client Microsoft teams avec un compte pour lequel le rôle d’administrateur général ou de service teams a été activé pour publier des applications pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="04b63-108">You need to be signed in to the Microsoft Teams client with an account that has either the global admin or teams service admin role enabled to publish apps for your organization.</span></span> <span data-ttu-id="04b63-109">En savoir plus sur [l’utilisation des rôles d’administrateur pour gérer teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="04b63-109">Learn more about [using administrator roles to manage Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="04b63-110">Obtenir un package d’application teams</span><span class="sxs-lookup"><span data-stu-id="04b63-110">Get a Teams app package</span></span>

<span data-ttu-id="04b63-111">Un package d’application teams est créé à l’aide de [teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="04b63-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="04b63-112">Une fois le package d’application installé, vous pouvez l’ajouter au catalogue d’applications de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="04b63-112">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="04b63-113">Même si tous les utilisateurs du client peuvent afficher le catalogue d’applications, seuls les administrateurs généraux et les administrateurs des services teams ont la possibilité de les publier et de les gérer.</span><span class="sxs-lookup"><span data-stu-id="04b63-113">While all users in the tenant can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="04b63-114">Accédez au catalogue des applications clientes.</span><span class="sxs-lookup"><span data-stu-id="04b63-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="04b63-115">Démarrez le client Microsoft Teams, puis connectez-vous à l’aide de vos informations d’identification d’administrateur de service global ou Teams.</span><span class="sxs-lookup"><span data-stu-id="04b63-115">Start the Microsoft Teams client and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="04b63-116">À partir de Microsoft teams Store, sélectionnez la nouvelle section intitulée pour votre organisation spécifique (dans cet exemple, contoso).</span><span class="sxs-lookup"><span data-stu-id="04b63-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="04b63-117">Les utilisateurs de votre organisation peuvent afficher les applications dans le catalogue et les installer pour les équipes dont ils sont membres.</span><span class="sxs-lookup"><span data-stu-id="04b63-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="04b63-119">Ajouter une application au catalogue d’applications locataire</span><span class="sxs-lookup"><span data-stu-id="04b63-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="04b63-120">Dans le Windows Store, sélectionnez **Télécharger un** > **chargement d’application personnalisé pour Contoso**.</span><span class="sxs-lookup"><span data-stu-id="04b63-120">From the store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image02.png)

    <span data-ttu-id="04b63-122">(Vous pouvez également choisir **Télécharger pour moi ou mes équipes**, qui s’appelle *chargement indépendant*.</span><span class="sxs-lookup"><span data-stu-id="04b63-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="04b63-123">Chargement indépendant rend l’application disponible uniquement pour vos équipes ou pour les équipes que vous sélectionnez.)</span><span class="sxs-lookup"><span data-stu-id="04b63-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="04b63-124">Accédez au package d’application et sélectionnez-le, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="04b63-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image03.png)

<span data-ttu-id="04b63-126">Lorsque vous revenez au catalogue d’applications de votre client, la nouvelle application d’entreprise est disponible.</span><span class="sxs-lookup"><span data-stu-id="04b63-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="04b63-127">N’oubliez pas que seuls les membres de votre organisation et vous avez accès à ce catalogue d’applications.</span><span class="sxs-lookup"><span data-stu-id="04b63-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="04b63-128">Mise à jour d’une application dans le catalogue des applications clientes</span><span class="sxs-lookup"><span data-stu-id="04b63-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="04b63-129">Dans le catalogue d’applications de votre client, sélectionnez «**...**»</span><span class="sxs-lookup"><span data-stu-id="04b63-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="04b63-130">dans le coin supérieur droit de l’application que vous voulez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="04b63-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="04b63-131">Accédez au package d’application mis à jour, sélectionnez-le, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="04b63-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image04.png)

<span data-ttu-id="04b63-133">L’application sera révisée vers la version 2,0.</span><span class="sxs-lookup"><span data-stu-id="04b63-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="04b63-134">Vous pouvez également supprimer l’application pour votre entreprise dans le menu.</span><span class="sxs-lookup"><span data-stu-id="04b63-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="04b63-135">Utiliser le portail d’administration Office 365 pour gérer le catalogue des applications clientes</span><span class="sxs-lookup"><span data-stu-id="04b63-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="04b63-136">Si vous avez des applications qui nécessitent des correctifs, vous pouvez désactiver temporairement les applications par le biais du portail d’administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="04b63-136">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="04b63-137">Sélectionnez **paramètres** > **services & compléments** > **Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="04b63-137">Select **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="04b63-138">Outre les paramètres précédents, il existe désormais une section consacrée aux applications de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="04b63-138">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="04b63-139">Vous pouvez sélectionner les applications que vous souhaitez activer ou désactiver.</span><span class="sxs-lookup"><span data-stu-id="04b63-139">You can choose which apps you want to enable or disable.</span></span>

![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image05.png)

<span data-ttu-id="04b63-141">La désactivation d’une application empêche les utilisateurs d’interagir avec celle-ci, sans supprimer entièrement l’application.</span><span class="sxs-lookup"><span data-stu-id="04b63-141">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="04b63-142">Ces contrôles vous offrent une plus grande souplesse et contrôle lors de la gestion des applications dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="04b63-142">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>
