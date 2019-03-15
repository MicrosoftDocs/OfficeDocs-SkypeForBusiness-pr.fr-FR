---
title: Gérer les comptes de ressource dans Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: La gestion des comptes de ressource dans Microsoft Teams
ms.openlocfilehash: dad2ea10f2dbdeb387a74d01fd48ca6de9805a5a
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30633249"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="20e03-103">Gérer les comptes de ressources dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="20e03-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="20e03-104">Un compte de ressource est également appelée un objet utilisateur désactivé dans Azure Active Directory et peut être utilisé pour représenter les ressources en général.</span><span class="sxs-lookup"><span data-stu-id="20e03-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="20e03-105">Dans Exchange, il peut être utilisé pour représenter des salles de conférence, par exemple et les autoriser à un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="20e03-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="20e03-106">Un compte de ressource peut être hébergé dans Microsoft 365 ou sur site à l’aide de Skype pour Business server, et ces comptes sont créés à l’aide des commandes Powershell.</span><span class="sxs-lookup"><span data-stu-id="20e03-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="20e03-107">Dans Microsoft Teams ou Skype pour Business en ligne, chaque file d’attente des appels ou auto attendant est nécessaire pour ont un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="20e03-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="20e03-108">Si un compte de ressource doit être un numéro de téléphone affecté dépendent de l’utilisation prévue de la file d’attente d’appel associé ou le standard automatique.</span><span class="sxs-lookup"><span data-stu-id="20e03-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="20e03-109">Consultez les articles sur les files d’attente de l’appel et qui sont liées au bas de cet article avant d’affecter un numéro de téléphone à un compte de ressource de standards automatiques.</span><span class="sxs-lookup"><span data-stu-id="20e03-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="20e03-110">Cet article s’applique à Microsoft Teams et Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="20e03-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="20e03-111">Conditions préalables pour affecter un numéro de téléphone à un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="20e03-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="20e03-112">Mise en route il est important de garder à l’esprit quelques points :</span><span class="sxs-lookup"><span data-stu-id="20e03-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="20e03-113">Votre organisation doit avoir (au minimum), une licence entreprise E3 plus **Système téléphonique** ou une licence Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="20e03-113">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="20e03-114">Le nombre de licences utilisateur **Système téléphonique** qui sont assignés affecte le nombre de numéros de service qui sont disponibles pour être utilisés pour les comptes de ressources affectées à appeler des files d’attente ou les standards automatiques.</span><span class="sxs-lookup"><span data-stu-id="20e03-114">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for resource accounts assigned to call queues or auto attendants.</span></span> <span data-ttu-id="20e03-115">Le nombre de comptes de ressources que vous pouvez avoir est varie selon le nombre de licences **Système téléphonique** et de **Conférence** qui sont assignés au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="20e03-115">The number of resource accounts you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="20e03-116">Pour plus d’informations sur les licences, voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="20e03-116">To learn more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="20e03-117">Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou Office 365 appelant Plans.</span><span class="sxs-lookup"><span data-stu-id="20e03-117">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="20e03-118">Consultez les [licences d’affecter des équipes Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="20e03-118">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="20e03-119">Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20e03-119">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="20e03-120">Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="20e03-120">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="20e03-121">Pour en savoir plus sur Office 365 appelant Plans, voir [Appel Plans pour Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="20e03-121">To learn more about Office 365 Calling Plans, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>
- <span data-ttu-id="20e03-122">Vous pouvez uniquement attribuer payants et les numéros de téléphone gratuit service que vous avez obtenu dans le **Centre d’administration de Microsoft équipes** ou transféré à partir d’un autre fournisseur de services vers un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="20e03-122">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="20e03-123">Pour obtenir et utiliser des numéros gratuits service, vous devez configurer les crédits de Communications.</span><span class="sxs-lookup"><span data-stu-id="20e03-123">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="20e03-124">Numéros de téléphone de l’utilisateur (abonné) ne peut pas être affectés à un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="20e03-124">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="20e03-125">Numéro payant service ou numéros de téléphone peuvent être utilisées.</span><span class="sxs-lookup"><span data-stu-id="20e03-125">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="20e03-126">Pour affecter un numéro de téléphone à un compte de ressource, vous devez obtenir ou transférer votre appel payant existant ou un service gratuit numéros.</span><span class="sxs-lookup"><span data-stu-id="20e03-126">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="20e03-127">Une fois que vous obtenez les numéros de téléphone gratuit service payant, ils s’affichent dans le **Centre d’administration de Microsoft équipes** > **vocale** > **numéros de téléphone**et la volonté de **type numérique** présent figurer en tant que **Service - gratuit**.</span><span class="sxs-lookup"><span data-stu-id="20e03-127">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="20e03-128">Pour obtenir vos numéros de service, voir les [numéros de téléphone de mise en service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) , ou si vous souhaitez transférer un numéro de service existant, voir les [numéros de téléphone transfert vers Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="20e03-128">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="20e03-129">Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration Microsoft Teams pour obtenir les numéros de service.</span><span class="sxs-lookup"><span data-stu-id="20e03-129">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="20e03-130">Accédez à [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour voir comment le faire à partir de l’extérieur des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="20e03-130">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="20e03-131">Créer un compte de ressource dans Powershell</span><span class="sxs-lookup"><span data-stu-id="20e03-131">Create a resource account in Powershell</span></span>

 <span data-ttu-id="20e03-132">Vous souhaite créer un compte de ressource en exécutant l’applet de commande Powershell approprié selon vos besoins (pour un ou plusieurs comptes de ressources), nommez chacune d’elles et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="20e03-132">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="20e03-133">Il n’existe actuellement aucune option pour la création d’un compte de ressource dans le centre d’administration Microsoft Teams, mais vous pouvez modifier les numéros de téléphone et modifier les appels en file d’attente ou automatique attendant affectations d’un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="20e03-133">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="20e03-134">Selon que votre numéro de téléphone est situé en ligne ou sur site, vous devez vous connecter à l’invite de Powershell approprié avec des privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="20e03-134">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="20e03-135">Implémentations hybride (numéros de numéros hébergés sur routage Direct, OPCH et CCE) utilise [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) pour créer un compte de ressource qui est hébergé sur site.</span><span class="sxs-lookup"><span data-stu-id="20e03-135">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="20e03-136">En ligne uniquement implémentations utilise [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) pour avoir un compte de ressource qui est hébergé en ligne.</span><span class="sxs-lookup"><span data-stu-id="20e03-136">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="20e03-137">Voici un exemple d’environnement de ligne de la création d’un compte de ressource :</span><span class="sxs-lookup"><span data-stu-id="20e03-137">The following is an online environment example of creating a resource account:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -DisplayName Node1 -SipAddress sip:node1@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
```

<span data-ttu-id="20e03-138">Pour plus d’informations sur cette commande, voir [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="20e03-138">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="20e03-139">Il est plus facile de définir le numéro de téléphone à l’aide du centre d’administration Microsoft Teams, comme décrit dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="20e03-139">It's easiest to set the phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="20e03-140">Vous pouvez également utiliser le `Set-CsOnlineApplicationInstance` commande pour attribuer un numéro de téléphone pour le compte de ressources après sa création initiale comme :</span><span class="sxs-lookup"><span data-stu-id="20e03-140">You can also use the `Set-CsOnlineApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity "CN={4f6c99fe-7999-4088-ac4d-e88e0b3d3820},OU=Redmond,DC=litwareinc,DC=com" -DisplayName Node1 -LineURI tel:+14255550100
```

<span data-ttu-id="20e03-141">Pour plus d’informations sur cette commande, voir [Set-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="20e03-141">See [Set-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="20e03-142">Gérer les paramètres de compte de ressource dans le centre d’administration de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="20e03-142">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="20e03-143">Pour gérer les paramètres de compte de ressource dans le centre d’administration de Microsoft Teams, accédez à **paramètres à l’échelle de la société**  > **comptes de ressources**, sélectionnez le compte de ressources que vous souhaitez modifier les paramètres pour, puis cliquez sur le bouton **Modifier** .</span><span class="sxs-lookup"><span data-stu-id="20e03-143">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="20e03-144">dans l’écran **Modifier le compte de la ressource** , vous ne pourrez pas modifier le :</span><span class="sxs-lookup"><span data-stu-id="20e03-144">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="20e03-145">**Nom d’affichage** pour le compte</span><span class="sxs-lookup"><span data-stu-id="20e03-145">**Display name** for the account</span></span>
- <span data-ttu-id="20e03-146">File d’attente des appels ou qui utilise le compte de standard automatique</span><span class="sxs-lookup"><span data-stu-id="20e03-146">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="20e03-147">Numéro de téléphone affectée au compte</span><span class="sxs-lookup"><span data-stu-id="20e03-147">Phone number assigned to the account</span></span>

<span data-ttu-id="20e03-148">Lorsque vous avez terminé, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="20e03-148">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="20e03-149">Informations connexes</span><span class="sxs-lookup"><span data-stu-id="20e03-149">Related Information</span></span>

<span data-ttu-id="20e03-150">Pour les implémentations qui sont hybride avec Skype pour Business Server :</span><span class="sxs-lookup"><span data-stu-id="20e03-150">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="20e03-151">Planifier les standards automatiques cloud</span><span class="sxs-lookup"><span data-stu-id="20e03-151">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="20e03-152">Configurer des standards automatiques cloud</span><span class="sxs-lookup"><span data-stu-id="20e03-152">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="20e03-153">Pour les implémentations d’équipes ou Skype pour Business Online :</span><span class="sxs-lookup"><span data-stu-id="20e03-153">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="20e03-154">Quels sont les standards automatiques du système téléphonique ?</span><span class="sxs-lookup"><span data-stu-id="20e03-154">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="20e03-155">Configurer les standards automatiques du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="20e03-155">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="20e03-156">Exemple de petite entreprise : configurer un standard automatique</span><span class="sxs-lookup"><span data-stu-id="20e03-156">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="20e03-157">Créer une file d’attente d’appels de système téléphonique</span><span class="sxs-lookup"><span data-stu-id="20e03-157">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="20e03-158">Nouvelle CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="20e03-158">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="20e03-159">Nouvelle CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="20e03-159">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
