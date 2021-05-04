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
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130374"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="90e33-103">Étape 4 : configurer un compte de ressource Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="90e33-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="90e33-104">Dans Microsoft Teams, un compte de ressource est requis pour chaque employé de la file d'attente d'appels ou de service automatique.</span><span class="sxs-lookup"><span data-stu-id="90e33-104">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="90e33-105">Des numéros de téléphone de service peuvent également être attribués aux comptes de ressources.</span><span class="sxs-lookup"><span data-stu-id="90e33-105">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="90e33-106">Il s'agit de la façon dont vous affectez des numéros de téléphone aux serveurs de service automatiques et aux files d'attente d'appels, ce qui permet aux appelants de l'extérieur Teams d'accéder au attendant automatique ou à la file d'attente d'appels.</span><span class="sxs-lookup"><span data-stu-id="90e33-106">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="90e33-107">Obtenir des licences utilisateur virtuel</span><span class="sxs-lookup"><span data-stu-id="90e33-107">Obtain virtual user licenses</span></span>

<span data-ttu-id="90e33-108">Les comptes de ressources nécessitent une licence pour l'utilisation des files d'attente et des files d'attente automatiques.</span><span class="sxs-lookup"><span data-stu-id="90e33-108">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="90e33-109">Vous pouvez utiliser une licence *utilisateur Microsoft 365 Système téléphonique virtuel.*</span><span class="sxs-lookup"><span data-stu-id="90e33-109">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

1. <span data-ttu-id="90e33-110">Connectez-vous au Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="90e33-110">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="90e33-111">Consultez **les**  >    >  **modules add-ons** Pour plus d'informations sur les services de facturation,  >  **voir tous les modules**</span><span class="sxs-lookup"><span data-stu-id="90e33-111">Go to **Billing** > **Purchase services** > **Add-ons** > **See all Add-ons products**</span></span>
3. <span data-ttu-id="90e33-112">Faites défiler jusqu'à la fin pour trouver **la Microsoft 365 Système téléphonique – Licence utilisateur** virtuel.</span><span class="sxs-lookup"><span data-stu-id="90e33-112">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="90e33-113">Sélectionnez **Détails,** puis **Acheter.**</span><span class="sxs-lookup"><span data-stu-id="90e33-113">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="90e33-114">Sur la page d'achat de licences, sélectionnez le nombre de licences utilisateur virtuel que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="90e33-114">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="90e33-115">Vous avez besoin d'une licence virtuelle pour chaque attendant automatique et chaque file d'attente d'appels que vous prévoyez de configurer.</span><span class="sxs-lookup"><span data-stu-id="90e33-115">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="90e33-116">Nous vous recommandons de sélectionner au moins cinq licences afin de pouvoir facilement configurer des files d'attente automatiques et des files d'attente d'appels à l'avenir sans avoir à acheter d'autres licences immédiatement.</span><span class="sxs-lookup"><span data-stu-id="90e33-116">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="90e33-117">**Décochez l'autorisation Affecter automatiquement à tous vos utilisateurs sans licence.**</span><span class="sxs-lookup"><span data-stu-id="90e33-117">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="90e33-118">Sélectionnez **Découvrir maintenant.**</span><span class="sxs-lookup"><span data-stu-id="90e33-118">Select **Check out now**.</span></span>
7. <span data-ttu-id="90e33-119">Confirmez votre commande, **sélectionnez Suivant,** puis **Commande.**</span><span class="sxs-lookup"><span data-stu-id="90e33-119">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="90e33-120">N'oubliez pas que vous devez  **toujours acheter** la licence, même si son coût est nul.</span><span class="sxs-lookup"><span data-stu-id="90e33-120">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="90e33-121">Créer un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="90e33-121">Create a resource account</span></span>

<span data-ttu-id="90e33-122">Une fois que vous avez reçu *votre Microsoft 365 Système téléphonique - Licence* Utilisateur virtuel, vous pouvez créer votre compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="90e33-122">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![Capture d'écran de l'interface utilisateur Ajouter un compte de ressource](../media/resource-account-add.png)

