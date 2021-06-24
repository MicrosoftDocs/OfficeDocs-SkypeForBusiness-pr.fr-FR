---
title: Configurer un compte de Microsoft 365 Business Voice ressources client
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
description: Découvrez comment configurer un compte de ressource Microsoft 365 Business Voice à utiliser avec les attendants automatiques.
appliesto:
- Microsoft Teams
ms.openlocfilehash: df5001b6f757b407e96a473d302c79d837af957c
ms.sourcegitcommit: 38fa37d83704200911866cf017566fcb128ea2fe
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105166"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="612db-103">Étape 4 : configurer un compte de ressource Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="612db-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="612db-104">Les comptes de ressources ne sont affectés à aucun utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="612db-104">Resource accounts aren't assigned to any specific user.</span></span> <span data-ttu-id="612db-105">En revanche, les comptes de ressources, qui utilisent une licence d’utilisateur virtuel gratuit, sont utilisés par les appareils et services dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="612db-105">Instead, resource accounts, which use a free virtual user license, are used by devices and services in Microsoft 365.</span></span> <span data-ttu-id="612db-106">Dans Microsoft Teams, les comptes de ressources sont affectés à des numéros de téléphone, puis associés à des files d’attente et des files d’attente automatiques.</span><span class="sxs-lookup"><span data-stu-id="612db-106">In Microsoft Teams, resource accounts are assigned phone numbers and are then associated with auto attendants and call queues.</span></span>

<span data-ttu-id="612db-107">En associant des comptes de ressources aux postes de service automatiques et aux files d’attente d’appels, vous pouvez leur ajouter un ou plusieurs numéros de téléphone gratuits ou gratuits.</span><span class="sxs-lookup"><span data-stu-id="612db-107">By associating resource accounts to auto attendants and call queues, you can add one or more toll or toll-free phone numbers to them.</span></span> <span data-ttu-id="612db-108">Par exemple, vous pouvez associer un compte de ressource à un numéro toll à un employé de service automatique pour les appelants locaux.</span><span class="sxs-lookup"><span data-stu-id="612db-108">For example, you could associate one resource account with a toll number to an auto attendant for local callers.</span></span> <span data-ttu-id="612db-109">Pour les appels longue distance, vous pouvez associer un autre compte de ressource à un numéro gratuit au même employé de service automatique.</span><span class="sxs-lookup"><span data-stu-id="612db-109">For long distance calls, you could associate another resource account with a toll-free number to the same auto attendant.</span></span>

<span data-ttu-id="612db-110">Les sections de cet article expliquent comment configurer un compte de ressource et lui attribuer un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="612db-110">The sections in this article show you how to set up a resource account and then assign a phone number to it.</span></span> <span data-ttu-id="612db-111">Plus tard, vous associerez le compte de ressource à un employé de service automatique.</span><span class="sxs-lookup"><span data-stu-id="612db-111">Later on, you'll associate the resource account with an auto attendant.</span></span>

<span data-ttu-id="612db-112">La vidéo suivante vous montre comment effectuer ces étapes dans le Centre d’administration Teams’administration.</span><span class="sxs-lookup"><span data-stu-id="612db-112">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OFYG]

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="612db-113">Obtenir des licences utilisateur virtuel</span><span class="sxs-lookup"><span data-stu-id="612db-113">Obtain virtual user licenses</span></span>

<span data-ttu-id="612db-114">Les comptes de ressources nécessitent une licence pour l’utilisation des files d’attente et des files d’attente automatiques.</span><span class="sxs-lookup"><span data-stu-id="612db-114">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="612db-115">Vous pouvez utiliser une licence *utilisateur Microsoft 365 Système téléphonique virtuel.*</span><span class="sxs-lookup"><span data-stu-id="612db-115">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

