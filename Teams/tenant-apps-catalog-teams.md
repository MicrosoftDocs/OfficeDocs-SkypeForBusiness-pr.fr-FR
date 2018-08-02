---
title: Publier des applications dans le catalogue d’applications client équipes Microsoft
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Conseils pour la publication d’applications dans le catalogue d’applications Microsoft équipes client.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 655a9da3670a7894e581cd2e6adebd02ef22706b
ms.sourcegitcommit: d619e44d685e2109b995ffd67ff4b98e5647c8ea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2018
ms.locfileid: "21762934"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="cbad3-103">Publier des applications dans le catalogue d’applications client équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="cbad3-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="cbad3-104">Vous pouvez utiliser le catalogue d’applications client équipes Microsoft pour tester et distribuer des applications métier de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cbad3-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="cbad3-105">Le catalogue d’applications client équipes vous permet de distribuer vos applications line-of-business qui ont été conçues spécialement pour votre organisation et que vous vous appuyez sur terminent fonctions critiques à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cbad3-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="cbad3-106">Vous pouvez publier des applications au catalogue d’applications client équipes directement depuis le client équipes.</span><span class="sxs-lookup"><span data-stu-id="cbad3-106">You can publish apps to the Teams Tenant Apps Catalog directly from the Teams client.</span></span>

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="cbad3-107">Publier une application dans le catalogue d’applications client à partir du client d’équipes</span><span class="sxs-lookup"><span data-stu-id="cbad3-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="cbad3-108">Obtenir un package d’application équipes</span><span class="sxs-lookup"><span data-stu-id="cbad3-108">Get a Teams app package</span></span>

<span data-ttu-id="cbad3-109">Un package d’application équipes est créé à l’aide des [Équipes application Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="cbad3-109">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="cbad3-110">Une fois le package d’application, vous pouvez l’ajouter à un catalogue d’applications de contenu d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="cbad3-110">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="cbad3-111">Tous les utilisateurs dans le client lors de la vue du catalogue d’applications, actuellement uniquement global admins peut avoir la possibilité de publier et gérer.</span><span class="sxs-lookup"><span data-stu-id="cbad3-111">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="cbad3-112">(Éventuellement, équipes administrateurs pourront faire également.)</span><span class="sxs-lookup"><span data-stu-id="cbad3-112">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="cbad3-113">Accédez au catalogue d’applications client</span><span class="sxs-lookup"><span data-stu-id="cbad3-113">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="cbad3-114">Dans le Store Teams Microsoft, sélectionnez la nouvelle section nommée pour votre organisation spécifique (dans cet exemple, Contoso).</span><span class="sxs-lookup"><span data-stu-id="cbad3-114">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="cbad3-115">Les utilisateurs de votre organisation peuvent afficher les applications dans le catalogue et installez-les aux équipes dont ils sont membres.</span><span class="sxs-lookup"><span data-stu-id="cbad3-115">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Capture d’écran de l’App Store équipes affichant le catalogue d’applications.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="cbad3-117">Ajouter une application au catalogue d’applications client</span><span class="sxs-lookup"><span data-stu-id="cbad3-117">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="cbad3-118">Dans le magasin, sélectionnez **télécharger une application personnalisée** > **télécharger pour Contoso**.</span><span class="sxs-lookup"><span data-stu-id="cbad3-118">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Capture d’écran de l’App Store équipes affichant le catalogue d’applications.](media/private-app-store-teams-image02.png)

<span data-ttu-id="cbad3-120">(Vous pouvez également choisir de **télécharger pour moi ou Mes équipes**, qui est appelée chargement de version test, ce qui rend l’application disponible uniquement pour votre ou vos équipes sélectionnés.)</span><span class="sxs-lookup"><span data-stu-id="cbad3-120">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="cbad3-121">Naviguer vers le package d’application et sélectionnez-le.</span><span class="sxs-lookup"><span data-stu-id="cbad3-121">Navigate to the app package and select it.</span></span>

![Capture d’écran de l’App Store équipes affichant le catalogue d’applications.](media/private-app-store-teams-image03.png)

<span data-ttu-id="cbad3-123">Lorsque vous retournez à votre catalogue d’applications client, la nouvelle application d’entreprise sera il.</span><span class="sxs-lookup"><span data-stu-id="cbad3-123">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="cbad3-124">N’oubliez pas seulement vous et les membres de votre organisation ont accès à ce catalogue d’applications.</span><span class="sxs-lookup"><span data-stu-id="cbad3-124">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="cbad3-125">Mettre à jour une application dans le catalogue d’applications client</span><span class="sxs-lookup"><span data-stu-id="cbad3-125">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="cbad3-126">À partir de votre catalogue d’applications client, sélectionnez «****»</span><span class="sxs-lookup"><span data-stu-id="cbad3-126">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="cbad3-127">sur supérieur droit de l’application que vous souhaitez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="cbad3-127">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="cbad3-128">Naviguez vers le package d’application mis à jour et sélectionnez-le.</span><span class="sxs-lookup"><span data-stu-id="cbad3-128">Navigate to the updated app package and select it.</span></span>

![Capture d’écran de l’App Store équipes affichant le catalogue d’applications.](media/private-app-store-teams-image04.png)

<span data-ttu-id="cbad3-130">L’application est révisée à la version 2.0.</span><span class="sxs-lookup"><span data-stu-id="cbad3-130">The app will be revised to version 2.0.</span></span> <span data-ttu-id="cbad3-131">Vous permet également de supprimer l’application de votre société dans ce menu.</span><span class="sxs-lookup"><span data-stu-id="cbad3-131">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="cbad3-132">Utilisez le portail d’administration d’Office 365 pour gérer le catalogue d’applications client</span><span class="sxs-lookup"><span data-stu-id="cbad3-132">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="cbad3-133">Si vous avez des applications qui nécessitent des correctifs, vous pouvez désactiver temporairement les applications via le portail d’administration d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="cbad3-133">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="cbad3-134">En plus des paramètres précédents, il est désormais une section dédié aux applications de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="cbad3-134">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="cbad3-135">Vous pouvez choisir les applications que vous souhaitez activer ou désactiver.</span><span class="sxs-lookup"><span data-stu-id="cbad3-135">You can choose which apps you want to enable or disable.</span></span>

![Capture d’écran de l’App Store équipes affichant le catalogue d’applications.](media/private-app-store-teams-image05.png)

<span data-ttu-id="cbad3-137">Cela empêche les utilisateurs d’interagir avec l’application, sans supprimer complètement de l’application.</span><span class="sxs-lookup"><span data-stu-id="cbad3-137">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="cbad3-138">Ces contrôles donner administrateurs davantage de flexibilité et contrôler quand la gouvernance des applications dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="cbad3-138">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