1. <span data-ttu-id="90e33-124">Dans le Teams d'administration, développez les **paramètres** à l'échelle de l'organisation, puis cliquez **sur Comptes de ressources.**</span><span class="sxs-lookup"><span data-stu-id="90e33-124">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>
2. <span data-ttu-id="90e33-125">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="90e33-125">Select **Add**.</span></span>
3. <span data-ttu-id="90e33-126">Dans le **volet Ajouter un compte de** ressource, remplissez Nom **d'affichage,** puis **Nom d'utilisateur.**</span><span class="sxs-lookup"><span data-stu-id="90e33-126">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="90e33-127">Choisissez un nom d'affichage descriptif tel que « employé principal de la ligne automatique » pour décrire l'objectif du compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="90e33-127">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
4. <span data-ttu-id="90e33-128">Dans **Type de compte ressource,** sélectionnez Le attendant **automatique.**</span><span class="sxs-lookup"><span data-stu-id="90e33-128">In **Resource account type**, select **Auto attendant**.</span></span>
5. <span data-ttu-id="90e33-129">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="90e33-129">Select **Save**.</span></span>

![Capture d'écran d'une liste des comptes de ressources](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="90e33-131">Attribuer une licence</span><span class="sxs-lookup"><span data-stu-id="90e33-131">Assign a license</span></span>

<span data-ttu-id="90e33-132">Après avoir créé votre compte de ressource, vous devez affecter une Microsoft 365 Système téléphonique *utilisateur* virtuel ou *une Système téléphonique* virtuel.</span><span class="sxs-lookup"><span data-stu-id="90e33-132">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Capture d'écran de l'interface utilisateur d'attribution de licences dans Microsoft 365 centre d'administration](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="90e33-134">Dans le centre Microsoft 365 d'administration, allez dans **Utilisateurs**  >  **actifs.**</span><span class="sxs-lookup"><span data-stu-id="90e33-134">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>
2. <span data-ttu-id="90e33-135">Sélectionnez votre compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="90e33-135">Select your resource account.</span></span>
1. <span data-ttu-id="90e33-136">Sous **l'onglet Licences et** applications, sous **Licences,** sélectionnez **Microsoft 365 Système téléphonique - Utilisateur virtuel.**</span><span class="sxs-lookup"><span data-stu-id="90e33-136">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="90e33-137">Sélectionnez **Enregistrer les modifications,** puis **Fermer.**</span><span class="sxs-lookup"><span data-stu-id="90e33-137">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="90e33-138">Affecter un numéro de service</span><span class="sxs-lookup"><span data-stu-id="90e33-138">Assign a service number</span></span>

![Capture d'écran de l'interface utilisateur affecter un numéro de service](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="90e33-140">Dans le Teams d'administration, allez dans les **paramètres** à l'échelle de l'organisation, puis **comptes de ressources.**</span><span class="sxs-lookup"><span data-stu-id="90e33-140">In the Teams admin center, go to **Org-wide settings** and then **Resource accounts**.</span></span> 
1. <span data-ttu-id="90e33-141">Sélectionnez le compte de ressource que vous viennent de créer, puis cliquez **sur Affecter/Désaffecter.**</span><span class="sxs-lookup"><span data-stu-id="90e33-141">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="90e33-142">Dans la **Téléphone du type de nombre,** sélectionnez En **ligne.**</span><span class="sxs-lookup"><span data-stu-id="90e33-142">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="90e33-143">Dans la **zone Numéro de téléphone** affecté, recherchez le numéro à utiliser, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="90e33-143">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="90e33-144">N'oubliez pas d'inclure l'code de pays (par exemple, **+1** 250 555 0012)</span><span class="sxs-lookup"><span data-stu-id="90e33-144">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="90e33-145">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="90e33-145">Click **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="90e33-146">Vous n'avez pas besoin de sélectionner un moyen de contrôle automatique sous **Affecter,** car le attendant automatique à qui vous voulez ajouter le numéro est déjà sélectionné.</span><span class="sxs-lookup"><span data-stu-id="90e33-146">You don't need to select an auto attendant under **Assign to** because the auto attendant you want to add the number to is already selected.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="90e33-147">Étape suivante : affecter des numéros de téléphone à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="90e33-147">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