> [!NOTE]
> <span data-ttu-id="612db-116">Vous ne devez effectuer les étapes suivantes que si vous vous êtes inscrit à une période d’essai de Business Voice.</span><span class="sxs-lookup"><span data-stu-id="612db-116">You should only need to perform the following steps if you've signed up for a Business Voice trial period.</span></span> <span data-ttu-id="612db-117">Si vous avez acheté des licences Business Voice, les licences virtuelles doivent déjà être appliquées à votre compte.</span><span class="sxs-lookup"><span data-stu-id="612db-117">If you purchased Business Voice licenses, virtual licenses should already be applied to your account.</span></span> 
>
> <span data-ttu-id="612db-118">Pour voir si vous avez déjà des licences virtuelles, connectez-vous à Microsoft 365 à l’aide d’un compte avec des autorisations d’administrateur global.</span><span class="sxs-lookup"><span data-stu-id="612db-118">To see if you already have virtual licenses, log into Microsoft 365 using an account with Global admin permissions.</span></span> <span data-ttu-id="612db-119">Ensuite, allez sur Facturation > [Vos produits.](https://admin.microsoft.com/Adminportal/Home#/subscriptions)</span><span class="sxs-lookup"><span data-stu-id="612db-119">Then go to Billing > [Your products](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span></span> <span data-ttu-id="612db-120">Si vous avez des licences virtuelles, elles apparaîtront Microsoft 365 Système téléphonique **- Utilisateur virtuel.**</span><span class="sxs-lookup"><span data-stu-id="612db-120">If you have virtual licenses, they'll appear as **Microsoft 365 Phone System - Virtual User**.</span></span>

1. <span data-ttu-id="612db-121">Ouvrez le Centre d’administration Microsoft 365 et connectez-vous avec un utilisateur en tant qu’administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="612db-121">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="612db-122">Dans le volet de navigation gauche, consultez les modules add-ons <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank"> **Billing**  >  **Purchase services**</a>Voir tous les produits  >    >  **d’modules add-ons.**</span><span class="sxs-lookup"><span data-stu-id="612db-122">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**Billing** > **Purchase services**</a> > **Add-ons** > **See all Add-ons products**.</span></span>
3. <span data-ttu-id="612db-123">Faites défiler jusqu’à la fin pour trouver **la Microsoft 365 Système téléphonique – Licence utilisateur** virtuel.</span><span class="sxs-lookup"><span data-stu-id="612db-123">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="612db-124">Sélectionnez **Détails,** puis **Acheter.**</span><span class="sxs-lookup"><span data-stu-id="612db-124">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="612db-125">Sur la page d’achat de licences, sélectionnez le nombre de licences utilisateur virtuels que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="612db-125">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="612db-126">Vous avez besoin d’une licence virtuelle pour chaque attendant automatique et chaque file d’attente d’appels que vous prévoyez de configurer.</span><span class="sxs-lookup"><span data-stu-id="612db-126">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="612db-127">Nous vous recommandons de sélectionner au moins cinq licences afin de pouvoir facilement configurer des files d’attente automatiques et des files d’attente d’appels à l’avenir sans avoir à acheter d’autres licences immédiatement.</span><span class="sxs-lookup"><span data-stu-id="612db-127">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="612db-128">**Décochez l’autorisation Affecter automatiquement à tous vos utilisateurs sans licence.**</span><span class="sxs-lookup"><span data-stu-id="612db-128">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="612db-129">Sélectionnez **Découvrir maintenant.**</span><span class="sxs-lookup"><span data-stu-id="612db-129">Select **Check out now**.</span></span>
7. <span data-ttu-id="612db-130">Confirmez votre commande, **sélectionnez Suivant,** puis **Commande.**</span><span class="sxs-lookup"><span data-stu-id="612db-130">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="612db-131">N’oubliez pas que vous devez  **toujours acheter** la licence, même si son coût est nul.</span><span class="sxs-lookup"><span data-stu-id="612db-131">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="612db-132">Créer un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="612db-132">Create a resource account</span></span>

<span data-ttu-id="612db-133">Une fois que vous avez reçu *votre Microsoft 365 Système téléphonique d’utilisateur* virtuel, vous pouvez créer votre compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="612db-133">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![Capture d’écran de l’interface utilisateur Ajouter un compte de ressource](../media/resource-account-add.png)

1. <span data-ttu-id="612db-135">Ouvrez le Microsoft Teams d’administration et connectez-vous avec un utilisateur en tant qu’administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="612db-135">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="612db-136">Dans le volet de navigation gauche, allez sur Comptes de ressources à l’échelle de <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">   >  **l’organisation.**</a></span><span class="sxs-lookup"><span data-stu-id="612db-136">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
3. <span data-ttu-id="612db-137">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="612db-137">Select **Add**.</span></span>
4. <span data-ttu-id="612db-138">Dans le **volet Ajouter un compte de** ressource, remplissez Nom **d’affichage,** puis **Nom d’utilisateur.**</span><span class="sxs-lookup"><span data-stu-id="612db-138">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="612db-139">Choisissez un nom d’affichage descriptif tel que « employé principal de la ligne automatique » pour décrire l’objectif du compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="612db-139">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
5. <span data-ttu-id="612db-140">Dans **Type de compte ressource,** sélectionnez Le attendant **automatique.**</span><span class="sxs-lookup"><span data-stu-id="612db-140">In **Resource account type**, select **Auto attendant**.</span></span>
6. <span data-ttu-id="612db-141">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="612db-141">Select **Save**.</span></span>

![Capture d’écran d’une liste des comptes de ressources](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="612db-143">Attribuer une licence</span><span class="sxs-lookup"><span data-stu-id="612db-143">Assign a license</span></span>

<span data-ttu-id="612db-144">Après avoir créé votre compte de ressource, vous devez affecter une Microsoft 365 Système téléphonique *utilisateur* virtuel ou *une Système téléphonique* virtuel.</span><span class="sxs-lookup"><span data-stu-id="612db-144">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Capture d’écran de l’interface utilisateur attribuer des licences dans le Centre d’administration Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="612db-146">Ouvrez le Centre d’administration Microsoft 365 et connectez-vous avec un utilisateur en tant qu’administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="612db-146">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="612db-147">Dans le volet de navigation gauche, allez à <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank"> **Utilisateurs**  >  **actifs.**</a></span><span class="sxs-lookup"><span data-stu-id="612db-147">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**Users** > **Active users**</a>.</span></span>
1. <span data-ttu-id="612db-148">Sélectionnez votre compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="612db-148">Select your resource account.</span></span>
1. <span data-ttu-id="612db-149">Sous **l’onglet Licences et** applications, sous **Licences,** sélectionnez **Microsoft 365 Système téléphonique - Utilisateur virtuel.**</span><span class="sxs-lookup"><span data-stu-id="612db-149">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="612db-150">Sélectionnez **Enregistrer les modifications,** puis **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="612db-150">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="612db-151">Affecter un numéro de service</span><span class="sxs-lookup"><span data-stu-id="612db-151">Assign a service number</span></span>

![Capture d’écran de l’interface utilisateur affecter un numéro de service](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="612db-153">Ouvrez le Microsoft Teams d’administration et connectez-vous avec un utilisateur en tant qu’administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="612db-153">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="612db-154">Dans le volet de navigation gauche, allez sur Comptes de ressources à l’échelle de <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">   >  **l’organisation.**</a></span><span class="sxs-lookup"><span data-stu-id="612db-154">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
1. <span data-ttu-id="612db-155">Sélectionnez le compte de ressource que vous viennent de créer, puis cliquez **sur Affecter/Désaffecter.**</span><span class="sxs-lookup"><span data-stu-id="612db-155">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="612db-156">Dans la **Téléphone du type de nombre,** sélectionnez En **ligne.**</span><span class="sxs-lookup"><span data-stu-id="612db-156">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="612db-157">Dans la **zone Numéro de téléphone** affecté, recherchez le numéro à utiliser, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="612db-157">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="612db-158">N’oubliez pas d’inclure l’code de pays (par exemple, **+1** 250 555 0012)</span><span class="sxs-lookup"><span data-stu-id="612db-158">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="612db-159">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="612db-159">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="612db-160">Étape suivante : affecter des numéros de téléphone à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="612db-160">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
