---
title: Publier des applications dans le catalogue d’applications client équipes Microsoft
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Conseils pour la publication d’applications dans le catalogue d’applications Microsoft équipes client.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 298caf3cee6fe6af38f22ef9ac7dd85991fd6dba
ms.sourcegitcommit: b42a6a56a0e1e4be1239174c1c3b4ab86517d043
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2018
ms.locfileid: "20050454"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="51a51-103">Publier des applications dans le catalogue d’applications client équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="51a51-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

> [!IMPORTANT]
> <span data-ttu-id="51a51-104">Cette page décrit une fonctionnalité de la version préliminaire et contenu préliminaire peut changer considérablement avant son lancement.</span><span class="sxs-lookup"><span data-stu-id="51a51-104">This page describes a pre-release feature and contains preliminary content that might change substantially before it is released.</span></span> <span data-ttu-id="51a51-105">Les captures d’écran sont des espaces réservés et peuvent différer de celle que vous voyez.</span><span class="sxs-lookup"><span data-stu-id="51a51-105">Any screenshots are placeholders and might look different than what you see.</span></span>

<span data-ttu-id="51a51-106">Vous pouvez utiliser le catalogue d’applications client équipes Microsoft pour tester et distribuer des applications métier de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="51a51-106">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="51a51-107">Le catalogue d’applications client équipes vous permet de distribuer vos applications line-of-business qui ont été conçues spécialement pour votre organisation et que vous vous appuyez sur terminent fonctions critiques à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="51a51-107">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="51a51-108">Vous pouvez publier des applications au catalogue d’applications client équipes directement depuis le client équipes.</span><span class="sxs-lookup"><span data-stu-id="51a51-108">You can publish apps to the Teams Tenant Apps Catalog directly from the Teams client.</span></span>

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="51a51-109">Publier une application dans le catalogue d’applications client à partir du client d’équipes</span><span class="sxs-lookup"><span data-stu-id="51a51-109">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="51a51-110">Obtenir un package d’application équipes</span><span class="sxs-lookup"><span data-stu-id="51a51-110">Get a Teams app package</span></span>

<span data-ttu-id="51a51-111">Un package d’application équipes est créé à l’aide des [Équipes application Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="51a51-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="51a51-112">Une fois le package d’application, vous pouvez l’ajouter à un catalogue d’applications de contenu d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="51a51-112">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="51a51-113">Alors que tous les utilisateurs dans le client peuvent afficher le catalogue d’applications, seuls les administrateurs ont la possibilité de gérer.</span><span class="sxs-lookup"><span data-stu-id="51a51-113">While all users in the tenant can view the app catalog, only admins have the ability to manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="51a51-114">Accédez au catalogue d’applications client</span><span class="sxs-lookup"><span data-stu-id="51a51-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="51a51-115">Dans le Store Teams Microsoft, sélectionnez la nouvelle section nommée pour votre organisation spécifique (dans cet exemple, Contoso).</span><span class="sxs-lookup"><span data-stu-id="51a51-115">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="51a51-116">Les utilisateurs de votre organisation peuvent afficher les applications dans le catalogue et installez-les aux équipes dont ils sont membres.</span><span class="sxs-lookup"><span data-stu-id="51a51-116">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Capture d’écran de l’App Store équipes affichant le catalogue d’applications.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="51a51-118">Ajouter une application au catalogue d’applications client</span><span class="sxs-lookup"><span data-stu-id="51a51-118">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="51a51-119">Dans le magasin, sélectionnez **télécharger une application personnalisée** > **télécharger pour Contoso**.</span><span class="sxs-lookup"><span data-stu-id="51a51-119">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Capture d’écran de l’App Store équipes affichant le catalogue d’applications.](media/private-app-store-teams-image02.png)

<span data-ttu-id="51a51-121">(Vous pouvez également choisir de **télécharger pour moi ou Mes équipes**, qui est appelée chargement de version test, ce qui rend l’application disponible uniquement pour votre ou vos équipes sélectionnés.)</span><span class="sxs-lookup"><span data-stu-id="51a51-121">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="51a51-122">Naviguer vers le package d’application et sélectionnez-le.</span><span class="sxs-lookup"><span data-stu-id="51a51-122">Navigate to the app package and select it.</span></span>

![Capture d’écran de l’App Store équipes affichant le catalogue d’applications.](media/private-app-store-teams-image03.png)

<span data-ttu-id="51a51-124">Lorsque vous retournez à votre catalogue d’applications client, la nouvelle application d’entreprise sera il.</span><span class="sxs-lookup"><span data-stu-id="51a51-124">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="51a51-125">N’oubliez pas seulement vous et les membres de votre organisation ont accès à ce catalogue d’applications.</span><span class="sxs-lookup"><span data-stu-id="51a51-125">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="51a51-126">Mettre à jour une application dans le catalogue d’applications client</span><span class="sxs-lookup"><span data-stu-id="51a51-126">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="51a51-127">À partir de votre catalogue d’applications client, sélectionnez «****»</span><span class="sxs-lookup"><span data-stu-id="51a51-127">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="51a51-128">sur supérieur droit de l’application que vous souhaitez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="51a51-128">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="51a51-129">Naviguez vers le package d’application mis à jour et sélectionnez-le.</span><span class="sxs-lookup"><span data-stu-id="51a51-129">Navigate to the updated app package and select it.</span></span>

![Capture d’écran de l’App Store équipes affichant le catalogue d’applications.](media/private-app-store-teams-image04.png)

<span data-ttu-id="51a51-131">L’application est révisée à la version 2.0.</span><span class="sxs-lookup"><span data-stu-id="51a51-131">The app will be revised to version 2.0.</span></span> <span data-ttu-id="51a51-132">Vous permet également de supprimer l’application de votre société dans ce menu.</span><span class="sxs-lookup"><span data-stu-id="51a51-132">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="51a51-133">Utilisez le portail d’administration d’Office 365 pour gérer le catalogue d’applications client</span><span class="sxs-lookup"><span data-stu-id="51a51-133">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="51a51-134">Si vous avez des applications qui nécessitent des correctifs, vous pouvez désactiver temporairement les applications via le portail d’administration d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="51a51-134">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="51a51-135">En plus des paramètres précédents, il est désormais une section dédié aux applications de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="51a51-135">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="51a51-136">Vous pouvez choisir les applications que vous souhaitez activer ou désactiver.</span><span class="sxs-lookup"><span data-stu-id="51a51-136">You can choose which apps you want to enable or disable.</span></span>

![Capture d’écran de l’App Store équipes affichant le catalogue d’applications.](media/private-app-store-teams-image05.png)

<span data-ttu-id="51a51-138">Cela empêche les utilisateurs d’interagir avec l’application, sans supprimer complètement de l’application.</span><span class="sxs-lookup"><span data-stu-id="51a51-138">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="51a51-139">Ces contrôles donner administrateurs davantage de flexibilité et contrôler quand la gouvernance des applications dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="51a51-139">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


