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
description: En savoir plus sur la gestion des comptes de ressource dans Microsoft Teams
ms.openlocfilehash: 055e419e5a82233676e5b66857589216b4dbca6d
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517231"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="c8e41-103">Gérer les comptes de ressources dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8e41-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="c8e41-104">Un compte de ressource est également appelée un objet utilisateur désactivé dans Azure Active Directory et peut être utilisé pour représenter les ressources en général.</span><span class="sxs-lookup"><span data-stu-id="c8e41-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="c8e41-105">Dans Exchange, il peut être utilisé pour représenter des salles de conférence, par exemple et les autoriser à un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="c8e41-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="c8e41-106">Un compte de ressource peut être hébergé dans Microsoft 365 ou sur site à l’aide de Skype pour Business server, et ces comptes sont créés à l’aide des commandes Powershell.</span><span class="sxs-lookup"><span data-stu-id="c8e41-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="c8e41-107">Dans Microsoft Teams ou Skype pour Business en ligne, chaque file d’attente des appels ou auto attendant est nécessaire pour ont un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="c8e41-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="c8e41-108">Si un compte de ressource doit être un numéro de téléphone affecté dépendent de l’utilisation prévue de la file d’attente d’appel associé ou le standard automatique.</span><span class="sxs-lookup"><span data-stu-id="c8e41-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="c8e41-109">Consultez les articles sur les files d’attente de l’appel et qui sont liées au bas de cet article avant d’affecter un numéro de téléphone à un compte de ressource de standards automatiques.</span><span class="sxs-lookup"><span data-stu-id="c8e41-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e41-110">Cet article s’applique à Microsoft Teams et Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="c8e41-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="c8e41-111">Conditions préalables pour affecter un numéro de téléphone à un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="c8e41-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="c8e41-112">Mise en route il est important de garder à l’esprit quelques points :</span><span class="sxs-lookup"><span data-stu-id="c8e41-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="c8e41-113">Une file d’attente automatique standard ou un appel est nécessaire pour avoir un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="c8e41-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="c8e41-114">Pour plus d’informations sur les comptes de ressources, voir [Gérer les comptes de ressources dans les équipes](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="c8e41-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="c8e41-115">Si vous souhaitez affecter un numéro de routage Direct, vous devez acquérir et affecter les licences suivantes aux comptes ressource \(Office 365 entreprise E1, E3 ou E5, avec le module complémentaire système téléphonique\).</span><span class="sxs-lookup"><span data-stu-id="c8e41-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="c8e41-116">Si vous affectez un numéro de service Microsoft au lieu de cela, vous devez acquérir et affecter les licences suivantes à votre compte de ressource \(Office 365 entreprise E1, E3 ou E5, avec le module complémentaire système téléphonique et un Plan d’appel de\).</span><span class="sxs-lookup"><span data-stu-id="c8e41-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="c8e41-117">Microsoft fonctionne sur un modèle de licence approprié pour les applications telles que les standards automatiques de nuage et les files d’attente des appels, maintenant vous devez utiliser le modèle de gestion des licences utilisateur pour.</span><span class="sxs-lookup"><span data-stu-id="c8e41-117">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c8e41-118">Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou Office 365 appelant Plans.</span><span class="sxs-lookup"><span data-stu-id="c8e41-118">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="c8e41-119">Consultez les [licences d’affecter des équipes Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c8e41-119">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="c8e41-120">Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8e41-120">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c8e41-121">Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c8e41-121">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="c8e41-122">Vous pouvez affecter un numéro hybride de routage Direct à votre compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="c8e41-122">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="c8e41-123">Pour plus d’informations, voir [Planifier le routage Direct](direct-routing-plan.md) .</span><span class="sxs-lookup"><span data-stu-id="c8e41-123">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="c8e41-124">Pour les plans d’appel Microsoft, vous ne pouvez affecter payants et les numéros de téléphone gratuit service que vous avez obtenu dans le **Centre d’administration de Microsoft équipes** ou transféré à partir d’un autre fournisseur de services vers un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="c8e41-124">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="c8e41-125">Pour obtenir et utiliser des numéros gratuits service, vous devez configurer les crédits de Communications.</span><span class="sxs-lookup"><span data-stu-id="c8e41-125">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e41-126">Numéros de téléphone de l’utilisateur (abonné) ne peut pas être affectés à un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="c8e41-126">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="c8e41-127">Numéro payant service ou numéros de téléphone peuvent être utilisées.</span><span class="sxs-lookup"><span data-stu-id="c8e41-127">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="c8e41-128">Pour affecter un numéro de téléphone à un compte de ressource, vous devez obtenir ou transférer votre appel payant existant ou un service gratuit numéros.</span><span class="sxs-lookup"><span data-stu-id="c8e41-128">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="c8e41-129">Une fois que vous obtenez les numéros de téléphone gratuit service payant, ils s’affichent dans le **Centre d’administration de Microsoft équipes** > **vocale** > **numéros de téléphone**et la volonté de **type numérique** présent figurer en tant que **Service - gratuit**.</span><span class="sxs-lookup"><span data-stu-id="c8e41-129">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="c8e41-130">Pour obtenir vos numéros de service, voir les [numéros de téléphone de mise en service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) , ou si vous souhaitez transférer un numéro de service existant, voir les [numéros de téléphone transfert vers Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c8e41-130">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8e41-131">Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration Microsoft Teams pour obtenir les numéros de service.</span><span class="sxs-lookup"><span data-stu-id="c8e41-131">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="c8e41-132">Accédez à [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour voir comment le faire à partir de l’extérieur des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="c8e41-132">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="c8e41-133">Créer un compte de ressource dans le centre d’administration de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8e41-133">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="c8e41-134">Pour créer un compte de ressource dans le centre d’administration de Microsoft Teams, accédez à **paramètres à l’échelle de la société** > **comptes de ressources**, puis cliquez sur **+ Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c8e41-134">To create a resource account  in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, then click **+ Add**.</span></span> <span data-ttu-id="c8e41-135">Dans la fenêtre contextuelle, indiquez le nom complet et nom d’utilisateur pour le compte de ressources (le nom de domaine doit renseigner automatiquement) puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c8e41-135">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![compte de ressource](media/res-acct.png)

<span data-ttu-id="c8e41-137">Vous devez également appliquer une licence pour le compte de la ressource, comme indiqué dans [l’attribution de licences aux utilisateurs dans Office 365 pour entreprises](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="c8e41-137">You will also need to apply a license to the resource account, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span></span>

<span data-ttu-id="c8e41-138">Une fois que vous avez créé le compte de ressources et attribué la licence, vous pouvez cliquer sur **Attribuer/supprimer l’attribution** pour affecter un numéro de téléphone pour le compte de ressources, ou pour affecter le compte de ressources à une file d’attente standard ou un appel automatique.</span><span class="sxs-lookup"><span data-stu-id="c8e41-138">Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a phone number to the resource account, or to assign the resource account to an auto attendant or call queue.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="c8e41-139">Créer un compte de ressource dans Powershell</span><span class="sxs-lookup"><span data-stu-id="c8e41-139">Create a resource account in Powershell</span></span>

 <span data-ttu-id="c8e41-140">Vous souhaite créer un compte de ressource en exécutant l’applet de commande Powershell approprié selon vos besoins (pour un ou plusieurs comptes de ressources), nommez chacune d’elles et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="c8e41-140">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="c8e41-141">Il n’existe actuellement aucune option pour la création d’un compte de ressource dans le centre d’administration Microsoft Teams, mais vous pouvez modifier les numéros de téléphone et modifier les appels en file d’attente ou automatique attendant affectations d’un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="c8e41-141">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="c8e41-142">Selon que votre numéro de téléphone est situé en ligne ou sur site, vous devez vous connecter à l’invite de Powershell approprié avec des privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="c8e41-142">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="c8e41-143">Implémentations hybride (numéros de numéros hébergés sur routage Direct, OPCH et CCE) utilise [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) pour créer un compte de ressource qui est hébergé sur site.</span><span class="sxs-lookup"><span data-stu-id="c8e41-143">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="c8e41-144">En ligne uniquement implémentations utilise [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) pour avoir un compte de ressource qui est hébergé en ligne.</span><span class="sxs-lookup"><span data-stu-id="c8e41-144">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="c8e41-145">Voici un exemple d’environnement en ligne de création de compte de la ressource avec un standard automatique ApplicationID.</span><span class="sxs-lookup"><span data-stu-id="c8e41-145">The following is an online environment example of creating resource account with an auto attendant ApplicationID.</span></span> <span data-ttu-id="c8e41-146">Pour une file d’attente de l’appel, vous pouvez utiliser le suivant ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07 :</span><span class="sxs-lookup"><span data-stu-id="c8e41-146">For a call queue, you can use the following ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

<span data-ttu-id="c8e41-147">Pour plus d’informations sur cette commande, voir [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c8e41-147">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e41-148">Il est plus facile de définir le numéro de téléphone en ligne à l’aide du centre d’administration Microsoft Teams, comme décrit dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="c8e41-148">It's easiest to set the online phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="c8e41-149">Vous pouvez également utiliser le `Set-CsOnlineVoiceApplicationInstance` commande pour attribuer un numéro de téléphone pour le compte de ressources après sa création initiale comme :</span><span class="sxs-lookup"><span data-stu-id="c8e41-149">You can also use the `Set-CsOnlineVoiceApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="c8e41-150">Si vous n’appliquez pas une licence lors de la création du compte de ressource, l’affectation de numéros de téléphone échouera.</span><span class="sxs-lookup"><span data-stu-id="c8e41-150">If you do not apply a license while creating the resource account the phone number assignment will fail.</span></span> 

<span data-ttu-id="c8e41-151">Pour plus d’informations sur cette commande, voir [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c8e41-151">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>



## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="c8e41-152">Gérer les paramètres de compte de ressource dans le centre d’administration de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8e41-152">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="c8e41-153">Pour gérer les paramètres de compte de ressource dans le centre d’administration de Microsoft Teams, accédez à **paramètres à l’échelle de la société**  > **comptes de ressources**, sélectionnez le compte de ressources que vous souhaitez modifier les paramètres pour, puis cliquez sur le bouton **Modifier** .</span><span class="sxs-lookup"><span data-stu-id="c8e41-153">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="c8e41-154">dans l’écran **Modifier le compte de la ressource** , vous ne pourrez pas modifier le :</span><span class="sxs-lookup"><span data-stu-id="c8e41-154">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="c8e41-155">**Nom d’affichage** pour le compte</span><span class="sxs-lookup"><span data-stu-id="c8e41-155">**Display name** for the account</span></span>
- <span data-ttu-id="c8e41-156">File d’attente des appels ou qui utilise le compte de standard automatique</span><span class="sxs-lookup"><span data-stu-id="c8e41-156">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="c8e41-157">Numéro de téléphone affectée au compte</span><span class="sxs-lookup"><span data-stu-id="c8e41-157">Phone number assigned to the account</span></span>

<span data-ttu-id="c8e41-158">Lorsque vous avez terminé, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c8e41-158">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="c8e41-159">Informations connexes</span><span class="sxs-lookup"><span data-stu-id="c8e41-159">Related Information</span></span>

<span data-ttu-id="c8e41-160">Pour les implémentations qui sont hybride avec Skype pour Business Server :</span><span class="sxs-lookup"><span data-stu-id="c8e41-160">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="c8e41-161">Planifier les standards automatiques cloud</span><span class="sxs-lookup"><span data-stu-id="c8e41-161">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="c8e41-162">Configurer des standards automatiques cloud</span><span class="sxs-lookup"><span data-stu-id="c8e41-162">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="c8e41-163">Pour les implémentations d’équipes ou Skype pour Business Online :</span><span class="sxs-lookup"><span data-stu-id="c8e41-163">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="c8e41-164">Quels sont les standards automatiques du système téléphonique ?</span><span class="sxs-lookup"><span data-stu-id="c8e41-164">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="c8e41-165">Configurer les standards automatiques du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="c8e41-165">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="c8e41-166">Exemple de petite entreprise : configurer un standard automatique</span><span class="sxs-lookup"><span data-stu-id="c8e41-166">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="c8e41-167">Créer une file d’attente d’appels de système téléphonique</span><span class="sxs-lookup"><span data-stu-id="c8e41-167">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="c8e41-168">Nouvelle CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="c8e41-168">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="c8e41-169">Nouvelle CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c8e41-169">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
