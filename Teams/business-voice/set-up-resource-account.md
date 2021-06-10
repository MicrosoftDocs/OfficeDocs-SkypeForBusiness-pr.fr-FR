---
title: Configurer un compte Microsoft 365 Business de ressource Voix
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Découvrez comment configurer un compte de Microsoft 365 Business voix pour une utilisation avec les attendants automatiques.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 618f26394f2b4acc44d56b814bd31c20ffe1a370
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282774"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="a6a21-103">Étape 4 : configurer un compte de ressource Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="a6a21-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="a6a21-104">Les comptes de ressources ne sont affectés à aucun utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="a6a21-104">Resource accounts aren't assigned to any specific user.</span></span> <span data-ttu-id="a6a21-105">En revanche, les comptes de ressources, qui utilisent une licence d’utilisateur virtuel gratuit, sont utilisés par les appareils et services dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a6a21-105">Instead, resource accounts, which use a free virtual user license, are used by devices and services in Microsoft 365.</span></span> <span data-ttu-id="a6a21-106">Dans Microsoft Teams, les comptes de ressources sont affectés à des numéros de téléphone, puis associés à des files d’attente et des files d’attente automatiques.</span><span class="sxs-lookup"><span data-stu-id="a6a21-106">In Microsoft Teams, resource accounts are assigned phone numbers and are then associated with auto attendants and call queues.</span></span>

<span data-ttu-id="a6a21-107">En associant des comptes de ressources aux postes de service automatiques et aux files d’attente d’appels, vous pouvez leur ajouter un ou plusieurs numéros de téléphone gratuits ou gratuits.</span><span class="sxs-lookup"><span data-stu-id="a6a21-107">By associating resource accounts to auto attendants and call queues, you can add one or more toll or toll-free phone numbers to them.</span></span> <span data-ttu-id="a6a21-108">Par exemple, vous pouvez associer un compte de ressource à un numéro toll à un service automatique pour les appelants locaux.</span><span class="sxs-lookup"><span data-stu-id="a6a21-108">For example, you could associate one resource account with a toll number to an auto attendant for local callers.</span></span> <span data-ttu-id="a6a21-109">Pour les appels longue distance, vous pouvez associer un autre compte de ressource à un numéro gratuit au même employé de service automatique.</span><span class="sxs-lookup"><span data-stu-id="a6a21-109">For long distance calls, you could associate another resource account with a toll-free number to the same auto attendant.</span></span>

<span data-ttu-id="a6a21-110">Les sections de cet article expliquent comment configurer un compte de ressource et lui attribuer un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="a6a21-110">The sections in this article show you how to set up a resource account and then assign a phone number to it.</span></span> <span data-ttu-id="a6a21-111">Plus tard, vous associerez le compte de ressource à un employé de service automatique.</span><span class="sxs-lookup"><span data-stu-id="a6a21-111">Later on, you'll associate the resource account with an auto attendant.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="a6a21-112">Obtenir des licences utilisateur virtuel</span><span class="sxs-lookup"><span data-stu-id="a6a21-112">Obtain virtual user licenses</span></span>

<span data-ttu-id="a6a21-113">Les comptes de ressources nécessitent une licence pour l’utilisation des files d’attente et des files d’attente automatiques.</span><span class="sxs-lookup"><span data-stu-id="a6a21-113">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="a6a21-114">Vous pouvez utiliser une licence *utilisateur Microsoft 365 Système téléphonique virtuel.*</span><span class="sxs-lookup"><span data-stu-id="a6a21-114">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

