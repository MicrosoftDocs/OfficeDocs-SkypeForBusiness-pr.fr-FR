---
title: Gérer les comptes de ressource dans Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: Dans cet article, vous allez découvrir comment créer, modifier et gérer des comptes de ressources dans Microsoft Teams.
ms.openlocfilehash: b47e00323129211f657ec1dafc4e62a7cd6e4321
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868611"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="f9e37-103">Gérer les comptes de ressources dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9e37-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="f9e37-104">Un compte de ressource est également connu sous le nom d' *objet utilisateur désactivé* dans Azure ad et peut être utilisé pour représenter des ressources en général.</span><span class="sxs-lookup"><span data-stu-id="f9e37-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="f9e37-105">Dans Exchange, il peut être utilisé pour représenter des salles de conférence, par exemple, et leur permettre d’avoir un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="f9e37-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="f9e37-106">Un compte de ressource peut être hébergé dans Microsoft 365 ou sur site à l’aide de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f9e37-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="f9e37-107">Dans Microsoft teams ou Skype entreprise Online, chaque file d’attente d’appels du système téléphonique ou le standard automatique est requis pour disposer d’au moins un compte de ressources associé.</span><span class="sxs-lookup"><span data-stu-id="f9e37-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="f9e37-108">La nécessité pour un compte de ressources d’avoir besoin d’un numéro de téléphone dépend de la manière dont vous souhaitez utiliser la file d’attente d’appels ou le standard automatique associé, comme illustré dans le schéma suivant.</span><span class="sxs-lookup"><span data-stu-id="f9e37-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="f9e37-109">Vous pouvez également vous référer aux articles sur les files d’attente d’appels et aux standards automatiques liés au bas de cet article avant d’affecter un numéro de téléphone à un compte de ressources.</span><span class="sxs-lookup"><span data-stu-id="f9e37-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![exemple de comptes de ressources et de licences utilisateur](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="f9e37-111">Cet article s’applique à Microsoft teams et à Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="f9e37-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="f9e37-112">Pour les comptes de ressources hébergés sur Skype entreprise Server 2019, voir [configurer les comptes de ressources](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="f9e37-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a><span data-ttu-id="f9e37-113">Affectation d’un numéro de téléphone à la file d’attente d’appels d’un système téléphonique</span><span class="sxs-lookup"><span data-stu-id="f9e37-113">Assign a phone number to a Phone System call queue</span></span>

<span data-ttu-id="f9e37-114">Si votre organisation utilise déjà au moins une licence de système téléphonique, vous pouvez attribuer un numéro de téléphone à la file d’attente d’appels du système téléphonique le processus est le suivant :</span><span class="sxs-lookup"><span data-stu-id="f9e37-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="f9e37-115">Obtenez un numéro de service.</span><span class="sxs-lookup"><span data-stu-id="f9e37-115">Obtain a service number.</span></span>
2. <span data-ttu-id="f9e37-116">Procurez-vous un système téléphonique [gratuit ou une licence de](teams-add-on-licensing/virtual-user.md) système téléphonique payant à utiliser avec le compte de ressources ou une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="f9e37-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="f9e37-117">Créez le compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="f9e37-117">Create the resource account.</span></span> <span data-ttu-id="f9e37-118">Un standard automatique ou une file d’attente d’appels doivent être associés à un compte de ressources associé.</span><span class="sxs-lookup"><span data-stu-id="f9e37-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="f9e37-119">Attribuez le système téléphonique ou un système téléphonique-licence utilisateur virtuel au compte de ressources.</span><span class="sxs-lookup"><span data-stu-id="f9e37-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="f9e37-120">Affectez un numéro de téléphone de service au compte de ressource auquel vous venez d’affecter des licences.</span><span class="sxs-lookup"><span data-stu-id="f9e37-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="f9e37-121">Créer une file d’attente des appels du système téléphonique ou un standard automatique</span><span class="sxs-lookup"><span data-stu-id="f9e37-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="f9e37-122">Liez le compte de ressource avec une file d’attente d’appels ou un standard automatique.</span><span class="sxs-lookup"><span data-stu-id="f9e37-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="f9e37-123">Si le standard automatique ou la file d’attente d’appels est imbriquée sous un standard automatique de niveau supérieur, le compte de ressources associé a uniquement besoin d’un numéro de téléphone si vous voulez que plusieurs points d’entrée soient présents dans la structure des standards automatiques et des files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f9e37-123">If the auto attendant or call queue is nested under a top-level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="f9e37-124">Pour rediriger les appels vers des utilisateurs de votre organisation qui sont hébergés en ligne, ils doivent disposer d’une licence de **système téléphonique** et être activés pour Enterprise Voice ou disposer d’offres Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9e37-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="f9e37-125">Voir [affecter des licences de compléments Microsoft teams](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="f9e37-125">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="f9e37-126">Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9e37-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="f9e37-127">Par exemple, exécutez :`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="f9e37-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="f9e37-128">Afin d’éviter les problèmes liés au compte de ressources, procédez comme suit dans cet ordre.</span><span class="sxs-lookup"><span data-stu-id="f9e37-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="f9e37-129">Si la file d’attente d’appels du système téléphonique ou le standard automatique que vous créez est imbriqué et qu’il n’est pas nécessaire de composer un numéro de téléphone, le processus est le suivant :</span><span class="sxs-lookup"><span data-stu-id="f9e37-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="f9e37-130">Créer le compte de ressources</span><span class="sxs-lookup"><span data-stu-id="f9e37-130">Create the resource account</span></span>
2. <span data-ttu-id="f9e37-131">Créer une file d’attente des appels du système téléphonique ou un standard automatique</span><span class="sxs-lookup"><span data-stu-id="f9e37-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="f9e37-132">Associez le compte de ressource à une file d’attente d’appels du système téléphonique ou un standard automatique</span><span class="sxs-lookup"><span data-stu-id="f9e37-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="f9e37-133">Créer un compte de ressources avec un numéro de téléphone</span><span class="sxs-lookup"><span data-stu-id="f9e37-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="f9e37-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="f9e37-134"><a name="phonenumber"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9e37-135">Un numéro de téléphone n’est pas attribué directement au standard automatique ou à la file d’attente d’appels, mais plutôt au compte de ressources associé au standard automatique ou à la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f9e37-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="f9e37-136">Un standard automatique ou une file d’attente d’appels de niveau supérieur exige qu’un numéro de téléphone soit lié à son standard automatique.</span><span class="sxs-lookup"><span data-stu-id="f9e37-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="f9e37-137">Pour créer un compte de ressource qui utilise un numéro de téléphone, le processus est le suivant :</span><span class="sxs-lookup"><span data-stu-id="f9e37-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="f9e37-138">Transférez ou obtenez un numéro de service gratuit ou payant.</span><span class="sxs-lookup"><span data-stu-id="f9e37-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="f9e37-139">Le numéro ne peut pas être attribué à un autre service vocal ou à un autre compte de ressources.</span><span class="sxs-lookup"><span data-stu-id="f9e37-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="f9e37-140">Avant d’affecter un numéro de téléphone à un compte de ressources, vous devez obtenir ou porter vos numéros de service gratuits ou payants existants.</span><span class="sxs-lookup"><span data-stu-id="f9e37-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="f9e37-141">Une fois que vous avez obtenu les numéros de téléphone de service gratuits ou payants, ils s’affichent dans les numéros de téléphone vocaux du **Centre d’administration Microsoft teams**  >  **Voice**  >  **Phone numbers**et le **type de numéro** est répertorié en tant que **service-** gratuit.</span><span class="sxs-lookup"><span data-stu-id="f9e37-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="f9e37-142">Pour obtenir vos numéros de service, reportez-vous à la rubrique [obtention de numéros de service](getting-service-phone-numbers.md) ou pour transférer un numéro de service existant, reportez-vous à la section transférer des [numéros de téléphone vers teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="f9e37-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="f9e37-143">Si vous affectez un numéro de téléphone à un compte de ressources, vous pouvez désormais utiliser la licence utilisateur virtuel du système téléphonique sans frais.</span><span class="sxs-lookup"><span data-stu-id="f9e37-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="f9e37-144">Cela fournit des fonctionnalités de système téléphonique aux numéros de téléphone au niveau de l’organisation, et vous permet de créer des capacités de mise en file d’attente et de standard automatique.</span><span class="sxs-lookup"><span data-stu-id="f9e37-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="f9e37-145">Obtenez une licence d’utilisateur virtuel de système téléphonique ou une licence de système téléphonique classique.</span><span class="sxs-lookup"><span data-stu-id="f9e37-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="f9e37-146">Pour obtenir la licence de l’utilisateur virtuel, dans le centre d’administration 365 de **Billing**Microsoft, accédez à  >  la section abonnements au composant additionnel**services d’achat**de facturation  >  **Add-on subscriptions** et faites défiler jusqu’à la fin, vous verrez la licence « système téléphonique-utilisateur virtuel ».</span><span class="sxs-lookup"><span data-stu-id="f9e37-146">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="f9e37-147">Sélectionnez **acheter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="f9e37-147">Select **Buy now**.</span></span> <span data-ttu-id="f9e37-148">Il y a un coût zéro, mais vous devez toujours suivre ces étapes pour acquérir la licence.</span><span class="sxs-lookup"><span data-stu-id="f9e37-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="f9e37-149">Créer un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="f9e37-149">Create a new resource account.</span></span> <span data-ttu-id="f9e37-150">Pour plus d’affichage, voir [créer un compte de ressources dans le centre d’administration Microsoft teams](#create-a-resource-account-in-the-microsoft-teams-admin-center) ou [créer un compte de ressources dans PowerShell](#create-a-resource-account-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="f9e37-150">See [Create a resource account in the Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell).</span></span>
4. <span data-ttu-id="f9e37-151">Attribution d’un système téléphonique- [licence d’utilisateur virtuel](teams-add-on-licensing/virtual-user.md) ou de système téléphonique au compte de ressources.</span><span class="sxs-lookup"><span data-stu-id="f9e37-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="f9e37-152">Voir [affecter des licences de compléments Microsoft teams](teams-add-on-licensing/assign-teams-add-on-licenses.md) et [attribuer des licences aux utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="f9e37-152">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) and [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
5. <span data-ttu-id="f9e37-153">Attribuez le numéro de service au compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="f9e37-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="f9e37-154">Voir [affecter/retirer des numéros de téléphone et des services](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="f9e37-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="f9e37-155">Configurez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f9e37-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="f9e37-156">Standard automatique Cloud</span><span class="sxs-lookup"><span data-stu-id="f9e37-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="f9e37-157">File d’attente d’appels Cloud</span><span class="sxs-lookup"><span data-stu-id="f9e37-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="f9e37-158">Liez le compte de ressources au standard automatique ou à la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f9e37-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="f9e37-159">Voir [affectation/désaffectation de numéros de téléphone et services](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="f9e37-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="f9e37-160">Lorsque vous créez un compte de ressources lors de la création d’un standard automatique, les licences sont appliquées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f9e37-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="f9e37-161">Créer un compte de ressources sans numéro de téléphone</span><span class="sxs-lookup"><span data-stu-id="f9e37-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="f9e37-162">Un standard automatique ou une file d’attente d’appels imbriqués nécessiteront un compte de ressources, mais dans de nombreux cas, le compte de ressource correspondant n’aura pas besoin d’un numéro de téléphone et de la gestion des licences nécessaires à la prise en charge d’un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="f9e37-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="f9e37-163">Pour créer un compte de ressources sans numéro de téléphone, vous devez effectuer les tâches suivantes dans l’ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="f9e37-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="f9e37-164">Créer un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="f9e37-164">Create a new resource account.</span></span> <span data-ttu-id="f9e37-165">Pour plus d’affichage, voir [créer un compte de ressources dans le centre d’administration Microsoft teams](#create-a-resource-account-in-the-microsoft-teams-admin-center) ou [créer un compte de ressources dans PowerShell](#create-a-resource-account-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="f9e37-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell).</span></span>

2. <span data-ttu-id="f9e37-166">Configurez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f9e37-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="f9e37-167">Standard automatique Cloud</span><span class="sxs-lookup"><span data-stu-id="f9e37-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="f9e37-168">File d’attente d’appels Cloud</span><span class="sxs-lookup"><span data-stu-id="f9e37-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
   
3. <span data-ttu-id="f9e37-169">Affectez le compte de ressource à la file d’attente d’appels ou au standard automatique.</span><span class="sxs-lookup"><span data-stu-id="f9e37-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="f9e37-170">Voir [affecter/retirer des numéros de téléphone et des services](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="f9e37-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>


## <a name="create-a-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="f9e37-171">Créer un compte de ressources dans le centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="f9e37-171">Create a resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="f9e37-172">Après avoir acheté une licence de système téléphonique, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à comptes de ressources de paramètres à l’échelle de l' **organisation**  >  **Resource accounts**.</span><span class="sxs-lookup"><span data-stu-id="f9e37-172">After you've bought a Phone System license, in the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**.</span></span>

![Capture d’écran de la page comptes de ressources](media/r-a-master.png)

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/teamscallout1.png)

<span data-ttu-id="f9e37-175">Pour créer un compte de ressource, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f9e37-175">To create a new resource account, click **Add**.</span></span> <span data-ttu-id="f9e37-176">Dans le **volet ajouter un compte de ressources** , spécifiez le nom d' **affichage**, le nom **d’utilisateur** (le nom de domaine doit remplir automatiquement) et le **type de compte de ressources** pour le compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="f9e37-176">In the **Add resource account** pane, fill out **Display name**, **Username** (the domain name should populate automatically), and **Resource account type** for the resource account.</span></span> <span data-ttu-id="f9e37-177">Le type de compte de ressource peut être de type **standard automatique** ou **file d’attente d’appels**, en fonction de l’application que vous voulez associer au compte de ressources.</span><span class="sxs-lookup"><span data-stu-id="f9e37-177">The resource account type can be either **Auto attendant** or **Call queue**, depending on the app you intend to associate to the resource account.</span></span> <span data-ttu-id="f9e37-178">Lorsque vous êtes prêt, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f9e37-178">When you're ready, click **Save**.</span></span>

![Capture d’écran des options de nouveau compte de ressources](media/res-acct.png)

<span data-ttu-id="f9e37-180">Appliquez ensuite une licence au compte de ressources dans le centre d’administration Microsoft 365, comme décrit dans la section [attribuer des licences aux utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="f9e37-180">Next, apply a license to the resource account in the Microsoft 365 Admin center, as described in [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="edit-resource-account"></a><span data-ttu-id="f9e37-181">Modifier le compte de ressources</span><span class="sxs-lookup"><span data-stu-id="f9e37-181">Edit resource account</span></span> 

<span data-ttu-id="f9e37-182">![Icône du numéro 2, qui référence une légende dans la capture d’écran précédente, ](media/teamscallout2.png) vous pouvez modifier le **nom d’affichage** du compte de ressources et le type de compte de **ressources** à l’aide de l’option **modifier** .</span><span class="sxs-lookup"><span data-stu-id="f9e37-182">![Icon of the number 2, referencing a callout in the previous screenshot](media/teamscallout2.png) You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="f9e37-183">Lorsque vous avez fin, cliquez sur **Enregistrer** .</span><span class="sxs-lookup"><span data-stu-id="f9e37-183">Click **Save** when you are done.</span></span>

![Capture d’écran de l’option modifier le compte de ressources](media/r-a-edit.png)

<span data-ttu-id="f9e37-185"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="f9e37-185"><a name="phonenumber"> </a></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="f9e37-186">Attribution/désaffectation des numéros de téléphone et services</span><span class="sxs-lookup"><span data-stu-id="f9e37-186">Assign/unassign phone numbers and services</span></span>

<span data-ttu-id="f9e37-187">![Icône du numéro 3, qui référence une légende dans la capture d’écran précédente ](media/teamscallout3.png) une fois que vous avez créé le compte de ressources et attribué la licence, vous pouvez cliquer sur **affecter/annuler** pour attribuer un numéro de service au compte de ressource, définir le type de numéro de téléphone ou affecter le compte de ressource à un standard automatique ou une file d’attente d’appels existante.</span><span class="sxs-lookup"><span data-stu-id="f9e37-187">![Icon of the number 3, referencing a callout in the previous screenshot](media/teamscallout3.png) After you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, set the phone number type, or assign the resource account to a specific auto attendant or call queue that already exists.</span></span> <span data-ttu-id="f9e37-188">L’attribution d’un numéro d’acheminement direct peut être réalisé à l’aide d’une cmdlet uniquement.</span><span class="sxs-lookup"><span data-stu-id="f9e37-188">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="f9e37-189">Si vous n’avez pas encore créé la file d’attente d’appels ou le standard automatique que vous allez associer au compte de ressources, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="f9e37-189">If you haven't yet created the  call queue or auto attendant you will associate to the resource account, leave that field blank.</span></span> <span data-ttu-id="f9e37-190">Vous pouvez lier le compte de ressources lors de sa création.</span><span class="sxs-lookup"><span data-stu-id="f9e37-190">You can link the resource account while you create it.</span></span> <span data-ttu-id="f9e37-191">Lorsque vous avez fin, cliquez sur **Enregistrer** .</span><span class="sxs-lookup"><span data-stu-id="f9e37-191">Click **Save** when you are done.</span></span>

<span data-ttu-id="f9e37-192">Les options disponibles pour le **type de numéro de téléphone** sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="f9e37-192">Options for the **Phone number type** are:</span></span>

- <span data-ttu-id="f9e37-193">Aucun</span><span class="sxs-lookup"><span data-stu-id="f9e37-193">None</span></span>
- <span data-ttu-id="f9e37-194">Online</span><span class="sxs-lookup"><span data-stu-id="f9e37-194">Online</span></span>
- <span data-ttu-id="f9e37-195">Numéro gratuit</span><span class="sxs-lookup"><span data-stu-id="f9e37-195">Toll-free</span></span>
- <span data-ttu-id="f9e37-196">Sur site</span><span class="sxs-lookup"><span data-stu-id="f9e37-196">On-premises</span></span>

![Capture d’écran des options d’attribution/de désaffectation](media/r-a-assign.png)

<span data-ttu-id="f9e37-198">Pour affecter un routage direct ou un numéro hybride à un compte de ressource, vous devez utiliser PowerShell, reportez-vous à la section suivante.</span><span class="sxs-lookup"><span data-stu-id="f9e37-198">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9e37-199">Si votre compte de ressource ne possède pas de licence valide, un échec de vérification interne entraîne un échec lorsque vous tentez d’affecter le numéro de téléphone au compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="f9e37-199">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="f9e37-200">Vous ne pourrez pas affecter le numéro ou associer le compte de ressources à une file d’attente d’appels ou un standard automatique.</span><span class="sxs-lookup"><span data-stu-id="f9e37-200">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9e37-201">Un numéro de téléphone n’est pas attribué directement au standard automatique ou à la file d’attente d’appels, mais plutôt au compte de ressources associé au standard automatique ou à la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f9e37-201">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="f9e37-202">Modifier un compte de ressource existant pour utiliser une licence utilisateur virtuel</span><span class="sxs-lookup"><span data-stu-id="f9e37-202">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="f9e37-203">Si vous décidez de basculer entre les licences sur votre compte de ressources existant d’une licence de système téléphonique vers une licence utilisateur virtuel, vous devez acquérir la licence utilisateur virtuel gratuite, puis suivre les étapes du centre d’administration 365 Microsoft pour [déplacer des utilisateurs vers un autre abonnement](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="f9e37-203">If you decide to switch the licenses on your existing resource account from a Phone System license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="f9e37-204">Supprimez toujours une licence de système téléphonique complet et attribuez-la à la licence utilisateur virtuel dans la même activité de licence.</span><span class="sxs-lookup"><span data-stu-id="f9e37-204">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="f9e37-205">Si vous supprimez l’ancienne licence, enregistrez les modifications du compte, ajoutez la nouvelle licence, puis enregistrez de nouveau les paramètres du compte, le compte de ressources risque de ne plus fonctionner comme prévu.</span><span class="sxs-lookup"><span data-stu-id="f9e37-205">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="f9e37-206">Si tel est le cas, nous vous recommandons de créer un compte de ressources pour la licence d’utilisateur virtuel et de supprimer le compte de ressource endommagé.</span><span class="sxs-lookup"><span data-stu-id="f9e37-206">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="f9e37-207">Créer un compte de ressources dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9e37-207">Create a resource account in Powershell</span></span>

<span data-ttu-id="f9e37-208">Selon que votre compte de ressources se trouve en ligne ou sur Skype entreprise Server 2019, vous devez vous connecter à l’invite PowerShell appropriée avec les privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f9e37-208">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="f9e37-209">Les exemples de cmdlets PowerShell suivants illustrent la création d’un compte de ressource hébergé en ligne à l’aide [de New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f9e37-209">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="f9e37-210">Pour les comptes de ressources hébergés sur Skype entreprise Server 2019 qui peuvent être utilisés avec les files d’attente d’appels Cloud et les standards automatiques Cloud, voir [planifier des files d’attente d’appels Cloud](/SkypeforBusiness/hybrid/plan-call-queue) ou [planifier des standards automatiques Cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="f9e37-210">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="f9e37-211">Les implémentations hybrides (numéros d’hébergement sur le routage direct) sont configurées à l’aide de l’applet de nouvelle applet de [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) sur un serveur Skype entreprise Server 2019 local.</span><span class="sxs-lookup"><span data-stu-id="f9e37-211">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="f9e37-212">L’ID d’application que vous devez utiliser lors de la création des instances d’application est le suivant :</span><span class="sxs-lookup"><span data-stu-id="f9e37-212">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="f9e37-213">**Standard automatique :** ce933385-9390-45D1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="f9e37-213">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="f9e37-214">**File d’attente des appels :** 11cd3e2e-FCCB-42AD-AD00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="f9e37-214">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="f9e37-215">Si vous souhaitez que la file d’attente d’appels ou le standard automatique puissent être recherchés par les utilisateurs de Skype entreprise Server 2019, vous devez créer vos comptes de ressources dans Skype entreprise Server 2019, car les comptes de ressources en ligne ne sont pas synchronisés avec Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f9e37-215">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="f9e37-216">Lorsque les enregistrements DNS SRV pour sipfederationtls sont résolus en Skype entreprise Server 2019, les comptes de ressources **doivent** être créés dans Skype entreprise Server 2019 à l’aide de marketing Management Shell et synchronisés avec Azure AD en ligne.</span><span class="sxs-lookup"><span data-stu-id="f9e37-216">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="f9e37-217">Pour créer un compte de ressources en ligne à utiliser avec un standard automatique, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f9e37-217">To create a resource account online for use with an auto attendant, use the following command:</span></span>

    ``` Powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId "ce933385-9390-45d1-9512-c8d228074e07" -DisplayName "Resource account 1"
    ```

2. <span data-ttu-id="f9e37-218">Vous ne serez pas en mesure d’utiliser le compte de ressource tant que vous n’avez pas appliqué de licence.</span><span class="sxs-lookup"><span data-stu-id="f9e37-218">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="f9e37-219">Pour plus d’informations sur l’application d’une licence à un compte dans le centre d’administration 365 Microsoft, voir[attribuer des licences à des utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) et [attribuer des licences Skype entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="f9e37-219">To learn how to apply a license to an account in the Microsoft 365 admin center, see[Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="f9e37-220">Facultatif Une fois la licence correcte appliquée au compte de ressources, vous pouvez affecter un numéro de téléphone au compte de ressource, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f9e37-220">(Optional) After the correct license is applied to the resource account, you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="f9e37-221">Tous les comptes de ressources ne nécessitent pas de numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="f9e37-221">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="f9e37-222">Si vous n’avez pas appliqué de licence au compte de ressource, le numéro de téléphone ne peut pas être attribué.</span><span class="sxs-lookup"><span data-stu-id="f9e37-222">If you didn't apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="f9e37-223">Pour plus d’informations sur cette commande [, voir Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f9e37-223">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f9e37-224">Il est plus facile de définir le numéro de téléphone en ligne à l’aide du centre d’administration de Microsoft Teams, comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="f9e37-224">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="f9e37-225">Pour attribuer un numéro de téléphone de routage direct à un compte de ressources (hébergé dans Microsoft teams ou Skype entreprise Server 2019), utilisez l’applet de commande suivante pour Skype entreprise Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="f9e37-225">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="f9e37-226">Gérer les paramètres de compte de ressources dans le centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="f9e37-226">Manage resource account settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="f9e37-227">Pour gérer les paramètres de compte de ressources dans le centre d’administration de Microsoft Teams, accédez à comptes de ressources de paramètres à l’échelle de l' **organisation**  >  **Resource accounts**, sélectionnez le compte de ressources dont vous avez besoin pour modifier les paramètres, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="f9e37-227">To manage resource account settings in Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click **Edit**.</span></span> <span data-ttu-id="f9e37-228">Dans le volet **modifier le compte de ressources** , vous pouvez modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f9e37-228">On the **Edit resource account** pane, you can change these settings:</span></span>

- <span data-ttu-id="f9e37-229">**Nom d’affichage** du compte</span><span class="sxs-lookup"><span data-stu-id="f9e37-229">**Display name** for the account</span></span>
- <span data-ttu-id="f9e37-230">File d’attente d’appels ou standard automatique qui utilise le compte</span><span class="sxs-lookup"><span data-stu-id="f9e37-230">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="f9e37-231">Numéro de téléphone attribué au compte</span><span class="sxs-lookup"><span data-stu-id="f9e37-231">Phone number assigned to the account</span></span>

<span data-ttu-id="f9e37-232">Lorsque vous avez terminé, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f9e37-232">When finished, click **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="f9e37-233">Supprimer un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="f9e37-233">Delete a resource account</span></span>

<span data-ttu-id="f9e37-234">Vérifiez que vous avez dissocié le numéro de téléphone du compte de ressources avant de le supprimer, afin d’éviter de rester bloqué dans le mode en attente.</span><span class="sxs-lookup"><span data-stu-id="f9e37-234">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="f9e37-235">Pour ce faire, vous pouvez utiliser l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f9e37-235">You can do that using the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="f9e37-236">Après quoi, vous pouvez supprimer le compte de ressources dans le centre d’administration 365 Microsoft, sous l’onglet utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f9e37-236">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="f9e37-237">Pour dissocier un numéro de téléphone de routage direct du compte de ressources, utilisez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f9e37-237">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="f9e37-238">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="f9e37-238">Troubleshooting</span></span>

### <a name="you-dont-see-the-phone-number-assigned-to-the-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="f9e37-239">Le numéro de téléphone attribué au compte de ressource n’apparaît pas dans le centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="f9e37-239">You don't see the phone number assigned to the resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="f9e37-240">Si vous ne voyez pas le numéro de téléphone attribué au compte de ressources dans le centre d’administration Microsoft teams et que vous ne pouvez pas attribuer le numéro à partir de cet emplacement, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="f9e37-240">If you don't see the phone number assigned to the resource account in the Microsoft Teams admin center and you are unable to assign the number from there, check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="f9e37-241">Si l’attribut Service affiche le point de terminaison d’une application Skype entreprise, exécutez l’applet de demande ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="f9e37-241">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below:</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="f9e37-242">Actualisez la page Web du centre d’administration teams après avoir exécuté le cmldet et vous devriez pouvoir affecter le numéro correctement.</span><span class="sxs-lookup"><span data-stu-id="f9e37-242">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

### <a name="you-get-a-we-cant-use-this-resource-account-for-services-error-message"></a><span data-ttu-id="f9e37-243">Vous obtenez un « nous ne pouvons pas utiliser ce compte de ressources pour les services ».</span><span class="sxs-lookup"><span data-stu-id="f9e37-243">You get a "We can't use this resource account for services."</span></span> <span data-ttu-id="f9e37-244">message d’erreur</span><span class="sxs-lookup"><span data-stu-id="f9e37-244">error message</span></span>

<span data-ttu-id="f9e37-245"><a name="blocksignin"> </a></span><span class="sxs-lookup"><span data-stu-id="f9e37-245"><a name="blocksignin"> </a></span></span>

<span data-ttu-id="f9e37-246">Vous recevez le message d’erreur suivant lorsque vous essayez d’utiliser un compte de ressources :</span><span class="sxs-lookup"><span data-stu-id="f9e37-246">You get the following error message when you try to use a resource account:</span></span>

<span data-ttu-id="f9e37-247">«Nous ne pouvons pas utiliser ce compte de ressources pour les services.</span><span class="sxs-lookup"><span data-stu-id="f9e37-247">"We can't use this resource account for services.</span></span> <span data-ttu-id="f9e37-248">Le compte de ressource doit être désactivé et empêché de se connecter.</span><span class="sxs-lookup"><span data-stu-id="f9e37-248">The resource account must be DISABLED and BLOCKED from signing in.</span></span> <span data-ttu-id="f9e37-249">Vous devez bloquer les connexions pour ce compte de ressources dans la page utilisateurs du centre d’administration 365 Microsoft.»</span><span class="sxs-lookup"><span data-stu-id="f9e37-249">You must BLOCK sign-ins for this resource account on the Users page in the Microsoft 365 admin center."</span></span>

<span data-ttu-id="f9e37-250">Par défaut, lorsque vous créez un compte de ressource, il est désactivé et la connexion est bloquée pour le compte.</span><span class="sxs-lookup"><span data-stu-id="f9e37-250">When you create a resource account, by default, it's disabled and sign in is blocked for the account.</span></span> <span data-ttu-id="f9e37-251">Vous ne devez pas modifier ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="f9e37-251">These settings shouldn't be changed.</span></span> <span data-ttu-id="f9e37-252">Pour résoudre ce problème, bloquez le compte de ressources pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="f9e37-252">To resolve this error message, block the resource account from signing in.</span></span> <span data-ttu-id="f9e37-253">Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="f9e37-253">To do this:</span></span>

1. <span data-ttu-id="f9e37-254">Dans le centre d’administration Microsoft 365, accédez à **utilisateurs**, recherchez, puis sélectionnez le compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="f9e37-254">In the Microsoft 365 admin center, go to **Users**, search for, and then select the resource account.</span></span>
2. <span data-ttu-id="f9e37-255">Dans la partie supérieure du volet sous le nom d’affichage, cliquez sur **bloquer cet utilisateur ?**, activez la case à cocher **empêcher cet utilisateur de vous connecter** , puis cliquez sur **enregistrer les modifications**.</span><span class="sxs-lookup"><span data-stu-id="f9e37-255">At the top of the pane under the display name, click **Block this user?**, select the **Block this user from signing in** check box, and then select **Save changes**.</span></span>

   ![Capture d’écran de l’option Bloquer cet utilisateur](media/res-acct-block.png)

    <span data-ttu-id="f9e37-257">Après cela, vous verrez « connexion bloquée » sous le nom d’affichage.</span><span class="sxs-lookup"><span data-stu-id="f9e37-257">After you do this, you'll see "Sign in blocked" under the display name.</span></span>

      ![Capture d’écran du message de connexion bloqué](media/res-acct-sign-in-blocked.png)

## <a name="related-information"></a><span data-ttu-id="f9e37-259">Informations connexes</span><span class="sxs-lookup"><span data-stu-id="f9e37-259">Related Information</span></span>

<span data-ttu-id="f9e37-260">Pour les implémentations hybrides avec Skype entreprise Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f9e37-260">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="f9e37-261">Planifier les standards automatiques cloud</span><span class="sxs-lookup"><span data-stu-id="f9e37-261">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="f9e37-262">Planifier les files d’attente d’appels cloud</span><span class="sxs-lookup"><span data-stu-id="f9e37-262">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="f9e37-263">Configurer les comptes de ressources locaux</span><span class="sxs-lookup"><span data-stu-id="f9e37-263">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="f9e37-264">Pour les implémentations dans teams ou Skype entreprise Online :</span><span class="sxs-lookup"><span data-stu-id="f9e37-264">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="f9e37-265">Un standard Cloud automatique, qu’est-ce que c’est ?</span><span class="sxs-lookup"><span data-stu-id="f9e37-265">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="f9e37-266">Configurer un standard automatique dans le cloud</span><span class="sxs-lookup"><span data-stu-id="f9e37-266">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="f9e37-267">Exemple de petite entreprise : configurer un standard automatique</span><span class="sxs-lookup"><span data-stu-id="f9e37-267">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="f9e37-268">Créer une file d’attente d’appels cloud</span><span class="sxs-lookup"><span data-stu-id="f9e37-268">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="f9e37-269">Nouveau-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="f9e37-269">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="f9e37-270">Nouveau-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="f9e37-270">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="f9e37-271">Nouveau-CsOnlineApplicationInstanceAssociation</span><span class="sxs-lookup"><span data-stu-id="f9e37-271">New-CsOnlineApplicationInstanceAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstanceassociation?view=skype-ps)

[<span data-ttu-id="f9e37-272">Système téléphonique-licence utilisateur virtuel</span><span class="sxs-lookup"><span data-stu-id="f9e37-272">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