> [!NOTE]
> <span data-ttu-id="a6a21-115">Vous ne devez effectuer les étapes suivantes que si vous vous êtes inscrit à une période d’essai de Business Voice.</span><span class="sxs-lookup"><span data-stu-id="a6a21-115">You should only need to perform the following steps if you've signed up for a Business Voice trial period.</span></span> <span data-ttu-id="a6a21-116">Si vous avez acheté des licences Business Voice, les licences virtuelles doivent déjà être appliquées à votre compte.</span><span class="sxs-lookup"><span data-stu-id="a6a21-116">If you purchased Business Voice licenses, virtual licenses should already be applied to your account.</span></span> 
>
> <span data-ttu-id="a6a21-117">Pour voir si vous avez déjà des licences virtuelles, connectez-vous à Microsoft 365 à l’aide d’un compte avec des autorisations d’administrateur global.</span><span class="sxs-lookup"><span data-stu-id="a6a21-117">To see if you already have virtual licenses, log into Microsoft 365 using an account with Global admin permissions.</span></span> <span data-ttu-id="a6a21-118">Ensuite, allez sur Facturation > [Vos produits.](https://admin.microsoft.com/Adminportal/Home#/subscriptions)</span><span class="sxs-lookup"><span data-stu-id="a6a21-118">Then go to Billing > [Your products](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span></span> <span data-ttu-id="a6a21-119">Si vous avez des licences virtuelles, elles apparaîtront Microsoft 365 Système téléphonique **- Utilisateur virtuel.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-119">If you have virtual licenses, they'll appear as **Microsoft 365 Phone System - Virtual User**.</span></span>

1. <span data-ttu-id="a6a21-120">Ouvrez le Microsoft 365 d’administration de l’utilisateur et connectez-vous avec un utilisateur en tant qu’administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="a6a21-120">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="a6a21-121">Dans le volet de navigation gauche, consultez les modules add-ons <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank"> **Billing**  >  **Purchase services**</a>Voir tous les produits  >    >  **d’modules add-ons.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-121">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**Billing** > **Purchase services**</a> > **Add-ons** > **See all Add-ons products**.</span></span>
3. <span data-ttu-id="a6a21-122">Faites défiler jusqu’à la fin pour trouver **la Microsoft 365 Système téléphonique – Licence utilisateur** virtuel.</span><span class="sxs-lookup"><span data-stu-id="a6a21-122">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="a6a21-123">Sélectionnez **Détails,** puis **Acheter.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-123">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="a6a21-124">Sur la page d’achat de licences, sélectionnez le nombre de licences utilisateur virtuels que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="a6a21-124">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="a6a21-125">Vous avez besoin d’une licence virtuelle pour chaque attendant automatique et chaque file d’attente d’appels que vous prévoyez de configurer.</span><span class="sxs-lookup"><span data-stu-id="a6a21-125">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="a6a21-126">Nous vous recommandons de sélectionner au moins cinq licences afin de pouvoir facilement configurer des files d’attente automatiques et des files d’attente d’appels à l’avenir sans avoir à acheter d’autres licences immédiatement.</span><span class="sxs-lookup"><span data-stu-id="a6a21-126">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="a6a21-127">**Décochez l’autorisation Affecter automatiquement à tous vos utilisateurs sans licence.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-127">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="a6a21-128">Sélectionnez **Découvrir maintenant.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-128">Select **Check out now**.</span></span>
7. <span data-ttu-id="a6a21-129">Confirmez votre commande, **sélectionnez Suivant,** puis **Commande.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-129">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="a6a21-130">N’oubliez pas que vous devez  **toujours acheter** la licence, même si son coût est nul.</span><span class="sxs-lookup"><span data-stu-id="a6a21-130">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="a6a21-131">Créer un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="a6a21-131">Create a resource account</span></span>

<span data-ttu-id="a6a21-132">Une fois que vous avez reçu *votre Microsoft 365 Système téléphonique d’utilisateur* virtuel, vous pouvez créer votre compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="a6a21-132">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![Capture d’écran de l’interface utilisateur Ajouter un compte de ressource](../media/resource-account-add.png)

1. <span data-ttu-id="a6a21-134">Ouvrez le Microsoft Teams d’administration et connectez-vous avec un utilisateur en tant qu’administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="a6a21-134">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="a6a21-135">Dans le volet de navigation gauche, allez sur Comptes de ressources à l’échelle de <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">   >  **l’organisation.**</a></span><span class="sxs-lookup"><span data-stu-id="a6a21-135">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
3. <span data-ttu-id="a6a21-136">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a6a21-136">Select **Add**.</span></span>
4. <span data-ttu-id="a6a21-137">Dans le **volet Ajouter un compte de** ressource, remplissez Nom **d’affichage,** puis **Nom d’utilisateur.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-137">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="a6a21-138">Choisissez un nom d’affichage descriptif tel que « employé principal de la ligne automatique » pour décrire l’objectif du compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="a6a21-138">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
5. <span data-ttu-id="a6a21-139">Dans **Type de compte ressource,** sélectionnez Le attendant **automatique.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-139">In **Resource account type**, select **Auto attendant**.</span></span>
6. <span data-ttu-id="a6a21-140">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a6a21-140">Select **Save**.</span></span>

![Capture d’écran d’une liste des comptes de ressources](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="a6a21-142">Attribuer une licence</span><span class="sxs-lookup"><span data-stu-id="a6a21-142">Assign a license</span></span>

<span data-ttu-id="a6a21-143">Après avoir créé votre compte de ressource, vous devez affecter une *Microsoft 365 Système téléphonique utilisateur* virtuel ou *une Système téléphonique* virtuel.</span><span class="sxs-lookup"><span data-stu-id="a6a21-143">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Capture d’écran de l’interface utilisateur d’attribution de licences dans Microsoft 365 centre d’administration](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="a6a21-145">Ouvrez le Microsoft 365 d’administration de l’utilisateur et connectez-vous avec un utilisateur en tant qu’administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="a6a21-145">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="a6a21-146">Dans le volet de navigation gauche, allez à <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank"> **Utilisateurs**  >  **actifs.**</a></span><span class="sxs-lookup"><span data-stu-id="a6a21-146">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**Users** > **Active users**</a>.</span></span>
1. <span data-ttu-id="a6a21-147">Sélectionnez votre compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="a6a21-147">Select your resource account.</span></span>
1. <span data-ttu-id="a6a21-148">Sous **l’onglet Licences et** applications, sous **Licences,** sélectionnez **Microsoft 365 Système téléphonique - Utilisateur virtuel.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-148">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="a6a21-149">Sélectionnez **Enregistrer les modifications,** puis **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-149">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="a6a21-150">Affecter un numéro de service</span><span class="sxs-lookup"><span data-stu-id="a6a21-150">Assign a service number</span></span>

![Capture d’écran de l’interface utilisateur affecter un numéro de service](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="a6a21-152">Ouvrez le Microsoft Teams d’administration et connectez-vous avec un utilisateur en tant qu’administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="a6a21-152">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="a6a21-153">Dans le volet de navigation gauche, allez sur Comptes de ressources à l’échelle de <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">   >  **l’organisation.**</a></span><span class="sxs-lookup"><span data-stu-id="a6a21-153">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
1. <span data-ttu-id="a6a21-154">Sélectionnez le compte de ressource que vous viennent de créer, puis cliquez **sur Affecter/Désaffecter.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-154">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="a6a21-155">Dans la **Téléphone du type de nombre,** sélectionnez En **ligne.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-155">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="a6a21-156">Dans la **zone Numéro de téléphone** affecté, recherchez le numéro à utiliser, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="a6a21-156">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="a6a21-157">N’oubliez pas d’inclure l’code de pays (par exemple, **+1** 250 555 0012)</span><span class="sxs-lookup"><span data-stu-id="a6a21-157">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="a6a21-158">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a6a21-158">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a6a21-159">Étape suivante : affecter des numéros de téléphone à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a6a21-159">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
